# Kantor Pixel 3D — Versi Website

Dasbor command center **Kantor Pixel 3D** yang bisa dibuka langsung dari browser
(HP/laptop) lewat GitHub Pages:
**https://sangraipoi-maker.github.io/kantor-pixel-3d-web/**

Ini jalur akses tambahan untuk dasbor yang sama dengan artefak Muse
`kantor-pixel-3d` (yang tidak diubah sama sekali):

- **Tampilan** — bundle klien yang sama persis dengan artefak
  (`assets/index-*.js` + `assets/index-*.css`), dirender dari `index.html`.
  Satu-satunya tambahan: skrip jembatan kecil di `index.html` yang menjawab
  permintaan data dasbor dari berkas `data.json`.
- **Data** — `data.json` berisi snapshot dasbor: umpan aktivitas tim Kantor
  Pixel + metrik agregat VM + cap waktu snapshot. Tidak ada kredensial, isi
  berkas, atau path internal di dalamnya.
- **Pembaruan** — cron `sinkron-kantor-pixel-3d` (tiap ±15 menit) menulis
  snapshot yang sama ke artefak DAN memperbarui `data.json` di repo ini lalu
  push, jadi kedua tampilan selalu seirama. Halaman me-*poll* `data.json`
  berkala dan selalu menampilkan label "Snapshot per <jam> WIB" apa adanya.

Prosedur sinkron lengkap: `~/workspace/kantor-pixel-3d-sync/CATATAN-SINKRON.md`
(di mesin Kav).
