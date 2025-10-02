---

# **Praktikum 2 – CSS Dasar**

---

## **Identitas**

### **Mata Kuliah** : Pemograman Web1 ###
### **Nama**        : Zaenal Maulana Rizki ###
### **NIM**         : 312410332 ###
### **Kelas**       : TI.24.A.4 ###
### **Dosen**       : Agung Nugroho, S.Kom., M.Kom. ###


---

## **Tujuan**


<img width="629" height="225" alt="image" src="https://github.com/user-attachments/assets/1b4f473d-4ee7-4b7e-a45b-97e8ece432c3" />


---

---

### 1. Membuat Dokumen HTML

Pada langkah ini, dibuat sebuah file HTML baru (misalnya: lab2_css_dasar.html) yang berisi struktur dasar dokumen HTML.


<img width="1510" height="1432" alt="no1" src="https://github.com/user-attachments/assets/3ec2ecee-44de-40cc-a60c-fb5aed90b4b5" />



**📷Screenshot:**
<img width="1919" height="420" alt="image" src="https://github.com/user-attachments/assets/1aa2c6b4-2ff6-45bd-8f44-197815742ebb" />


---

## 2. Mendeklarasikan CSS Internal

CSS internal ditulis pada bagian `<head>` menggunakan tag `<style>`.
CSS ini digunakan untuk mengatur tampilan elemen pada halaman yang sama.

**Kode:**

<img width="972" height="1090" alt="no2" src="https://github.com/user-attachments/assets/04b4b231-2c58-424f-875a-8bd0fc67101d" />


**📷Screenshot:**
<img width="1915" height="439" alt="image" src="https://github.com/user-attachments/assets/1d259e6c-2611-4ea0-9786-607e094e6fae" />


---

## 3. Menambahkan Inline CSS

Inline CSS ditulis langsung pada elemen HTML menggunakan atribut `style`.
CSS jenis ini hanya berlaku pada elemen yang ditentukan.

**Kode:**

<img width="1434" height="520" alt="image" src="https://github.com/user-attachments/assets/74c3c7f6-0606-4553-85c9-d9d18a4fe42b" />


**📷Screenshot:**
<img width="1900" height="196" alt="image" src="https://github.com/user-attachments/assets/9e2056ed-14fe-45ca-a48d-dc454683f2f8" />

---

## 4. Menambahkan Eksternal CSS

Selain internal dan inline, CSS juga bisa ditulis terpisah di file `.css`, lalu dipanggil ke HTML dengan `<link>`.

**Kode File CSS (`style_eksternal.css`):**

<img width="740" height="1888" alt="image" src="https://github.com/user-attachments/assets/dcfa6203-24fd-438f-b87c-f6f848791a66" />

**Kode Pemanggilan di HTML:**

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

**📷Screenshot:**
![Eksternal CSS](screenshot/eksternal.png)

```

---

📌 Jadi kamu tinggal ganti bagian `![Screenshot](...)` dengan file screenshot hasil run HTML kamu (sesuai kayak temanmu).  

Mau aku bikinin **versi README lengkap** langsung dengan struktur step 1–4 (HTML, internal CSS, inline CSS, eksternal CSS) biar bisa kamu copy-paste ke repo?
```

111
## **1. Eksperimen mengubah properti dan nilai CSS**

Disini saya mencoba mengubah dan menambah properti pada CSS dengan mengacu pada CSS Cheat Sheet.

### Contoh Kode:

```css
body {
    background-color: lightblue;
    font-family: Arial, sans-serif;
}

h1 {
    color: darkred;
    text-align: center;
    font-size: 30px;
}

p {
    color: darkgreen;
    line-height: 1.8;
    font-size: 16px;
}
```

**Hasil**:

* Latar belakang halaman berubah menjadi biru muda.
* Judul `<h1>` berwarna merah gelap dan berada di tengah.
* Paragraf `<p>` berwarna hijau dengan jarak antar baris lebih lebar.

---

## **2. Perbedaan h1 { ... } dengan #intro h1 { ... }**

* `h1 { ... }` → berlaku untuk semua elemen `<h1>` di halaman web.
* `#intro h1 { ... }` → hanya berlaku untuk elemen `<h1>` yang berada di dalam elemen dengan `id="intro"`.

### Contoh Kode:

```css
h1 {
    color: red;
}
#intro h1 {
    color: blue;
}
```

```html
<h1>Judul Umum</h1>
<div id="intro">
    <h1>Judul di Intro</h1>
</div>
```

**Hasil**:

* "Judul Umum" → merah.
* "Judul di Intro" → biru.

---

## **3. Urutan Prioritas (Internal, Eksternal, Inline CSS)**

Jika pada elemen yang sama terdapat **Eksternal, Internal, dan Inline CSS**, maka prioritas yang berlaku:

**Inline > Internal > Eksternal**

### Contoh Kode:

**File: `style.css`**

```css
p {
    color: red;
}
```

**File: `soal3.html`**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Soal 3</title>

  <!-- Eksternal CSS -->
  <link rel="stylesheet" href="style.css">

  <!-- Internal CSS -->
  <style>
    /* Internal CSS */
    p { color: green; }
  </style>
</head>
<body>
  <!-- Inline CSS -->
  <p style="color: blue;">Teks Paragraf</p>
</body>
</html>
```

**Hasil**: Teks paragraf berwarna **biru**, karena inline CSS memiliki prioritas tertinggi.

---

## **4. ID vs Class**

Jika elemen HTML memiliki **ID dan Class**, maka aturan dengan selector **ID lebih kuat** daripada Class.

### Contoh Kode:

```css
#paragraf-1 {
    color: red;
}
.text-paragraf {
    color: green;
}
```

```html
<p id="paragraf-1" class="text-paragraf">Contoh Paragraf</p>
```

**Hasil**: Teks paragraf berwarna **merah**, karena selector ID (`#paragraf-1`) lebih spesifik dibandingkan class (`.text-paragraf`).

---

## **Kesimpulan**

* CSS dapat ditulis secara **eksternal, internal, atau inline**.
* Selector `h1` berlaku umum, sedangkan `#intro h1` hanya untuk elemen tertentu di dalam ID `intro`.
* Urutan prioritas CSS: **Inline > Internal > Eksternal**.
* Jika terdapat ID dan Class, **ID lebih diprioritaskan** karena memiliki spesifisitas lebih tinggi.

---
