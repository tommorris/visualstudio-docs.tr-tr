---
title: VSPerfASPNETCmd ile Hızlı Web sitesi profili oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- proflilng tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 32078c69453a1d569fdba23313917759ff500bd6
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256077"
---
# <a name="rapid-web-site-profiling-with-vsperfaspnetcmd"></a>Profil oluşturma VSPerfASPNETCmd ile hızlı web sitesi

**VSPerfASPNETCmd** komut satırı aracı, kolayca profiline sağlar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulamaları. Comparison için [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı aracı seçenekleri azaltılmış, ortam değişkenleri ayarlanması gerekir ve bilgisayar yeniden başlatıldığı gerekli değildir. Kullanarak **VSPerfASPNETCmd** bağımsız Profil Oluşturucu ile profil oluşturma için tercih edilen yöntemdir. Daha fazla bilgi için bkz: [nasıl yapılır: bağımsız profil oluşturucuyu yükleme](../profiling/how-to-install-the-stand-alone-profiler.md).

> [!NOTE]
> Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

 Eşzamanlılık verileri toplama veya duraklatma ve sürdürme kullanarak profili oluşturma gibi bazı senaryolarda **VSPerfCmd** için tercih edilen profil yöntemdir.

> [!NOTE]
> Profil oluşturma araçları komut satırı araçları içinde bulunur *\Team Tools\Performance Araçları* Visual Studio yükleme dizininin alt. 64-bit bilgisayarlarda, 32-bit bulunan VSPerfASPNETCmd aracını *\Team Tools\Performance Araçları* dizin. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

## <a name="profile-an-aspnet-application"></a>Bir ASP.NET uygulamasını profil

Profil için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması, aşağıdaki bölümlerde açıklanan komutlardan birini yazın. Web sitesi başlatıldı ve verileri toplamak profil oluşturucu başlatır. Uygulamanızın çalışma ve tarayıcıyı kapatın. Profil oluşturmayı durdurmak için basın **Enter** komut istemi penceresinde anahtar.

> [!NOTE]
> Varsayılan olarak, sonra Komut İstemi'ni döndürmüyor bir **vsperfaspnetcmd** komutu. Kullanabileceğiniz **/nowait** dönmek için komut istemi zorlamak için seçeneği. Bkz: [/nowait seçeneğini kullanmak](#UsingNoWait).

## <a name="to-collect-application-statistics-by-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak uygulama istatistikleri toplamak için
 Örnekleme profili oluşturma yöntemi, varsayılan değerdir **VSPerfASPNETCmd** araç ve komut satırında belirtilmesi gerekmez. Aşağıdaki komut satırını belirtilen web uygulamasından uygulama istatistikleri toplar:

 **vsperfaspnetcmd**  *websiteUrl*

## <a name="to-collect-detailed-timing-data-by-using-the-instrumentation-method"></a>Ayrıntılı izleme metodunu kullanarak zamanlama verileri toplamak için

Ayrıntılı zamanlama verileri bir dinamik olarak derlenmiş toplamak için aşağıdaki komut satırını kullanın [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması:

**vsperfaspnetcmd/Trace***websiteUrl*

Statik olarak profil istiyorsanız derlenmiş. *dll* dosyaların web uygulamanızdaki, dosyaları kullanarak izleme gerekir [Vsınstr](../profiling/vsinstr.md) komut satırı aracı. Vsperfaspnetcmd/Trace komut Araçlı dosyalarından verileri içerir.

## <a name="to-collect-net-memory-data"></a>.NET bellek verileri toplamak için

**/Memory** seçeneğini nesneleri .NET bellek ayırma hakkında veri toplar ve bu nesnelerin ömrü hakkındaki verileri toplayabilir. Ayırma veri toplama olan varsayılan modunu **/Memory** veri seçeneği ve komut satırında belirtilmesi gerekmez.

 **vsperfaspnetcmd /memory** *websiteUrl*

 Kullanım **ömrü** nesne yaşam verisi ayrıca ayırma verilerini toplamak için parametre:

 **vsperfaspnetcmd /memory:lifetime** *websiteUrl*

 Aynı zamanda **/izleme** .NET bellek verileri ayrıntılı zamanlama bilgilerle ekleme seçeneği:

 **vsperfaspnetcmd /memory**[**: ömrü**]   **/izleme**`websiteUrl`

## <a name="to-collect-tier-interaction-data"></a>Katman etkileşim verileri toplamak için

> [!WARNING]
> Katman etkileşimli profil oluşturma (TIP) verilerini herhangi bir sürümünü Visual Studio kullanarak toplanabilir. Ancak, katman etkileşimli profil oluşturma verilerini, yalnızca Visual Studio kuruluş içinde görüntülenebilir.
>
> Windows 8 veya Windows Server 2012'de ipucu verileri toplamak için izlemeyi kullanın (**/izleme**) seçeneği.

Veri örnekleme ile Katman etkileşim verileri toplamak için:

**vsperfaspnetcmd /tip** `websiteUrl`

Katman etkileşim verileri ile izleme verileri toplamak için:

**vsperfaspnetcmd/Trace /tip** *websiteUrl*

Katman etkileşim verileri ile .NET bellek verileri toplamak için:

**vsperfaspnetcmd /memory**[**: ömrü**] *  */ipucu *** websiteUrl*

## <a name="use-the-nowait-option"></a>/ Nowait seçeneğini kullanın

Varsayılan olarak, sonra Komut İstemi'ni döndürmüyor bir **vsperfaspnetcmd** komutu. Döndürülecek komut istemi zorlamak için aşağıdaki söz dizimini seçeneğini kullanabilirsiniz. Ardından, komut istemi penceresinde diğer işlemler gerçekleştirebilirsiniz. Profil oluşturma sonlandırmak için kullanmak **shutdown** ayrı bir seçeneğinde **vsperfaspnetcmd** komutu.

Profil oluşturmayı başlatmak için:

**vsperfaspnetcmd** [*/seçenekleri*] *  */nowait *** websiteUrl*

Profil oluşturma sona erdirmek için:

**vsperfaspnetcmd shutdown** *websiteUrl*

## <a name="additional-options"></a>Ek Seçenekler

Aşağıdaki seçeneklerden birini dışında bu bölümde, daha önce listelenen komutları ekleyebileceğiniz **vsperfaspnetcmd shutdown** komutu.

|Seçenek|Açıklama|
|------------|-----------------|
|**/ Çıktı:** `VspFile`|Varsayılan olarak, profil oluşturma verileri (. *Vsp*) dosyası geçerli dizinde dosya adıyla oluşturulur **PerformanceReport.vsp**. Farklı bir konum, dosya adı veya her ikisini belirtmek için/Output seçeneği kullanın.|
|**/ Paket sembolleri: kapalı**|Varsayılan olarak, VsPerfASPNETCmd simgeler (işlev ve parametre adları ve benzeri) katıştırır. *vsp* dosya. Simgeler katıştırma profil oluşturma veri dosyası çok büyük hale getirebilirsiniz. Erişimi varsa. *pdb* verilerini analiz ederken, sembolleri içeren dosyaları /packsymbols kullanın: simgelerini katıştırma devre dışı bırakma seçeneği kapalı.|
