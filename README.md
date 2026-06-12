# Etap 7 — Portföy Projesi: Uçtan Uca Pipeline 🏆

> Yol haritamın final/capstone projesi. Önceki tüm etapları birleştiren, Docker üzerinde çalışan, zamanlanmış tam bir veri pipeline'ı. **Portföyümün vitrin projesi.**

Bir futbol verisi API'sinden otomatik veri çekip, warehouse'a yükleyip, dbt ile dönüştürüp, bir dashboard'da gösteren uçtan uca akış.

## Mimari
```
football-data.org API
        │ (requests)
        ▼
   Orkestrasyon (Airflow/Kestra) ──── her gece zamanlı
        │
        ▼
   Warehouse (PostgreSQL / BigQuery)   ← Load
        │
        ▼
   dbt (staging → mart: puan durumu, form)  ← Transform
        │
        ▼
   Looker Studio dashboard               ← Serve

   [ Her şey Docker compose üstünde ]
```

## Kullanılan teknolojiler
- **Extract:** [football-data.org](https://www.football-data.org) API + `requests`
- **Orchestrate:** Airflow / Kestra (Zoomcamp'ten)
- **Load:** PostgreSQL veya BigQuery
- **Transform:** dbt (staging → mart katmanları)
- **Serve:** [Looker Studio](https://lookerstudio.google.com)
- **Paketleme:** Docker compose

## Çalıştırma
```bash
# TODO: API key'i .env'e koy
docker compose up
```

## Dashboard
<!-- TODO: Looker Studio linki + ekran görüntüsü -->

## Notlar
<!-- TODO: her aracın neden seçildiği, mimari kararlar -->

## ✅ Final testi
> Projeyi hiç bilmeyen birine 10 dakikada mimariyi anlatabiliyor ve "şu veri neden bu tabloda?" sorularına cevap verebiliyorsam, DE temelim oturmuş demektir.
