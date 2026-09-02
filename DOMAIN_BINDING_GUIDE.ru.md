# Статус и руководство по привязке домена `evaline.website`

## Статус: ЗАВЕРШЕНО И АКТИВНО
- **Домен:** `evaline.website` / `www.evaline.website`
- **DNS Регистратор:** Spaceship (A-записи направлены на `136.114.26.252`)
- **Сервер GCP:** `evaline-micro-vm` (`e2-micro`, `us-central1-a`)
- **Статический IP:** `136.114.26.252` (Зарезервирован в GCP `us-central1`, $0/мес в рамках Free Tier)
- **Веб-сервер:** Caddy
- **SSL-сертификат:** Активен (Автоматический HTTPS через Let's Encrypt / ZeroSSL)
- **Каталог сайта:** `/var/www/evaline.website`

---

## Сводка конфигурации

### 1. За резервирование статического IP (Выполнено)
IP `136.114.26.252` зарезервирован как статический IP-адрес `evaline-micro-ip` в регионе `us-central1`.

### 2. Конфигурация веб-сервера (`/etc/caddy/Caddyfile`)
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

### 3. Файлы сайта
Файлы вашего сайта можно размещать в директории `/var/www/evaline.website/` на сервере `evaline-micro-vm`.
