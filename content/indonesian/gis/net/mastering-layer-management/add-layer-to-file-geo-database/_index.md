---
"description": "Pelajari cara menambahkan layer baru ke File Geodatabase (GDB) menggunakan Aspose.GIS for .NET. Panduan komprehensif ini mencakup prasyarat, impor namespace, dan langkah-langkah detail untuk membuat dan memvalidasi layer dalam dataset GIS Anda."
"linktitle": "Tambahkan Layer ke Geodatabase File"
"second_title": "Aspose.GIS .NET API"
"title": "Menambahkan Layer ke Geodatabase File Menggunakan Aspose.GIS untuk .NET"
"url": "/id/gis/net/mastering-layer-management/add-layer-to-file-geo-database/"
"weight": 16
---

## Perkenalan

Teknologi Sistem Informasi Geografis (SIG) memainkan peran penting dalam analisis dan visualisasi data modern. Aspose.GIS untuk .NET adalah pustaka luar biasa yang memungkinkan pengembang untuk memanipulasi data geografis secara efisien. Panduan terperinci ini membahas cara menambahkan lapisan baru ke dataset File Geodatabase (GDB) menggunakan Aspose.GIS untuk .NET. Ikuti langkah-langkah komprehensif ini untuk mengintegrasikan lapisan dengan lancar dan meningkatkan kemampuan SIG Anda.

## Prasyarat untuk Menambahkan Lapisan ke File GDB

Sebelum kita melanjutkan, pastikan Anda memiliki hal berikut:

1. Pustaka Aspose.GIS untuk .NET  
   Unduh dan instal perpustakaan dari [Aspose.GIS untuk halaman .NET](https://reference.aspose.com/gis/net/).

2. Kumpulan Data Geodatabase File (GDB)  
   Pastikan Anda memiliki kumpulan data GDB untuk operasi tersebut.

3. Lingkungan Pengembangan  
   Instal dan konfigurasikan IDE pilihan Anda dengan dukungan .NET (misalnya, Visual Studio).

4. Lisensi Sementara (Opsional)  
   Untuk evaluasi fitur lengkap, mintalah [lisensi sementara](https://purchase.conholdate.com/temporary-license/).

5. Direktori Data  
   Siapkan direktori untuk mengelola kumpulan data masukan dan keluaran Anda.

## Mengimpor Namespace yang Diperlukan

Sebelum membuat kode, sertakan namespace penting untuk mengakses fungsionalitas Aspose.GIS. Tambahkan cuplikan kode berikut di awal proyek Anda:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Langkah 1: Gandakan Dataset GDB

Untuk menjaga integritas dataset asli Anda, buat duplikat. Gunakan kode berikut untuk menyalin dataset ke lokasi baru:

```csharp
string dataDir = "C:\\GISData\\"; // Direktori yang berisi kumpulan data Anda
string originalPath = dataDir + "ExistingDataset.gdb";
string newDatasetPath = dataDir + "ModifiedDataset.gdb";

// Fungsi untuk menduplikasi direktori
RunExamples.CopyDirectory(originalPath, newDatasetPath);
```

## Langkah 2: Buka Dataset dan Periksa Kemampuan Pembuatan

Aspose.GIS memungkinkan pengembang untuk membuka set data dan memverifikasi apakah lapisan baru dapat ditambahkan. Gunakan cuplikan kode berikut untuk mengonfirmasi kemampuan pembuatan set data:

```csharp
using (var dataset = Dataset.Open(newDatasetPath, Drivers.FileGdb))
{
    Console.WriteLine($"Can Create Layers: {dataset.CanCreateLayers}"); // Harus mengembalikan True
}
```

## Langkah 3: Buat Layer Baru di Dataset

Menambahkan layer memerlukan pendefinisian sistem referensi spasial dan atributnya. Berikut cara membuat dan mengisi layer dengan data sampel:

```csharp
using (var dataset = Dataset.Open(newDatasetPath, Drivers.FileGdb))
{
    // Buat layer baru dengan sistem referensi spasial WGS 84
    using (var layer = dataset.CreateLayer("NewLayer", SpatialReferenceSystem.Wgs84))
    {
        // Tambahkan skema atribut
        layer.Attributes.Add(new FeatureAttribute("LocationName", AttributeDataType.String));

        // Membuat dan menambahkan fitur
        var feature = layer.ConstructFeature();
        feature.SetValue("LocationName", "Sample Point");
        feature.Geometry = new Point(34.0522, -118.2437); // Garis Bujur dan Garis Lintang
        layer.Add(feature);
    }
}
```

## Langkah 4: Buka dan Validasi Layer Baru

Setelah membuat layer, validasi isinya untuk memastikan akurasi. Gunakan cuplikan kode berikut:

```csharp
using (var dataset = Dataset.Open(newDatasetPath, Drivers.FileGdb))
{
    using (var layer = dataset.OpenLayer("NewLayer"))
    {
        Console.WriteLine($"Feature Count: {layer.Count}");
        Console.WriteLine($"Attribute Value: {layer[0].GetValue<string>("LocationName")}");
    }
}
```

## Kesimpulan

Menambahkan layer ke dataset File Geodatabase dengan Aspose.GIS for .NET merupakan proses yang mudah jika Anda mengikuti langkah-langkah ini. Mulai dari menduplikasi dataset hingga membuat dan memvalidasi layer, pustaka ini menyediakan berbagai alat canggih untuk mengelola data GIS. Dengan menguasai teknik-teknik ini, Anda dapat meningkatkan alur kerja GIS dan mencapai manipulasi data geografis yang efisien.

## Pertanyaan yang Sering Diajukan

### Apa kegunaan Aspose.GIS for .NET?
Aspose.GIS untuk .NET adalah pustaka yang dirancang untuk memproses dan memanipulasi data geografis, mendukung berbagai format file, termasuk Shapefile, GDB, dan banyak lagi.

### Bisakah saya menambahkan beberapa lapisan dalam satu operasi?
Ya, Aspose.GIS memungkinkan pembuatan dan pengelolaan beberapa lapisan dalam satu kumpulan data.

### Sistem referensi spasial apa yang didukung?
Pustaka ini mendukung sejumlah sistem referensi spasial, termasuk WGS 84, NAD 83, dan CRS khusus.

### Di mana saya dapat menemukan dukungan?
Kunjungi [Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) untuk diskusi dan dukungan komunitas.

### Apakah ada uji coba gratis yang tersedia?
Ya, sebuah [uji coba gratis](https://releases.aspose.com/) tersedia untuk menguji fitur perpustakaan.