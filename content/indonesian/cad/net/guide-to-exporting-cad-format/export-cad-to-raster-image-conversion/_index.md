---
"description": "Pelajari cara mengonversi tata letak CAD ke berbagai format gambar raster secara efisien menggunakan Aspose.CAD untuk .NET. Panduan komprehensif ini memandu Anda melalui prosesnya dengan kode yang jelas."
"linktitle": "Konversi Ekspor CAD ke Gambar Raster"
"second_title": "Aspose.CAD .NET - Format Berkas CAD dan BIM"
"title": "Konversi Ekspor CAD ke Gambar Raster dengan Aspose.CAD untuk .NET"
"url": "/id/cad/net/guide-to-exporting-cad-format/export-cad-to-raster-image-conversion/"
"weight": 10
---

## Perkenalan

Ingin mengonversi tata letak CAD ke format gambar raster dengan mudah menggunakan Aspose.CAD untuk .NET? Panduan langkah demi langkah ini dirancang untuk membantu Anda menavigasi prosesnya, lengkap dengan cuplikan kode ringkas untuk pengalaman yang lancar. Baik Anda seorang pengembang berpengalaman maupun pemula, tutorial ini memberikan wawasan berharga untuk semua tingkat keahlian.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

- Aspose.CAD untuk Pustaka .NET: Unduh dan instal pustaka dari [Situs web Aspose.CAD](https://releases.aspose.com/cad/net/).
- File Gambar CAD: Miliki file gambar CAD Anda (misalnya, `conic_pyramid.dxf`) siap untuk dikonversi.

## Mengimpor Namespace yang Diperlukan

Di proyek .NET Anda, Anda perlu mengimpor namespace yang diperlukan untuk menggunakan fungsi Aspose.CAD. Tambahkan kode berikut di awal kode Anda:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.CAD;
```

## Langkah 1: Muat Gambar CAD Anda

Pertama, tentukan direktori dan muat file CAD Anda ke dalam instance Gambar:

```csharp
string MyDir = "Your Document Directory";
string sourceFilePath = MyDir + "conic_pyramid.dxf";

// Muat gambar CAD
using (var image = Image.Load(sourceFilePath))
{
    // Lanjutkan ke langkah berikutnya
}
```

## Langkah 2: Buat Opsi Rasterisasi

Selanjutnya, atur opsi rasterisasi, tentukan dimensi yang diinginkan untuk gambar keluaran:

```csharp
// Inisialisasi CadRasterizationOptions
var rasterizationOptions = new CadRasterizationOptions
{
    PageWidth = 500,
    PageHeight = 500
};
```

## Langkah 3: Tentukan Lapisan untuk Konversi

Jika Anda ingin mengonversi lapisan tertentu, tambahkan ke opsi rasterisasi Anda:

```csharp
// Tentukan lapisan yang akan dikonversi
rasterizationOptions.Layers = new [] { "LayerA" };
```

## Langkah 4: Siapkan Opsi Ekspor JPEG

Sekarang, buat opsi untuk format gambar yang ingin Anda ekspor (JPEG dalam kasus ini):

```csharp
// Buat JpegOptions untuk mengekspor
var options = new JpegOptions
{
    VectorRasterizationOptions = rasterizationOptions
};
```

## Langkah 5: Ekspor ke Format JPEG

Terakhir, simpan gambar yang dikonversi:

```csharp
// Tentukan jalur file keluaran dan simpan gambar
string outputFilePath = MyDir + "CADLayersToRasterImageFormats_out.jpg";
image.Save(outputFilePath, options);
```

## Fitur Tambahan: Konversi Semua Lapisan

Untuk mengonversi semua lapisan pada gambar CAD Anda, Anda dapat menerapkan metode seperti ini:

```csharp
void ConvertAllLayersToRasterImageFormats()
{
    // Ulangi melalui lapisan dan simpan masing-masing sebagai file JPEG terpisah
    // Kode implementasi Anda di sini
}
```

## Kesimpulan

Selamat! Anda telah mempelajari cara efektif mengonversi tata letak CAD ke format gambar raster menggunakan Aspose.CAD untuk .NET. Panduan ini menawarkan pendekatan langsung yang cocok bagi pengembang yang menginginkan konversi CAD yang efisien.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekspor ke format gambar yang berbeda?

Tentu saja! Cukup tukar saja `JpegOptions` dengan pilihan format lainnya, seperti `PngOptions` atau `BmpOptions`, tergantung pada kebutuhan Anda.

### Apakah versi uji coba tersedia?

Ya, Anda dapat mengunduh versi uji coba untuk menjelajahi fungsionalitas dengan mengikuti ini [link](https://releases.aspose.com/cad/net/).

### Di mana saya dapat menemukan dukungan untuk Aspose.CAD?

Untuk dukungan komunitas, lihat Aspose.CAD [forum](https://forum.aspose.com/c/cad/19), atau pertimbangkan untuk membeli lisensi untuk bantuan yang lebih khusus.

### Apakah lisensi sementara memungkinkan?

Ya, lisensi sementara tersedia; Anda dapat memintanya [Di Sini](https://purchase.conholdate.com/temporary-license/).

### Di mana saya dapat mengakses dokumentasi terperinci?

Kunjungi dokumentasi lengkapnya [Di Sini](https://reference.aspose.com/cad/net/) untuk informasi lebih lanjut.