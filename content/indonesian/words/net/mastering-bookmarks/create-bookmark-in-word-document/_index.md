---
"description": "Pelajari cara menyempurnakan dokumen Word Anda dengan membuat dan mengelola bookmark menggunakan Aspose.Words untuk .NET. Panduan tutorial langkah demi langkah ini."
"linktitle": "Buat Bookmark di Dokumen Word dengan Aspose.Words untuk .NET"
"second_title": "API Pemrosesan Dokumen Aspose.Words"
"title": "Buat Bookmark di Dokumen Word dengan Aspose.Words untuk .NET"
"url": "/id/words/net/mastering-bookmarks/create-bookmark-in-word-document/"
"weight": 10
---

## Perkenalan

Menavigasi dokumen besar memang sulit, tetapi bookmark akan mempermudahnya! Tutorial ini akan memandu Anda membuat bookmark di dokumen Word menggunakan Aspose.Words untuk .NET. Anda akan mempelajari langkah demi langkah cara menyiapkan dokumen, menambahkan bookmark, dan menyimpannya sebagai PDF. Ayo mulai!

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Words untuk Pustaka .NET: Unduh dan instal dari [Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Gunakan Visual Studio atau IDE apa pun yang kompatibel dengan .NET.
3. Pengetahuan Dasar C#: Keakraban dengan konsep pemrograman C# akan sangat membantu.

## Mengimpor Namespace

Pertama, impor namespace yang diperlukan untuk bekerja dengan Aspose.Words:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Siapkan Dokumen dan DocumentBuilder

Buat dokumen baru dan inisialisasi `DocumentBuilder`, yang memungkinkan Anda menambahkan konten dan penanda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Buat Bookmark Utama

Untuk membuat bookmark, Anda perlu menentukan titik awal dan titik akhirnya. Berikut cara membuat bookmark bernama "Bookmark Saya":

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside the main bookmark.");
```
- `StartBookmark`: Menandai awal penanda buku.
- `Writeln`: Menambahkan teks dalam penanda buku.

## Langkah 3: Buat Bookmark Bersarang

Anda dapat menumpuk bookmark untuk pengaturan yang lebih baik. Berikut cara menambahkan "Bookmark Bersarang" di dalam "Bookmark Saya":

```csharp
builder.StartBookmark("Nested Bookmark");
builder.Writeln("Text inside the nested bookmark.");
builder.EndBookmark("Nested Bookmark");
```
- Nesting memungkinkan Anda membuat struktur hierarkis. 
- `EndBookmark`: Menutup penanda saat ini.

## Langkah 4: Tambahkan Teks di Luar Bookmark Bersarang

Setelah membuat penanda bersarang, lanjutkan menambahkan konten dalam penanda utama:

```csharp
builder.Writeln("Text after the nested bookmark.");
builder.EndBookmark("My Bookmark");
```
Ini memastikan bahwa penanda utama mencakup penanda bersarang dan teks tambahan apa pun.

## Langkah 5: Konfigurasikan Opsi Penyimpanan PDF

Untuk menyertakan penanda buku dalam PDF, konfigurasikan opsi penyimpanan:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);
```
- `PdfSaveOptions`: Menentukan bagaimana dokumen disimpan sebagai PDF.
- `BookmarksOutlineLevels`: Mengatur hierarki penanda dalam PDF.

## Langkah 6: Simpan Dokumen

Terakhir, simpan dokumen sebagai PDF:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```
Itu `Save` metode menyimpan dokumen dalam format dan lokasi yang ditentukan, lengkap dengan penanda.

## Kesimpulan

Membuat bookmark di dokumen Word dengan Aspose.Words untuk .NET itu mudah dan meningkatkan navigasi dokumen. Baik Anda membuat laporan, eBook, atau mengelola dokumen yang ekstensif, bookmark sangatlah berharga. Ikuti tutorial ini, dan Anda akan memiliki PDF yang tertata rapi dan penuh bookmark dalam waktu singkat!

## Pertanyaan yang Sering Diajukan

### Bisakah saya membuat beberapa penanda pada tingkat yang berbeda?
Ya! Anda dapat membuat beberapa penanda dan menentukan hierarkinya saat menyimpan sebagai PDF.

### Bagaimana cara memperbarui teks penanda buku?
Menggunakan `DocumentBuilder.MoveToBookmark` untuk menavigasi ke penanda dan memperbarui teks.

### Apakah mungkin untuk menghapus penanda buku?
Tentu saja! Gunakan `Bookmarks.Remove` metode dengan menentukan nama penanda.

### Bisakah saya membuat penanda buku dalam format lain selain PDF?
Ya, Aspose.Words mendukung bookmark dalam format seperti DOCX, HTML, dan EPUB.

### Bagaimana saya bisa memastikan penanda buku muncul dengan benar dalam PDF?
Mendefinisikan `BookmarksOutlineLevels` dengan benar di `PdfSaveOptions` untuk memastikan penanda buku disertakan dalam kerangka PDF.