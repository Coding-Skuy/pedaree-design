# Arsitektur pedaree-design

TownHall: https://github.com/Coding-Skuy/Pedaree-TownHall

## Lapisan

1. Token: warna, tipografi, jarak, radius di `tokens/`.
2. Komponen: lencana stok, bilah kedaluwarsa, kartu resep (dipakai ulang).
3. Layar: stok, mutasi, resep hemat di `screens/`.

## Makna status

- Stok: `tersedia` (hijau), `menipis` (kuning), `habis` (merah).
- Kedaluwarsa: `aman` (lebih dari 7 hari), `segera` (1 sampai 7 hari),
  `lewat` (melewati tanggal).

## Keputusan

- Token tunggal dibangun ke Android (Compose), iOS (SwiftUI), dan web (CSS).
- Kartu resep mengikuti gaya Pawonee; Pedaree hanya menambah lapisan status.
