Monitoring stack (Prometheus + exporters)

Cara menjalankan:

1. Masuk ke folder monitoring:

   cd monitoring

2. Jalankan docker compose:

   docker compose up -d

3. Buka Prometheus di: http://<host>:9090
   Buka Grafana di: http://<host>:3000 (user: admin / password: admin123)

Verifikasi health:

- Cek container:

  docker compose ps

- Cek logs Prometheus:

  docker logs prometheus --tail=50

File konfigurasi:

- `prometheus/prometheus.yml` - konfigurasi scrape targets
- `prometheus/alert.rules.yml` - contoh alert rules

Notes:
- Pastikan port yang dipetakan tidak bentrok dengan service lain di host.
- Sesuaikan `snmp.yml` bila menggunakan SNMP exporter.
