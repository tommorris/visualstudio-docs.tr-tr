---
title: Visual Studio UWP uygulamalarında ağ kullanımını analiz | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 45fa397d-d7a1-4c4c-9c97-ede6c21643bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a41e41b4448bcec34a24464f4f62e85d0765436d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="analyze-network-usage-in-uwp-apps"></a>UWP uygulamalarında ağ kullanımını çözümleme
Visual Studio **ağ** Tanılama aracı kullanılarak yapılan ağ işlemleri hakkındaki verileri toplar [Windows.Web.Http API](/uwp/api/windows.web.http). Verileri çözümleme, erişim ve kimlik doğrulama sorunları, yanlış önbellek kullanımı ve görüntü gibi sorunları gidermek ve performans indirme yardımcı olabilir.  
  
 Ağ aracı yalnızca UWP uygulamaları destekler. Diğer platformlar şu anda desteklenmiyor.  
  
> [!NOTE]
>  Ağ aracı daha eksiksiz bir açıklaması için bkz: [Tanıtımı Visual Studio'nun Ağ aracı](http://blogs.msdn.com/b/visualstudio/archive/2015/05/04/introducing-visual-studios-network-tool.aspx).  
  
## <a name="collecting-network-tool-data"></a>Ağ aracı verileri toplama  
 Çalışması gerektiğini **ağ** Visual Studio bilgisayarda açık bir Visual Studio projesi aracıyla.  
  
1.  Projesini Visual Studio'da açın.  
  
2.  Menüsünde **hata ayıklama / Performans Profil Oluşturucu...** . Seçin **ağ**ve ardından **Başlat**.  
  
3.  Ağ aracı, uygulamanızın HTTP trafiği toplamaya başlar.  
  
     Uygulamanızı çalıştırma gibi sol bölmede Özet görünümü otomatik olarak yakalanan HTTP işlemleri listesini görüntüler. Ayrıntılar bölmesini sağ bölmede, daha fazla bilgi için Özet görünümde bir öğe seçin.  
  
4.  Seçin **durdurmak** uygulamayı kapatın.  
  
 Rapor penceresinde aşağıdakine benzer görünmelidir:  
  
 ![Ağ penceresi](../profiling/media/network_fullwindow.png "NETWORK_FullWindow")  
  
## <a name="analyzing-data"></a>Veri çözümleme  
 Uygulamanızı çalışırken ya da bile uygulama, Özet görünümünde görüntülenen ağ işlemlerden birini seçerek kapatıldıktan sonra yakalanan HTTP trafiği analiz edebilirsiniz.  
  
 **Ağ** Özet görünümü, uygulamanızın Çalıştır her ağ işlemi için verileri gösterir. Sıralamak için sütun başlığını seçin veya görüntülemek için içerik türlerini seçin **içerik türü** filtre görünümü.  
  
 Seçin **HAR Kaydet** Fiddler gibi üçüncü taraf araçları tarafından kullanılabilecek bir JSON dosyası oluşturmak için.  
  
 **Ağ** ayrıntıları görünümlerini Özet görünümünde bir ağ işlemi hakkında daha fazla bilgi görüntüler.  
  
 ![Ağ aracı Ayrıntılar bölmesinde](../profiling/media/network_detailsviewpane.png "NETWORK_DetailsViewPane")  
  
|||  
|-|-|  
|**Üstbilgileri**|Olay istek üstbilgileri hakkında bilgi.|  
|**Gövde**|İstek ve yanıt yükü veriler.|  
|**Parametreler**|Sorgu dizesi parametresi adları ve değerleri.|  
|**Çerezler**|Yanıt ve istek tanımlama bilgisi verileri.|  
|**Zamanlamaları**|Seçili kaynaklardan alınırken içinde aşamaları bir grafik.|  
  
 Ağ **Özet** çubuğunu gösterir ne kadar verinin aktarıldığı, belirli bir anda, görüntülenen ağ işlemlerinin sayısı sürdü bunları ve kaç tane hataları (istekleriyle 4xx veya 5xx yanıtlarını) indirmek için ne kadar süre görünür.  
  
### <a name="analysis-tips"></a>Analiz ipuçları  
 Bu aracı vurgular çalıştırırken, yararlı olabilecek belirli alanları ağ analiz ilgili:  
  
1.  Önbellekten tam olarak sunulan istekleri olarak gösterilir **(önbelleğinden)** içinde **alınan** sütun. Bu önbellek etkili bir şekilde kullanıcı bant genişliğinden tasarruf için kullanmanıza veya yanıtlarını yanlışlıkla önbelleğe alma ve uygulamanızın güncel olmayan verileri ile son kullanıcı sağlama belirlemenize yardımcı olabilir.  
  
2.  Hata yanıtları (4xx veya 5xx) görüntülenir, **sonuçları** kırmızı bir duruma sahip sütun kod ve Özet çubuğunda da vurgulanmıştır. Bu, birçok olası istekleri arasında kolay nokta hataları, uygulamanızda kolaylaştırır.  
  
3.  Yanıt oldukça yazdırma düğme (içinde gövde sekmesi) JSON, XML, HTML, CSS, JavaScript ve TypeScript yanıt yüklerini içeriğin okunabilirliğini artırarak ayrıştırma yardımcı olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil Araçları ile veya olmadan hata ayıklayıcı çalıştırın](../profiling/running-profiling-tools-with-or-without-the-debugger.md)  
 [Visual Studio Günlüğü: Giriş Visual Studio'nun ağ denetleyici](http://go.microsoft.com/fwlink/?LinkId=535022)   
 [Kanal 9 Video: VS tanılama araçları - yeni ağ profil oluşturucu](http://channel9.msdn.com/Series/ConnectOn-Demand/206)  
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)
