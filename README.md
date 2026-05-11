# Simple LMS - Docker & Django Foundation

## Deskripsi
Project Simple LMS dibuat menggunakan Django Framework dengan PostgreSQL database dan dijalankan menggunakan Docker Compose.

---

## Project Structure

Docker & Django Foundation/

├── docker-compose.yml  
├── Dockerfile  
├── .env.example  
├── requirements.txt  
├── manage.py  
├── config/  
│ ├── settings.py  
│ ├── urls.py  
│ └── wsgi.py  
└── README.md  

---

## Cara Menjalankan Project

### 1. Build dan Jalankan Container

docker compose up -d --build

### 2. Jalankan Migration

docker compose exec web python manage.py migrate

### 3. Buat Superuser

docker compose exec web python manage.py createsuperuser

### 4. Akses Website

http://localhost:8001

---

## Environment Variables Explanation

File .env.example berisi konfigurasi database:

DB_NAME=lmsdb  
DB_USER=postgres  
DB_PASSWORD=password123  
DB_HOST=db  
DB_PORT=5432  

Penjelasan:

- DB_NAME = nama database PostgreSQL
- DB_USER = username database
- DB_PASSWORD = password database
- DB_HOST = nama service database di Docker Compose
- DB_PORT = port PostgreSQL

---

## Screenshot

### Django Welcome Page

Tambahkan screenshot halaman localhost setelah project berjalan.

Contoh:
screenshots/django-home.png

---

## Services

- web = Django Application
- db = PostgreSQL Database

---

## Author

Nama: Jonathan Naufal Farrel  
Mata Kuliah: Pemrograman Sisi Server
=======
# Docker-Django
Project ini dibuat sebagai tugas mata kuliah Pemrograman Sisi Server untuk memahami implementasi Docker pada aplikasi Django dengan database PostgreSQL.