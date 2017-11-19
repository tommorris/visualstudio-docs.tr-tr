---
title: "VSPerfASPNETCmd ile Hızlı Web sitesi profili oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- proflilng tools,VSPerfASPNETCmd
- VSPerfASPNETCmd
ms.assetid: 9a9d62a6-549a-45ac-a948-76eb98586ac5
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a1f2bc5acb69aa49fb37713942edb4e018039e8a
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="rapid-web-site-profiling-with-vsperfaspnetcmd"></a>VSPerfASPNETCmd ile Hızlı Web Sitesi Profili Oluşturma
**VSPerfASPNETCmd** komut satırı aracı, kolayca profiline sağlar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamaları. Comparison için [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı aracı seçenekleri azaltılmış, ortam değişkenleri ayarlanması gerekir ve bilgisayar yeniden başlatıldığı gerekli değildir. Kullanarak **VSPerfASPNETCmd** bağımsız Profil Oluşturucu ile profil oluşturma için tercih edilen yöntemdir. Daha fazla bilgi için bkz: [nasıl yapılır: tek başına profil oluşturucuyu yükleme](../profiling/how-to-install-the-stand-alone-profiler.md).  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Eşzamanlılık verileri toplama veya duraklatma ve sürdürme kullanarak profili oluşturma gibi bazı senaryolarda **VSPerfCmd** için tercih edilen profil yöntemdir.  
  
> [!NOTE]
>  Profil oluşturma araçları komut satırı araçları \Team Tools\Performance araçları alt dizininde bulunan [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yükleme dizini. 64 bit bilgisayarlarda, 32 bit \Team Tools\Performance Tools dizininde bulunan VSPerfASPNETCmd aracını kullanın. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresini PATH ortam değişkenine ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
## <a name="profiling-an-aspnet-application"></a>Bir ASP.NET uygulamasını profil oluşturma  
 Profil için bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, aşağıdaki bölümlerde açıklanan komutlardan birini yazın. Web sitesi başlatıldı ve verileri toplamak profil oluşturucu başlatır. Uygulamanızın çalışma ve tarayıcıyı kapatın. Profil oluşturmayı durdurmak için komut istemi penceresinde Enter tuşuna basın.  
  
> [!NOTE]
>  Varsayılan olarak, sonra Komut İstemi'ni döndürmüyor bir **vsperfaspnetcmd** komutu. Kullanabileceğiniz **/nowait** dönmek için komut istemi zorlamak için seçeneği. Bkz: [/nowait seçeneği kullanılarak](#UsingNoWait).  
  
## <a name="to-collect-application-statistics-by-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak uygulama istatistikleri toplamak için  
 Örnekleme profili oluşturma yöntemi, varsayılan değerdir **VSPerfASPNETCmd** araç ve komut satırında belirtilmesi gerekmez. Aşağıdaki komut satırını belirtilen Web uygulamasından uygulama istatistikleri toplar:  
  
 **vsperfaspnetcmd***websiteUrl*   
  
## <a name="to-collect-detailed-timing-data-by-using-the-instrumentation-method"></a>Ayrıntılı izleme metodunu kullanarak zamanlama verileri toplamak için  
 Ayrıntılı zamanlama verileri bir dinamik olarak derlenmiş toplamak için aşağıdaki komut satırını kullanın [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması:  
  
 **vsperfaspnetcmd/Trace***websiteUrl*   
  
 Statik olarak derlenmiş .dll dosyaları, Web uygulamanızda profil isterseniz, kullanarak dosyaları izleme gerekir [Vsınstr](../profiling/vsinstr.md) komut satırı aracı. Vsperfaspnetcmd/Trace komut Araçlı dosyalarından verileri içerir.  
  
## <a name="to-collect-net-memory-data"></a>.NET bellek verileri toplamak için  
 **/Memory** seçeneğini nesneleri .NET bellek ayırma hakkında veri toplar ve bu nesnelerin ömrü hakkındaki verileri toplayabilir. Ayırma veri toplama olan varsayılan modunu **/Memory** veri seçeneği ve komut satırında belirtilmesi gerekmez.  
  
 **vsperfaspnetcmd /memory** *websiteUrl*  
  
 Kullanım **ömrü** nesne yaşam verisi ayrıca ayırma verilerini toplamak için parametre:  
  
 **vsperfaspnetcmd /memory:lifetime** *websiteUrl*  
  
 Aynı zamanda **/izleme** .NET bellek verileri ayrıntılı zamanlama bilgilerle ekleme seçeneği:  
  
 **vsperfaspnetcmd /memory**[**: ömrü**]   **/izleme**`websiteUrl`  
  
## <a name="to-collect-tier-interaction-data"></a>Katman etkileşim verileri toplamak için  
  
> [!WARNING]
>  Katman etkileşimli profil oluşturma (TIP) verilerini kullanarak toplanmasını [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], veya [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)]. Ancak, katman etkileşimli profil oluşturma verilerini yalnızca görüntülenebilir [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] ve [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
>   
>  Windows 8 veya Windows Server 2012'de ipucu verileri toplamak için izlemeyi kullanın (**/izleme**) seçeneği.  
  
 Veri örnekleme ile Katman etkileşim verileri toplamak için:  
  
 **vsperfaspnetcmd /tip**`websiteUrl`  
  
 Katman etkileşim verileri ile izleme verileri toplamak için:  
  
 **vsperfaspnetcmd/Trace /tip** *websiteUrl*  
  
 Katman etkileşim verileri ile .NET bellek verileri toplamak için:  
  
 **vsperfaspnetcmd /memory**[**: ömrü**] **/İpucu***websiteUrl*  
  
##  <a name="UsingNoWait"></a>/ Nowait seçeneğini kullanma  
 Varsayılan olarak, sonra Komut İstemi'ni döndürmüyor bir **vsperfaspnetcmd** komutu. Döndürülecek komut istemi zorlamak için aşağıdaki söz dizimini seçeneğini kullanabilirsiniz. Ardından, komut istemi penceresinde diğer işlemler gerçekleştirebilirsiniz. Profil oluşturma sonlandırmak için kullanmak **shutdown** ayrı bir seçeneğinde **vsperfaspnetcmd** komutu.  
  
 Profil oluşturmayı başlatmak için:  
  
 **vsperfaspnetcmd** [*/seçenekleri*] **/nowait***websiteUrl*  
  
 Profil oluşturma sona erdirmek için:  
  
 **vsperfaspnetcmd shutdown** *websiteUrl*  
  
## <a name="additional-options"></a>Ek Seçenekler  
 Aşağıdaki seçeneklerden birini dışında bu bölümde, daha önce listelenen komutları ekleyebileceğiniz **vsperfaspnetcmd shutdown** komutu.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Çıkış:**`VspFile`|Varsayılan olarak, profil oluşturma veri (.vsp) dosyası geçerli dizinde dosya adıyla oluşturulur **PerformanceReport.vsp**. Farklı bir konum, dosya adı veya her ikisini belirtmek için/Output seçeneği kullanın.|  
|**/ Paket sembolleri: kapalı**|Varsayılan olarak, VsPerfASPNETCmd simgeler (işlev ve parametre adları, vb.) .vsp dosyasında katıştırır. Simgeler katıştırma profil oluşturma veri dosyası çok büyük hale getirebilirsiniz. Verileri analiz ederken, sembolleri içeren .pdb dosyaları erişim olacaksa, /packsymbols kullanın: simgelerini katıştırma devre dışı bırakma seçeneği kapalı.|
