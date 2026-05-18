# Praktikum Linux Sesi 5  
## Data Processing dengan Shell Tools

**Mata Kuliah:** Sistem Operasi (MITI.202 / MISI.202)  
**Nama:** Hanif Muslim  
**Kelas:** SIF/TIK 25  
**Topik:** Praktikum command-line untuk data processing dan migrasi data

---

# Deskripsi Praktikum

Pada praktikum ini dilakukan proses pengolahan data menggunakan shell tools Linux seperti `grep`, `awk`, `sed`, `sort`, `uniq`, `wc`, `tail`, dan command Linux lainnya.

Seluruh proses dikerjakan di Linux box Ubuntu menggunakan terminal dan command-line sesuai instruksi worksheet praktikum.

Praktikum juga melatih proses transfer file menggunakan SSH, SCP, dan penggunaan shell tools untuk melakukan filtering, pencarian, manipulasi, serta analisis data.

---

# Persiapan dan Setup

## Install OpenSSH Server

```bash
sudo apt install openssh-server
sudo systemctl enable --now ssh
Cek IP Linux
hostname -I
Test SSH
ssh user@ip-linux
Transfer File menggunakan SCP

Transfer file dilakukan dari Windows host ke Linux box menggunakan command:

scp data.csv chiel@192.168.xxx.xxx:/home/chiel/praktikum-linux-sesi5/exercise-1-csv/

Transfer berhasil dilakukan setelah konfigurasi VirtualBox diubah menjadi Bridged Adapter.

Struktur Folder Repository
praktikum-linux-sesi5/
├── README.md
├── exercise-1-csv/
│   ├── prompt.txt
│   ├── data.csv
│   ├── solution.sh
│   └── output/
Exercise 1 — CSV Customer Data
Generate Data

Data customer dibuat menggunakan AI webchat dengan format CSV.

Kolom yang digunakan:

id
nama
email
no_hp
tanggal_daftar
status

Data memiliki:

format tanggal campuran
email duplikat
typo capitalization
status dengan variasi huruf besar kecil
Command yang Digunakan
Menampilkan isi file
cat data.csv
Menghitung jumlah baris
wc -l data.csv
Mencari customer Gmail
grep gmail data.csv
Menampilkan baris terakhir
tail -3 data.csv
Copy file
cp data.csv backup.csv
Rename file
mv backup.csv cadangan.csv
Compress file
zip -r latihan.zip .
Hasil Processing
1. Menghitung jumlah customer per status

Dilakukan menggunakan command awk, sort, dan uniq untuk normalisasi lowercase dan menghitung jumlah status customer.

2. Konversi tanggal ke ISO 8601

Dilakukan menggunakan sed untuk mengubah format tanggal menjadi yyyy-mm-dd.

3. Ekstrak customer Gmail

Dilakukan menggunakan:

grep gmail data.csv

Hasil disimpan ke folder output.

4. Hapus data duplikat berdasarkan email

Dilakukan menggunakan command awk dengan filtering kolom email.

5. Identifikasi nama yang tidak title-case

Dilakukan menggunakan filtering capitalization pada nama customer.

Kendala yang Dihadapi
1. Konfigurasi Network VirtualBox

Awalnya SCP gagal karena Ubuntu masih menggunakan NAT. Masalah diselesaikan dengan mengubah adapter menjadi Bridged Adapter.

2. SSH dan SCP

Beberapa kali koneksi gagal karena:

password salah
IP berubah
service SSH belum aktif
3. Penggunaan Vim

Awalnya mengalami kesulitan saat menggunakan Vim, terutama:

masuk insert mode
save file
keluar dari editor

Command yang dipelajari:

i
:wq
:q!
Refleksi
1. Kesulitan terbesar

Kesulitan terbesar adalah konfigurasi SSH dan penggunaan SCP karena sebelumnya belum pernah melakukan transfer file antar sistem menggunakan terminal Linux.

2. Command baru yang dipelajari

Beberapa command baru yang dipelajari:

scp
grep
awk
sed
zip
vim
3. Skenario penggunaan di dunia kerja

Skill ini dapat digunakan pada:

system administrator
DevOps engineer
backend developer
data processing server
monitoring log server
4. Total waktu pengerjaan

Estimasi waktu pengerjaan:

Setup Ubuntu dan SSH: ±2 jam
Transfer file dan SCP: ±1 jam
Processing CSV dan command Linux: ±2 jam
Dokumentasi dan GitHub: ±1 jam

Total: ±6 jam

Kesimpulan

Praktikum ini membantu memahami penggunaan Linux terminal untuk data processing dan transfer file menggunakan shell tools.

Selain itu, praktikum ini juga memberikan pengalaman penggunaan SSH, SCP, Vim, dan command Linux yang umum digunakan pada lingkungan server Linux dan dunia kerja IT.
