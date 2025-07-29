---
"description": "Temukan cara ahli mengontrol visibilitas konten dalam dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah ini."
"linktitle": "Kelola Visibilitas Bookmark di Dokumen Word"
"second_title": "API Pemrosesan Dokumen Aspose.Words"
"title": "Kelola Visibilitas Bookmark di Dokumen Word"
"url": "/id/words/net/mastering-bookmarks/manage-bookmark-visibility-word-document/"
"weight": 10
---

## Perkenalan

Siap meningkatkan kemampuan manipulasi dokumen Anda dengan Aspose.Words untuk .NET? Baik Anda seorang pengembang berpengalaman yang mengotomatiskan tugas dokumen atau seseorang yang ingin tahu cara mengontrol berkas Word secara terprogram, panduan ini dirancang khusus untuk Anda. Hari ini, kita akan membahas cara menampilkan dan menyembunyikan konten berdasarkan bookmark dalam dokumen Word. Mari kita mulai!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Visual Studio: Versi apa pun yang kompatibel dengan .NET.
2. Aspose.Words untuk .NET: Unduh sekarang [Di Sini](https://releases.aspose.com/words/net/).
3. Pengetahuan Dasar C#: Kemampuan menulis program C# sederhana sudah cukup.
4. Contoh Dokumen Word: Siapkan dokumen Word (misalnya, "Bookmarks.docx") yang berisi bookmark untuk tutorial ini.

### Buat Proyek Baru

1. Buka Visual Studio dan buat proyek Aplikasi Konsol (.NET Core) baru. Beri nama seperti "BookmarkVisibilityManager".

### Instal Aspose.Words untuk .NET

Tambahkan Aspose.Words ke proyek Anda melalui NuGet Package Manager:

1. Navigasi ke Alat > Manajer Paket NuGet > Kelola Paket NuGet untuk Solusi.
2. Cari "Aspose.Words".
3. Instal paketnya.

Setelah proyek Anda siap, mari lanjutkan untuk memuat dokumen.

## Mengimpor Namespace

Mulailah dengan mengimpor namespace penting. Namespace ini menyediakan kelas dan metode yang diperlukan untuk memanipulasi dokumen Word dengan Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

## Langkah 1: Memuat Dokumen

Untuk memanipulasi dokumen Word, kita perlu memuatnya terlebih dahulu. Berikut caranya:

```csharp
// Tentukan jalur ke direktori dokumen Anda.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

Potongan kode ini mengatur jalur ke direktori dokumen Anda dan memuat dokumen ke dalam `Document` obyek.

## Langkah 2: Tampilkan/Sembunyikan Konten yang Ditandai

Sekarang, mari kita buat metode untuk mengubah visibilitas konten berdasarkan bookmark. Kita akan menyebut metode ini `ShowHideBookmarkedContent`.

Berikut implementasi metodenya:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    if (bm != null)
    {
        Node currentNode = bm.BookmarkStart;
        while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
        {
            if (currentNode.NodeType == NodeType.Run)
            {
                Run run = (Run)currentNode;
                run.Font.Hidden = isHidden;
            }
            currentNode = currentNode.NextSibling;
        }
    }
}
```

- Pengambilan Penanda Buku: `Bookmark bm = doc.Range.Bookmarks[bookmarkName];` mengambil penanda yang ditentukan.
- Penelusuran Node: Kami mengulangi node-node yang ada di dalam penanda.
- Toggle Visibilitas: Untuk setiap `Run` simpul (mewakili segmen teks), kami mengaturnya `Hidden` properti berdasarkan `isHidden` parameter.

## Langkah 3: Menerapkan Metode

Sekarang metode kita sudah siap, mari kita gunakan untuk menampilkan atau menyembunyikan konten dalam penanda tertentu:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true); // Menyembunyikan konten dalam "MyBookmark1"
```

Baris ini akan menyembunyikan konten yang terkait dengan penanda bernama "MyBookmark1".

## Langkah 4: Menyimpan Dokumen

Setelah Anda membuat perubahan, jangan lupa untuk menyimpan dokumen yang dimodifikasi:

```csharp
doc.Save(dataDir + "UpdatedBookmarks.docx");
```

Ini menyimpan dokumen dengan pengaturan visibilitas yang diperbarui.

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menampilkan dan menyembunyikan konten yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET. Pustaka canggih ini menyederhanakan manipulasi dokumen, menjadikannya ideal untuk mengotomatiskan laporan, membuat templat, atau bereksperimen dengan berkas Word. Selamat membuat kode!

## Pertanyaan yang Sering Diajukan

### Bisakah saya mengaktifkan beberapa penanda sekaligus?
Ya, cukup hubungi `ShowHideBookmarkedContent` metode untuk setiap penanda yang ingin Anda alihkan.

### Apakah menyembunyikan konten memengaruhi struktur dokumen?
Tidak, menyembunyikan konten hanya memengaruhi visibilitasnya; konten tetap utuh dalam dokumen.

### Bisakah saya menggunakan metode ini untuk jenis konten lainnya?
Metode ini dirancang khusus untuk menjalankan teks. Untuk jenis konten lainnya, Anda perlu menyesuaikan logika traversal node.

### Apakah Aspose.Words untuk .NET gratis?
Aspose.Words menawarkan uji coba gratis [Di Sini](https://releases.aspose.com/), tetapi lisensi penuh diperlukan untuk penggunaan produksi. Anda dapat membelinya [Di Sini](https://purchase.aspose.com/buy).

### Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah?
Untuk dukungan, kunjungi forum komunitas Aspose [Di Sini](https://forum.aspose.com/c/words/8).