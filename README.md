# Praktikum Pemrograman Web (INF11197) — Modul 7

Aplikasi CRUD Data Mahasiswa berbasis Laravel, PDO Prepared Statement, MariaDB/MySQL, dan Blade Tanpa CSS.

- **NIM**: 2401020166

## Fitur Utama (Modul 7)
- **Read, Pencarian & Filter**: Menampilkan data mahasiswa (`JOIN program_studi`), pencarian kata kunci (`LIKE` pada `nim`, `nama`, dan `email`), serta filter berdasarkan `program_studi_id`.
- **Create**: Penambahan data mahasiswa baru dengan validasi sisi server dan pencegahan duplikat NIM/email.
- **Update**: Halaman form ubah mahasiswa (`mahasiswa-edit.blade.php`) dan pembaruan data (`PUT /mahasiswa/{id}`) dengan pengecekan duplikat `id <> :id`.
- **Delete**: Penghapusan data mahasiswa (`DELETE /mahasiswa/{id}`) dengan konfirmasi browser (`onclick="return confirm('Hapus data ini?')"`).

## Struktur Data (`praktikum_web_2401020166`)
- `program_studi` (master): `id`, `nama_prodi`
- `mahasiswa`: `id`, `nim`, `nama`, `email`, `usia`, `program_studi_id`, `created_at`, `updated_at`

## Route
| Method | URI | Nama Route | Fungsi |
|---|---|---|---|
| GET | `/mahasiswa` | `mahasiswa.index` | Indeks, pencarian (`q`), filter (`program_studi_id`) |
| POST | `/mahasiswa` | `mahasiswa.store` | Create data mahasiswa |
| GET | `/mahasiswa/{id}/edit` | `mahasiswa.edit` | Halaman form ubah mahasiswa (`mahasiswa-edit.blade.php`) |
| PUT | `/mahasiswa/{id}` | `mahasiswa.update` | Update data mahasiswa (`id <> :id`) |
| DELETE | `/mahasiswa/{id}` | `mahasiswa.destroy` | Delete data mahasiswa |
