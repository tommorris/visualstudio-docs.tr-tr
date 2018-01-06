---
title: "Nasıl yapılır: Koleksiyon yöntemleri seçme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, choosing collection method
- profiling tools, choosing collection method
- performance collection methods
ms.assetid: c87cfd3a-0fc7-49ae-9c05-d8480891cc63
caps.latest.revision: "34"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ff646066c4e29c46c7ad3c24322d368fa54da9eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-choose-collection-methods"></a>Nasıl yapılır: Koleksiyon Metotları Seçme
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Destek performans verilerini toplama üç yöntem profil oluşturma araçları: örnekleme, araçları ve eşzamanlılık. .NET bellek ayırma ve yaşam süresi verilerini toplamak için örnekleme veya araçları yöntemi de kullanabilirsiniz.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Performans oturumu kullanabilirsiniz **yöntemi** özelliği, uygulamanız için en uygun koleksiyonu yöntemi belirtin. Performans Sihirbazı, performans Gezgini ya da bir performans oturumu özellik sayfalarından koleksiyonu yöntemi ayarlayabilirsiniz. Komut satırı araçları kullanıyorsanız bkz [komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md) daha fazla bilgi için.  
  
## <a name="performance-wizard"></a>Performans Sihirbazı  
  
#### <a name="to-select-a-collection-method-using-the-performance-wizard"></a>Performans Sihirbazı'nı kullanarak bir koleksiyon yöntemi seçmek için  
  
-   Sihirbazın ilk sayfasında aşağıdaki seçeneklerden birini seçin:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**CPU örnekleme**|İlk çözümleme ve CPU kullanımı sorunları çözümlemek için yararlı olan uygulama istatistikleri toplar.|  
|**İzleme**|Odaklı analiz ve giriş/çıkış performans sorunlarını çözümlemek için yararlı olan ayrıntılı zamanlama verileri toplar.|  
|**.NET bellek ayırma**|Toplar [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] örnekleme profili oluşturma yöntemi kullanarak bellek ayırma verileri.|  
|**Eşzamanlılık**|Sayısal kaynak çakışması veri toplar.|  
  
## <a name="performance-explorer"></a>Performans Gezgini  
  
#### <a name="to-select-a-collection-method-using-performance-explorer"></a>Performans Gezgini kullanarak bir koleksiyon yöntemi seçmek için  
  
1.  Üzerinde **performans Gezgini** araç yanındaki oka tıklayın **yöntemi** aşağı açılan liste.  
  
2.  Tercih ettiğiniz koleksiyonu yöntemi tıklatın.  
  
## <a name="performance-session-property-pages"></a>Performans oturumu özellik sayfaları  
  
#### <a name="to-select-the-sampling-or-instrumentation-method-using-performance-session-properties"></a>Performans oturum özellikleri kullanarak örnekleme veya araçları yöntemini seçmek için  
  
1.  İçinde **performans Gezgini**, performans oturumu seçin.  
  
     Bir performans oturumu dosya adı .psess uzantısına sahiptir.  
  
2.  Performans oturumu sağ tıklatın ve ardından **özellikleri**.  
  
3.  İçinde **özellik sayfaları**, tıklatın **genel**.  
  
4.  Tercih ettiğiniz koleksiyonu yöntemi tıklatın.  
  
    -   Örnekleme verileri toplarken kullanılabilen diğer seçenekler hakkında daha fazla bilgi için bkz: [tarafından örnekleme kullanarak performans istatistikleri toplama](../profiling/collecting-performance-statistics-by-using-sampling.md)  
  
    -   Örnekleme verileri toplarken kullanılabilen diğer seçenekler hakkında daha fazla bilgi için bkz: [tarafından araçları kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md).  
  
#### <a name="to-select-net-memory-data-collection-by-using-performance-session-properties"></a>Performans oturum özellikleri kullanarak .NET bellek verileri toplama seçmek için  
  
1.  İçinde **performans Gezgini**, performans oturumu seçin.  
  
     Bir performans oturumu dosya adı .psess uzantısına sahiptir.  
  
2.  Performans oturumu sağ tıklatın ve ardından **özellikleri**.  
  
3.  İçinde **özellik sayfaları**, tıklatın **genel**.  
  
4.  Tıklatın **örnekleme** veya **Araçları**.  
  
5.  Tıklatın **toplamak .NET nesne ayırma bilgileri** sayısı ve boyutu toplamak için [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] nesne ayırma.  
  
6.  (İsteğe bağlı) Tıklatın **ayrıca .NET nesne ömrü bilgileri toplamak** içinde nesne belleği geri atık toplama nesli hakkında veri toplamak üzere.  
  
     .NET bellek verileri toplarken kullanılabilen diğer seçenekler hakkında daha fazla bilgi için bkz: [toplama .NET bellek ayırma ve yaşam verisi](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md).  
  
#### <a name="to-select-concurrency-data-collection-by-using-performance-session-properties"></a>Performans oturum özellikleri kullanarak eşzamanlılık verileri toplama seçmek için  
  
1.  İçinde **performans Gezgini**, performans oturumu sağ tıklatın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları**, tıklatın **genel**.  
  
3.  Tıklatın **eşzamanlılık**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)   
 [Performans oturum özellikleri](../profiling/performance-session-properties.md)