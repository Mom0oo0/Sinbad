# Pelican deployment

Import `egg-shawarma-sinbad.json` in the Pelican panel, then create a server with the `ghcr.io/mom0oo0/shawarmasinbad:main` image. The image needs to be rebuilt from this repository after adding the Pelican launcher; the existing GitHub Actions workflow publishes it when changes reach `main`.

Set the Rails master key and admin password in the server variables. To enable the integrated Cloudflare Tunnel, create a remotely-managed tunnel in Cloudflare and set its token as `CLOUDFLARED_TOKEN`. Configure the tunnel's public hostname service to `http://localhost:<allocated server port>` inside the server container. Leave the token empty to run the Rails app without a tunnel.

Mount a persistent Pelican volume at `/rails/storage` before starting the server. Rails stores its production SQLite databases and uploaded files there; without that mount, those files may be lost when the server is recreated. Allocate the server port in Pelican as usual; Rails binds to `0.0.0.0` on that port.