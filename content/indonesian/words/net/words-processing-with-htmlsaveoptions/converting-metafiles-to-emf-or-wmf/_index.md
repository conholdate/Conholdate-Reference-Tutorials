---
"description": "Pelajari cara mengonversi gambar SVG ke format EMF atau WMF dengan mudah di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah dengan contoh kode untuk hasil yang akurat dan kompatibel."
"linktitle": "Mengonversi Metafile ke EMF atau WMF"
"second_title": "API Pemrosesan Dokumen Aspose.Words"
"title": "Mengonversi Metafile ke EMF atau WMF"
"url": "/id/words/net/words-processing-with-htmlsaveoptions/converting-metafiles-to-emf-or-wmf/"
"weight": 10
---

## Perkenalan

Mengelola dan mengonversi format gambar secara efisien merupakan bagian penting dalam pembuatan dokumen Word profesional. Dalam panduan ini, kami akan membahas penggunaan Aspose.Words for .NET untuk mengonversi gambar SVG ke format EMF (Enhanced Metafile) atau WMF (Windows Metafile) agar integrasinya lancar. Tutorial ini memberikan instruksi langkah demi langkah yang jelas untuk membantu pengembang melakukan konversi dengan mudah.

## Prasyarat untuk Mengonversi SVG ke EMF atau WMF

Untuk memastikan pengalaman pengembangan yang lancar, pastikan prasyarat berikut terpenuhi:

- Aspose.Words untuk .NET: Dapatkan versi terbaru dari [Aspose merilis halaman](https://releases.aspose.com/words/net/).
- .NET Framework: Verifikasi instalasi .NET Framework (atau .NET Core/5/6 tergantung pada lingkungan Anda).
- Lingkungan Pengembangan: Visual Studio direkomendasikan karena fitur-fiturnya yang tangguh.
- Kemahiran C#: Kemampuan dasar dalam pemrograman C# sangatlah penting.

## Mengimpor Namespace yang Diperlukan

Dalam proyek Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Words:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Tentukan Direktori Dokumen

Siapkan jalur direktori tempat dokumen Word Anda akan disimpan. Ini penting untuk mengelola berkas keluaran secara efektif.

```csharp
string dataDir = @"C:\MyDocuments\";
```

Mengganti `@"C:\MyDocuments\"` dengan jalur yang Anda inginkan.

## Langkah 2: Siapkan String HTML yang Berisi SVG

Tulis string HTML yang menyematkan konten SVG Anda. Ini memungkinkan Aspose.Words untuk merender dan memproses SVG tersebut.

```csharp
string htmlContent = 
    @"<html>
        <body>
            <svg xmlns='http://www.w3.org/2000/svg' lebar='300' tinggi='100' kotak tampilan='0 0 300 100'>
                <rect x='10' y='10' width='280' height='80' fill='blue' stroke='black' stroke-width='2'/>
                <text x='20' y='60' fill='white' font-size='20'>Aspose SVG Example</text>
            </svg>
        </body>
    </html>";
```

## Langkah 3: Konfigurasikan Opsi Pemuatan HTML

Untuk memastikan penanganan konversi SVG yang tepat, konfigurasikan `HtmlLoadOptions` dengan `ConvertSvgToEmf`.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions
{
    ConvertSvgToEmf = true
};
```

## Langkah 4: Muat HTML ke dalam Dokumen Word

Gunakan opsi beban yang dikonfigurasi untuk membuat `Document` objek dari string HTML.

```csharp
using (MemoryStream htmlStream = new MemoryStream(Encoding.UTF8.GetBytes(htmlContent)))
{
    Document document = new Document(htmlStream, loadOptions);
}
```

## Langkah 5: Konfigurasikan Opsi Penyimpanan untuk EMF/WMF

Sesuaikan opsi penyimpanan untuk menentukan format metafile yang diinginkan. Di sini, kita pilih `HtmlMetafileFormat.Emf`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    MetafileFormat = HtmlMetafileFormat.Emf
};
```

## Langkah 6: Simpan Dokumen

Simpan dokumen menggunakan opsi penyimpanan yang ditentukan.

```csharp
document.Save(dataDir + "ConvertedDocument.emf", saveOptions);
```

Berkas yang dihasilkan akan berisi konten SVG yang dikonversi ke format EMF.

## Kesimpulan

Tutorial ini menunjukkan cara mengonversi gambar SVG ke format EMF atau WMF menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat meningkatkan kompatibilitas dan fidelitas visual dokumen Word Anda. Baik Anda mengotomatiskan pembuatan dokumen maupun menyiapkan laporan berkualitas tinggi, metode ini memastikan hasil yang mulus.

## Pertanyaan yang Sering Diajukan

### Bisakah saya menggunakan metode ini untuk memproses beberapa SVG secara batch?
Ya, Anda dapat mengulangi beberapa berkas HTML yang berisi SVG, menerapkan proses yang sama dalam satu putaran.

### Apa perbedaan antara EMF dan WMF?
EMF adalah versi penyempurnaan dari WMF, menawarkan dukungan yang lebih baik untuk grafik kompleks dan ukuran data yang lebih besar.

### Apakah Aspose.Words kompatibel dengan .NET Core?
Ya, Aspose.Words untuk .NET mendukung .NET Core dan .NET 5/6, membuatnya cocok untuk aplikasi lintas-platform modern.

### Bisakah saya mempertahankan format SVG asli dalam output?
Tidak, metode ini secara khusus mengonversi SVG ke EMF/WMF. Namun, Anda dapat mempertahankan SVG asli dengan menyematkannya langsung ke dalam dokumen tanpa konversi.

### Di mana saya dapat mengunduh uji coba gratis Aspose.Words?
Anda dapat mengunduh uji coba gratis dari [Aspose merilis halaman](https://releases.aspose.com/).