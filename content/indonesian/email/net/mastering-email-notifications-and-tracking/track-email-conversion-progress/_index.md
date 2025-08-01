---
"description": "Pelajari langkah demi langkah cara melacak progres konversi email di C# menggunakan Aspose.Email untuk .NET. Tingkatkan efisiensi proyek Anda dengan tutorial mendetail ini."
"linktitle": "Lacak Kemajuan Konversi Email dengan Aspose.Email untuk .NET"
"second_title": "API Pemrosesan Email Aspose.Email .NET"
"title": "Lacak Kemajuan Konversi Email dengan Aspose.Email untuk .NET"
"url": "/id/email/net/mastering-email-notifications-and-tracking/track-email-conversion-progress/"
"weight": 12
---

## Perkenalan

Mengelola dokumen email secara efisien seringkali melibatkan pelacakan progres konversinya. Aspose.Email untuk .NET menyediakan perangkat yang andal untuk mencapai hal ini, memungkinkan pengembang untuk menangani operasi email dengan lancar. Tutorial ini membahas cara melacak progres konversi dokumen email dalam C#, menguraikan prosesnya langkah demi langkah agar mudah dipahami.  

## Prasyarat  

Sebelum kita masuk ke tutorial, mari pastikan Anda sudah menyiapkan semuanya:  

1. Aspose.Email untuk .NET: Unduh dan instal [Aspose.Email untuk .NET](https://releases.aspose.com/email/net/) perpustakaan.  
2. Lingkungan Pengembangan: Instal Visual Studio atau IDE lain yang kompatibel dengan .NET.  
3. .NET Framework: Pastikan .NET Framework 4.5 atau yang lebih baru telah terinstal.  
4. Lisensi Sementara: Pertimbangkan untuk mendapatkan [lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk menjelajahi fitur Aspose.Email secara lengkap.  
5. Contoh File Email: Siapkan `.eml` berkas (misalnya, `test.eml`) untuk digunakan sebagai sampel.  

## Paket Impor  

Untuk menggunakan Aspose.Email di proyek Anda, Anda perlu mengimpor namespace yang diperlukan. Tambahkan pernyataan using berikut di bagian atas berkas Anda:  

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.SaveOptions;
using System;
using System.IO;
```

## Langkah 1: Siapkan Proyek Anda  

Mulailah dengan membuat aplikasi konsol C# baru di Visual Studio. Ini akan menjadi fondasi untuk menerapkan pelacakan konversi dokumen email.  
  
1. Buka Visual Studio dan buat proyek Aplikasi Konsol baru.  
2. Instal paket Aspose.Email NuGet:  
```sh
Install-Package Aspose.Email
```  
3. Tambahkan `.eml` file ke direktori proyek Anda.  

## Langkah 2: Muat File Email  

Sekarang, muat file email ke dalam `MailMessage` objek. Ini adalah langkah pertama dalam mengolah data email.  
 
```csharp
string dataDir = "Your Document Directory";
var fileName = dataDir + "test.eml";
MailMessage msg = MailMessage.Load(fileName);
```
 
- `dataDir`: Menentukan direktori tempat berkas email Anda berada.  
- `MailMessage.Load`: Membaca `.eml` berkas dan mempersiapkannya untuk operasi selanjutnya.  

## Langkah 3: Inisialisasi Aliran Memori  

Selanjutnya, buatlah `MemoryStream` objek untuk menyimpan data email yang dikonversi sementara.  
 
```csharp
MemoryStream ms = new MemoryStream();
```

A `MemoryStream` digunakan di sini untuk mengelola keluaran proses konversi tanpa menyimpan data langsung ke disk.  

## Langkah 4: Tentukan Opsi Konversi  

Menyiapkan `EmlSaveOptions` dengan penangan kemajuan khusus untuk melacak kemajuan konversi.  
 
```csharp
EmlSaveOptions opt = new EmlSaveOptions(MailMessageSaveType.EmlFormat);
opt.CustomProgressHandler = new ConversionProgressEventHandler(ShowEmlConversionProgress);
```
  
- `MailMessageSaveType.EmlFormat`: Menentukan format keluaran.  
- `CustomProgressHandler`: Menetapkan fungsi penanganan khusus untuk memantau kemajuan.  

## Langkah 5: Simpan Email ke Aliran Memori  

Simpan `MailMessage` objek menggunakan opsi yang ditentukan, mengaktifkan fungsi pelacakan kemajuan.  
 
```csharp
msg.Save(ms, opt);
```
 
Langkah ini memulai proses konversi email dan mengirimkan pembaruan ke pengendali kemajuan.  

## Langkah 6: Terapkan Penangan Kemajuan  

Definisikan `ShowEmlConversionProgress` metode untuk menangani pembaruan kemajuan dan menampilkannya di konsol.  
 
```csharp
private static void ShowEmlConversionProgress(ProgressEventHandlerInfo info)
{
    int total;
    int saved;

    switch (info.EventType)
    {
        case ProgressEventType.MimeStructureCreated:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine($"MimeStructureCreated - TotalMimePartCount: {total}");
            Console.WriteLine($"MimeStructureCreated - SavedMimePartCount: {saved}");
            break;

        case ProgressEventType.MimePartSaved:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine($"MimePartSaved - TotalMimePartCount: {total}");
            Console.WriteLine($"MimePartSaved - SavedMimePartCount: {saved}");
            break;

        case ProgressEventType.SavedToStream:
            total = info.TotalMimePartCount;
            saved = info.SavedMimePartCount;
            Console.WriteLine($"SavedToStream - TotalMimePartCount: {total}");
            Console.WriteLine($"SavedToStream - SavedMimePartCount: {saved}");
            break;
    }
}
```
 
- `ProgressEventHandlerInfo`:Memberikan rincian tentang proses konversi.  
- Switch Case: Menangani berbagai tahap konversi: `MimeStructureCreated`, `MimePartSaved`, Dan `SavedToStream`.  

### Apa yang Diharapkan?  
Saat konversi berlangsung, Anda akan melihat pembaruan terperinci yang dicetak ke konsol, seperti:  
```plaintext
MimeStructureCreated - TotalMimePartCount: 10  
MimeStructureCreated - SavedMimePartCount: 3  
MimePartSaved - TotalMimePartCount: 10  
MimePartSaved - SavedMimePartCount: 5  
```

## Kesimpulan  

Melacak progres konversi dokumen email dalam C# kini semakin mudah berkat Aspose.Email untuk .NET. Dengan mengikuti tutorial ini, Anda telah mempelajari cara memuat berkas email, mengatur pengendali progres, dan menyimpan data email sambil memantau seluruh proses. Fungsionalitas ini memastikan Anda tetap terinformasi dan memegang kendali selama pengoperasian dokumen email.  

## Pertanyaan yang Sering Diajukan  

### Bisakah saya menggunakan kode ini untuk format selain `.eml`?  
Ya, modifikasi `MailMessageSaveType` agar sesuai dengan format lain seperti MSG atau MHTML.  

### Bagaimana cara menangani file email berukuran besar?  
Pertimbangkan untuk menggunakan `FileStream` sebagai pengganti `MemoryStream` untuk kinerja yang lebih baik dengan file besar.  

### Apa itu lisensi sementara, dan bagaimana cara mendapatkannya?  
Lisensi sementara memungkinkan Anda mengevaluasi seluruh fitur perpustakaan secara gratis. Dapatkan sekarang! [Di Sini](https://purchase.aspose.com/temporary-license/).  

### Dapatkah saya mengintegrasikan kode ini ke dalam aplikasi web?  
Ya, kode tersebut kompatibel dengan aplikasi web yang menggunakan ASP.NET atau kerangka kerja serupa.  

### Di mana saya dapat menemukan sumber daya tambahan?  
Lihat di sini [dokumentasi](https://reference.aspose.com/email/net/) atau kunjungi [forum dukungan](https://forum.aspose.com/c/email/12/) untuk bantuan.