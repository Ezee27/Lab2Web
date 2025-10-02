---

# **Praktikum 2 – CSS Dasar**

---

## **Identitas**

### **Mata Kuliah** : Pemrograman Web1 ###
### **Nama**        : Zaenal Maulana Rizki ###
### **NIM**         : 312410332 ###
### **Kelas**       : TI.24.A.4 ###
### **Dosen**       : Agung Nugroho, S.Kom., M.Kom. ###


---

## **Tujuan**

<img width="602" height="214" alt="image" src="https://github.com/user-attachments/assets/9f5c20d9-4b54-4f91-aecc-bce6e1c5459d" />

---

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
