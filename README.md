# Korpus_Bahasa_Sunda
Repositori ini berisi korpus ujaran spontan bahasa Sunda yang dikembangkan untuk mendukung perancangan dan pelatihan sistem Pengenal Ucapan Otomatis (*Automatic Speech Recognition* - ASR). Korpus ini dibentuk sebagai pemenuhan tugas besar fase 1 untuk mata kuliah IF4071 Pemrosesan Ucapan.

---

## Gambaran Umum Korpus

- **Bahasa / Dialek:** Bahasa Sunda
- **Tujuan Korpus:** Pengenal Ucapan Otomatis (*Automatic Speech Recognition*)
- **Gaya Ujaran:** Ujaran spontan (*Spontaneous speech*) berbasis stimulus pertanyaan terbuka
- **Penutur:** 10 orang (5 laki-laki, 5 perempuan)
- **Topik Pembicaraan:** Makanan (*Food*), perjalanan (*Travel*), dan Kegiatan sehari-hari (*Hobby*)

---

## Spesifikasi Teknis Audio

| Parameter | Nilai / Konfigurasi | Keterangan |
| :--- | :--- | :--- |
| **Format Berkas** | WAV (Linear PCM) | Format audio tanpa kompresi *lossy* |
| **Sampling Rate** | 16.000 Hz (16 kHz) | Standar pemrosesan model ASR |
| **Kedalaman Bit (*Bit Depth*)** | 16-bit | Resolusi kuantisasi standar sinyal akustik |
| **Channel Audio** | Mono (1 kanal) | Menjamin konsistensi satu jalur sinyal |
| **Tingkat Rekam (*Recording Level*)** | Rentang -12 dB hingga -6 dB | Mencegah distorsi pemotongan sinyal (*clipping*) |

---

## Struktur Direktori

```text
Korpus_Bahasa_Sunda
│
├── annotation/
│   └──  annotation.csv 
│
├── audio/
│   ├── S01/
│   │   ├── S01_T01_001.wav
│   │   └── ...
│   ├── S02/
│       └── ...
│   ├── ...
│   └── S10/
│       └── ...
│
├── consent/
│   ├── Consent_S02.pdf
│   ├── Consent_S04.pdf
│   ├── Consent_S06.pdf
│   ├── Consent_S08.pdf  
│   └── Consent_S10.pdf
│
├── documentation/
│   ├── Dokumentasi Hasil QC.pdf
│   └── Laporan Proses Pengumpulan.pdf
│
├── metadata/
│   └── metadata.csv
│
└── README.md

```

---

## Skema Data

### 1. `metadata.csv`

Menyimpan atribut rekaman pada tingkat sesi dan karakteristik penutur:

* `File`: Nama berkas audio (Sxx_Tyy_zzz.wav)
* `Speaker`: ID unik penutur (S01 – S10)
* `Gender`: Jenis kelamin penutur (M / F)
* `Topic`: Topik percakapan (_Food_, _Travel_, _Hobby_)
* `Duration`: Durasi rekaman audio dalam detik
* `Environment`: Kondisi lingkungan perekaman (_Indoor_)
* `Quality`: Label kendali mutu (_Good_, _Acceptable_, _Reject_)

### 2. `annotation.csv`

Menyimpan penjajaran transkripsi teks dengan stempel waktu (*timestamps*):

* `File`: Nama berkas audio rujukan
* `Speaker`: ID penutur
* `Start`: Titik waktu awal ujaran dalam detik
* `End`: Titik waktu akhir ujaran dalam detik
* `Topic`: Topik ujaran
* `Transcription`: Transkripsi teks verbatim ujaran
* `Special_Event`: Informasi kondisi / fenomena yang terjadi dalam segmen tersebut, atau tanda hubung (-) jika audio normal

---

## Kategorisasi Label Mutu (*Quality Label*)

Setiap berkas dievaluasi melalui uji dengar langsung untuk dikelompokkan ke dalam kategorisasi berikut:

* **Good:** Bebas distorsi suara, rasio SNR tinggi, dan artikulasi penutur terdengar jernih.
* **Acceptable:** Terdapat anomali akustik minor yang tidak menurunkan kualitas audio secara signifikan (misal: desis kipas halus atau hembusan napas tipis).
* **Reject:** Kerusakan sinyal fatal seperti *clipping* ekstrem, _noise_ lingkungan dominan, atau kata yang terpotong di tengah kalimat.

---


## Anggota Kelompok

| Nama | NIM |
| :--- | :--- |
| William Andrian Dharma T | 13523006 |
| Rafen Max Alessandro | 13523031 |
| Karol Yangqian Poetracahya | 13523093 |
| Steven Owen Liauw | 13523103 |
| Leonard Arif Sutiono | 18223120 |