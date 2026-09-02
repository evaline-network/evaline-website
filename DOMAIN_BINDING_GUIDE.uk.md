# Статус та посібник з прив'язки домену `evaline.website`

## Статус: ЗАВЕРШЕНО ТА АКТИВНО
- **Домен:** `evaline.website` / `www.evaline.website`
- **DNS Реєстратор:** Spaceship (A-записи спрямовані на `136.114.26.252`)
- **Сервер GCP:** `evaline-micro-vm` (`e2-micro`, `us-central1-a`)
- **Статична IP:** `136.114.26.252` (Зарезервовано в GCP `us-central1`, $0/міс у межах Free Tier)
- **Вебсервер:** Caddy
- **SSL-сертифікат:** Активний (Автоматичний HTTPS через Let's Encrypt / ZeroSSL)
- **Каталог сайту:** `/var/www/evaline.website`

---

## Зведення конфігурації

### 1. Резервування статичної IP (Виконано)
IP `136.114.26.252` зарезервовано як статичну IP-адресу `evaline-micro-ip` в регіоні `us-central1`.

### 2. Конфігурація вебсервера (`/etc/caddy/Caddyfile`)
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

### 3. Файли сайту
Файли вашого сайту можна розміщувати в директорії `/var/www/evaline.website/` на сервері `evaline-micro-vm`.
