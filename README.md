Judul:
Implementasi MLOps Sederhana dengan Python, Docker, dan PostgreSQL

Deskripsi:
Proyek ini merupakan implementasi sederhana dari konsep MLOps yang bertujuan untuk menjalankan aplikasi Python di dalam container dan terhubung dengan database PostgreSQL. Aplikasi Python (uts.py) berfungsi untuk membuat tabel, menambahkan data, serta menampilkan data dari database. Seluruh sistem dikemas menggunakan Docker dan diorkestrasi menggunakan Docker Compose agar dapat dijalankan dengan mudah dan konsisten di berbagai lingkungan.
Proyek ini menggunakan base image python:3.9-slim karena ukurannya yang ringan dan efisien, sehingga mempercepat proses build dan deployment container. Image ini sudah cukup untuk menjalankan aplikasi Python tanpa membawa dependensi yang tidak diperlukan, sehingga sesuai dengan best practice dalam penggunaan Docker.

Arsitektur sistem terdiri dari dua container utama, yaitu app dan database (PostgreSQL). Container app menjalankan skrip Python yang terhubung ke database menggunakan environment variables seperti host, user, dan password. Komunikasi antar container terjadi melalui jaringan internal Docker Compose, di mana service app mengakses database menggunakan nama service db sebagai host. Selain itu, digunakan depends_on agar container app hanya berjalan setelah database siap, serta volume pada database untuk memastikan data tetap tersimpan meskipun container dihentikan.
