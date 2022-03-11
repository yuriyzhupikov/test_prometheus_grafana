# Prometheus
___
### Для работы Prometheus понадобится:
``Prometheus``
``Node_exporter``
``Alertmanager``
``Client_golang``
___
### Prometheus - сервер запрашиваюший метрики различных сервисов 
#### Установка
1. ``git clone repo``
2. Находим билд под свою платформу (например linux-amd64) `` https://github.com/prometheus/prometheus/releases``
3. Исполняемы файлы перемещаем в ``/var/local/bin``
- ``cd prometheus-*``
- ``cp prometheus promtool /usr/local/bin``
- ``mkdir /etc/prometheus /var/lib/prometheus``
- ``cp prometheus.yml /etc/prometheus``
- Дополнительно можно создать пользователя и группу:
- ``useradd --no-create-home --home-dir / --shell /bin/false prometheus``
- ``chown -R prometheus:prometheus /var/lib/prometheus``
4. Создаём символью ссылку на ``promethus.service``:
- ``sudo ln ./prometheus.service /etc/systemd/system/prometheus.service``
5. Запускаем Prometheus server
- ``systemctl daemon-reload``
- ``systemctl start prometheus``
6. Перейти по адресу http://localhost:9090 (по умолчанию)
___
###Node_exporter
Позволяет измерять различные ресурсы машины, такие как использование памяти, диска и процессора
#### Установка

