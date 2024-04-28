### Media server

#### Services

- [Jellyfin](https://github.com/jellyfin/jellyfin) media server to share, manage and stream digital media.
- [Radarr](https://github.com/Radarr/Radarr) movie organizer/manager for usenet and torrent users.
- [Sonarr](https://github.com/Sonarr/Sonarr) smart PVR for newsgroup and bittorrent users.
- [Bazarr](https://www.bazarr.media/) manages and downloads subtitles for sonarr and radarr.
- [Prowlarr](https://github.com/Prowlarr/Prowlarr) torrent indexer manager.
- [Flaresolverr](https://github.com/FlareSolverr/FlareSolverr) proxy server to bypass Cloudflare protection to indexers.
- [qBittorrent](https://github.com/qbittorrent/qBittorrent) bittorrent client.

#### Folder structure
```
media-server/
    media-docker-compose.yml
    appdata/
        jellyfin/config/
        radarr/config/
        sonarr/config/
        prowlarr/config/
        qbittorrent/config/
        flaresolverr/config/

```
```
.mediastorage/
    downloads/
    movies/
    shows/
```

- qBittorrent downloads the files in `.mediastorage/downloads` directory, after the download finish, radarr (and sonarr) moves the file to the correct directory.
- Jellyfin monitore `.mediastora/movies` and `.mediastora/shows` to check the new media available.
- Bazarr points to `.mediastora/movies` and `.mediastora/shows` to check subtitles to new media.
