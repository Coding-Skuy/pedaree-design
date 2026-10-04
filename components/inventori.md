# Komponen inventori Pedaree

## LencanaStok

Properti: `status` (tersedia, menipis, habis), `label` teks jumlah.
Contoh: `<LencanaStok status="menipis" label="200 ml" />`.
Warna mengikuti `tokens/warna.json`.

## BilahKedaluwarsa

Properti: `status` (aman, segera, lewat), `sisaHari` angka.
Contoh: `<BilahKedaluwarsa status="segera" sisaHari="2" />`.

## KartuResep (dipakai ulang dari Pawonee)

Dipakai apa adanya; Pedaree menempelkan `LencanaStok` di sudut kartu.
Perubahan gaya kartu dikoordinasikan dengan Pawonee.
