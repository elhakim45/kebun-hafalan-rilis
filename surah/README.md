# Katalog surah unduhan Kebun Hafalan

Folder ini disalin otomatis ke repo publik `kebun-hafalan-rilis/surah/` setiap ada perubahan di branch `main`.
Aplikasi membaca dari sana lewat menu **Unduh surah lain**.

## Isi folder

- `index.json`: daftar surah yang bisa diunduh.
- `001.json` … `077.json`: satu file per surah.

### Format `index.json`

```json
{
 "v": 1,
 "sumber": "Teks Arab: … Terjemahan: …",
 "items": [
  {"id": 1, "n": "Al-Fatihah", "ar": "الفاتحة", "ayat": 7, "juz": 1, "kb": 1, "file": "001.json", "v": 1, "maxKata": 9}
 ]
}
```

| Kolom | Arti |
|---|---|
| `id` | Nomor surah (1–114). Surah 78–114 sudah ada di aplikasi, jadi tidak perlu dimasukkan. |
| `n`, `ar` | Nama latin dan nama Arab. |
| `ayat`, `juz` | Jumlah ayat dan juz tempat surah dimulai (untuk pengelompokan di daftar). |
| `kb` | Ukuran file, ditampilkan di tombol unduh. |
| `file` | Nama file surah. |
| `v` | Versi isi file. Naikkan bila isi surah diperbaiki. |

### Format file surah (mis. `001.json`)

Sama dengan data bawaan aplikasi:

```json
[1, "Al-Fatihah", "الفاتحة", [
  ["بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ", "Dengan nama Allah Yang Maha Pengasih, Maha Penyayang."],
  ["…teks ayat 2…", "…arti ayat 2…"]
]]
```

- Satu pasangan `[teks Arab, arti]` per ayat, berurutan.
- Kata dalam teks Arab dipisah spasi; tanda waqaf yang berdiri sendiri diabaikan oleh game.
- Basmalah tidak ditulis di awal ayat 1 (kecuali Al-Fatihah).
- Arti boleh `""`, tetapi mode Tebak Arti hanya muncul bila semua arti terisi.

## Sumber data

- Teks Arab: Tanzil Quran Text, edisi Simple (tanzil.net), CC BY 3.0, sama dengan teks Juz 30 di aplikasi.
- Terjemahan: Kementerian Agama RI, melalui QuranEnc.com.

## Mengubah atau menambah surah

1. Ubah atau tambahkan file surah dengan format di atas.
2. Perbarui baris yang sesuai di `index.json` (naikkan `v` bila isinya berubah).
3. Merge ke `main`. Katalog di repo publik ikut diperbarui; aplikasi tidak perlu dirilis ulang.
