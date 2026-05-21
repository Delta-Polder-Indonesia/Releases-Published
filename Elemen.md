# Panduan Elemen dan Atribut HTML/Markdown yang Diperbolehkan

Dokumen ini merupakan panduan lengkap mengenai elemen dan atribut HTML serta Markdown (setelah dikonversi ke HTML) yang diizinkan untuk digunakan. Setiap elemen dijelaskan secara detail disertai contoh penerapan praktis.

---

## Daftar Isi

1. [Elemen Umum dan Atribut Global](#1-elemen-umum-dan-atribut-global)
2. [Elemen Teks dan Formatting](#2-elemen-teks-dan-formatting)
3. [Elemen Ruby (Anotasi Fonik)](#3-elemen-ruby-anotasi-fonik)
4. [Elemen List](#4-elemen-list)
5. [Elemen Tabel](#5-elemen-tabel)
6. [Elemen Media](#6-elemen-media)
7. [Elemen Semantik Tambahan](#7-elemen-semantik-tambahan)
8. [Ringkasan Aturan Keamanan](#8-ringkasan-aturan-keamanan)

---

## 1. Elemen Umum dan Atribut Global

### `<* title|style>`
Elemen apa pun dengan atribut `title` atau `style`. Atribut `title` menampilkan tooltip saat kursor diarahkan, sedangkan `style` digunakan untuk styling inline.

**Contoh Penerapan:**

```html
<!-- Contoh dengan title -->
<p title="Ini adalah tooltip">Arahkan kursor ke sini untuk melihat tooltip</p>

<!-- Contoh dengan style -->
<p style="color: blue; font-size: 16px;">Teks ini berwarna biru dengan ukuran 16px</p>
```

**Penjelasan:**
- `title`: Memberikan informasi tambahan yang muncul sebagai tooltip. Berguna untuk memberikan keterangan singkat tanpa mengganggu tampilan utama.
- `style`: Menyisipkan CSS langsung pada elemen. Ideal untuk styling cepat, meskipun untuk proyek besar disarankan menggunakan file CSS terpisah.

---

## 2. Elemen Teks dan Formatting

### `<a href=(ftp|http|https|mailto|relative) name>`
Hyperlink untuk menavigasi ke sumber lain.

**Contoh Penerapan:**

```html
<!-- Link ke website (https) -->
<a href="https://www.example.com">Kunjungi Website</a>

<!-- Link email (mailto) -->
<a href="mailto:email@example.com">Kirim Email</a>

<!-- Link relatif (file lokal) -->
<a href="halaman-lain.html">Ke Halaman Lain</a>

<!-- Link FTP -->
<a href="ftp://ftp.example.com/file.zip">Download File FTP</a>

<!-- Dengan atribut name (anchor) -->
<a name="bagian-bawah">Bagian Bawah Dokumen</a>
<a href="#bagian-bawah">Lompat ke Bagian Bawah</a>
```

**Penjelasan:**
- `href`: Menentukan destinasi link. Bisa berupa URL absolut (http/https), email (mailto), protokol FTP, atau path relatif.
- `name`: Membuat penanda (bookmark) dalam dokumen yang dapat dilompat menggunakan fragment identifier (`#`).

---

### `<abbr title>`
Menandai singkatan atau akronim dengan penjelasan lengkapnya.

**Contoh Penerapan:**

```html
<p>Bahasa pemrograman <abbr title="HyperText Markup Language">HTML</abbr> 
digunakan untuk membuat halaman web.</p>
```

**Penjelasan:**
- `title`: Menyimpan arti lengkap dari singkatan tersebut.
- Manfaat: Membantu pembaca yang tidak familiar dengan singkatan, serta meningkatkan aksesibilitas bagi screen reader.

---

### `<b>`
Menebalkan teks tanpa menambahkan makna semantik penting.

**Contoh Penerapan:**

```html
<p>Perhatikan kata <b>penting</b> dalam kalimat ini.</p>
```

**Penjelasan:**
- `<b>` hanya mengubah tampilan visual (bold). Gunakan `<strong>` jika teks memiliki signifikansi semantik yang tinggi.

---

### `<blockquote cite=(http|https|relative)>`
Menyajikan kutipan panjang dari sumber lain.

**Contoh Penerapan:**

```html
<blockquote cite="https://www.example.com/artikel">
  <p>Web adalah medium yang menghubungkan manusia di seluruh dunia 
  melalui jaringan informasi yang tak terbatas.</p>
</blockquote>
```

**Penjelasan:**
- `cite`: Menunjukkan URL sumber asli kutipan.
- Browser biasanya menampilkan blockquote dengan indentasi di kedua sisi dan jarak antar paragraf.

---

### `<br>`
Line break (jeda baris).

**Contoh Penerapan:**

```html
<p>Baris pertama<br>Baris kedua<br>Baris ketiga</p>
```

**Penjelasan:**
- `<br>` adalah elemen kosong (tidak memiliki tag penutup).
- Gunakan untuk memisahkan baris dalam aliran teks, seperti dalam alamat atau puisi. Hindari penggunaan berlebihan untuk spacing; gunakan CSS untuk jarak yang lebih besar.

---

### `<center>`
Menyelaraskan konten ke tengah (deprecated, tapi masih didukung).

**Contoh Penerapan:**

```html
<center>
  <p>Teks ini berada di tengah halaman</p>
  <img src="https://example.com/gambar.jpg" alt="Gambar">
</center>
```

**Penjelasan:**
- Elemen ini dianggap usang dalam HTML5. Alternatif modern menggunakan CSS: `<div style="text-align: center;">`.

---

### `<cite>`
Menandai judul karya kreatif (buku, film, lagu, dll).

**Contoh Penerapan:**

```html
<p>Novel <cite>Laskar Pelangi</cite> karya Andrea Hirata menjadi 
bestseller di Indonesia.</p>
```

**Penjelasan:**
- `<cite>` memberikan makna semantik bahwa teks tersebut adalah judul karya.
- Browser biasanya menampilkannya dalam gaya italic.

---

### `<code>`
Menampilkan potongan kode komputer.

**Contoh Penerapan:**

```html
<p>Untuk menampilkan teks tebal, gunakan tag <code>&lt;b&gt;</code>.</p>
```

**Penjelasan:**
- Browser menampilkan `<code>` dengan font monospace (seperti Courier).
- Gunakan entity HTML (`&lt;` dan `&gt;`) untuk menampilkan karakter `<` dan `>` agar tidak diinterpretasikan sebagai tag.

---

### `<dd>`, `<dl>`, `<dt>`
Daftar definisi (Definition List).

**Contoh Penerapan:**

```html
<dl>
  <dt>HTML</dt>
  <dd>Bahasa markup standar untuk membuat halaman web</dd>

  <dt>CSS</dt>
  <dd>Bahasa stylesheet untuk mendesain tampilan web</dd>

  <dt>JavaScript</dt>
  <dd>Bahasa pemrograman untuk membuat halaman web interaktif</dd>
</dl>
```

**Penjelasan:**
- `<dl>`: Container untuk seluruh daftar definisi.
- `<dt>`: Term (istilah) yang akan dijelaskan.
- `<dd>`: Definition (definisi/penjelasan) dari istilah tersebut.
- Tampilan default: `<dt>` tanpa indentasi, `<dd>` dengan indentasi ke kanan.

---

### `<del>`
Menandai teks yang telah dihapus atau diubah.

**Contoh Penerapan:**

```html
<p>Harga asli: <del>Rp 500.000</del></p>
<p>Harga diskon: Rp 350.000</p>
```

**Penjelasan:**
- Browser menampilkan `<del>` dengan garis coret (strikethrough).
- Berguna untuk menunjukkan perubahan dalam dokumen, seperti daftar revisi atau perbandingan harga.

---

### `<details open>`
Widget interaktif yang dapat dibuka/tutup.

**Contoh Penerapan:**

```html
<details open>
  <summary>Informasi Penting</summary>
  <p>Konten ini akan ditampilkan secara default karena atribut "open" ada.</p>
  <p>Klik summary untuk menyembunyikan konten ini.</p>
</details>

<details>
  <summary>Klik untuk melihat detail</summary>
  <p>Konten ini tersembunyi secara default.</p>
</details>
```

**Penjelasan:**
- `open`: Atribut boolean yang membuat konten terlihat saat halaman dimuat.
- `<summary>`: Judul yang selalu terlihat dan dapat diklik.
- Berguna untuk FAQ, spoiler, atau menghemat ruang tampilan.

---

### `<dfn title>`
Menandai istilah yang sedang didefinisikan dalam konteks.

**Contoh Penerapan:**

```html
<p><dfn title="HyperText Transfer Protocol">HTTP</dfn> adalah protokol 
yang digunakan untuk mentransfer data di World Wide Web.</p>
```

**Penjelasan:**
- `<dfn>` menandakan bahwa paragraf atau kalimat tersebut mendefinisikan istilah tersebut.
- `title`: Memberikan definisi lengkap atau ekspansi singkatan.

---

### `<div>`
Container generik untuk mengelompokkan elemen.

**Contoh Penerapan:**

```html
<div style="background-color: #f0f0f0; padding: 20px;">
  <h2>Judul Bagian</h2>
  <p>Paragraf dalam div ini memiliki background abu-abu.</p>
</div>
```

**Penjelasan:**
- `<div>` tidak memiliki makna semantik sendiri. Ia adalah blok kosong yang digunakan untuk mengelompokkan elemen dan menerapkan styling atau script.
- Sebelum HTML5, `<div>` dengan class/id digunakan untuk membuat layout (header, sidebar, footer). Sekarang elemen semantik seperti `<header>`, `<nav>`, `<main>`, `<footer>` lebih disarankan.

---

### `<em>`
Menekankan teks (emphasis).

**Contoh Penerapan:**

```html
<p>Saya <em>sangat</em> menyarankan Anda untuk membaca buku ini.</p>
```

**Penjelasan:**
- `<em>` memberikan penekanan semantik. Browser menampilkannya dalam italic.
- Berbeda dengan `<i>` yang hanya mengubah tampilan tanpa penekanan makna.

---

### `<h1>` hingga `<h6>`
Heading (judul) dengan tingkatan hierarki.

**Contoh Penerapan:**

```html
<h1>Judul Utama Artikel (Level 1)</h1>
<h2>Bab 1: Pendahuluan (Level 2)</h2>
<h3>1.1 Latar Belakang (Level 3)</h3>
<h4>1.1.1 Sejarah Awal (Level 4)</h4>
<h5>Detail Spesifik (Level 5)</h5>
<h6>Catatan Kaki Sangat Detail (Level 6)</h6>
```

**Penjelasan:**
- `<h1>` adalah judul paling penting, biasanya hanya satu per halaman.
- Hierarki harus logis: jangan loncat dari `<h2>` ke `<h4>`.
- Penting untuk SEO dan aksesibilitas screen reader.

---

### `<hr>`
Horizontal rule (garis pemisah horizontal).

**Contoh Penerapan:**

```html
<h2>Bab 1</h2>
<p>Isi bab pertama...</p>
<hr>
<h2>Bab 2</h2>
<p>Isi bab kedua...</p>
```

**Penjelasan:**
- `<hr>` adalah elemen kosong yang membuat garis horizontal.
- Secara semantik, menandakan perubahan tema atau pemisahan antar bagian konten.
- Di HTML5, `<hr>` memiliki makna semantik sebagai "thematic break", bukan sekadar garis dekoratif.

---

### `<i>`
Teks italic tanpa penekanan semantik.

**Contoh Penerapan:**

```html
<p>Kata <i>algoritma</i> berasal dari nama matematikawan Al-Khwarizmi.</p>
<p>Nama kapal <i>Titanic</i> terkenal dalam sejarah.</p>
```

**Penjelasan:**
- `<i>` digunakan untuk teks dalam bahasa asing, nama kapal, istilah teknis, atau teks yang perlu dibedakan tanpa penekanan kuat.
- Gunakan `<em>` untuk penekanan yang lebih kuat secara semantik.

---

### `<ins>`
Menandai teks yang baru ditambahkan.

**Contoh Penerapan:**

```html
<p>Dokumen ini telah diperbarui. <ins>Bagian ini adalah tambahan terbaru.</ins></p>
```

**Penjelasan:**
- Browser menampilkan `<ins>` dengan garis bawah (underline).
- Sering digunakan bersama `<del>` untuk menunjukkan perubahan dalam dokumen.

---

### `<kbd>`
Menandai input keyboard.

**Contoh Penerapan:**

```html
<p>Untuk menyimpan file, tekan <kbd>Ctrl</kbd> + <kbd>S</kbd>.</p>
```

**Penjelasan:**
- Browser menampilkan `<kbd>` dengan font monospace.
- Memberikan petunjuk visual bahwa teks tersebut merepresentasikan tombol keyboard.

---

### `<mark>`
Menyoroti teks yang relevan dalam konteks tertentu.

**Contoh Penerapan:**

```html
<p>Hasil pencarian untuk "HTML": 
Dokumen ini membahas tentang <mark>HTML</mark> dan penggunaannya 
dalam pengembangan web.</p>
```

**Penjelasan:**
- Browser menampilkan `<mark>` dengan background kuning (highlight).
- Berbeda dengan `<strong>` atau `<em>`, `<mark>` menunjukkan relevansi dalam konteks spesifik (misalnya hasil pencarian).

---

### `<p>`
Paragraf.

**Contoh Penerapan:**

```html
<p>Ini adalah paragraf pertama. Paragraf adalah unit dasar dalam penulisan 
yang terdiri dari satu atau lebih kalimat yang membahas topik tertentu.</p>

<p>Ini adalah paragraf kedua. Paragraf baru akan memiliki jarak vertikal 
dengan paragraf sebelumnya.</p>
```

**Penjelasan:**
- Browser menambahkan margin vertikal antar paragraf secara default.
- Jangan gunakan `<br>` untuk membuat paragraf baru; gunakan `<p>`.

---

### `<pre>`
Preformatted text (teks dengan format tetap).

**Contoh Penerapan:**

```html
<pre>
function halo() {
    console.log("Halo Dunia!");
    return true;
}
</pre>
```

**Penjelasan:**
- Browser menampilkan teks dalam `<pre>` persis seperti yang ditulis, termasuk spasi, tab, dan jeda baris.
- Font yang digunakan adalah monospace.
- Ideal untuk menampilkan kode, puisi, atau ASCII art.

---

### `<q cite=(http|https|relative)>`
Kutipan pendek (inline quotation).

**Contoh Penerapan:**

```html
<p>Einstein pernah berkata, <q cite="https://example.com/einstein-quotes">
Imagination is more important than knowledge</q>.</p>
```

**Penjelasan:**
- Browser menambahkan tanda kutip otomatis di sekitar `<q>`.
- `cite`: Menunjukkan sumber kutipan.
- Gunakan `<blockquote>` untuk kutipan yang lebih panjang dan memerlukan paragraf tersendiri.

---

### `<s>`
Teks yang tidak lagi relevan atau akurat.

**Contoh Penerapan:**

```html
<p>Harga lama: <s>Rp 1.000.000</s></p>
<p>Harga baru: Rp 750.000</p>
```

**Penjelasan:**
- `<s>` menandakan bahwa teks tersebut sudah tidak berlaku, berbeda dengan `<del>` yang menunjukkan penghapusan dalam konteks editing.
- Browser menampilkannya dengan garis coret.

---

### `<samp>`
Menampilkan output dari program komputer.

**Contoh Penerapan:**

```html
<p>Setelah menjalankan program, terminal menampilkan:</p>
<samp>Error: File not found. Please check the path.</samp>
```

**Penjelasan:**
- `<samp>` merepresentasikan hasil atau output dari sistem komputer.
- Biasanya ditampilkan dengan font monospace.

---

### `<small>`
Teks dengan ukuran lebih kecil (catatan kaki, hak cipta).

**Contoh Penerapan:**

```html
<p>Konten utama artikel ini...</p>
<small>&copy; 2024 Nama Perusahaan. Hak cipta dilindungi undang-undang.</small>
```

**Penjelasan:**
- `<small>` secara semantik digunakan untuk teks sekunder, catatan kaki, atau informasi legal.
- Browser menampilkannya dengan ukuran font lebih kecil dari teks sekitarnya.

---

### `<span>`
Inline container generik.

**Contoh Penerapan:**

```html
<p>Warna <span style="color: red;">merah</span> melambangkan keberanian, 
sedangkan <span style="color: blue;">biru</span> melambangkan ketenangan.</p>
```

**Penjelasan:**
- `<span>` tidak memiliki makna semantik atau efek visual sendiri.
- Digunakan untuk menerapkan styling atau script pada bagian kecil teks dalam paragraf.

---

### `<strike>`
Teks dengan garis coret (deprecated, gunakan `<s>` atau `<del>`).

**Contoh Penerapan:**

```html
<p>Teks ini <strike>sudah tidak digunakan lagi</strike> dalam HTML5.</p>
```

**Penjelasan:**
- `<strike>` adalah elemen lama yang dianggap usang. Gunakan `<s>` untuk teks yang tidak relevan atau `<del>` untuk teks yang dihapus.

---

### `<strong>`
Penekanan kuat (strong importance).

**Contoh Penerapan:**

```html
<p><strong>Peringatan:</strong> Jangan mematikan komputer selama proses update!</p>
```

**Penjelasan:**
- `<strong>` memberikan penekanan semantik yang lebih kuat dari `<em>`.
- Browser menampilkannya dengan bold.
- Gunakan untuk peringatan, informasi kritis, atau hal yang sangat penting.

---

### `<sub>`
Subscript (teks di bawah garis dasar).

**Contoh Penerapan:**

```html
<p>Rumus kimia air: H<sub>2</sub>O</p>
<p>Rumus matematika: x<sub>1</sub> + x<sub>2</sub> = 10</p>
```

**Penjelasan:**
- `<sub>` menurunkan teks setengah baris dan memperkecil ukurannya.
- Sering digunakan dalam rumus kimia, matematika, atau notasi ilmiah.

---

### `<summary>`
Judul untuk elemen `<details>`.

**Contoh Penerapan:**

```html
<details>
  <summary>Petunjuk Penggunaan</summary>
  <ol>
    <li>Buka aplikasi</li>
    <li>Masukkan data</li>
    <li>Klik tombol Simpan</li>
  </ol>
</details>
```

**Penjelasan:**
- `<summary>` harus menjadi child pertama dari `<details>`.
- Selalu terlihat dan dapat diklik untuk membuka/menutup konten detail.

---

### `<sup>`
Superscript (teks di atas garis dasar).

**Contoh Penerapan:**

```html
<p>2<sup>3</sup> = 8</p>
<p>Catatan kaki<sup><a href="#catatan-1">[1]</a></sup></p>
```

**Penjelasan:**
- `<sup>` mengangkat teks setengah baris dan memperkecil ukurannya.
- Digunakan dalam eksponen matematika, catatan kaki, ordinal (1<sup>st</sup>, 2<sup>nd</sup>).

---

### `<time datetime pubdate>`
Menandai waktu/tanggal dengan format mesin-readable.

**Contoh Penerapan:**

```html
<p>Artikel ini dipublikasikan pada <time datetime="2024-03-15" pubdate>
15 Maret 2024</time>.</p>

<p>Acara dimulai pukul <time datetime="2024-03-15T09:00:00+07:00">
09:00 WIB</time>.</p>
```

**Penjelasan:**
- `datetime`: Format ISO 8601 yang dapat dibaca oleh mesin (browser, search engine, screen reader).
- `pubdate`: Menandakan bahwa waktu tersebut adalah tanggal publikasi artikel.
- Format datetime: `YYYY-MM-DD` untuk tanggal, atau `YYYY-MM-DDTHH:MM:SS+ZZ:ZZ` untuk waktu lengkap dengan zona waktu.

---

### `<tt>`
Teletype text (deprecated).

**Contoh Penerapan:**

```html
<p>Font <tt>monospace</tt> digunakan untuk kode.</p>
```

**Penjelasan:**
- `<tt>` adalah elemen lama untuk teks monospace. Gunakan `<code>`, `<kbd>`, atau `<samp>` sebagai pengganti yang lebih semantik, atau gunakan CSS `font-family: monospace;`.

---

### `<u>`
Teks dengan garis bawah (underline).

**Contoh Penerapan:**

```html
<p>Kata <u>speling</u> seharusnya dieja "spelling".</p>
```

**Penjelasan:**
- `<u>` secara semantik digunakan untuk menandai teks yang memerlukan perhatian khusus, seperti nama yang dieja fonetik atau kata yang salah eja.
- Hindari penggunaan untuk styling semata; gunakan CSS `text-decoration: underline;` untuk tujuan dekoratif.

---

### `<var>`
Menandai variabel dalam konteks matematika atau pemrograman.

**Contoh Penerapan:**

```html
<p>Rumus luas lingkaran: A = π<var>r</var><sup>2</sup></p>
<p>Dalam JavaScript, buat variabel dengan <code>let <var>namaVariabel</var>;</code></p>
```

**Penjelasan:**
- Browser menampilkan `<var>` dalam italic.
- Digunakan untuk merepresentasikan variabel matematika, parameter fungsi, atau placeholder.

---

## 3. Elemen Ruby (Anotasi Fonik)

### `<ruby>`, `<rp>`, `<rt>`
Anotasi untuk membaca karakter (terutama bahasa Asia Timur).

**Contoh Penerapan:**

```html
<ruby>
  漢 <rp>(</rp><rt>かん</rt><rp>)</rp>
  字 <rp>(</rp><rt>じ</rt><rp>)</rp>
</ruby>
```

**Penjelasan:**
- `<ruby>`: Container untuk teks utama dan anotasi.
- `<rt>`: Ruby text (anotasi fonik atau terjemahan).
- `<rp>`: Ruby parenthesis (tanda kurung fallback untuk browser yang tidak mendukung ruby).
- Jika browser mendukung ruby, `<rp>` tidak akan ditampilkan. Jika tidak, teks dalam `<rp>` akan muncul sebagai tanda kurung di sekitar `<rt>`.

---

## 4. Elemen List

### `<ol>`, `<ul>`, `<li>`
Ordered list (bernomor) dan Unordered list (berbulet).

**Contoh Penerapan:**

```html
<!-- Ordered List -->
<ol>
  <li>Langkah pertama: Persiapkan bahan</li>
  <li>Langkah kedua: Campurkan bahan</li>
  <li>Langkah ketiga: Masak dengan api sedang</li>
</ol>

<!-- Unordered List -->
<ul>
  <li>Apel</li>
  <li>Jeruk</li>
  <li>Mangga</li>
</ul>

<!-- Nested List -->
<ul>
  <li>Buah-buahan:
    <ul>
      <li>Apel</li>
      <li>Pisang</li>
    </ul>
  </li>
  <li>Sayuran:
    <ul>
      <li>Wortel</li>
      <li>Bayam</li>
    </ul>
  </li>
</ul>
```

**Penjelasan:**
- `<ol>`: List dengan nomor (1, 2, 3 atau a, b, c atau i, ii, iii).
- `<ul>`: List dengan bullet point.
- `<li>`: List item, harus berada dalam `<ol>` atau `<ul>`.
- List dapat bersarang (nested) untuk membuat hierarki.

---

## 5. Elemen Tabel

### `<table>`, `<thead>`, `<tbody>`, `<tfoot>`, `<tr>`, `<th>`, `<td>`

**Contoh Penerapan:**

```html
<table>
  <thead>
    <tr>
      <th>No</th>
      <th>Nama Produk</th>
      <th>Harga</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Laptop</td>
      <td>Rp 8.000.000</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Mouse</td>
      <td>Rp 150.000</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2"><strong>Total</strong></td>
      <td><strong>Rp 8.150.000</strong></td>
    </tr>
  </tfoot>
</table>
```

**Penjelasan:**
- `<table>`: Container tabel.
- `<thead>`: Bagian header tabel (biasanya berisi judul kolom).
- `<tbody>`: Bagian body tabel (data utama).
- `<tfoot>`: Bagian footer tabel (ringkasan, total).
- `<tr>`: Table row (baris).
- `<th>`: Table header cell (sel header, biasanya bold dan tengah).
- `<td>`: Table data cell (sel data biasa).
- Struktur `<thead>`, `<tbody>`, `<tfoot>` membantu screen reader dan memungkinkan scrolling body tanpa menggeser header.

---

## 6. Elemen Media

### `<iframe allowfullscreen frameborder height src=(YouTube|YouTube-nocookie|Bilibili) width>`
Menyematkan halaman web lain.

**Contoh Penerapan:**

```html
<!-- YouTube -->
<iframe 
  src="https://www.youtube.com/embed/dQw4w9WgXcQ" 
  width="560" 
  height="315" 
  frameborder="0" 
  allowfullscreen>
</iframe>

<!-- YouTube NoCookie (lebih privasi) -->
<iframe 
  src="https://www.youtube-nocookie.com/embed/dQw4w9WgXcQ" 
  width="560" 
  height="315" 
  frameborder="0" 
  allowfullscreen>
</iframe>

<!-- Bilibili -->
<iframe 
  src="https://player.bilibili.com/player.html?bvid=BV1xx411c7mD" 
  width="800" 
  height="600" 
  frameborder="0" 
  allowfullscreen>
</iframe>
```

**Penjelasan:**
- `src`: URL sumber yang diizinkan (hanya domain YouTube, YouTube-nocookie, atau Bilibili).
- `width` & `height`: Dimensi iframe dalam piksel.
- `frameborder`: Menghilangkan border (0 = tanpa border).
- `allowfullscreen`: Memungkinkan video untuk ditampilkan fullscreen.
- YouTube-nocookie tidak menyimpan cookie tracking sampai user menekan play.

---

### `<img src=(https) alt height width>`
Menyematkan gambar.

**Contoh Penerapan:**

```html
<img 
  src="https://example.com/gambar.jpg" 
  alt="Pemandangan pegunungan saat matahari terbenam" 
  width="800" 
  height="600">
```

**Penjelasan:**
- `src`: URL gambar (harus HTTPS).
- `alt`: Teks alternatif yang muncul jika gambar gagal dimuat atau untuk screen reader.
- `width` & `height`: Dimensi gambar. Menentukan dimensi membantu browser mengalokasikan ruang sebelum gambar dimuat, mencegah layout shift.
- **Selalu sertakan `alt`**: Kosongkan (`alt=""`) jika gambar hanya dekoratif, berisi teks deskriptif jika gambar informatif.

---

### `<video src=(https) poster height width>`
Menyematkan video.

**Contoh Penerapan:**

```html
<video 
  src="https://example.com/video.mp4" 
  poster="https://example.com/thumbnail.jpg" 
  width="640" 
  height="360" 
  controls>
  Browser Anda tidak mendukung pemutaran video.
</video>
```

**Penjelasan:**
- `src`: URL file video (harus HTTPS).
- `poster`: Gambar thumbnail yang ditampilkan sebelum video diputar.
- `width` & `height`: Dimensi pemutar video.
- Konten di dalam tag `<video>` (seperti teks "Browser Anda...") adalah fallback untuk browser yang tidak mendukung elemen video.
- Atribut `controls` (meskipun tidak disebutkan dalam daftar, biasanya diperlukan) menambahkan tombol play, pause, volume.

---

## 7. Elemen Semantik Tambahan

### `<em>` vs `<i>`, `<strong>` vs `<b>`
Perbedaan penting dalam penggunaan:

**Contoh Penerapan:**

```html
<!-- <em> untuk penekanan semantik -->
<p>Saya <em>sangat</em> merekomendasikan buku ini. (Penekanan suara)</p>

<!-- <i> untuk teks yang berbeda tanpa penekanan -->
<p>Kata <i>rendezvous</i> berasal dari bahasa Prancis. (Istilah asing)</p>

<!-- <strong> untuk kepentingan tinggi -->
<p><strong>Bahaya:</strong> Tegangan tinggi! (Peringatan kritis)</p>

<!-- <b> untuk menarik perhatian tanpa makna khusus -->
<p>Cari kata <b>penting</b> dalam teks ini. (Kata kunci visual)</p>
```

**Penjelasan:**
- `<em>` dan `<strong>` memiliki makna semantik (penting bagi screen reader dan SEO).
- `<i>` dan `<b>` hanya mengubah tampilan visual tanpa menambahkan makna struktural.

---

## 8. Ringkasan Aturan Keamanan

| Atribut | Izin | Contoh Valid |
|---------|------|-------------|
| `href` | ftp, http, https, mailto, relative | `href="https://site.com"`, `href="page.html"` |
| `src` (iframe) | YouTube, YouTube-nocookie, Bilibili | `src="https://www.youtube.com/embed/..."` |
| `src` (img/video) | https | `src="https://cdn.site.com/img.jpg"` |
| `cite` | http, https, relative | `cite="https://jurnal.com/artikel"` |

Semua aturan ini memastikan konten yang ditampilkan aman, tidak mengeksekusi script berbahaya, dan hanya memuat sumber dari domain terpercaya.

---

## Catatan Penting

1. **Validasi**: Pastikan semua atribut `src` menggunakan protokol HTTPS untuk keamanan.
2. **Aksesibilitas**: Selalu gunakan atribut `alt` pada gambar dan `title` pada link yang memerlukan konteks tambahan.
3. **Semantik**: Pilih elemen berdasarkan makna konten, bukan tampilan visual. Gunakan CSS untuk styling.
4. **Nested Elements**: Beberapa elemen dapat bersarang (nested) untuk membuat struktur yang lebih kompleks, seperti list dalam list atau tabel dengan banyak baris.
5. **Deprecated Elements**: Hindari penggunaan elemen usang seperti `<center>`, `<strike>`, dan `<tt>`. Gunakan alternatif modern yang lebih semantik.

---

*Dokumen ini disusun sebagai panduan referensi untuk penggunaan elemen dan atribut HTML/Markdown yang diperbolehkan.*
