> Versi: v1.0.0 | Status: disetujui | Menggantikan: -

# ARSITEKTUR-AI-DEV — Stack terkunci dan batas context (pedaree-design)

Mengacu: Pedaree-TownHall `platform/versions/v1.0.0` (https://github.com/Coding-Skuy/Pedaree-TownHall/tree/main/platform/versions/v1.0.0), beku 2026-10-07. Dokumen ini MELENGKAPI `versions/v1.0.0/docs/40-TECHSTACK.md` dan `versions/v1.0.0/docs/60-BLAST-RADIUS.md` (keduanya beku v1.0.0 dan tidak diedit; isinya hanya ringkasan satu paragraf). Tidak menduplikasi BRD/PRD/FRD/FSD/SRS.

Baris Pedaree townhall-roadmap §2: point of concern "FEFO; stockout <8%; waste <1.500 g/Rp50.000/bln"; batas context "13 satuan baku; konsumen modul `pantry-resep` milik Pawonee". Rujukan lintas divisi: KONTEKS §3.1, §6, §8, §9.

## 1. Matriks stack

| Komponen | Kondisi saat ini (tercatat dari manifes/README) | Target terkunci v1.0.0 |
|---|---|---|
| Token | `tokens/warna.json` (3 status stok, 3 status kedaluwarsa, jarak) | token lengkap: 5 status kedaluwarsa + 3 status stok + jarak + tipografi |
| Build token | Style Dictionary 4.3.0 (`package.json`) | Style Dictionary (keluaran Compose + CSS) |
| Komponen | `components/inventori.md` | spesifikasi `.md` sebagai sumber; implementasi di repo klien |
| Desain visual | belum terdaftar | Figma (link terdaftar di README) |



## 3. Boleh disentuh repo ini

- `tokens/`, `components/*.md`, flow, aset desain, README (link Figma).
- Spesifikasi kartu ringkas, dasbor, dan alur catat stok.

## 4. Dilarang

- Menambah kode aplikasi/server.
- Mengubah flow besar tanpa PRD/FSD versi baru di TownHall.
- Mendefinisikan ulang ambang/label kedaluwarsa di luar `notifikasi/10`.
- Menyentuh DB divisi lain (DB per service; Titeny hanya read-only ke DB sumber).
- Membuat pesanan TitipO otomatis dari sinyal stok (hanya anjuran, relevansi 48 jam).
- Mengubah modul `:shared:pantry-resep` (milik Pawonee), daftar 13 satuan, ambang kedaluwarsa, atau audiens JWT tanpa PR TownHall + ADR.

## 5. Kontrak yang diproduksi

- Token dan pemetaan Compose/CSS.
- Spesifikasi komponen, flow 5 alur, link Figma.

## 6. Kontrak yang dikonsumsi

- Ambang dan label status dari `notifikasi/10-sop-kedaluwarsa.md`.
- Daftar layar/tampilan dari `produk/10`, `metrik/10`.

## 7. Dampak bila berubah

- Perubahan token/komponen memengaruhi `pedaree-app-kmp` dan `pedaree-web`.

## Batasan

- Dokumen ini hanya mencatat stack dan batas; tidak mengubah manifes atau kode. Kondisi saat ini dicatat apa adanya.
- Versi dikunci eksak di manifes saat kickoff coding; perubahan dicatat lewat ADR baru.
- JWT audiens `pedaree`, DB logis `pedaree`, dan kepemilikan Pawonee atas `:shared:pantry-resep` tidak berubah oleh dokumen ini.
