---
"description": "Temukan cara mengelola kumpulan data besar secara efisien di Excel dengan memanfaatkan pustaka Aspose.Cells untuk .NET. Panduan ini memberikan pendekatan langkah demi langkah untuk mengidentifikasi jumlah baris dan kolom maksimum yang didukung oleh format berkas XLS dan XLSX."
"linktitle": "Temukan Baris dan Kolom Maksimum dalam Format XLS dan XLSX"
"second_title": "API Pemrosesan Excel Aspose.Cells .NET"
"title": "Temukan Baris dan Kolom Maksimum dalam Format XLS dan XLSX"
"url": "/id/cells/net/mastering-workbook-settings/find-maximum-rows-and-columns/"
"weight": 11
---

## Perkenalan

Mengelola kumpulan data besar di Excel bisa jadi menantang, terutama terkait batasan berbagai format file. Tutorial ini akan memandu Anda menggunakan pustaka Aspose.Cells for .NET untuk menentukan jumlah baris dan kolom maksimum yang didukung oleh format XLS (Excel 97-2003) dan XLSX (Excel 2007 dan yang lebih baru). Setelah menyelesaikan tutorial ini, Anda akan mampu menangani tugas-tugas terkait Excel secara efisien.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. [Kerangka .NET](https://dotnet.microsoft.com/en-us/download) atau [.NET Core](https://dotnet.microsoft.com/en-us/download) terinstal pada sistem Anda.
2. [Aspose.Cells untuk .NET](https://releases.aspose.com/cells/net/) perpustakaan yang diunduh dan direferensikan dalam proyek Anda (Anda juga dapat menginstalnya melalui [NuGet](https://www.nuget.org/packages/Aspose.Cells/)).

## Mengimpor Paket yang Diperlukan

Tambahkan pernyataan using berikut di bagian atas file C# Anda untuk mengimpor paket yang diperlukan dari pustaka Aspose.Cells:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Langkah 1: Baris dan Kolom Maksimum untuk Format XLS

Mari kita mulai dengan mencari jumlah baris dan kolom maksimum yang didukung oleh format XLS.

```csharp
// Cetak pesan tentang format XLS.
Console.WriteLine("Maximum Rows and Columns supported by XLS format:");

// Buat buku kerja dalam format XLS.
Workbook wb = new Workbook(FileFormatType.Excel97To2003);

// Ambil baris dan kolom maksimum.
int maxRows = wb.Settings.MaxRow + 1;
int maxCols = wb.Settings.MaxColumn + 1;

// Tampilkan hasilnya.
Console.WriteLine("Maximum Rows: " + maxRows);
Console.WriteLine("Maximum Columns: " + maxCols);
Console.WriteLine();
```

1. Cetak pesan untuk menunjukkan bahwa kami bekerja dengan format XLS.
2. Membuat sebuah `Workbook` contoh untuk format XLS menggunakan `FileFormatType.Excel97To2003`.
3. Dapatkan baris dan kolom maksimum dengan `wb.Settings.MaxRow` Dan `wb.Settings.MaxColumn`, menambahkan 1 karena ini berbasis nol.
4. Keluarkan baris dan kolom maksimum ke konsol.

## Langkah 2: Baris dan Kolom Maksimum untuk Format XLSX

Selanjutnya, kita akan menjelajahi baris dan kolom maksimum yang didukung oleh format XLSX.

```csharp
// Cetak pesan tentang format XLSX.
Console.WriteLine("Maximum Rows and Columns supported by XLSX format:");

// Buat buku kerja dalam format XLSX.
wb = new Workbook(FileFormatType.Xlsx);

// Ambil baris dan kolom maksimum.
maxRows = wb.Settings.MaxRow + 1;
maxCols = wb.Settings.MaxColumn + 1;

// Tampilkan hasilnya.
Console.WriteLine("Maximum Rows: " + maxRows);
Console.WriteLine("Maximum Columns: " + maxCols);
```

1. Cetak pesan yang menunjukkan kami bekerja dengan format XLSX.
2. Membuat sebuah `Workbook` contoh untuk format XLSX menggunakan `FileFormatType.Xlsx`.
3. Ambil dan keluarkan baris dan kolom maksimum seperti sebelumnya.

## Langkah 3: Menampilkan Pesan Sukses

Setelah menjalankan langkah-langkahnya, mari kita tandai keberhasilan.

```csharp
Console.WriteLine("Execution completed successfully: Maximum Rows and Columns retrieval for both formats.");
```

## Kesimpulan

Dalam tutorial ini, Anda mempelajari cara menggunakan pustaka Aspose.Cells for .NET untuk menemukan jumlah baris dan kolom maksimum yang didukung oleh format berkas XLS dan XLSX. Memahami batasan ini sangat penting untuk manajemen data Excel yang efektif, memastikan kumpulan data Anda selaras dengan kemampuan format.

## Pertanyaan yang Sering Diajukan

### Berapa jumlah baris maksimum yang didukung oleh format XLS?
Jumlah baris maksimum yang didukung oleh format XLS adalah 65.536.

### Berapa jumlah maksimum kolom yang didukung oleh format XLS?
Jumlah maksimum kolom yang didukung oleh format XLS adalah 256.

### Berapa jumlah baris maksimum yang didukung oleh format XLSX?
Jumlah baris maksimum yang didukung oleh format XLSX adalah 1.048.576.

### Berapa jumlah maksimum kolom yang didukung oleh format XLSX?
Jumlah kolom maksimum yang didukung oleh format XLSX adalah 16.384.

### Dapatkah saya menggunakan pustaka Aspose.Cells untuk .NET dengan format file Excel lainnya?
Ya, Aspose.Cells untuk .NET mendukung berbagai format file, termasuk XLS, XLSX, ODS, dan lainnya. Periksa [dokumentasi](https://reference.aspose.com/cells/net/) untuk rincian tentang fitur dan fungsi yang didukung.