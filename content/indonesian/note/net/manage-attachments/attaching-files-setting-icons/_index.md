---
"description": "Pelajari langkah demi langkah cara melampirkan file dan mengatur ikon kustom di dokumen Microsoft OneNote menggunakan Aspose.Note untuk .NET. Tingkatkan aplikasi .NET Anda dengan fitur manajemen dokumen dan kustomisasi yang mudah."
"linktitle": "Lampirkan File dan Atur Ikon di Aspose.Note"
"second_title": "Aspose.Note .NET API"
"title": "Melampirkan File dan Mengatur Ikon di Aspose.Note untuk .NET"
"url": "/id/note/net/manage-attachments/attaching-files-setting-icons/"
"weight": 10
---

## Perkenalan

Aspose.Note untuk .NET adalah pustaka canggih yang dirancang bagi pengembang untuk membuat, memanipulasi, dan mengonversi berkas Microsoft OneNote secara terprogram. Fitur unggulan pustaka ini adalah kemampuannya untuk melampirkan berkas ke dokumen OneNote dan menyesuaikan ikonnya. Dalam panduan ini, kita akan membahas cara memanfaatkan Aspose.Note untuk .NET untuk melampirkan berkas dan mengatur ikon kustom dengan mudah, yang akan memperkaya fungsionalitas dokumen OneNote Anda.

## Prasyarat

Sebelum menerapkan solusinya, pastikan Anda memiliki hal berikut:

- Lingkungan Pengembangan: Visual Studio atau IDE serupa yang dikonfigurasi untuk pengembangan .NET.
- Instalasi Perpustakaan: Instal [Aspose.Note untuk .NET](https://releases.aspose.com/words/net/) perpustakaan.
- Pengetahuan Pemrograman: Pemahaman dasar tentang C#.

## Mengimpor Namespace yang Diperlukan

Tambahkan namespace ini ke proyek Anda untuk fungsionalitas penting:

```csharp
using System.IO;
using Aspose.Note;
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
```

Berikut ini adalah langkah-langkah implementasinya secara terperinci, langkah demi langkah.

## Langkah 1: Buat Dokumen OneNote Baru

Inisialisasi dokumen OneNote baru menggunakan `Document` kelas.

```csharp
Document doc = new Document();
```

## Langkah 2: Tambahkan Halaman Baru

Tambahkan halaman ke dokumen untuk mengatur catatan dan lampiran Anda.

```csharp
Aspose.Note.Page page = new Aspose.Note.Page(doc);
```

## Langkah 3: Siapkan Garis Besar

Membuat sebuah `Outline` objek, yang berfungsi sebagai wadah untuk elemen di halaman OneNote Anda.

```csharp
Outline outline = new Outline(doc);
```

## Langkah 4: Inisialisasi Elemen Garis Besar

Sebuah `OutlineElement` akan berisi lampiran dan ikon terkait.

```csharp
OutlineElement outlineElem = new OutlineElement(doc);
```

## Langkah 5: Lampirkan File dan Tentukan Ikonnya

Tentukan berkas yang akan dilampirkan dan berikan ikonnya.

```csharp
string dataDir = "Your Document Directory";

using (var stream = File.OpenRead(dataDir + "icon.jpg"))
{
    AttachedFile attachedFile = new AttachedFile(doc, dataDir + "attachment.txt", stream, ImageFormat.Jpeg);
    outlineElem.AppendChildLast(attachedFile);
}
```

## Langkah 6: Merakit Struktur Dokumen

Tambahkan `OutlineElement` ke `Outline`, dan `Outline` ke `Page`.

```csharp
outline.AppendChildLast(outlineElem);
page.AppendChildLast(outline);
```

## Langkah 7: Tambahkan Halaman ke Dokumen

Terakhir, sertakan halaman tersebut dalam dokumen OneNote Anda.

```csharp
doc.AppendChildLast(page);
```

## Langkah 8: Simpan Dokumen

Ekspor dokumen Anda yang telah diperbarui dengan lampiran file dan ikon.

```csharp
dataDir = dataDir + "AttachFileAndSetIcon_out.one";
doc.Save(dataDir);
```

## Kesimpulan

Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda dapat dengan mudah melampirkan file dan mengatur ikon kustom di dokumen OneNote menggunakan Aspose.Note untuk .NET. Fungsionalitas ini dapat meningkatkan pengaturan dokumen dan pengalaman pengguna secara signifikan, menjadikan aplikasi Anda lebih tangguh dan kaya fitur.

## Pertanyaan yang Sering Diajukan

### Bisakah beberapa file dilampirkan ke satu catatan?
Ya, Anda dapat melampirkan beberapa file dengan mengulangi proses lampiran untuk setiap file.

### Format gambar apa yang didukung untuk ikon?
Aspose.Note mendukung format JPEG, PNG, BMP, dan GIF untuk ikon lampiran.

### Apakah mungkin untuk melampirkan file secara dinamis dari URL eksternal?
Anda dapat mengunduh file menggunakan pustaka .NET seperti `HttpClient` lalu lampirkan menggunakan Aspose.Note.

### Apakah ada batasan ukuran file untuk lampiran?
Tidak ada batasan ukuran eksplisit yang diberlakukan oleh Aspose.Note, tetapi pastikan sumber daya sistem Anda dapat menangani file besar.

### Bisakah ikon diubah ukurannya sebelum ditetapkan?
Ya, Anda dapat memanipulasi gambar ikon menggunakan .NET `System.Drawing` perpustakaan sebelum melampirkannya.

Untuk bantuan lebih lanjut, jelajahi [dokumentasi](https://reference.aspose.com/words/net/) atau hubungi [Aspose dukungan](https://forum.aspose.com/c/words/8).