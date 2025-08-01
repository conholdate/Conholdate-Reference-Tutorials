---
"description": "Pelajari cara mengubah font selama konversi MHT menggunakan Aspose.Email untuk .NET. Ikuti panduan langkah demi langkah ini untuk kustomisasi yang mudah."
"linktitle": "Mengubah Kustomisasi Font MHT menggunakan C#"
"second_title": "API Pemrosesan Email Aspose.Email .NET"
"title": "Mengubah Kustomisasi Font MHT menggunakan C#"
"url": "/id/email/net/mastering-email-header-manipulation/changing-mht-font-customization/"
"weight": 11
---

## Perkenalan

Dalam dunia komunikasi web, berkas MHT (MHTML) merupakan cara praktis untuk menyimpan dan berbagi konten web, lengkap dengan gambar, tautan, dan gaya. Namun, apa yang terjadi jika Anda perlu mempercantik berkas MHT tersebut dengan mengubah font? Berkat Aspose.Email untuk .NET, tugas ini menjadi mudah. Dalam tutorial ini, kami akan memandu Anda langkah demi langkah melalui proses mengubah font selama konversi MHT. Baik Anda sedang mengembangkan aplikasi yang menangani pemformatan email atau hanya ingin menyesuaikan dokumen untuk bisnis Anda, panduan ini akan membekali Anda dengan pengetahuan yang dibutuhkan.

## Prasyarat

Sebelum menyelami kode, ada beberapa hal penting yang harus Anda persiapkan:

1. Visual Studio: Anda memerlukan lingkungan pengembangan terintegrasi (IDE) untuk mengerjakan proyek C# Anda.
2. Aspose.Email untuk Pustaka .NET: Pastikan Anda telah menginstal pustaka tersebut. Anda dapat mengunduhnya dari [link](https://releases.aspose.com/email/net/).
3. .NET Framework: Proyek Anda harus kompatibel dengan .NET Framework; biasanya, .NET Core atau versi yang lebih baru berfungsi dengan baik.

Sudah beres? Keren! Ayo kita mulai.

## Mengimpor Paket

Pertama-tama, pastikan proyek Anda telah diatur untuk menggunakan namespace yang diperlukan. Anda perlu menyertakan kode berikut di bagian atas berkas C# Anda:

```csharp
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Tools;
```

Paket-paket ini akan memberi Anda akses ke fungsionalitas yang dibutuhkan untuk bekerja dengan berkas MHT dan memodifikasi isinya.

Sekarang, mari kita uraikan langkah-langkah yang terlibat dalam mengubah font selama konversi MHT.

## Langkah 1: Muat File MHT

Hal pertama yang perlu Anda lakukan adalah memuat file MHT Anda ke dalam `MailMessage` objek. Di sinilah Anda dapat mengakses dan memanipulasi kontennya.

```csharp
MailMessage message = MailMessage.Load("input.mht", new MhtmlLoadOptions());
```

Penjelasan: Di sini, `"input.mht"` adalah jalur ke file MHT Anda. `MhtmlLoadOptions()` memungkinkan Anda mengonfigurasikan cara berkas dimuat, misalnya, menangani lampiran atau sumber daya tertaut secara berbeda.

## Langkah 2: Ulangi Melalui Tampilan Alternatif

Berkas MHT sering kali memiliki beberapa tampilan alternatif, terutama jika berisi konten HTML. Anda perlu mengulang tampilan-tampilan ini untuk menemukan tampilan yang ingin Anda ubah.

```csharp
foreach (var alternateView in message.AlternateViews)
{
    if (alternateView.ContentType.MediaType == "text/html")
    {
        var htmlView = (AlternateView)alternateView;
        var linkedResources = htmlView.LinkedResources;
```

Penjelasan: Anda sedang memeriksa setiap `AlternateView` untuk melihat apakah itu bertipe HTML. Jika ya, Anda dapat mengakses `LinkedResources`, tempat font apa pun yang ditautkan dalam HTML biasanya disimpan.

## Langkah 3: Identifikasi dan Kustomisasi Font

Sekarang setelah Anda memiliki akses ke sumber daya yang tertaut, Anda dapat mengidentifikasi sumber daya mana yang berupa font dan menyesuaikannya sesuai kebutuhan.

```csharp
foreach (var linkedResource in linkedResources)
{
    if (linkedResource.ContentType.MediaType == "application/x-font-ttf")
    {
        linkedResource.ContentType.Name = "Arial";  // Ubah ke font yang diinginkan
        linkedResource.TransferEncoding = TransferEncoding.Base64;  // Pastikan sudah dikodekan dengan benar
    }
}
```

Penjelasan: Perulangan ini memeriksa apakah tipe konten sumber daya yang ditautkan adalah font TrueType. Jika cocok, Anda dapat mengubah nama font sesuai keinginan (seperti "Arial" dalam contoh ini). `TransferEncoding` juga harus diatur untuk memastikan bahwa data font dikodekan dengan benar saat dokumen disimpan.

## Langkah 4: Simpan File MHT yang Diperbarui

Setelah menyesuaikan font, saatnya menyimpan berkas MHT yang telah dimodifikasi. Pastikan Anda menggunakan opsi penyimpanan yang tepat untuk menjaga integritas berkas.

```csharp
message.Save("output.mht", SaveOptions.DefaultMhtml);
```

Penjelasan: Pada baris kode ini, `"output.mht"` adalah nama file tempat Anda ingin menyimpan konten yang diperbarui. Menggunakan `SaveOptions.DefaultMhtml` memastikan bahwa file baru mempertahankan format MHT.

## Kesimpulan

Mengubah font dalam berkas MHT dapat meningkatkan tampilan dan nuansa dokumen Anda secara signifikan. Dengan memanfaatkan Aspose.Email untuk .NET, Anda dapat dengan mudah memuat berkas MHT, memodifikasi kontennya, dan menyimpan perubahan hanya dengan beberapa baris kode. Baik Anda mengerjakan proyek pribadi maupun aplikasi yang lebih besar, menguasai keterampilan ini dapat meningkatkan cara Anda menyajikan informasi.

## Pertanyaan yang Sering Diajukan

### Apa format MHT?
MHT adalah format arsip halaman web yang menyimpan dokumen HTML, gambar, dan sumber daya lainnya dalam satu file.

### Bisakah saya mengubah aspek lain dari file MHT menggunakan Aspose?
Tentu saja! Aspose.Email memungkinkan Anda memodifikasi hampir setiap aspek file MHT, termasuk lampiran, header, dan lainnya.

### Apakah Aspose.Email untuk .NET gratis?
Aspose menawarkan uji coba gratis, tetapi versi lengkapnya memerlukan lisensi. Anda bisa mendapatkan lisensi sementara dari [Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Email?
Anda dapat menemukan dokumentasi dan contoh yang lengkap di [Halaman dokumentasi Aspose Email](https://reference.aspose.com/email/net/).

### Bagaimana jika saya menemui masalah saat menggunakan Aspose?
Jika Anda menghadapi masalah, Anda dapat menghubungi dukungan di [Forum dukungan Aspose](https://forum.aspose.com/c/email/12/).