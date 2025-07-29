---
"description": "Temukan cara mudah menyesuaikan orientasi halaman berkas PDF menggunakan Aspose.PDF untuk .NET. Panduan langkah demi langkah ini memberikan petunjuk yang jelas tentang cara memuat, memutar, dan menyimpan dokumen Anda."
"linktitle": "Ubah Orientasi Halaman PDF"
"second_title": "Referensi API Aspose.PDF untuk .NET"
"title": "Ubah Orientasi Halaman PDF"
"url": "/id/pdf/net/master-pdf-page-management/change-pdf-page-orientation/"
"weight": 10
---

## Perkenalan

Pernahkah Anda menemukan berkas PDF yang orientasi halamannya salah total? Baik itu dokumen yang dipindai secara tidak benar atau dokumen yang hanya membutuhkan tata letak berbeda, menyesuaikan orientasi dapat membuat perbedaan besar. Untungnya, Aspose.PDF untuk .NET menawarkan cara yang canggih dan mudah digunakan untuk memanipulasi berkas PDF, termasuk mengubah orientasi halaman. Dalam panduan ini, kami akan memandu Anda melalui prosesnya langkah demi langkah, baik Anda ingin beralih dari potret ke lanskap atau sebaliknya.

## Prasyarat

Sebelum kita membahas detailnya, pastikan Anda telah menyiapkan hal-hal berikut:

- Aspose.PDF untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.PDF. Jika Anda belum melakukannya, Anda dapat [unduh di sini](https://releases.aspose.com/pdf/net/).
- Lingkungan Pengembangan .NET: Anda dapat menggunakan Visual Studio, JetBrains Rider, atau IDE lain yang Anda sukai untuk pengembangan .NET.
- Pengetahuan Dasar C#: Keakraban dengan C# akan membantu Anda mengikutinya dengan lebih mudah.
- Berkas PDF: Siapkan contoh berkas PDF untuk pengujian. Anda dapat membuatnya sendiri atau mengunduh contoh secara daring.

Jika Anda baru memulai, pertimbangkan untuk mencoba Aspose.PDF dengan [lisensi sementara gratis](https://purchase.aspose.com/temporary-license/) sebelum memutuskan untuk [beli versi lengkapnya](https://purchase.aspose.com/buy).

## Mengimpor Ruang Nama

Untuk memanipulasi halaman PDF, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek C# Anda terlebih dahulu. Tambahkan baris berikut di bagian atas berkas kode Anda:

```csharp
using System.IO;
using Aspose.Pdf;
```

Sekarang setelah semuanya disiapkan, mari kita mulai!

## Langkah 1: Muat Dokumen PDF

Langkah pertama adalah memuat berkas PDF yang ingin Anda ubah. Gunakan `Document` kelas dari namespace Aspose.PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(Path.Combine(dataDir, "input.pdf"));
```

Pastikan untuk mengganti `"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke berkas PDF Anda.

## Langkah 2: Ulangi Setiap Halaman

Selanjutnya, kita akan melakukan pengulangan pada setiap halaman dalam dokumen PDF. Ini memungkinkan kita untuk menerapkan perubahan orientasi ke semua halaman:

```csharp
foreach (Page page in doc.Pages)
{
    // Memanipulasi setiap halaman
}
```

## Langkah 3: Akses MediaBox Halaman

Setiap halaman PDF memiliki `MediaBox` yang menentukan batas-batasnya. Kita perlu mengaksesnya untuk memeriksa orientasi saat ini dan melakukan penyesuaian:

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

Itu `MediaBox` menyediakan dimensi halaman, termasuk lebar dan tinggi.

## Langkah 4: Tukar Lebar dan Tinggi

Untuk mengubah orientasi halaman, kita akan menukar nilai lebar dan tinggi. Penyesuaian ini akan mengubah dimensi halaman:

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Di sini, kami menghitung dimensi baru dan memposisikan ulang sudut kiri bawah (`LLY`) sebagaimana mestinya.

## Langkah 5: Perbarui MediaBox dan CropBox

Sekarang setelah kita memiliki dimensi baru, kita akan menerapkan perubahan ini ke `MediaBox` Dan `CropBox` untuk memastikan halaman ditampilkan dengan benar:

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

## Langkah 6: Putar Halaman

Untuk menyelesaikan perubahan orientasi, kita akan memutar halaman. Hal ini mudah dilakukan dengan Aspose.PDF:

```csharp
page.Rotate = Rotation.on90; // Putar 90 derajat
```

Garis ini secara efektif membalik halaman ke orientasi yang diinginkan.

## Langkah 7: Simpan PDF Output

Setelah mengubah orientasi semua halaman, simpan dokumen yang diperbarui ke file baru:

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

Pastikan untuk memberikan nama file baru untuk menghindari penimpaan dokumen asli.

## Kesimpulan

Dan begitulah! Mengubah orientasi halaman berkas PDF menggunakan Aspose.PDF untuk .NET adalah proses yang mudah. Dengan memuat dokumen, mengulang halaman, memperbarui MediaBox, dan menyimpan berkas, Anda dapat dengan mudah menyesuaikan tata letak sesuai kebutuhan. Baik Anda sedang mengoreksi dokumen yang dipindai dengan buruk atau memformat halaman untuk presentasi, panduan ini akan membantu Anda menyelesaikan pekerjaan secara efisien.

## Pertanyaan yang Sering Diajukan

### Bisakah saya memutar halaman tertentu, bukan semua halaman dalam PDF?  
Ya, Anda dapat memodifikasi loop untuk menargetkan halaman tertentu berdasarkan indeksnya alih-alih mengulangi semua halaman.

### Apakah yang `MediaBox`?  
Itu `MediaBox` mendefinisikan ukuran dan bentuk halaman dalam berkas PDF, menentukan di mana konten ditempatkan.

### Apakah Aspose.PDF untuk .NET berfungsi dengan format file lain?  
Ya, Aspose.PDF dapat menangani berbagai format file, termasuk HTML, XML, XPS, dan banyak lagi.

### Apakah ada versi gratis Aspose.PDF untuk .NET?  
Ya, Anda bisa memulai dengan [uji coba gratis](https://releases.aspose.com/) atau meminta [lisensi sementara](https://purchase.aspose.com/temporary-license/).

### Bisakah saya membatalkan perubahan yang sudah disimpan?  
Setelah Anda menyimpan dokumen, perubahannya bersifat permanen. Sebaiknya Anda membuat salinannya atau menyimpan cadangan berkas aslinya.