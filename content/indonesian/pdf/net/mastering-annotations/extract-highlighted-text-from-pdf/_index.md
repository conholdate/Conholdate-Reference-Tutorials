---
"description": "Maksimalkan potensi dokumen PDF Anda dengan mempelajari cara mengekstrak teks yang disorot menggunakan Aspose.PDF untuk .NET. Panduan komprehensif ini memandu Anda melalui setiap langkah, mulai dari pengaturan hingga implementasi."
"linktitle": "Ekstrak Teks yang Disorot dari PDF Menggunakan Aspose.PDF untuk .NET"
"second_title": "Referensi API Aspose.PDF untuk .NET"
"title": "Ekstrak Teks yang Disorot dari PDF Menggunakan Aspose.PDF untuk .NET"
"url": "/id/pdf/net/mastering-annotations/extract-highlighted-text-from-pdf/"
"weight": 60
---

## Perkenalan

Saat bekerja dengan berkas PDF, mengekstrak teks yang disorot sangat penting untuk analisis data, peninjauan konten, atau pengorganisasian catatan. Jika Anda menggunakan Aspose.PDF untuk .NET, Anda beruntung. Tutorial ini memberikan petunjuk langkah demi langkah yang jelas tentang cara mengekstrak teks yang disorot secara efisien dari dokumen PDF.

## Prasyarat

Sebelum memulai, pastikan Anda telah menyiapkan hal-hal berikut:

- Aspose.PDF untuk Pustaka .NET: Unduh pustaka dari [halaman rilis](https://releases.aspose.com/pdf/net/).
- Lingkungan Pengembangan: Lingkungan kerja seperti Visual Studio.
- Pengetahuan Dasar C#: Diperlukan pemahaman tentang C# dan pemrograman berorientasi objek.
- Lisensi Aspose: Meskipun Anda dapat memulai dengan uji coba gratis, [lisensi sementara](https://purchase.aspose.com/temporary-license/) atau lisensi penuh dari [Di Sini](https://purchase.aspose.com/buy) akan menyediakan akses tanpa batas.

## Impor Namespace yang Diperlukan

Mulailah dengan mengimpor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ruang nama ini menyediakan akses ke kelas dan metode yang diperlukan untuk menangani dokumen PDF dan anotasi.

## Langkah 1: Siapkan Direktori Proyek Anda

Tentukan direktori tempat file PDF Anda berada:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Pastikan untuk mengganti jalur dengan direktori sebenarnya dari berkas PDF Anda.

## Langkah 2: Muat Dokumen PDF

Muat dokumen PDF dengan kode berikut:

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

Pastikan file yang ditentukan ada di direktori yang diberikan.

## Langkah 3: Akses Anotasi di Halaman

Untuk mengakses anotasi, ulangi anotasi pada halaman yang Anda inginkan (dalam hal ini, halaman pertama):

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
    if (annotation is TextMarkupAnnotation)
    {
        TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

Kode ini menyaring untuk `TextMarkupAnnotation` jenis, yang mewakili sorotan.

## Langkah 4: Ekstrak Teks yang Disorot

Sekarang, ekstrak dan tampilkan teks dari anotasi yang disorot:

```csharp
        TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
        foreach (TextFragment tf in collection)
        {
            Console.WriteLine(tf.Text);
        }
    }
}
```

Ini mengambil semua fragmen teks yang ditandai terkait dengan sorotan dan mencetaknya ke konsol.

## Kesimpulan

Mengekstrak teks yang disorot dari PDF menggunakan Aspose.PDF untuk .NET sangatlah mudah dan dapat meningkatkan proses penanganan dokumen Anda secara signifikan. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat secara efisien mengumpulkan teks yang disorot untuk berbagai aplikasi, seperti penyusunan laporan atau analisis data.

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengekstrak jenis anotasi lainnya?
Ya, cukup sesuaikan `if` kondisi untuk menyertakan berbagai jenis anotasi seperti `TextAnnotation` atau `StampAnnotation`.

### Bagaimana cara mengekstrak teks yang disorot dari semua halaman PDF?
Anda dapat mengulang semua halaman menggunakan:
```csharp
for (int i = 1; i <= doc.Pages.Count; i++)
{
    foreach (Annotation annotation in doc.Pages[i].Annotations) { ... }
}
```

### Apakah diperlukan lisensi untuk Aspose.PDF untuk .NET?
Uji coba gratis tersedia, tetapi pertimbangkan [lisensi sementara](https://purchase.aspose.com/temporary-license/) atau lisensi penuh untuk akses lengkap.

### Bisakah saya menyimpan teks yang diekstrak ke dalam sebuah berkas?
Tentu saja! Anda dapat memodifikasi kode untuk menulis teks yang diekstrak ke dalam berkas teks.

### Apakah Aspose.PDF mendukung platform lain?
Ya, Aspose.PDF juga mendukung Java dan platform lainnya, menyediakan fungsionalitas serupa.