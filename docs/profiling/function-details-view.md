---
title: İşlev Ayrıntıları görünümü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.functiondetails
helpviewer_keywords:
- Function Details view
- Profiling Tools, Function Details view
ms.assetid: 8806954f-cf28-48d5-81b2-d722ceaf7d27
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a7ce7bfbe9d68a7edcc0711c1f7e954612e67d0c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31578315"
---
# <a name="function-details-view"></a>İşlev Ayrıntıları Görünümü
**İşlev Ayrıntıları görünümü** penceresinde aşağıdaki bilgiler görüntülenir:  
  
-   **Maliyet dağıtım** çubuk grafik seçili işlev adı veriliyordu tarafından işlevleri arasında ve seçtiğiniz bir işlev ile seçilen işlevi yürütülen işlevleri çağırma arasındaki ilişkileri temsil eder .  
  
-   **İşlevi performans ayrıntıları** belirttiğiniz işlevi için Özet profil oluşturma verilerini gösteren tablo.  
  
-   **İşlevi kod görünümü** penceresi kodu kullanılabilir olduğunda bu işlev kodu gösterir.  
  
 **İşlevi kod görünümü** ayrı bir bölme bir penceredir. Varsayılan olarak, iki bölmeleri yatay olarak ayrılır ve **işlevi kod görünümü** pencere çerçevesi alt kısmındaki konumlandırılır.  
  
-   İki dikey bölmeleri için tıklatın **bölünmüş ekran dikey** araç çubuğunda.  
  
-   Bölmeleri göreli boyutunu değiştirmek için çerçeveler arasında gölgeli kenarlık'ı tıklatın ve kenarlık farklı bir konuma sürükleyin.  
  
## <a name="cost-distribution-bar-chart"></a>Maliyet dağıtım çubuk grafiği  
  
### <a name="performance-metrics"></a>Performans ölçümleri  
 İçinde **performans ölçüm** aşağı açılan listesinde, hangi değerlerin görüntülenir belirtebilirsiniz. Profil oluşturma veri dosyasında kullanılan profil oluşturma yöntemi kullanılabilir değerleri bağlıdır. Adlar parantez içinde satır adlarıdır **işlevi performans ayrıntıları** tablo.  
  
### <a name="bar-chart"></a>Çubuk Grafiği  
 **İşlevleri çağırma**  
  
 **İşlevleri çağırma** çubuğu seçili işlevini çağırdı işlevleri gösterir. Seçili işlevi için performans ölçüm toplam değerini çağıran işleve katkı orantılı olarak arama işlevi içeriyor blok boyutunda olabilir.  
  
 Görünümde seçili işlevi yapmak için bir arama işlevi adını tıklatabilirsiniz.  
  
-   Listelemek için çok fazla işlevleri çağırma varsa, en küçük Katkıları işlevleriyle toplanır bir **diğer** bloğu. Tıklatın **diğer** seçili işlevinde tüm çağıran ve çağrılan işlevlerini görüntülemek için **arayan/Aranan görünümü** penceresi. Daha fazla bilgi için bkz: [arayan/Aranan görünümü](../profiling/caller-callee-view.md).  
  
-   Hiçbir işlevleri çağırma varsa veya işlevi bir iş parçacığı veya işlem girişi işlevinin ise bir **, üst yığın** blok görüntülenir.  
  
 **Seçili işlevi**  
  
 Seçili işlevi çubuğu çağrılan işlevlerin ve kod Katkıları seçili işlevinin toplam performans ölçüm seçili işlev gösterir. Proportion için çağrılan işlev veya işlev gövdesi içeriyor blok boyutu olan toplam değeri kendi katkısı seçili işlevi için performans ölçüsünün.  
  
 Görünümde seçili işlevi yapmak için çağrılan bir işlevin adını tıklatabilirsiniz.  
  
-   **Toplam** performans ölçüm seçili işlevi için bir değerdir.  
  
-   **İşlev gövdesi** bloğunu işlevinin gövdesini kodda doğrudan yürütülmesi oluştu performans ölçüm toplam değerini miktarını temsil eder.  
  
-   Seçili işlev tarafından çağrılan işlevleri bloklarında listelenir. Seçili işlevleri blok boyutunu toplam performans ölçümü çağrılan işlev oluştu seçili işlevi için miktarını temsil eder.  
  
-   Listelemek için çok fazla işlevleri çağırma varsa, en küçük Katkıları işlevleriyle toplanır bir **diğer** bloğu. Tıklatın **diğer** seçili işlevinde tüm çağıran ve çağrılan işlevlerini görüntülemek için **arayan/Aranan görünümü** penceresi. Daha fazla bilgi için bkz: [arayan/Aranan görünümü](../profiling/caller-callee-view.md).  
  
-   Hiçbir çağrılan işlevlerin varsa bir **alt, yığın** blok görüntülenir.  
  
## <a name="function-performance-details"></a>İşlev performans ayrıntıları  
 İşlev performans ayrıntıları tablo Özet verilerini seçili işlevi için performans ölçümleri sağlar. Hem değer hem de yüzde görünür. Grafik ve ayrıntıları görünür profil oluşturma verileri tablo belirt belirttiğiniz **performans ölçüm** listesi.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Özel**|-İşlev gövdesi yürütülmesi içinde oluşan performans ölçüm miktarı.|  
|**Çağrılarında**|-Seçili işlevini çağırdı işlevlerde oluştu performans ölçüm tutar.|  
|**Her ikisi de dahil toplam**|-Toplam **özel** ve **içinde çağrıları** değerleri.|  
  
## <a name="function-code-view"></a>İşlev kod görünümü  
 **İşlevi kod görünümü** penceresi kullanılabilir olduğunda kaynak kodunu listesini görüntüler. Diğer işlevleri çağırmak kaynak kod satırlarını yanındaki gölgeli bir sütun çağrılan işlev için performans ölçümü değerleri içerir. Kaynak kodu düzenlemek için kaynak kodu dosyasının bağlantısını tıklatın.  
  
## <a name="cost-distribution-bar-chart-values"></a>Maliyet dağıtım çubuk grafik değerleri  
  
### <a name="sampling"></a>Örnekleme  
 Aşağıdaki tabloda örnekleme yöntemini kullanarak toplanan profil oluşturma verileri için performans ölçüm listesindeki değerlerin açıklanmaktadır.  
  
|||  
|-|-|  
|**Kapsayıcı örnekleri (toplanan örnekleri)**|-Bir arama işlevi için seçilen işlevi çağırma bu işlev tarafından çağrıldığında, toplanan örnek sayısı.<br />-İşlev gövdesi için seçilen işlevi kendi kodu çalıştırırken, toplanan örnek sayısı.<br />-Çağrılan işlev için çağrılan işlev seçili işlev çağrısından nedeniyle yürütürken, toplanan örnek sayısı.|  
  
### <a name="instrumentation"></a>İzleme  
 Aşağıdaki tabloda izleme metodunu kullanarak toplanan profil oluşturma verileri için performans ölçüm listesindeki değerlerin açıklanmaktadır.  
  
|||  
|-|-|  
|**Geçen dahil süre (geçen süre)**|Geçen süre, bağlam anahtarlarının ve girdi/çıktı işlemleri gibi işletim sistemi çağrılarında harcanan zamanın içerir.<br /><br /> -İçin bir **işlevi çağırma**, işlev tarafından adı veriliyordu seçili işlevi örneklerini yürütme harcanan süre miktarı. Seçili işlev tarafından çağrılan işlevlerde geçen süre dahil edilir.<br />-İçin **işlev gövdesi**, geçen süre toplam miktarı harcanan seçili işlevi kodu çalıştırma. Çağrılan işlevlerde geçen süre dahil değildir.<br />-Adlı bir işlev için tutar seçili işlevin adı veriliyordu işlevi örneklerini yürütme için harcanan süre. Toplam harcanan zamanın işlevini çağırdı işlevlerde içerir. Seçili işlev tarafından çağrılan işlevlerde geçen süre dahil edilir.|  
|**Uygulama dahil saati (uygulama)**|Uygulama zamanı bağlam anahtarlarının ve girdi/çıktı işlemleri gibi işletim sistemi çağrılarında harcanan zamanın içermez.<br /><br /> -İçin bir **işlevi çağırma**, işlev tarafından adı veriliyordu seçili işlevi örneklerini yürütme harcandığını uygulama süre miktarı. Seçili işlev tarafından çağrılan işlevlerde geçen süre dahil edilir.<br />-İçin **işlev gövdesi**, toplam uygulama harcanan zaman seçili işlevi kodu çalıştırma. Çağrılan işlevlerde geçen süre dahil değildir.<br />-Adlı bir işlev için tutar uygulama tarafından seçilen işlevi adı veriliyordu işlevi örneklerini yürütme için harcanan süre. Toplam harcanan zamanın işlevini çağırdı işlevlerde içerir.|  
  
### <a name="net-memory"></a>.NET bellek  
 Aşağıdaki tabloda .NET bellek profili oluşturma yöntemi kullanılarak toplanan profil oluşturma verileri için performans ölçüm listesindeki değerlerin açıklanmaktadır.  
  
|||  
|-|-|  
|**Kapsayıcı ayırmaları (ayırmaları)**|-İçin bir **işlevi çağırma**, işlevini çağırdı seçili işlevi örnekleri tarafından ayrılan nesne sayısı. Seçili işlevini çağırdı işlevleri tarafından ayrılan nesnelerin sayısını içerir.<br />-İçin **işlev gövdesi**, tarafından ayrılan nesne sayısını kendi kodu çalıştırırken seçili işleve göre. Seçili işlev tarafından çağrılan işlevlerinde ayrılmış nesneleri dahil edilmez.<br />-Çağrılan işlev için seçilen işlevin adı veriliyordu işlevi örnekleri tarafından ayrılan nesne sayısı. İşlevi çağrıldığında işlevleri tarafından ayrılan nesnelerin sayısını içerir.|  
|**Kapsayıcı bayt (bayt)**|-İçin bir **işlevi çağırma**, işlevini çağırdı seçili işlevi örnekleri tarafından ayrılan bayt sayısı. Seçili işlevini çağırdı işlevleri tarafından ayrılan bayt sayısını içerir.<br />-İçin **işlev gövdesi**, kendi kodu çalıştırırken, seçili işlevi tarafından ayrılan bayt toplam sayısı. Seçili işlev tarafından çağrılan işlevlerinde ayrılan bayt dahil edilmez.<br />-Çağrılan işlev için seçilen işlevin adı veriliyordu işlevi örnekleri tarafından ayrılan bayt sayısı. İşlevi çağrıldığında işlevleri tarafından ayrılan bayt sayısını içerir.|  
  
### <a name="concurrency"></a>Eşzamanlılık  
 Aşağıdaki tabloda eşzamanlılık yöntemi kullanılarak toplanan profil oluşturma verileri için performans ölçüm listesindeki değerlerin açıklanmaktadır.  
  
|||  
|-|-|  
|**Kapsayıcı çekişmeleri (çekişmeleri)**|-İçin bir **işlevi çağırma**, işlevini çağırdı seçili işlevi durumlarda oluştu kaynak Çekişme olayları sayısı. Çekişme olayları seçili işlevini çağırdı işlevlerde içerir.<br />-İçin **işlev gövdesi**, işlev kendi kod yürütülürken oluşan Çekişme olayları toplam sayısı. Seçili işlevi tarafından adı veriliyordu işlevlerinde gerçekleşen çekişmeleri dahil edilmez.<br />-Çağrılan işlev için seçilen işlevin adı veriliyordu işlevi örneklerini oluştu Çekişme olayları sayısı. Sayı oluştu Çekişme olayları işlevini çağırdı işlevlerde içerir.|  
|**Kapsayıcı saati (engellenen) engellendi**|-Bir arama işlevi için kaynak harcanan zamanın Çekişme olayları seçili örnekleri için işlev işlevini çağırdı. Zaman engellenen zaman adlı işlevi seçili işlevlerde içerir.<br />-İçin **işlev gövdesi**, işlev kendi kod yürütülürken oluşan Çekişme olayları harcanan toplam süre. Seçili işlevini çağırdı işlevlerde gerçekleşen çekişmeleri dahil edilmez.<br />-Çağrılan işlev için kaynak çakışması olaylarda seçili işlevini çağırdı işlevi örnekleri için harcanan süre. Zaman oluştu engellenen zaman işlevini çağırdı işlevlerde içerir.|