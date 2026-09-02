# Domain Binding Guide & Status for `evaline.website`

## Status: COMPLETE & ACTIVE
- **Domain:** `evaline.website` / `www.evaline.website`
- **DNS Registrar:** Spaceship (A Records point to `136.114.26.252`)
- **GCP Server:** `evaline-micro-vm` (`e2-micro`, `us-central1-a`)
- **Static External IP:** `136.114.26.252` (Reserved in GCP `us-central1`, $0/month in Free Tier)
- **Web Server:** Caddy
- **SSL Certificate:** Active (Automatic TLS issued via Let's Encrypt / ZeroSSL)
- **Web Directory:** `/var/www/evaline.website`

---

## Configuration Summary

### 1. Static IP Reservation (Completed)
IP `136.114.26.252` has been reserved as a static IP address named `evaline-micro-ip` in region `us-central1`.

### 2. Web Server Configuration (`/etc/caddy/Caddyfile`)
```caddy
evabot.online, www.evabot.online {
    root * /var/www/evabot.online
    file_server
}

evaline.website, www.evaline.website {
    root * /var/www/evaline.website
    file_server
}
```

### 3. Website Files
Website files can be uploaded to `/var/www/evaline.website/` on `evaline-micro-vm`.
