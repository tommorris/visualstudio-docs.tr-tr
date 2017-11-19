---
title: "Sembol bilgilerini performans veri dosyalarıyla kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- packsymbols, in profiling tools reports
- profiling tools, packsymbols
ms.assetid: 8b802505-e94d-4ee0-83e4-fdd790a332c1
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89913922d4c806e591d6a488f35242444d16ceb0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="saving-symbol-information-with-performance-data-files"></a>Performans veri dosyalarıyla kaydetme sembol bilgileri
Kullanıyorsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) dosyaları analiz etmek ve planlama VSP dosyanızı farklı bir bilgisayara taşımak, proje ayarları kaydetmek için performansı ayarlayın veya *seri* içinde simgeleri Rapor dosyanız. Bu rapor dosyasının boyutu artar. Simgeler seri hale getirme iki nedenlerle gereklidir:  
  
-   Katıştırmak için hedef derlemeleri önce bir performans raporu kod simgeleri geçici depolama alanına konumlarından kaybolur.  
  
-   Böylece performans raporu profili bilgisayardan taşınabilir ve farklı simgeleri olabilir başka bir bilgisayarda analiz raporu açtıysanız aynı bilgileri çıkartır sembolleri korumak için.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Simgeler serileştirebilen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE veya komut satırından:  
  
-   Sembolleri serileştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE, noktasına **Araçları** menü çubuğu ve ardından **seçenekleri**. İçinde **seçenekleri** penceresinde, seçin **performans araçları**ve ardından **otomatik olarak sembol bilgilerini serileştirme** onay kutusu.  
  
-   Paket SEMBOLLERİ eşdeğer komut satırı seçeneği olduğunda rapor dosyalarını kaydedin. Simgeler seri hale getirmek için şunu yazın **vsperfreport /summary:all /packsymbols filename.vsp**.  
  
## <a name="troubleshooting-symbol-problems"></a>Sembol sorunlarını giderme  
 Kendi kodunuzu semboller görmüyorsanız, bazı yaygın çözümleri kullanılabilir:  
  
-   Vsperfreport /debugsympath konumların tam bir listesini görüntülemek için komut satırında sembol bilgilerini profil oluşturucu bileşenleri burada yüklüyorsunuz ve kullanılan simge dosyaları projenizi kullanarak dosyaları olup olmadığını eşleşen çalıştırın.  
  
-   Vsperfreport /PACKSYMBOLS bayrağı ya da çalıştırdığınızdan emin olun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] genel performans explorer seçeneklerinde serileştirme sembol bilgileri seçeneğe sahip IDE.  
  
-   Tür veri toplanan /SUMMARY:TYPE vsperfreport komut satırı ekleyin.  
  
 Windows veya başka Microsoft programlarını simgeleri görmüyorsanız:  
  
-   Windows simgesi önbelleğiniz yolunu ayarladığınızdan emin olun. Sembol önbellek yolunu ayarlayabilir için aşağıdakilerden birini yapın:  
  
    -   Set hata ayıklayıcı -> sembolleri seçeneğini [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] doğru yola IDE.  
  
    -   -Symbolpath seçeneği, simgeler eklemek için VSPerfReport komut satırı ekleyin.  
  
-   Semboller görmüyorsanız [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], ASP sunucu için doğru ayarlanmış simge sunucusu olduğundan emin olun.  
  
## <a name="repacking-symbols"></a>Repacking simgeleri  
 Simge bir rapora yeniden paketleyin istiyorsanız, VsPerfReport komut satırı aracını kullanarak bunu yapabilirsiniz. Aşağıdaki komut satırlarını kullanın:  
  
 VsPerfReport - clearpackedsymbols filename.vsp  
  
 VsPerfReport - paket sembolleri-özeti: tüm filename.vsp  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araçları verilerini kaydetme ve performans dışarı aktarma](../profiling/saving-and-exporting-performance-tools-data.md)   
 [Nasıl yapılır: başvuru pencereleri sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md)   
 [VSPerfReport](../profiling/vsperfreport.md)