---
"description": "Pelajari cara menyimpan dokumen Microsoft OneNote sebagai file PDF secara efisien menggunakan Aspose.Note untuk .NET. Panduan ini memandu Anda melalui prasyarat yang diperlukan, dan menawarkan FAQ yang bermanfaat."
"linktitle": "Menyimpan Dokumen OneNote dalam PDF"
"second_title": "Aspose.Note .NET API"
"title": "Menyimpan Dokumen OneNote dalam PDF Menggunakan Aspose.Note untuk .NET"
"url": "/id/note/net/one-note-document-manipulation/saving-one-note-document-pdf/"
"weight": 26
---

## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara menyimpan dokumen ke format PDF menggunakan Aspose.Note untuk .NET. Aspose.Note adalah pustaka canggih yang memungkinkan pengembang untuk bekerja dengan berkas Microsoft OneNote secara terprogram. Kita akan membahas prasyarat, mengimpor namespace, dan memberikan panduan langkah demi langkah untuk menyimpan dokumen ke PDF dalam berbagai tata letak halaman.

## Prasyarat
1. Visual Studio: Pastikan sudah terinstal.
2. Aspose.Note untuk .NET: Unduh dan instal pustaka.
3. Pengetahuan C#: Diperlukan pemahaman dasar tentang bahasa tersebut.

## Mengimpor Namespace yang Diperlukan
Sebelum melanjutkan, impor namespace berikut dalam kode Anda:

```csharp
using System;
using System.IO;
using Aspose.Note.Saving;
```

## Langkah 1: Simpan ke PDF dengan Pengaturan Halaman Surat
```csharp
public static void SaveToPdfUsingLetterPageSettings()
{
    string dataDir = "Your Document Directory"; // Perbarui jalur ini
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingLetterPageSettings.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.Letter });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Memuat dokumen OneNote dan menyimpannya sebagai PDF menggunakan pengaturan halaman berukuran letter.

## Langkah 2: Simpan ke PDF dengan Pengaturan Halaman A4 (Tanpa Batas Tinggi)
```csharp
public static void SaveToPdfUsingA4PageSettingsWithoutHeightLimit()
{
    string dataDir = "Your Document Directory"; // Perbarui jalur ini
    Document oneFile = new Document(dataDir + "OneNote.one");
    var dst = Path.Combine(dataDir, "SaveToPdfUsingA4PageSettingsWithoutHeightLimit.pdf");
    
    oneFile.Save(dst, new PdfSaveOptions() { PageSettings = PageSettings.A4NoHeightLimit });
    Console.WriteLine("\nOneNote document saved successfully.\nFile saved at " + dst);
}
```
Mirip dengan Langkah 1 tetapi menggunakan pengaturan halaman A4 tanpa batasan ketinggian.

## Kesimpulan
Tutorial ini berhasil menunjukkan cara mengonversi file OneNote ke format PDF menggunakan Aspose.Note. Dengan memanfaatkan berbagai pengaturan halaman, pengembang mendapatkan fleksibilitas dalam manajemen dokumen.

## Pertanyaan yang Sering Diajukan
### Bisakah Aspose.Note menangani file OneNote yang rumit?
Ya, ia secara efektif menangani berbagai fitur file OneNote yang kompleks.

### Apakah Aspose.Note cocok untuk proyek komersial?
Ya, Anda dapat menggunakannya untuk aplikasi komersial setelah membeli lisensi.

### Apakah Aspose.Note menawarkan uji coba gratis?
Ya, uji coba gratis tersedia untuk eksplorasi.

### Di mana saya dapat menemukan dokumentasi untuk Aspose.Note?
Dokumentasi terperinci tersedia di situs referensi Aspose.

### Butuh bantuan lebih lanjut?
Untuk pertanyaan dan dukungan, lihat forum Aspose.Note.