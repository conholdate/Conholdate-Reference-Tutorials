---
"description": "Pelajari cara mudah mengonversi setiap halaman dokumen Word menjadi gambar PNG individual menggunakan Aspose.Words untuk .NET. Panduan ini menyediakan petunjuk langkah demi langkah, termasuk contoh kode."
"linktitle": "Panggilan Balik Penyimpanan Halaman di Dokumen Word"
"second_title": "API Pemrosesan Dokumen Aspose.Words"
"title": "Panggilan Balik Penyimpanan Halaman di Dokumen Word"
"url": "/id/words/net/guide-to-image-save-options/page-saving-callback-word-document/"
"weight": 10
---

## Perkenalan

Pernahkah Anda perlu mengonversi setiap halaman dokumen Word menjadi gambar individual? Baik Anda ingin membuat thumbnail untuk pratinjau atau memecah laporan panjang menjadi visual yang mudah dipahami, Aspose.Words untuk .NET menjadikan tugas ini mudah dan efisien. Dalam panduan ini, kami akan memandu Anda melalui proses pengaturan panggilan balik penyimpanan halaman untuk menyimpan setiap halaman dokumen Anda sebagai gambar PNG. Mari kita mulai!

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Words untuk .NET: Unduh dan instal dari [Di Sini](https://releases.aspose.com/words/net/).
2. Visual Studio: Versi apa pun akan berfungsi, tetapi kami akan menggunakan Visual Studio 2019 untuk panduan ini.
3. Pengetahuan Dasar C#: Keakraban dengan C# akan membantu Anda mengikutinya dengan lancar.

## Langkah 1: Impor Namespace yang Diperlukan

Pertama, kita perlu mengimpor namespace yang diperlukan. Ini memungkinkan kita mengakses kelas dan metode yang diperlukan tanpa perlu mengetikkan namespace lengkap setiap kali.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 2: Tentukan Direktori Dokumen Anda

Selanjutnya, atur jalur ke direktori dokumen Anda. Di sinilah dokumen Word input Anda berada dan gambar output akan disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 3: Muat Dokumen Anda

Sekarang, mari kita muat dokumen yang ingin Anda proses. Pastikan dokumen Anda, yang bernama "Rendering.docx", berada di direktori yang ditentukan.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 4: Konfigurasikan Opsi Penyimpanan Gambar

Kami akan mengatur opsi untuk menyimpan gambar, dengan menentukan bahwa kami ingin menyimpan halaman sebagai file PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

Di Sini, `PageSet` mendefinisikan rentang halaman yang akan disimpan, dan `PageSavingCallback` menunjuk ke kelas panggilan balik kustom kita.

## Langkah 5: Terapkan Panggilan Balik Penyimpanan Halaman

Sekarang, kita perlu mengimplementasikan kelas panggilan balik yang menangani bagaimana setiap halaman disimpan.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

Kelas ini mengimplementasikan `IPageSavingCallback` antarmuka. Di dalam `PageSaving` metode ini, kami menentukan pola penamaan untuk setiap halaman yang disimpan.

## Langkah 6: Simpan Dokumen sebagai Gambar

Terakhir, kami menyimpan dokumen menggunakan opsi yang dikonfigurasi.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Kesimpulan

Selamat! Anda telah berhasil mengatur panggilan balik penyimpanan halaman untuk menyimpan setiap halaman dokumen Word sebagai gambar PNG terpisah menggunakan Aspose.Words untuk .NET. Teknik ini sangat berguna untuk berbagai aplikasi, mulai dari membuat pratinjau halaman hingga menghasilkan gambar halaman individual untuk laporan.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menyimpan halaman dalam format selain PNG?
Ya! Anda dapat menyimpan halaman dalam format seperti JPEG, BMP, dan TIFF dengan mengubah `SaveFormat` di dalam `ImageSaveOptions`.

### Bagaimana cara menyimpan halaman tertentu saja?
Untuk menyimpan halaman tertentu, sesuaikan `PageSet` parameter dalam `ImageSaveOptions` untuk menyertakan halaman yang diinginkan saja.

### Apakah mungkin untuk menyesuaikan kualitas gambar?
Tentu saja! Anda dapat mengontrol kualitas gambar keluaran dengan mengatur properti seperti `ImageSaveOptions.JpegQuality`.

### Bagaimana saya dapat menangani dokumen besar secara efisien?
Untuk dokumen besar, pertimbangkan untuk memproses halaman secara bertahap untuk mengelola penggunaan memori secara efektif.

### Di mana saya dapat menemukan informasi lebih lanjut tentang Aspose.Words untuk .NET?
Untuk panduan dan contoh yang lengkap, lihat [Dokumentasi Aspose.Words](https://reference.aspose.com/words/net/).