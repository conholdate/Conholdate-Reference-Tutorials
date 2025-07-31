---
"description": "Pelajari cara memanfaatkan kelas di Aspose.Tasks for .NET untuk memfilter tugas proyek berdasarkan berbagai kondisi. Dengan menggabungkan kriteria seperti tugas ringkasan dan atribut non-null."
"linktitle": "Pemfilteran Tugas DAN Operasi di Aspose.Tasks"
"second_title": "Aspose.Tasks .NET API"
"title": "Pemfilteran Tugas DAN Operasi di Aspose.Tasks"
"url": "/id/tasks/net/master-advanced-features/task-filtering-and-operation/"
"weight": 10
---

## Perkenalan

Dalam tutorial ini, kita akan menjelajahi cara melakukan penyaringan lanjutan tugas proyek di Aspose.Tasks untuk .NET dengan memanfaatkan `Util.And` Fitur canggih ini memungkinkan pengembang untuk memfilter tugas berdasarkan berbagai kriteria secara efisien.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Pengetahuan dasar pemrograman C#.
2. Aspose.Tasks untuk .NET telah terinstal. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari [tautan ini](https://releases.aspose.com/tasks/net/).
3. Lingkungan pengembangan terpadu (IDE) seperti Visual Studio untuk menulis dan menjalankan kode.

## Mengimpor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek C# Anda. Ini akan memungkinkan Anda mengakses fungsionalitas yang disediakan oleh Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks.Util;

```

## Langkah 1: Inisialisasi Proyek dan Kumpulkan Tugas

Pertama, inisialisasi proyek Aspose.Tasks dan kumpulkan semua tugas di dalamnya. Untuk tujuan demonstrasi, kita asumsikan ada berkas proyek bernama `Project2.mpp`.

```csharp
// Jalur ke direktori dokumen
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");

// Kumpulkan semua tugas anak
var taskCollector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, taskCollector, 0);
```

## Langkah 2: Tentukan Kondisi Filter

Pada langkah ini, kita akan menentukan kondisi untuk memfilter tugas. Dalam contoh kita, kita akan membuat dua kondisi: satu untuk memfilter tugas ringkasan dan satu lagi untuk memastikan tugas tersebut bernilai null.

```csharp
var summaryCondition = new SummaryCondition();
var notNullCondition = new NotNullCondition();
```

## Langkah 3: Gabungkan Kondisi dengan Operasi AND

Langkah selanjutnya adalah menggabungkan kondisi-kondisi ini menggunakan `Util.And` kelas. Hal ini memungkinkan kita untuk membuat kondisi komposit yang mewajibkan kedua kriteria tersebut.

```csharp
var combinedCondition = new And<Task>(summaryCondition, notNullCondition);
```

## Langkah 4: Terapkan Tugas Kondisi dan Filter Gabungan

Sekarang, mari terapkan kondisi gabungan ke tugas-tugas yang dikumpulkan untuk menyaring tugas-tugas spesifik yang memenuhi kedua kondisi tersebut.

```csharp
List<Task> filteredTasks = Filter(taskCollector.Tasks, combinedCondition);
```

## Langkah 5: Keluarkan Tugas yang Difilter

Terakhir, kami akan mengulangi tugas-tugas yang telah difilter dan menampilkan detail yang relevan. Ini akan membantu kami memahami tugas-tugas yang memenuhi kriteria kami.

```csharp
Console.WriteLine("Filtered Tasks:");
foreach (var task in filteredTasks)
{
    Console.WriteLine(" - Task Name: " + task.Get(Tsk.Name));
}
```

## Kesimpulan

Dalam tutorial ini, kami mendemonstrasikan cara melakukan operasi penyaringan lanjutan di Aspose.Tasks untuk .NET menggunakan `Util.And` Dengan menggabungkan beberapa kondisi, kami dapat memfilter tugas secara efektif, sehingga meningkatkan utilitas aplikasi manajemen proyek kami.

## Pertanyaan yang Sering Diajukan

### Apa itu Aspose.Tasks untuk .NET?

Aspose.Tasks untuk .NET adalah API komprehensif yang dirancang bagi pengembang untuk memanipulasi file Microsoft Project secara terprogram dalam aplikasi .NET.

### Bisakah saya menggabungkan lebih dari dua kondisi menggunakan Util.And?

Ya! Itu `Util.And` Kelas memungkinkan Anda menggabungkan beberapa kondisi, mengaktifkan logika penyaringan kompleks yang disesuaikan dengan kebutuhan Anda.

### Apakah ada versi uji coba gratis yang tersedia untuk Aspose.Tasks?

Ya, Anda dapat mengunduh versi uji coba gratis dari [tautan ini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks?

Dokumentasi terperinci tersedia [Di Sini](https://reference.aspose.com/tasks/net/).

### Bagaimana saya bisa mencari dukungan untuk Aspose.Tasks?

Dukungan tersedia melalui forum komunitas Aspose.Tasks, yang dapat diakses [Di Sini](https://forum.aspose.com/c/tasks/15).