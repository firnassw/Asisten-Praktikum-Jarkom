<div align="center">

  <img src="frontend/public/logo.png" alt="Asisten Praktikum Jaringan Komputer Logo" width="500"/>

  <p align="center">
    <strong>Platform Interaktif dan Deterministik untuk Perhitungan Jaringan Komputer, Alokasi Subnetting, dan Otomasi Konfigurasi Cisco Packet Tracer.</strong>
  </p>

  <p align="center">
    Presisi Matematis Murni (Bitwise Integer) • Sesuai Standar Modul Laboratorium • Siap Salin ke Cisco IOS dan Lembar Responsi
  </p>

  <p align="center">
    <a href="#fitur-utama"><img src="https://img.shields.io/badge/Fitur-Lengkap-FCE76C?style=for-the-badge&logoColor=1F1E22&labelColor=1F1E22" alt="Fitur"/></a>
    <a href="#tangkapan-layar-antarmuka"><img src="https://img.shields.io/badge/UI-Neo--Brutalism-8BD0FC?style=for-the-badge&logoColor=1F1E22&labelColor=1F1E22" alt="Tampilan"/></a>
    <a href="#arsitektur-dan-alur-sistem"><img src="https://img.shields.io/badge/Arsitektur-FastAPI_%2B_React_19-3776AB?style=for-the-badge&logoColor=white&labelColor=1F1E22" alt="Arsitektur"/></a>
    <a href="#panduan-instalasi-dan-menjalankan"><img src="https://img.shields.io/badge/Mulai-Cepat-16794C?style=for-the-badge&logoColor=white&labelColor=1F1E22" alt="Panduan"/></a>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python 3.12"/>
    <img src="https://img.shields.io/badge/FastAPI-0.110+-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI"/>
    <img src="https://img.shields.io/badge/React-19.2-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React 19"/>
    <img src="https://img.shields.io/badge/TypeScript-5.0+-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
    <img src="https://img.shields.io/badge/TailwindCSS-v4-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white" alt="Tailwind CSS v4"/>
    <img src="https://img.shields.io/badge/Vite-8.3-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite"/>
    <img src="https://img.shields.io/badge/Tests-116%20Passed-16794C?style=flat-square&logo=checkmarx&logoColor=white" alt="116 Passing Tests"/>
    <img src="https://img.shields.io/badge/License-MIT-FCE76C?style=flat-square&colorA=1F1E22&colorB=FCE76C" alt="MIT License"/>
  </p>

</div>

---

## Daftar Isi

1. [Tentang Proyek](#tentang-proyek)
2. [Masalah dan Solusi](#masalah-dan-solusi)
3. [Prinsip Desain Sistem](#prinsip-desain-sistem)
4. [Tangkapan Layar Antarmuka](#tangkapan-layar-antarmuka)
5. [Fitur Utama](#fitur-utama)
6. [Arsitektur dan Alur Sistem](#arsitektur-dan-alur-sistem)
7. [Teknologi yang Digunakan](#teknologi-yang-digunakan)
8. [Panduan Instalasi dan Menjalankan](#panduan-instalasi-dan-menjalankan)
   * [Opsi A: Menjalankan Secara Lokal (Manual)](#opsi-a-menjalankan-secara-lokal-manual)
   * [Opsi B: Menjalankan dengan Docker](#opsi-b-menjalankan-dengan-docker)
9. [Dokumentasi REST API](#dokumentasi-rest-api)
10. [Pengujian dan Verifikasi Kualitas](#pengujian-dan-verifikasi-kualitas)
11. [Sistem Desain: Neo-Brutalism](#sistem-desain-neo-brutalism)
12. [Struktur Direktori Repositori](#struktur-direktori-repositori)
13. [Kontribusi dan Lisensi](#kontribusi-dan-lisensi)

---

<a id="tentang-proyek"></a>
## Tentang Proyek

**Asisten Praktikum Jaringan (APJ)** adalah platform web yang dibangun untuk memfasilitasi kebutuhan praktikum Jaringan Komputer, khususnya pada lingkungan simulasi **Cisco Packet Tracer**. Sistem menangani kalkulasi subnetting IPv4, alokasi hierarkis FLSM dan VLSM, perancangan skema pengalamatan jaringan gedung, hingga pembuatan skrip konfigurasi router secara otomatis.

Berbeda dengan kalkulator IP umum yang sekadar memberikan tabel biner akhir tanpa konteks penjabaran, APJ memproses dan menyusun setiap jawaban **tahap demi tahap seperti lembar jawaban ujian responsi laboratorium**, mengacu pada kurikulum praktikum:
* **Modul 2**: Konfigurasi Dasar Jaringan dan Subnetting CIDR
* **Modul 3**: Jaringan Nirkabel, Access Point, dan Konfigurasi DHCP Server Router
* **Modul 4**: Server Web, Domain Name System (DNS), dan Pengalamatan IP Perangkat

---

<a id="masalah-dan-solusi"></a>
## Masalah dan Solusi

| Masalah Umum di Laboratorium | Solusi Asisten Praktikum Jaringan |
|---|---|
| **Kesalahan Manusia pada Kalkulasi Bit**<br>Kesalahan 1 bit pada invers mask atau network address mengakibatkan seluruh node pada Packet Tracer tidak dapat saling terhubung (*Request Timed Out*). | **Mesin Bitwise Deterministik 100%**<br>Perhitungan subnetting dieksekusi secara deterministik menggunakan operasi bitwise integer murni tanpa kompromi pembulatan floating point. |
| **Penyusunan Lembar Jawaban Responsi**<br>Kalkulator daring lazimnya tidak memuat rincian parameter "Diketahui", "Ditanya", dan "Langkah Perhitungan". | **Struktur Jawaban Standar Laboratorium**<br>Menyajikan penjabaran rumus baku (2<sup>x</sup>, 2<sup>y</sup>-2, invers mask, tabel bobot bit) yang siap disalin ke lembar ujian. |
| **Kerumitan Alokasi FLSM dan VLSM**<br>Kesulitan memprioritaskan alokasi host, risiko bentrok antarblok alamat, serta alokasi yang melebihi kapasitas jaringan induk. | **Visualisasi Blok dan Deteksi Batas Induk**<br>Pengurutan kebutuhan host otomatis, visual bar alokasi memori subnet, dan deteksi dini ketika ruang alamat tidak mencukupi. |
| **Pengetikan Skrip CLI Cisco IOS Manual**<br>Konfigurasi DHCP Router pada Packet Tracer rentan galat pengetikan sintaks pada `ip dhcp pool` dan `ip dhcp excluded-address`. | **Generator Skrip Cisco IOS Otomatis**<br>Menghasilkan 10 baris perintah CLI Cisco IOS terstandar yang siap disalin dan ditempel langsung ke terminal router. |
| **Rekapitulasi Laporan Praktikum Lambat**<br>Memindahkan tabel pengalamatan puluhan perangkat satu per satu ke lembar laporan memakan banyak waktu. | **Fitur Salin TSV dan Mode Cetak Bersih**<br>Penyalinan data format Tab-Separated Values (TSV) langsung ke spreadsheet dan Word, serta layout cetak ramah kertas. |

---

<a id="prinsip-desain-sistem"></a>
## Prinsip Desain Sistem

```
+------------------------------------------------------------------------+
|                          7 PRINSIP DESAIN APJ                          |
+-------------------+-------------------+--------------------------------+
| 1. Non-AI Engine  | 2. Pure Bitwise   | 3. Verifikasi Data Uji Emas    |
|    (Deterministik)|    (Hanya Integer)|    (G-JAR-01 s.d. G-JAR-12)    |
+-------------------+-------------------+--------------------------------+
| 4. Transparan     | 5. Format Seragam | 6. Arsitektur Modular          |
|    (Bebas Fiktif) |    (Unified UI)   |    (Feature Registry Core)     |
+-------------------+-------------------+--------------------------------+
| 7. Desain Neo-Brutalism Responsif untuk Ponsel dan Desktop             |
+------------------------------------------------------------------------+
```

1. **Deterministik Murni**: Menghindari penggunaan LLM pada logika matematika bit. Output konsisten, terukur, berkecepatan tinggi (<10ms), dan bebas halusinasi.
2. **Hanya Operasi Integer**: Dihitung menggunakan operator bitwise (`&`, `|`, `~`, `<<`, `>>`) dan `.bit_length()`, tanpa fungsi pembulatan atau aproksimasi desimal.
3. **Terverifikasi terhadap Data Uji Emas**: Memiliki cakupan uji 100% terhadap seluruh skenario kunci jawaban modul (`G-JAR-01` sampai `G-JAR-12`).
4. **Transparan dan Jujur**: Menghindari keluaran fiktif. Jika parameter input melanggar batasan (misalnya subnet melebihi kapasitas atau prefix /31-/32), sistem menyajikan peringatan spesifik.
5. **Format Jawaban Seragam**: Seluruh modul menyajikan struktur keluaran terpadu: Parameter Diketahui, Kartu Langkah Pengerjaan, Tabel Hasil Akhir, dan Blok Kesimpulan.
6. **Arsitektur Modular**: Modul-modul kalkulasi terdaftar secara independen melalui mekanisme Feature Registry (`FR-18`).
7. **Antarmuka Neo-Brutalism Fungsional**: Menggunakan kontras tinggi, garis pembatas tegas 2px, bayangan solid 3px, serta tipografi terbaca jelas (*Montserrat* dan *JetBrains Mono*) pada layar ponsel (360px) hingga monitor desktop.

---

<a id="tangkapan-layar-antarmuka"></a>
## Tangkapan Layar Antarmuka

<div align="center">
  <table>
    <tr>
      <td width="50%" align="center">
        <strong>Dasbor Utama (Beranda)</strong><br/><br/>
        <img src="docs/design/beranda.png" alt="Dasbor Utama Asisten Praktikum Jaringan" width="100%"/>
        <p><em>Pilihan modul praktikum dengan navigasi instan dan kartu contoh soal terintegrasi.</em></p>
      </td>
      <td width="50%" align="center">
        <strong>Analisis Subnetting CIDR</strong><br/><br/>
        <img src="docs/design/subnetting.png" alt="Analisis Subnetting CIDR" width="100%"/>
        <p><em>Kalkulasi Network Address, Broadcast Address, rentang host valid, dan tabel blok subnet.</em></p>
      </td>
    </tr>
    <tr>
      <td width="50%" align="center">
        <strong>Pembagian FLSM dan VLSM</strong><br/><br/>
        <img src="docs/design/flsm-vlsm.png" alt="FLSM dan VLSM" width="100%"/>
        <p><em>Alokasi subnet dinamis dan seragam dengan visualisasi bar pembagian ruang alamat.</em></p>
      </td>
      <td width="50%" align="center">
        <strong>Perencanaan Subnetting Ruangan</strong><br/><br/>
        <img src="docs/design/rencana.png" alt="Perencanaan Ruangan dan NIM" width="100%"/>
        <p><em>Perhitungan subnet dari dua digit NIM, persentase cadangan host, dan usulan gateway.</em></p>
      </td>
    </tr>
    <tr>
      <td width="50%" align="center">
        <strong>Generator Skrip DHCP Cisco IOS</strong><br/><br/>
        <img src="docs/design/dhcp.png" alt="Generator DHCP Router Cisco" width="100%"/>
        <p><em>Skrip 10 baris CLI Cisco IOS siap pakai beserta estimasi IP pertama klien.</em></p>
      </td>
      <td width="50%" align="center">
        <strong>Tampilan Mobile Responsif</strong><br/><br/>
        <img src="docs/design/landing.png" alt="Tampilan Responsif Asisten Praktikum Jaringan" width="100%"/>
        <p><em>Antarmuka responsif yang dapat diakses dengan nyaman melalui perangkat bergerak di ruang laboratorium.</em></p>
      </td>
    </tr>
  </table>
</div>

---

<a id="fitur-utama"></a>
## Fitur Utama

### 1. Analisis Subnetting CIDR (`/subnetting`)
* **Input**: Alamat IPv4 tunggal dan prefix CIDR (contoh: `192.168.10.45/26`).
* **Keluaran**:
  * Kelas IP default dan subnet mask desimal bertitik (`255.255.255.192`).
  * Bitwise Network Address (`AND`) dan Broadcast Address (`OR` Invers Mask).
  * Invers Mask (Wildcard Mask) desimal bertitik.
  * Jumlah subnet ($2^x$) dan kapasitas host valid per subnet ($2^y - 2$).
  * Tabel seluruh blok subnet dan penanda blok spesifik dari IP yang dianalisis.

### 2. Alokasi FLSM dan VLSM (`/flsm-vlsm`)
* **FLSM (Fixed-Length Subnet Mask)**: Membagi jaringan induk menjadi subnet-subnet berukuran identik berdasarkan kebutuhan host tertinggi. Dilengkapi deteksi kapasitas induk.
* **VLSM (Variable-Length Subnet Mask)**: Mengurutkan kebutuhan host secara otomatis dari yang terbesar, mengalokasikan subnet secara hierarkis, serta menyajikan visual bar alokasi memori.

### 3. Perencanaan Subnetting Ruangan dan NIM (`/rencana`)
* **Integrasi NIM Praktikum**: Otomatis menerjemahkan dua digit terakhir NIM mahasiswa menjadi network induk (`192.168.XX.0/24`).
* **Fitur Tambahan**:
  * Pengaturan persentase cadangan host masa depan per ruangan.
  * Opsi penambahan +1 host untuk interface Gateway Router.
  * Tab komparasi langsung antara skema dengan gateway dan tanpa gateway.

### 4. Konversi Antar Basis Bilangan (`/konversi`)
* Konversi dua arah antara Biner, Oktal, Desimal, dan Heksadesimal.
* Konversi alamat IPv4 4-oktet desimal ke format 32-bit biner penuh.
* Dilengkapi Tabel Pembobotan Bit Modul (128, 64, 32, 16, 8, 4, 2, 1) serta langkah pembagian berulang.

### 5. Generator Skrip DHCP Cisco IOS (`/dhcp`)
* Menghasilkan konfigurasi CLI standar Cisco IOS 10 baris:
  ```cisco
  Router> enable
  Router# configure terminal
  Router(config)# interface FastEthernet0/0
  Router(config-if)# ip address 192.168.10.1 255.255.255.0
  Router(config-if)# no shutdown
  Router(config-if)# exit
  Router(config)# ip dhcp excluded-address 192.168.10.1 192.168.10.10
  Router(config)# ip dhcp pool LAB_JARINGAN
  Router(dhcp-config)# network 192.168.10.0 255.255.255.0
  Router(dhcp-config)# default-router 192.168.10.1
  Router(dhcp-config)# dns-server 8.8.8.8
  ```
* Prediksi alamat IP klien pertama yang akan diterima oleh workstation pada Cisco Packet Tracer.

### 6. Tabel Rekapitulasi Alamat IP (`/tabel-ip`)
* Manajemen antarmuka IP untuk seluruh perangkat jaringan (Router, Switch, Server, PC, Laptop, Access Point).
* **Deteksi Konflik Otomatis**: Memeriksa bentrok IP kembar dan alamat yang berada di luar subnet target.
* **Salin TSV (Tab-Separated Values)**: Memindahkan data tabel ke lembar kerja Excel atau Google Docs dalam satu klik.
* **Mode Cetak**: Format lembar kertas A4 yang bersih tanpa elemen tombol navigasi.

---

<a id="arsitektur-dan-alur-sistem"></a>
## Arsitektur dan Alur Sistem

Arsitektur aplikasi menerapkan pemisahan tanggung jawab (*Separation of Concerns*): antarmuka reaktif di frontend dan mesin kalkulasi deterministik murni di backend.

```mermaid
flowchart TD
    subgraph Klien["Frontend (React 19, TypeScript, Vite)"]
        UI["Formulir Interaktif (State dan Validasi)"]
        Renderer["StepRenderer Engine"]
        Card["StepCard (Langkah 1..N)"]
        Table["ResultTable (Copy TSV, Print)"]
        Bar["Address Block Visualizer"]
    end

    subgraph Server["Backend (Python 3.12, FastAPI)"]
        API["FastAPI App Router (/api/jaringan/*)"]
        Registry["Feature Registry Core (FR-18)"]
        Pydantic["Pydantic v2 Schema Validator"]
        Solver["Solver: Bitwise Integer Math"]
        Steps["Steps Engine: Formatter Lembar Jawaban"]
    end

    UI -->|1. HTTP POST Request (JSON)| API
    API -->|2. Validasi Skema Input| Pydantic
    Pydantic -->|3. Data Tervalidasi| Solver
    Solver -->|4. Hasil Kalkulasi Bitwise| Steps
    Steps -->|5. Jawaban Terstruktur (StrukturJawaban)| Registry
    Registry -->|6. JSON Response| Renderer
    Renderer --> Card
    Renderer --> Table
    Renderer --> Bar
```

### Format Respon Terstruktur (`StrukturJawaban`)
Seluruh endpoint API mengembalikan struktur seragam:
```json
{
  "fitur": "subnet",
  "diketahui": [
    { "label": "Alamat IP", "nilai": "192.168.10.45" },
    { "label": "Prefix CIDR", "nilai": "/26" }
  ],
  "langkah": [
    {
      "nomor": 1,
      "judul": "Menentukan Subnet Mask dan Invers Mask",
      "penjelasan": "Prefix /26 menunjukkan 26 bit pertama bernilai 1...",
      "tabel": null,
      "hasil": "Subnet Mask: 255.255.255.192 | Invers Mask: 0.0.0.63"
    }
  ],
  "hasil_akhir": {
    "tabel": [...]
  },
  "kesimpulan": "Alamat IP 192.168.10.45/26 berada pada subnet ke-1 dengan rentang host valid 192.168.10.1 s.d. 192.168.10.62.",
  "peringatan": []
}
```

---

<a id="teknologi-yang-digunakan"></a>
## Teknologi yang Digunakan

### Frontend
* **Core**: [React 19](https://react.dev/) dan [TypeScript](https://www.typescriptlang.org/)
* **Build Tool**: [Vite 8](https://vitejs.dev/)
* **Routing**: [React Router v7](https://reactrouter.com/)
* **Styling**: [Tailwind CSS v4](https://tailwindcss.com/) dengan palet kustom Neo-Brutalism
* **Icons**: [Lucide React](https://lucide.dev/)
* **Testing**: [Vitest](https://vitest.dev/) + React Testing Library + jsdom
* **Linter**: [Oxlint](https://oxc.rs/)

### Backend
* **Core**: [Python 3.12](https://www.python.org/)
* **Framework**: [FastAPI](https://fastapi.tiangolo.com/) (Asynchronous REST API)
* **Validation**: [Pydantic v2](https://docs.pydantic.dev/)
* **ASGI Server**: [Uvicorn](https://www.uvicorn.org/)
* **Testing**: [pytest](https://pytest.org/) + [HTTPX](https://www.python-httpx.org/)

---

<a id="panduan-instalasi-dan-menjalankan"></a>
## Panduan Instalasi dan Menjalankan

### Prasyarat Sistem
* **Python** 3.10+ (Direkomendasikan Python 3.12)
* **Node.js** 18+ dan **npm** 9+
* *Opsional*: Docker

---

<a id="opsi-a-menjalankan-secara-lokal-manual"></a>
### Opsi A: Menjalankan Secara Lokal (Manual)

#### 1. Clone Repositori
```bash
git clone https://github.com/firnassw/Asisten-Praktikum-Jarkom.git
cd Asisten-Praktikum-Jarkom
```

#### 2. Menjalankan Backend (FastAPI)
Buka terminal pertama:
```bash
cd backend

# Membuat virtual environment
python -m venv venv

# Aktivasi virtual environment
# Windows:
venv\Scripts\activate
# Linux / macOS:
source venv/bin/activate

# Instalasi dependensi
pip install -r requirements.txt

# Menjalankan server backend
python -m uvicorn app.main:app --host 127.0.0.1 --port 8000 --reload
```
> **Akses Backend**: Kunjungi `http://127.0.0.1:8000/docs` untuk membuka dokumentasi interaktif Swagger UI.

#### 3. Menjalankan Frontend (React + Vite)
Buka terminal kedua:
```bash
cd frontend

# Instalasi paket
npm install

# Menjalankan development server
npm run dev
```
> **Akses Frontend**: Buka aplikasi melalui `http://localhost:5173`. Request ke `/api/*` secara otomatis diarahkan ke backend port 8000.

---

<a id="opsi-b-menjalankan-dengan-docker"></a>
### Opsi B: Menjalankan dengan Docker

Backend dilengkapi `Dockerfile` mandiri untuk kemudahan deployment:

```bash
cd backend

# Membangun image Docker
docker build -t asisten-jarkom-backend .

# Menjalankan kontainer
docker run -p 8000:8000 asisten-jarkom-backend
```

---

<a id="dokumentasi-rest-api"></a>
## Dokumentasi REST API

Endpoint backend dapat diuji secara interaktif melalui Swagger di `/docs` atau Redoc di `/redoc`:

| Metode | Endpoint | Deskripsi | Parameter Utama |
|---|---|---|---|
| `GET` | `/api/health` | Pengecekan status server | - |
| `GET` | `/api/modul` | Mengambil daftar seluruh modul aktif (FR-18) | - |
| `POST` | `/api/jaringan/subnet` | Analisis satu alamat IP dan prefix CIDR | `alamat_ip`, `prefix` |
| `POST` | `/api/jaringan/flsm` | Alokasi Fixed-Length Subnet Mask | `induk`, `daftar_kebutuhan`, `gaya_modul` |
| `POST` | `/api/jaringan/vlsm` | Alokasi Variable-Length Subnet Mask | `induk`, `daftar_kebutuhan` |
| `POST` | `/api/jaringan/rencana` | Perencanaan Subnetting Ruangan dan NIM | `nim`, `daftar_ruangan`, `hitung_gateway` |
| `POST` | `/api/jaringan/konversi` | Konversi antar basis dan IPv4 biner | `nilai`, `basis_asal`, `basis_tujuan` |
| `POST` | `/api/jaringan/dhcp` | Generator skrip Cisco IOS DHCP Router | `nama_pool`, `network`, `gateway`, `dns` |
| `POST` | `/api/jaringan/tabel-ip` | Rekapitulasi dan audit tabel IP perangkat | `daftar_perangkat` |

---

<a id="pengujian-dan-verifikasi-kualitas"></a>
## Pengujian dan Verifikasi Kualitas

Integritas perhitungan diverifikasi terhadap **Data Uji Emas Modul Praktikum** (`G-JAR-01` sampai `G-JAR-12`).

```
========================= 116 TOTAL TESTS PASSING =========================
  Backend (pytest)   :  81 Unit & Integration Tests (Deterministik 100%)
  Frontend (Vitest)  :  35 Component, Form, & Rendering Tests
===========================================================================
```

### Menjalankan Tes Backend (`pytest`)
```bash
cd backend
pytest -v
```
*Menguji skenario kalkulasi CIDR, FLSM, VLSM, generator DHCP, deteksi bentrok IP, validasi skema Pydantic, dan kode error.*

### Menjalankan Tes Frontend (`Vitest`)
```bash
cd frontend
npm test
```
*Menguji rendering komponen responsif, interaksi formulir, penyalinan TSV, kartu langkah, dan penanganan kondisi error.*

---

<a id="sistem-desain-neo-brutalism"></a>
## Sistem Desain: Neo-Brutalism

Aplikasi menerapkan estetika **Neo-Brutalism** dengan kontras tegas dan hierarki visual yang jelas:

<div align="center">
  <table>
    <tr>
      <td align="center" bgcolor="#FCE76C"><strong style="color:#1F1E22">Primary Yellow</strong><br/><code>#FCE76C</code></td>
      <td align="center" bgcolor="#8BD0FC"><strong style="color:#1F1E22">Sky Blue</strong><br/><code>#8BD0FC</code></td>
      <td align="center" bgcolor="#FF8F5C"><strong style="color:#1F1E22">Coral Orange</strong><br/><code>#FF8F5C</code></td>
      <td align="center" bgcolor="#1F1E22"><strong style="color:#FFFFFF">Ink Black</strong><br/><code>#1F1E22</code></td>
      <td align="center" bgcolor="#F5F6F8"><strong style="color:#1F1E22">Neutral Gray</strong><br/><code>#F5F6F8</code></td>
      <td align="center" bgcolor="#16794C"><strong style="color:#FFFFFF">Success Green</strong><br/><code>#16794C</code></td>
    </tr>
  </table>
</div>

* **Border dan Bayangan**: Garis tepi tegas `2px solid #1F1E22` dipadukan dengan *hard offset shadow* `3px 3px 0 #1F1E22` tanpa efek blur gaussian.
* **Kombinasi Tipografi**:
  * **Montserrat**: Tipografi sans-serif untuk judul, label formulir, dan narasi penjelasan.
  * **JetBrains Mono**: Tipografi monospace untuk angka oktet, alamat IP, representasi biner, dan perintah CLI Cisco IOS.

---

<a id="struktur-direktori-repositori"></a>
## Struktur Direktori Repositori

```text
Asisten-Praktikum-Jarkom/
├── backend/
│   ├── app/
│   │   ├── main.py                     # Entry point FastAPI, CORS dan Exception Handlers
│   │   ├── core/
│   │   │   ├── errors.py               # Standardisasi kode error API terstruktur
│   │   │   ├── registry.py             # Feature Registry dinamis (FR-18)
│   │   │   └── schemas.py              # Skema respon seragam (StrukturJawaban)
│   │   └── modules/
│   │       └── jaringan/
│   │           ├── router.py           # Endpoint REST API jaringan komputer
│   │           ├── schemas.py          # Validasi skema input/output Pydantic v2
│   │           ├── solver.py           # Logika perhitungan bitwise integer murni
│   │           └── steps.py            # Penyusun narasi langkah jawaban responsi
│   ├── tests/                          # 81 Test case pytest (Data Uji Emas Modul)
│   ├── Dockerfile                      # Kontainer Docker mandiri FastAPI
│   ├── Procfile                        # Konfigurasi deployment PaaS
│   └── requirements.txt                # Dependensi Python backend
│
├── frontend/
│   ├── public/                         # Aset publik, logo SVG, dan favicon
│   ├── src/
│   │   ├── components/                 # Komponen UI (StepCard, ResultTable, Banner, dll.)
│   │   ├── pages/                      # Halaman fitur (Subnetting, FLSM, Rencana, DHCP, dll.)
│   │   ├── services/                   # HTTP client API fetch
│   │   ├── types/                      # Definisi tipe TypeScript
│   │   └── test/                       # 35 Test case Vitest
│   ├── package.json                    # Dependensi frontend React 19
│   ├── tailwind.config.ts              # Konfigurasi desain Neo-Brutalism
│   └── vite.config.ts                  # Konfigurasi Vite dan proxy backend
│
├── docs/
│   ├── PRD.pdf                         # Dokumen Product Requirement Document v2.0
│   ├── design.md                       # Panduan Design System, token warna dan font
│   ├── KONTEKS.md                      # Dokumentasi filosofi domain praktikum
│   └── design/                         # Galeri tangkapan layar antarmuka
│
├── vercel.json                         # Konfigurasi deployment monorepo Vercel
├── LICENSE                             # Lisensi Open Source MIT
└── README.md                           # Dokumentasi utama proyek
```

---

<a id="kontribusi-dan-lisensi"></a>
## Kontribusi dan Lisensi

### Pembuat dan Pengembang
Dikembangkan untuk mendukung praktikum **Jaringan Komputer**, Program Studi Informatika, Fakultas Teknik Industri, **UPN "Veteran" Yogyakarta**.

* **Lead Developer & Maintainer**: **Wahid Firnas** ([@firnassw](https://github.com/firnassw))

### Alur Kontribusi
Kontribusi perbaikan bug, penyesuaian dokumentasi, atau penambahan skenario modul baru dilakukan melalui mekanisme Pull Request:
1. Fork repositori ini
2. Buat branch fitur baru (`git checkout -b fitur/nama-fitur`)
3. Lakukan commit perubahan (`git commit -m 'feat: deskripsi perubahan'`)
4. Jalankan seluruh pengujian (`pytest` dan `npm test`)
5. Push ke branch repositori fork (`git push origin fitur/nama-fitur`)
6. Buka Pull Request

### Lisensi
Proyek ini didistribusikan di bawah naungan lisensi **MIT**. Rincian ketentuan lisensi tercantum pada berkas [LICENSE](LICENSE).
