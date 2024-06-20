# Project-Capstone-Bangkit-Academy-2024

## API Documentation

### Register User
**Endpoint:** `POST /register`

**Description:** Mendaftarkan pengguna baru dengan email, password, dan username.

#### Request Body:
```json
{
  "email": "abdul4@gmail.com",
  "password": "password123",
  "username": "newuser"
}
```

#### Response:

**Success (201 Created):**
```json
{
  "message": "Pengguna berhasil didaftarkan",
  "user": {
      "uid": "gMKNYhX7mxZsCoX2ZPyc8srZiQq2",
      "email": "abdul4@gmail.com",
      "emailVerified": false,
      "disabled": false,
      "metadata": {
          "lastSignInTime": null,
          "creationTime": "Thu, 20 Jun 2024 09:17:44 GMT",
          "lastRefreshTime": null
      },
      "tokensValidAfterTime": "Thu, 20 Jun 2024 09:17:44 GMT",
      "providerData": [
          {
              "uid": "abdul4@gmail.com",
              "email": "abdul4@gmail.com",
              "providerId": "password"
          }
      ]
  }
}
```

**Error (400 Bad Request):**
```json
{
  "errors": [
    {
      "msg": "Email tidak valid",
      "param": "email",
      "location": "body"
    }
  ]
}
```

### Login User
**Endpoint:** `POST /login`

**Description:** Login pengguna dengan email dan password.

#### Request Body:
```json
{
  "email": "admin@gmail.com",
  "password": "password123"
}
```

#### Response:

**Success (200 OK):**
```json
{
  "kind": "identitytoolkit#VerifyPasswordResponse",
  "localId": "7nCqIJt2lEXzQ490wzNxXLjy7Np2",
  "email": "admin@gmail.com",
  "displayName": "",
  "idToken": "eyJhbGciOiJSUzI1NiIsImtpZCI6IjduY3Y5USJ9.eyJpc3MiOiJodHRwczovL2lkZW50aXR5dG9vbGtpdC5nb29nbGUuY29tLyIsImF1ZCI6ImNhdC1icmVlZC1hNzBkYiIsImlhdCI6MTcxODg5MTI5OCwiZXhwIjoxNzIwMTAwODk4LCJ1c2VyX2lkIjoiN25DcUlKdDJsRVh6UTQ5MHd6TnhYTGp5N05wMiIsImVtYWlsIjoiYWRtaW5AZ21haWwuY29tIiwic2lnbl9pbl9wcm92aWRlciI6InBhc3N3b3JkIiwidmVyaWZpZWQiOmZhbHNlfQ.BcyHz-4IWx60KDT5n2hGaEykDU-KElHwssIGxPQ6mMgPqBEMgFWcaa1zW0BNZrXF-2uIbj3jsJbtBukOVaM0RMgBGLffKjkCGaxac80c6Pr-6w9Qp8nXdBHe18MHJepWKjbsIgvbr6wjwjTc2gEM2zxxWHNiYhviE3puuPQU05Wa4sF3xR01V5YY6_UC3p__4Ab0nlxVV5dnxEV82CrL-jcuTSA5bOgMshiS_DxxlxiJorL1WK7UtWOh-es_YOABLOIReKfC1CNT5n8wfr9TrdBQWPXiZece3ONWBC7tiZJpQjXIeSrXUXJvkHMIHA5EV8oa--nGJJitnoQ0CqeF7w",
  "registered": true
}
```

**Error (400 Bad Request):**
```json
{
  "errors": [
    {
      "msg": "Email atau password salah",
      "param": "email",
      "location": "body"
    }
  ]
}
```

### Get Cat Breeds
**Endpoint:** `GET /cat-breeds`

**Description:** Mengambil daftar ras kucing.

#### Response:

**Success (200 OK):**
```json
[
  {
      "Definisi": "Kucing Abyssinian, juga dikenal sebagai Abys, memiliki kemiripan yang mencolok dengan kucing yang digambarkan dalam mural Mesir kuno. Mereka memiliki mata berbentuk almond, telinga yang tajam, dan tubuh yang ramping. Beberapa orang percaya bahwa Abyssinian adalah keturunan langsung dari kucing purba yang dihormati ini, sementara yang lain berpendapat bahwa mereka berasal dari tempat yang sekarang disebut Etiopia dan melakukan perjalanan bersama tentara Inggris ke Inggris, menurut Abyssinian Cat Club. Semua kucing Abyssinian memiliki bulu agouti, yang berarti setiap helai bulunya memiliki berbagai warna: pita gelap, pita terang, dan ujung gelap. Hal ini membuat bulu halus mereka tampak seperti garam dan merica.",
      "gambar": "https://storage.googleapis.com/pawpal/cat%20breeds/Abyssinian_118.jpg",
      "id_ras": 1,
      "list_penyakit": "Aortic thromboembolism, Atopic dermatitis (atopy), Diabetes mellitus,  Increased osmotic fragility of erythrocytes, Pyruvate kinase deficiency, Feline infectious peritonitis (FIP), Mycobacterium avium complex infection, Urinary tract infections (UTI), Acquired myasthenia gravis, Patellar luxation, Acquired myasthenia gravis, Progressive retinal atrophy (PRA), Renal amyloidosis, Dystocia, Pyometra (cystic endometrial hyperplasia–pyometra complex)",
      "nama_ras": "Abyssinian"
  }
]
```

### Get Cat Breeds by ID
**Endpoint:** `GET /cat-breeds/:id`

**Description:** Mengambil detail ras kucing berdasarkan ID.

#### Response:

**Success (200 OK):**
```json
{
  "Definisi": "Kucing Abyssinian, juga dikenal sebagai Abys, memiliki kemiripan yang mencolok dengan kucing yang digambarkan dalam mural Mesir kuno. Mereka memiliki mata berbentuk almond, telinga yang tajam, dan tubuh yang ramping. Beberapa orang percaya bahwa Abyssinian adalah keturunan langsung dari kucing purba yang dihormati ini, sementara yang lain berpendapat bahwa mereka berasal dari tempat yang sekarang disebut Etiopia dan melakukan perjalanan bersama tentara Inggris ke Inggris, menurut Abyssinian Cat Club. Semua kucing Abyssinian memiliki bulu agouti, yang berarti setiap helai bulunya memiliki berbagai warna: pita gelap, pita terang, dan ujung gelap. Hal ini membuat bulu halus mereka tampak seperti garam dan merica.",
  "gambar": "https://storage.googleapis.com/pawpal/cat%20breeds/Abyssinian_118.jpg",
  "id_ras": 1,
  "list_penyakit": "Aortic thromboembolism, Atopic dermatitis (atopy), Diabetes mellitus,  Increased osmotic fragility of erythrocytes, Pyruvate kinase deficiency, Feline infectious peritonitis (FIP), Mycobacterium avium complex infection, Urinary tract infections (UTI), Acquired myasthenia gravis, Patellar luxation, Acquired myasthenia gravis, Progressive retinal atrophy (PRA), Renal amyloidosis, Dystocia, Pyometra (cystic endometrial hyperplasia–pyometra complex)",
  "nama_ras": "Abyssinian"
}
```

### Get Symptoms
**Endpoint:** `GET /symptoms`

**Description:** Mengambil daftar gejala.

#### Response:

**Success (200 OK):**
```json
[
  {
      "definisi_penyakit": "Pada kondisi ini ventrikel yang mengalami hipertrofi menyebabkan gagal jantung kongestif dan disritmia. Insidensinya dilaporkan sebesar 1,6-5,2% pada kucing, namun jarang terjadi pada anjing. Kemungkinan besar kondisi tersebut diturunkan, meskipun faktor pengubah dapat menyebabkan ekspresi kondisi yang bervariasi.",
      "gejala": "Sesak napas, kelelahan, batuk kronis",
      "id_penyakit": 1,
      "nama_penyakit": "Hypertrophic cardiomyopathy",
      "penanganan": "Pemberian obat untuk mengurangi beban jantung, diet rendah sodium, operasi jika diperlukan"
  },
  {
      "definisi_penyakit": "Bekuan darah yang menempel di aorta ekor, terutama pada kucing tetapi kadang-kadang pada anjing, menyebabkan tanda-tanda paresis atau kelumpuhan tungkai belakang, ekstremitas dingin, dan nyeri. Hal ini sering dikaitkan dengan penyakit jantung pada kucing, dan banyak kasus mungkin muncul bersamaan dengan gagal jantung.",
      "gejala": "Kelemahan atau kelumpuhan tungkai belakang, kaki dingin
