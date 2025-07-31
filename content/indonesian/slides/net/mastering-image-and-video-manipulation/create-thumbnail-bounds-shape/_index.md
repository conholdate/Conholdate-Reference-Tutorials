---
"description": "Pelajari cara menggunakan Aspose.Slides for .NET untuk membuat gambar mini dengan batas yang ditentukan untuk bentuk dalam presentasi PowerPoint. Panduan lengkap ini menyediakan petunjuk langkah demi langkah."
"linktitle": "Membuat Thumbnail dengan Batas untuk Bentuk di Aspose.Slides"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Membuat Thumbnail dengan Batasan untuk Bentuk di Aspose.Slides"
"url": "/id/slides/net/mastering-image-and-video-manipulation/create-thumbnail-bounds-shape/"
"weight": 10
---

## Perkenalan

Jika Anda seorang pengembang .NET yang mencari cara efisien untuk membuat gambar mini dengan batas untuk bentuk dalam presentasi PowerPoint, Aspose.Slides for .NET adalah alat yang sangat baik untuk dipertimbangkan. Pustaka canggih ini menyederhanakan manipulasi berkas PowerPoint, memungkinkan Anda mengekstrak dan mengolah data penting dengan mudah. Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan gambar mini dengan batas untuk suatu bentuk.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Slides untuk Pustaka .NET: Unduh dan instal dari [Situs Aspose](https://releases.aspose.com/slides/net/).
2. Jalur File: Ganti `"Your Documents Directory"` dalam kode dengan jalur sebenarnya ke dokumen Anda.

## Impor Namespace yang Diperlukan

Untuk memanfaatkan fitur Aspose.Slides, mulailah dengan mengimpor namespace yang diperlukan di awal proyek Anda:

```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```

## Langkah 1: Membuat Instansiasi Kelas Presentasi

Pertama, Anda perlu menginisialisasi `Presentation` kelas untuk mewakili berkas PowerPoint Anda:

```csharp
string dataDir = "Your Documents Directory\\";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Objek presentasi Anda sekarang siap untuk dimanipulasi.
}
```

Menggunakan `using` pernyataan di sini memastikan bahwa sumber daya dilepaskan dengan tepat setelah Anda selesai.

## Langkah 2: Buat Gambar Miniatur dengan Batas Bentuk

Berikutnya, Anda akan membuat gambar mini suatu bentuk dalam presentasi Anda dengan batasan yang ditentukan:

```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // Bitmap sekarang berisi gambar mini dalam batasan yang ditentukan.
}
```

Dalam cuplikan ini, `ShapeThumbnailBounds.Appearance` Menentukan batas tampilan bentuk yang Anda inginkan. Sesuaikan parameter (1, 1) untuk lebar dan tinggi sesuai kebutuhan berdasarkan kebutuhan keluaran Anda.

## Langkah 3: Simpan Gambar Miniatur ke Disk

Terakhir, simpan gambar mini yang dihasilkan dalam format yang disukai, seperti PNG:

```csharp
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```

Di sini, Anda dapat menyesuaikan nama file dan format menurut kebutuhan proyek Anda.

Selamat! Anda telah berhasil membuat thumbnail dengan batas untuk sebuah bentuk menggunakan Aspose.Slides for .NET. Proses ini mudah dan dapat dengan mudah diintegrasikan ke dalam aplikasi .NET Anda.

## Kesimpulan

Aspose.Slides untuk .NET menyederhanakan proses pembuatan dan pengelolaan presentasi PowerPoint, membekali pengembang dengan alat-alat canggih untuk membuat gambar mini dan banyak lagi. Dengan mengikuti panduan ini, Anda telah mempelajari langkah-langkah penting untuk menggunakan pustaka ini secara efisien dalam proyek Anda.

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Slides kompatibel dengan kerangka kerja .NET terbaru?

Ya, Aspose.Slides sering diperbarui untuk mendukung versi terbaru kerangka .NET.

### Dapatkah saya menggunakan Aspose.Slides untuk proyek komersial?

Tentu saja! Aspose.Slides menawarkan berbagai pilihan lisensi yang cocok untuk penggunaan individu dan komersial. Periksa [Di Sini](https://purchase.aspose.com/buy) untuk informasi lebih lanjut.

### Apakah ada uji coba gratis yang tersedia?

Ya! Anda dapat menjelajahi fitur-fitur Aspose.Slides dengan uji coba gratis yang tersedia. [Di Sini](https://releases.aspose.com/).

### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Slides?

Untuk bantuan, kunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) untuk terhubung dengan komunitas dan pengembang berpengalaman.

### Bisakah saya memperoleh lisensi sementara untuk Aspose.Slides?

Ya, lisensi sementara untuk proyek jangka pendek dapat diperoleh [Di Sini](https://purchase.aspose.com/temporary-license/).