---
"description": "Maksimalkan potensi konversi Excel ke PDF Anda dengan Aspose.Cells untuk .NET. Dalam panduan komprehensif ini, pelajari cara mengelola sumber daya eksternal, seperti gambar, untuk memastikan PDF Anda mencerminkan persyaratan format yang tepat."
"linktitle": "Kontrol Sumber Daya Eksternal dengan Aspose.Cells untuk .NET"
"second_title": "API Pemrosesan Excel Aspose.Cells .NET"
"title": "Kontrol Sumber Daya Eksternal dengan Aspose.Cells untuk .NET"
"url": "/id/cells/net/mastering-rendering-and-exporting/control-external-resources/"
"weight": 12
---

## Perkenalan

Di era digital saat ini, mengonversi lembar kerja Excel ke dokumen PDF merupakan tugas yang umum dan penting. Baik Anda sedang menyiapkan laporan, data keuangan, atau materi presentasi, memastikan PDF Anda sesuai dengan format yang diinginkan sangatlah penting. Aspose.Cells untuk .NET menyediakan pustaka canggih yang memungkinkan Anda mengontrol proses konversi ini secara detail, terutama saat menangani sumber daya eksternal seperti gambar. Dalam panduan ini, kita akan membahas cara mengelola sumber daya eksternal secara efektif selama proses konversi Excel ke PDF menggunakan Aspose.Cells. Mari kita mulai!

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan hal berikut:

1. Visual Studio atau IDE apa pun yang kompatibel dengan .NET: Ini akan menjadi lingkungan pengembangan Anda.
2. Aspose.Cells untuk .NET: Jika Anda belum menginstalnya, kunjungi [Unduhan Aspose](https://releases.aspose.com/cells/net/) halaman untuk mendapatkan versi terbaru.
3. Pengetahuan Dasar C#: Keakraban dengan C# akan sangat bermanfaat. Jika Anda memerlukan klarifikasi tentang konsep apa pun, silakan mencarinya.
4. Contoh Berkas Excel: Siapkan berkas Excel, seperti "samplePdfSaveOptions_StreamProvider.xlsx," yang berisi sumber daya eksternal yang ingin Anda konversi.
5. Berkas Gambar untuk Pengujian: Gunakan berkas gambar seperti "newPdfSaveOptions_StreamProvider.png" sebagai sumber daya eksternal selama konversi.

## Impor Paket yang Diperlukan

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dari pustaka Aspose.Cells. Tambahkan direktif "using" berikut di bagian atas berkas C# Anda:

```csharp
using System.IO;
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Cells;
using Aspose.Cells.Drawing;
using Aspose.Cells.Rendering;
using System;
```

Ruang nama ini menyediakan kelas dan metode penting untuk tugas Anda.

## Langkah 1: Buat Kelas Penyedia Aliran

Pertama, buat kelas penyedia aliran yang mengimplementasikan `IStreamProvider` Antarmuka. Kelas ini akan memungkinkan Anda mengontrol bagaimana sumber daya eksternal dimuat.

```csharp
class MyStreamProvider : IStreamProvider
{
    public void CloseStream(StreamProviderOptions options)
    {
        Debug.WriteLine("-----Close Stream-----");
    }

    public void InitStream(StreamProviderOptions options)
    {
        string sourceDir = "Your Document Directory";
        Debug.WriteLine("-----Init Stream-----");
        
        // Memuat gambar ke dalam aliran memori
        byte[] bts = File.ReadAllBytes(Path.Combine(sourceDir, "newPdfSaveOptions_StreamProvider.png"));
        MemoryStream ms = new MemoryStream(bts);
        options.Stream = ms;
    }
}
```

- CloseStream: Metode ini dipanggil saat aliran ditutup, saat ini sedang mencatat pesan debug.
- InitStream: Metode ini membaca file gambar eksternal sebagai array byte, mengubahnya menjadi aliran memori, dan menetapkannya ke `options.Stream` milik.

## Langkah 2: Siapkan Direktori Sumber dan Output

Berikutnya, tentukan direktori untuk berkas Excel dan PDF keluaran.

```csharp
// Direktori sumber
string sourceDir = "Your Document Directory";
// Direktori keluaran
string outputDir = "Your Document Directory";
```

Mengganti `"Your Document Directory"` dengan jalur sebenarnya pada sistem Anda tempat file Anda berada.

## Langkah 3: Muat File Excel Anda

Sekarang, muat berkas Excel yang ingin Anda buat PDF-nya.

```csharp
// Muat file Excel sumber yang berisi gambar eksternal
Workbook wb = new Workbook(sourceDir, "samplePdfSaveOptions_StreamProvider.xlsx");
```

Itu `Workbook` Kelas dari Aspose.Cells mewakili berkas Excel Anda, yang mungkin menyertakan berbagai sumber daya eksternal seperti gambar.

## Langkah 4: Atur Opsi Penyimpanan PDF

Sebelum menyimpan buku kerja sebagai PDF, tentukan opsi penyimpanan yang Anda inginkan.

```csharp
// Tentukan Opsi Penyimpanan PDF - Penyedia Streaming
PdfSaveOptions opts = new PdfSaveOptions
{
    OnePagePerSheet = true // Simpan setiap lembar di halaman baru
};
```

Ini menciptakan contoh `PdfSaveOptions`, memungkinkan Anda untuk menyesuaikan format PDF. `OnePagePerSheet` opsi memastikan bahwa setiap lembar Excel muncul pada halaman terpisah dalam PDF final.

## Langkah 5: Tetapkan Penyedia Streaming Anda

Hubungkan Anda `Workbook` contoh dengan `MyStreamProvider` kelas yang Anda buat sebelumnya.

```csharp
wb.Settings.StreamProvider = new MyStreamProvider();
```

Baris ini memastikan bahwa setiap kali sumber daya eksternal ditemukan selama konversi, penyedia kustom Anda akan mengelolanya sebagaimana mestinya.

## Langkah 6: Simpan Buku Kerja sebagai PDF

Sekarang, simpan buku kerja Excel Anda sebagai PDF.

```csharp
// Simpan buku kerja ke PDF
wb.Save(outputDir + "outputPdfSaveOptions_StreamProvider.pdf", opts);
```

Dengan memanggil `Save` metode pada objek buku kerja dan meneruskan direktori keluaran beserta opsi PDF, Anda mengonversi file Excel menjadi PDF yang diformat dengan baik.

## Langkah 7: Konfirmasi Eksekusi Berhasil

Terakhir, ada baiknya untuk memastikan prosesnya berhasil diselesaikan.

```csharp
Console.WriteLine("ControlLoadingOfExternalResourcesInExcelToPDF executed successfully.\r\n");
```

Pesan ini akan memberi tahu Anda tentang status operasi Anda, memberikan umpan balik yang bermanfaat.

## Kesimpulan

Anda kini telah menguasai proses pengendalian sumber daya eksternal selama konversi Excel ke PDF menggunakan Aspose.Cells! Dengan mengikuti langkah-langkah ini, Anda dapat memastikan dokumen Anda memuat gambar dan elemen eksternal lainnya secara akurat, sehingga menghasilkan produk akhir yang sempurna setiap saat.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.Cells?
Aspose.Cells adalah pustaka hebat untuk pengembang .NET yang memungkinkan pembuatan, manipulasi, konversi, dan perenderan file Excel dalam berbagai format.

### Bagaimana cara mengunduh Aspose.Cells?
Anda dapat mengunduh versi terbaru dari [Tautan unduhan](https://releases.aspose.com/cells/net/).

### Bisakah saya mencoba Aspose.Cells secara gratis?
Ya! Anda dapat mengakses uji coba gratis dengan mengunjungi [Halaman uji coba gratis](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan untuk Aspose.Cells?
Untuk pertanyaan terkait dukungan, kunjungi [Forum Dukungan Aspose](https://forum.aspose.com/c/cells/9).

### Bagaimana cara memperoleh lisensi sementara untuk Aspose.Cells?
Anda dapat mengajukan permohonan lisensi sementara [Di Sini](https://purchase.aspose.com/temporary-license/).