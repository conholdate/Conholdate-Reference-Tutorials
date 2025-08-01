---
"description": "Pelajari cara menambahkan teks dengan mudah dari bagian yang ditandai di dokumen Word dengan Aspose.Words untuk .NET. Tutorial langkah demi langkah ini."
"linktitle": "Menambahkan Teks dari Bagian yang Ditandai di Dokumen Word"
"second_title": "API Pemrosesan Dokumen Aspose.Words"
"title": "Menambahkan Teks dari Bagian yang Ditandai di Dokumen Word"
"url": "/id/words/net/mastering-bookmarks/append-text-from-bookmarked-sections/"
"weight": 10
---

## Perkenalan

Pernahkah Anda merasa kesulitan menambahkan teks dari bagian yang ditandai di dokumen Word? Anda berada di tempat yang tepat! Tutorial ini akan memandu Anda langkah demi langkah menggunakan Aspose.Words untuk .NET. Setelah selesai, Anda akan dapat menambahkan teks yang ditandai seperti seorang profesional. Mari kita mulai!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Aspose.Words untuk .NET: Jika Anda belum menginstalnya, Anda dapat [unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Lingkungan pengembangan .NET seperti Visual Studio.
- Pengetahuan Dasar C#: Keakraban dengan konsep pemrograman C# dasar akan bermanfaat.
- Dokumen Word dengan Penanda: Dokumen Word yang berisi penanda yang akan kita gunakan untuk menambahkan teks.

## Impor Namespace yang Diperlukan

Pertama, kita perlu mengimpor namespace yang diperlukan untuk mengakses fungsionalitas Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

## Langkah 1: Muat Dokumen dan Inisialisasi Variabel

Mari kita mulai dengan memuat dokumen Word sumber dan tujuan dan menginisialisasi variabel yang diperlukan.

```csharp
// Muat dokumen sumber dan tujuan.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Inisialisasi pengimpor dokumen.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Temukan penanda buku di dokumen sumber.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Langkah 2: Identifikasi Paragraf Awal dan Akhir

Selanjutnya, kita perlu menemukan paragraf tempat penanda dimulai dan berakhir. Ini penting untuk mengekstrak teks yang tepat.

```csharp
// Identifikasi paragraf di awal dan akhir penanda buku.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

// Validasi paragraf.
if (startPara == null || endPara == null)
    throw new InvalidOperationException("Bookmark start or end does not have a valid paragraph parent.");
```

## Langkah 3: Validasi Orang Tua Paragraf

Kita perlu memastikan bahwa paragraf awal dan akhir berbagi simpul induk yang sama. Ini adalah pendekatan yang disederhanakan untuk menghindari kerumitan.

```csharp
// Periksa apakah paragraf awal dan akhir memiliki induk yang sama.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs must have the same parent.");
```

## Langkah 4: Identifikasi Node yang Akan Dihentikan

Sekarang, kita perlu menentukan di mana akan berhenti menyalin teks, yaitu di simpul tepat setelah paragraf akhir.

```csharp
// Identifikasi simpul segera setelah paragraf akhir.
Node endNode = endPara.NextSibling;
```

## Langkah 5: Tambahkan Teks yang Ditandai ke Dokumen Tujuan

Terakhir, kita akan mengulang simpul dari paragraf awal ke simpul setelah paragraf akhir dan menambahkannya ke dokumen tujuan.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Impor simpul saat ini ke dokumen tujuan.
    Node newNode = importer.ImportNode(curNode, true);

    // Tambahkan simpul yang diimpor ke dokumen tujuan.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Simpan dokumen tujuan yang diperbarui.
dstDoc.Save("appended_document.docx");
```

## Kesimpulan

Selamat! Anda berhasil menambahkan teks dari bagian yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET. Pustaka canggih ini memudahkan manipulasi dokumen, dan kini Anda memiliki keterampilan praktis lainnya. Selamat membuat kode!

## Pertanyaan yang Sering Diajukan

### Bisakah saya menambahkan teks dari beberapa penanda sekaligus?
Ya, Anda dapat mengulangi proses untuk setiap penanda buku dan menambahkan teks seperlunya.

### Bagaimana jika paragraf awal dan akhir memiliki induk yang berbeda?
Contoh saat ini mengasumsikan mereka memiliki induk yang sama. Jika tidak, Anda perlu menerapkan penanganan yang lebih kompleks.

### Apakah format asli teks yang ditambahkan akan dipertahankan?
Tentu saja! Menggunakan `ImportFormatMode.KeepSourceFormatting` memastikan bahwa format asli dipertahankan.

### Apakah mungkin untuk menambahkan teks ke posisi tertentu dalam dokumen tujuan?
Ya, Anda dapat menambahkan teks ke posisi mana pun yang diinginkan dengan menavigasi ke simpul yang sesuai dalam dokumen tujuan.

### Bisakah saya menambahkan teks dari penanda buku ke bagian baru?
Ya, Anda dapat membuat bagian baru di dokumen tujuan dan menambahkan teks di sana.