# ADR-0001 — Fondasi teknis pedaree-design

Status: Diterima | Tanggal: 2026-10-14

## Konteks

Mobile dan web harus tampil konsisten, termasuk label status kedaluwarsa H-7 sampai H-1 dan 'Pakai hari ini'. Sumber kebenaran: Pedaree-TownHall `platform/versions/v1.0.0` (https://github.com/Coding-Skuy/Pedaree-TownHall/tree/main/platform/versions/v1.0.0), beku 2026-10-07; lintas divisi: [KONTEKS-LINTAS-DIVISI.md](https://github.com/Coding-Skuy/ChefGenie-TownHall/blob/main/KONTEKS-LINTAS-DIVISI.md). Tiket fondasi: PDR-DSG-001 (issue #1).

## Keputusan

1. Repo desain tidak berisi kode produk; hanya token, flow, spesifikasi komponen, dan tautan Figma.
2. Token framework-agnostik dengan pemetaan eksplisit ke Compose Multiplatform dan CSS (SvelteKit).
3. Warna status mengikuti SOP: AMAN hijau, WASPADA kuning, SEGERA oranye, HARI_INI merah, KEDALUWARSA abu-merah (`notifikasi/10` bab 2).
4. Flow dikunci: 5 alur catat stok (masuk, pakai, opname, pindah, buang) — maks 3 layar mobile, 2 langkah web.
5. Perubahan flow besar = PRD/FSD versi baru di TownHall.

## Konsekuensi

- Token saat ini hanya 3 status kedaluwarsa (aman/segera/lewat); harus diperluas menjadi 5 (PDR-DSG-002).
- Perubahan token memengaruhi `pedaree-app-kmp` dan `pedaree-web`.
- Link Figma menjadi artefak wajib di README.
