---
title: "Performans Raporu genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, about performance rerports
- performance, reports
- performance reports, about performance reports
ms.assetid: 7324c24c-fd09-479b-b2ad-e0c3b613e040
caps.latest.revision: "45"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0244cbae9a331303434db89a42518812efc2677b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="performance-report-overview"></a>Performans Raporu genel bakış
Profil oluşturma verileri performans oturumun görüntüleyebilirsiniz **performans raporu** Visual Studio Team System geliştirme sürümü tümleşik geliştirme ortamı (IDE) penceresi. Profil oluşturma verileri .vsp ve .vsps dosyalarında kaydedilir. Rapor görünümü windows görüntülemek ve uygulama performans sorunları çözümlemek etkinleştirin.  
  
> [!CAUTION]
>  Profil oluşturma veri dosyası, bilgisayar adı gibi hassas bilgileri, işletim sistemi, dosya yolları, bellek bilgileri ve diğer bilgisayar kurulum bilgileri sürümünü içerir. Dağıtım hem yerel .vsp biçimiyle hem de bir .csv veya bir .xml dosyasına dışarı aktardığınızda verilerin katı denetime korumanız gerekir.  
>   
>  Olay izleme verileri performans oturumun bir parçası olarak toplanır, olay izleme (.etl) günlük dosyası ek bilgi görünebilir. Bu bilgiler, etki alanı ve kullanıcı adınızı içerir; Bu nedenle, günlük dosyasının dağıtım katı denetime korumanız gerekir.  
  
## <a name="performance-report-window"></a>Performans Raporu penceresi  
 Performans rapor penceresini görüntülemek, yönetmek ve performans verilerini filtrelemek için kullanılan bir araç penceresi ve özelleştirilebilir sorgu denetimi içerir.  
  
 Performans rapor penceresini ana araç çubuğunda her görünüm erişebilir. Yanındaki oka tıklayın **Geçerli Görünüm** listesini görüntülemek ve kullanılabilir tek bir görünüm seçin.  
  
 Performans Raporu penceresi aşağıdaki veri görünümleri sağlar:  
  
### <a name="summary-view"></a>Özet Görünümü  
 Varsayılan olarak, profil oluşturma verilerini Özet görünümünde görüntülenir. Bu görünüm, performans sorunlarını araştırmasını bir başlangıç noktasıdır. Özet görünümünde her satırında, işlev veya modül adını sağ tıklayarak daha ayrıntılı görünümler taşıyabilirsiniz. Daha fazla bilgi için bkz: [özeti görünümü](../profiling/summary-view.md).  
  
### <a name="callercallee-view"></a>Arayan/Aranan görünümü  
 Arayan/Aranan görünümü tek bir işlevi için bir çağrı ağacı görüntüler. Görünüm, üç bölüme ayrılır:  
  
-   Hedef işlevi ortasında görünümü görüntülenir.  
  
-   (Arayanlar) işlevini çağırdı işlevleri hedef işlevi görüntülenir.  
  
-   Hedef işlev (callees) tarafından çağrılan işlevleri hedefin altında görüntülenir.  
  
 Çağrılan listesi veya Aranan listedeki herhangi bir işlev çift tıklayarak farklı bir işlevi seçebilirsiniz. Daha fazla bilgi için bkz: [arayan/Aranan görünümü](../profiling/caller-callee-view.md).  
  
### <a name="call-tree-view"></a>Çağrı Ağacı Görünümü  
 Çağrı ağacı görünümü profili uygulamada geçiş işlevi yürütme yollarını görüntüler. Ağaç kökü uygulamanın veya bileşenin içine giriş noktasıdır. Her işlevi düğüm tüm adlı işlevleri ve bu işlev çağrıları hakkında performans verilerini listeler.  
  
 Çağrı ağacı görünümü de genişletin ve en uzun süre tüketilen veya sık örneklenen bir işlev yürütme yolunu vurgulayın. En etkin yol görüntülenecek işlevi sağ tıklayın ve ardından **genişletin etkin yolunuzda**. Daha fazla bilgi için bkz: [çağrı ağacı görünümü](../profiling/call-tree-view.md).  
  
### <a name="process-view"></a>İşlem Görünümü  
 İşlem görünümü her işlemi ve profili iş parçacığı için performans verilerini görüntüler. Daha fazla bilgi için bkz: [işlem görünümü](../profiling/process-view.md).  
  
### <a name="modules-view"></a>Modüller Görünümü  
 Modüller görünümü projeye modüllerini listeler ve her modül için profil oluşturma verileri sunar. Genişlet veya Daralt işlevi profil oluşturma verilerini görüntülemek için modül adı. Profil oluşturma verilerini kaynak kodu satır ve yönerge işaretçisi ayrıca veri örnekleme kullanarak toplanan olduğunda kullanılabilir. Daha fazla bilgi için bkz: [modüller görünümü](../profiling/modules-view.md).  
  
### <a name="functions-view"></a>İşlevler Görünümü  
 İşlevler görünümü profil oluşturma sırasında adı veriliyordu işlevleri listeler. Daha fazla bilgi için bkz: [işlevler görünümü](../profiling/functions-view.md).  
  
### <a name="line-view"></a>Satır görünümü  
 Satırlar görünümü örnekleme profili oluşturma sırasında yürütüldü belirli bir kaynak kod satırları görüntülemenizi sağlar. Daha fazla bilgi için bkz: [satırlar görünümü](../profiling/lines-view.md).  
  
### <a name="instruction-pointer-ip-view"></a>Yönerge işaretçisi (IP) görünümü  
 Yönerge işaretçisi görünümünü örnekleme profili oluşturma sırasında yürütüldü özel yönergeler görüntülemenizi sağlar. Daha fazla bilgi için bkz: [yönerge işaretçileri (IP) görünümü](../profiling/instruction-pointers-ips-view.md).  
  
### <a name="allocation-view"></a>Ayırma görünümü  
 Ayırma görünümü kullanılabilir değilse **toplamak .NET nesne ayırma** üzerinde seçilmedi **genel** sayfasında **Performans oturumunu** Özellikleri iletişim kutusu. Bkz: [performans oturumuna genel bakış](../profiling/performance-session-overview.md). Ayırma görünümü uygulama veya bileşen tarafından ayrılan .NET nesneleri listeler. Bir nesne satır genişletildiğinde çağrı ağacı görüntülenir. Çağrı ağacı nesne oluşturulmasında sonuçlandı yürütme yolları gösterilmektedir. Her işlev çağrısı ağacında (bunlar dahil) ve özel ayırmalarının sayısı hakkında bilgiler de görüntülenir. Ayırma görünümü de genişletin ve en büyük sayı nesnelerin ayrılmış bir işlevin yürütme yolu vurgulayın. En etkin yol görüntülenecek işlevi sağ tıklayın ve ardından **genişletin etkin yolunuzda**. Daha fazla bilgi için bkz: [toplama .NET bellek ayırma ve yaşam verisi](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md) ve [ayırmalar görünümü](../profiling/dotnet-memory-allocations-view.md).  
  
### <a name="objects-lifetime-view"></a>Nesne ömrü görünümü  
 Nesne ömrü görünümü kullanılabilir değilse **toplamak .NET nesne ayırma bilgileri** ve **ayrıca .NET nesne ömrü bilgileri toplamak** üzerinde seçilmedi **genel**sayfasında **Performans oturumunu** Özellikleri iletişim kutusu.  
  
 Nesne ömrü görünümü her çöp koleksiyonu oluşturma toplanmış olan nesneleri sayısını ve her türdeki örneklerin toplam sayısını görüntüler. Daha fazla bilgi için bkz: [nesne ömrü görünümü](../profiling/object-lifetime-view.md).  
  
## <a name="customizable-filter-control"></a>Özelleştirilebilir filtre denetimi  
 Özelleştirilebilir filtre denetimi aşağıdaki seçenekler vardır:  
  
-   **Alma filtresi** -önceden kaydedilmiş özel bir sorgu alır.  
  
-   **Filtre verme** -özel sorgu belirtilen konuma kaydeder.  
  
-   **Sorguyu yürütmek** -sorgu özel sorgu denetiminde gösterilen gibi çalışır.  
  
-   **Sorguyu durdurmak** -çalıştıran bir sorgu yürütme durdurur. Bu düğme hiçbir sorgu çalışıyorsa kullanılabilir değil.  
  
-   **Sorgu Göster** -özel sorgu denetim gösterir/gizler.  
  
-   **Analyzed kaydetmek** -raporu geçerli çözümlenmesi birlikte .vsps dosyası olarak kaydeder.  
  
-   **Dışarı aktarma** -geçerli raporda kaydeder. CVS biçimlendirilmiş veya. XML biçimli dosya için farklı görünümleri kaydetmek için seçeneklere sahip.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araçları verilerini performansını analiz etme](../profiling/analyzing-performance-tools-data.md)   
 [Performans rapor görünümleri](../profiling/performance-report-views.md)