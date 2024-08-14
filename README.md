# Прозрачный прокси

Ставит прозрачный прокси в зависимости от выбора

`iptables` заворачивает весь входящий траффик на порт redsocs. `redsocs` перенаправляет на прокси сервер

## Тип прокси

- `ciadpi`
- `squid`

```yaml
proxy_type: "squid"
```

## Конфигурация интерфейса локальной сети

```yaml
proxy_interface: "enp0s8"
proxy_address: "192.168.33.1"
proxy_netwrok: "192.168.33.0/24"
```

## Включить DHCP сервер

```yaml
dnsmasq_dhcp: false
```

## Порт redsocs

```yaml
redsocks_port: 12345
```

## Порт squid

```yaml
squid_port: 3128
```

## Порт ciadpi

```yaml
ciadpi_port: 1080
```

## Плэйбук

```yaml
- name: Install proxy
  hosts:
    - all
  become: true
  roles:
    - role: imbicile.proxy
      tags: proxy
```
