---
"description": "Temukan cara mengelola berkas Excel berukuran besar secara efisien dengan menyesuaikan tingkat kompresi menggunakan Aspose.Cells untuk .NET. Panduan langkah demi langkah ini mencakup semuanya, mulai dari menyiapkan direktori hingga mengukur waktu kompresi, membantu Anda mengoptimalkan ukuran berkas dan meningkatkan kinerja."
"linktitle": "Menyesuaikan Tingkat Kompresi di Buku Kerja"
"second_title": "API Pemrosesan Excel Aspose.Cells .NET"
"title": "Menyesuaikan Tingkat Kompresi di Buku Kerja"
"url": "/id/cells/net/mastering-workbook-operations/adjusting-compression-level/"
"weight": 14
---

## Perkenalan

Mengelola berkas Excel berukuran besar bisa menjadi tantangan tersendiri, terutama dalam hal efisiensi penyimpanan dan transfer. Untungnya, kompresi berkas dapat mengurangi ukuran berkas secara signifikan, sehingga lebih mudah ditangani. Jika Anda menggunakan Aspose.Cells untuk .NET, Anda dapat menyesuaikan tingkat kompresi buku kerja dengan mudah. Panduan ini akan memandu Anda melalui prosesnya langkah demi langkah, dengan memberikan penjelasan yang jelas tentang setiap bagian kode.

## Prasyarat

Sebelum kita masuk ke kode, pastikan Anda memiliki prasyarat berikut:

1. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami potongan kode dengan lebih baik.
2. Pustaka Aspose.Cells: Unduh dan instal pustaka Aspose.Cells dari [Di Sini](https://releases.aspose.com/cells/net/).
3. Visual Studio: Lingkungan pengembangan seperti Visual Studio diperlukan untuk menjalankan kode.
4. .NET Framework: Pastikan proyek Anda disiapkan dengan versi .NET Framework yang kompatibel.

## Mengimpor Paket yang Diperlukan

Untuk memulai, Anda perlu mengimpor paket-paket yang diperlukan ke dalam proyek C# Anda. Tambahkan baris-baris berikut di bagian atas berkas kode Anda:

```csharp
using Aspose.Cells.Rendering;
using Aspose.Cells.WebExtensions;
using System;
```

Paket-paket ini penting untuk bekerja dengan file Excel menggunakan pustaka Aspose.Cells. `Aspose.Cells` namespace berisi semua kelas yang diperlukan untuk memanipulasi file Excel, sementara `Aspose.Cells.Xlsb` menyediakan opsi untuk menyimpan file dalam format XLSB.

## Langkah 1: Tentukan Direktori Sumber dan Output

Pertama, atur direktori tempat file sumber Anda berada dan tempat Anda ingin menyimpan file keluaran:

```csharp
// Tentukan direktori sumber dan keluaran
string sourceDir = "Your Document Directory\\";
string outDir = "Your Document Directory\\";
```

Pastikan untuk mengganti `"Your Document Directory\\"` dengan jalur sebenarnya ke direktori Anda. Ini memastikan program Anda dapat menemukan berkas yang dibutuhkan untuk bekerja.

## Langkah 2: Muat Buku Kerja

Berikutnya, muat buku kerja yang ingin Anda kompres:

```csharp
Workbook workbook = new Workbook(sourceDir + "LargeSampleFile.xlsx");
```

Di sini, kita membuat contoh baru dari `Workbook` kelas dan muat berkas Excel yang sudah ada. Pastikan nama berkas sesuai dengan nama di direktori sumber Anda.

## Langkah 3: Siapkan Opsi Penyimpanan

Sekarang, konfigurasikan opsi penyimpanan untuk buku kerja Anda:

```csharp
XlsbSaveOptions options = new XlsbSaveOptions();
```

Itu `XlsbSaveOptions` Kelas ini memungkinkan Anda menentukan berbagai opsi saat menyimpan buku kerja dalam format XLSB, termasuk tingkat kompresi.

## Langkah 4: Ukur Waktu Kompresi untuk Level 1

Mulailah dengan tingkat kompresi pertama dan ukur waktu yang diperlukan untuk menyimpan buku kerja:

```csharp
options.CompressionType = OoxmlCompressionType.Level1;
var watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_1_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 1 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Cuplikan ini menetapkan jenis kompresi ke Level 1, menyimpan buku kerja, dan mengukur waktu yang telah berlalu.

## Langkah 5: Ukur Waktu Kompresi untuk Level 6

Selanjutnya, uji kinerja dengan kompresi Level 6:

```csharp
options.CompressionType = OoxmlCompressionType.Level6;
watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_6_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 6 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Langkah ini serupa dengan langkah sebelumnya, tetapi dengan tingkat kompresi yang lebih tinggi.

## Langkah 6: Ukur Waktu Kompresi untuk Level 9

Terakhir, evaluasi kinerja dengan tingkat kompresi tertinggi:

```csharp
options.CompressionType = OoxmlCompressionType.Level9;
watch = Stopwatch.StartNew();
workbook.Save(outDir + "LargeSampleFile_level_9_out.xlsb", options);
watch.Stop();
Console.WriteLine("Level 9 Elapsed Time: " + watch.ElapsedMilliseconds + " ms");
```

Langkah ini menetapkan tingkat kompresi ke Level 9, di mana Anda kemungkinan akan melihat pengurangan paling signifikan dalam ukuran file, meskipun prosesnya mungkin memakan waktu lebih lama.

## Langkah 7: Hasil Akhir

Setelah menyelesaikan semua level kompresi, keluarkan pesan yang menunjukkan bahwa proses telah selesai dengan sukses:

```csharp
Console.WriteLine("Compression adjustment completed successfully.");
```

Baris sederhana ini mengonfirmasi bahwa program Anda telah dijalankan tanpa masalah.

## Kesimpulan

Menyesuaikan tingkat kompresi buku kerja Anda menggunakan Aspose.Cells untuk .NET adalah proses sederhana yang dapat menghasilkan peningkatan signifikan dalam ukuran dan kinerja berkas. Dengan mengikuti langkah-langkah yang diuraikan dalam panduan ini, Anda dapat menerapkan kompresi secara efisien di aplikasi Anda, yang akan meningkatkan kemampuan manajemen berkas Excel Anda.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.Cells?  
Aspose.Cells adalah pustaka canggih untuk .NET yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi file Excel tanpa memerlukan Microsoft Excel.

### Bagaimana cara menginstal Aspose.Cells?  
Anda dapat mengunduh dan menginstal Aspose.Cells dari [Situs web Aspose](https://releases.aspose.com/cells/net/).

### Tingkat kompresi apa yang tersedia?  
Aspose.Cells mendukung beberapa tingkat kompresi mulai dari Tingkat 1 (kompresi terendah) hingga Tingkat 9 (kompresi tertinggi).

### Bisakah saya menguji Aspose.Cells secara gratis?  
Ya! Anda bisa mendapatkan uji coba gratis Aspose.Cells. [Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan untuk Aspose.Cells?  
Untuk pertanyaan atau dukungan apa pun, kunjungi forum dukungan Aspose [Di Sini](https://forum.aspose.com/c/cells/9).