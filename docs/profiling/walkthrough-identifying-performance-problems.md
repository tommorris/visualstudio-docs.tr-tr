---
title: "İzlenecek yol: Performans sorunları tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance, analyzing
- profiling applications, walkthroughs
ms.assetid: 36f6f123-0c14-4763-99c3-bd60ecb95b87
caps.latest.revision: "53"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d52f6bfe745cf7e8684094cf9244b6eedcba13a9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-identifying-performance-problems"></a>İzlenecek yol: Performans sorunları tanımlama
Bu kılavuz, performans sorunlarını tanımlamak için bir uygulama profili gösterilmiştir.  
  
 Bu kılavuzda, yönetilen bir uygulama profili oluşturma ve uygulamada performans sorunlarını tanımlamak ve yalıtmak için örnekleme ve araçları kullanarak sürecini adım adım.  
  
 Bu kılavuzda, şu adımları izler:  
  
-   Örnekleme yöntemini kullanarak bir uygulama profili.  
  
-   Bulun ve performans sorunu düzeltmek için örneklenen profil oluşturma sonuçlarını çözümleyin.  
  
-   Uygulama izleme metodunu kullanarak profil.  
  
-   Bulun ve performans sorunu düzeltmek için izleme eklenmiş profil oluşturma sonuçlarını çözümleyin.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   C# Ara anlama.  
  
-   Bir kopyasını [PeopleTrax örneği](../profiling/peopletrax-sample-profiling-tools.md).  
  
 Profil oluşturma tarafından sağlanan bilgiler ile çalışmak için hata ayıklama sembol bilgileri kullanılabilir olması en iyisidir.  
  
## <a name="profiling-by-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak profil oluşturma  
 Örnekleme olarak söz konusu işlemi düzenli aralıklarla etkin işlevi belirlemek için sorgulanan profil bir yöntemdir. Sonuçta elde edilen veri işlem örneklenen olduğunda ne sıklıkta söz konusu işlevi üstünde çağrı yığını olan sayısına sağlar.  
  
#### <a name="to-profile-an-application-by-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak bir uygulama profili için  
  
1.  Açık [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] yönetici ayrıcalıklarına sahip. Yönetici olarak çalıştırma profili oluşturma için gereklidir.  
  
2.  PeopleTrax çözümü açın.  
  
     PeopleTrax çözüm şimdi Çözüm Gezgini doldurur.  
  
3.  Proje yapılandırma ayarı kümesine **sürüm**.  
  
     Yayın derlemesi uygulamanızda performans sorunlarını algılamak için kullanmanız gerekir. Yayın derlemesinde hata ayıklama derlemesi performansı olumsuz etkileyebilir ve performans sorunlarını doğru şekilde göstermeye değil içine derlenmiş ek bilgiler içerdiğinden profil oluşturma için önerilir.  
  
4.  Üzerinde **Çözümle** menüsünde, select **Performans Profil Oluşturucu**seçeneğini belirleyip **performans Sihirbazı**ve ardından **Başlat**.  
  
     Performans Sihirbazı görünür.  
  
5.  Emin olun **CPU örnekleme (önerilir)** seçilir ve ardından **sonraki**.  
  
6.  İçinde **profil oluşturma için hedef olarak belirtmek istediğiniz hangi uygulamanın**PeopleTrax seçin ve ardından **sonraki**.  
  
     [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]Proje oluşturulur ve uygulama profilini başlatır. **PeopleTrax** uygulama penceresi görünür.  
  
7.  Tıklatın **alma kişiler**.  
  
8.  Tıklatın **ExportData**.  
  
     Not Defteri'nde açılır ve dışarı aktarılan verileri içeren yeni bir dosya görüntüler **PeopleTrax**.  
  
9. Not Defteri'ni kapatın ve sonra kapatın **PeopleTrax** uygulama.  
  
     Profil oluşturma verileri profil oluşturucu oluşturur (\*.vsp) dosya, dosya adı performans Gezgini penceresi Raporlar bölümünde listelenir ve otomatik olarak yükler **Özet** anapenceresindeveridosyasındagörünümü[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
#### <a name="to-analyze-sampled-profiling-results"></a>Çözümlenecek örneklenen sonuçları profil oluşturma  
  
1.  Özet görünümü zaman çizelgesi CPU kullanımının çalıştırmak, profil oluşturma süresince görüntüler **etkin yolunuzda** en etkin olan uygulamanın çağrı ağacı dalı temsil eden listesi ve listesini  **İşlevler en yapılması tek tek iş** en yoğun bir şekilde kendi işlev gövdesine kodu yürütülürken örneklenen işlevler gösterir.  
  
     İncelemek **etkin yolunuzda** listelemek ve PeopleNS.People.GetNames yöntemi listesinin sonuna yakın PeopleTrax işlevi olduğuna dikkat edin. Konumuna çözümleme için iyi bir aday kolaylaştırır. GetNames içinde ayrıntılarını görüntülemek için işlev adına tıklayın **işlev ayrıntıları** görünümü.  
  
2.  **İşlev ayrıntıları** görünümü iki windows içerir. Maliyet dağıtım penceresi işlevi tarafından çalışmanın, adlı işlevleri tarafından çalışmanın ve örneklenen örnek sayısı için işlevini çağırdı işlevleri katkı grafik bir görünümünü sağlar. Bir işlev adına tıklayarak görünümün odağını olduğu işlevini değiştirebilirsiniz. Örneğin, seçili işlevi GetPeople yapmak için PeopleNS.People.GetPeople tıklayabilirsiniz.  
  
     **İşlevi kod görünümü** penceresi gösterilir işlevi için kaynak kodu varsa ve seçili işlevi en pahalı satırları vurgular. GetNames seçildiğinde, bu işlev bir dize uygulama kaynaklarından okur ve ardından kullanır görebilirsiniz bir <xref:System.IO.StringReader> dizesindeki her satır eklemek için bir <xref:System.Collections.ArrayList>. Bu işlev iyileştirmek için belirgin bir yolu yoktur.  
  
3.  PeopleNS.People.GetPeople GetNames yalnızca çağıranı olduğundan, kendi kodu incelemek için maliyet dağıtım penceresinde GetPeople'ı tıklatın. Bu yöntem bir <xref:System.Collections.ArrayList> PersonInformationNS.PersonInformation nesnelerle kişiler ve GetNames tarafından üretilen şirketler adları. Ancak, GetNames iki kez PersonInformation nesne oluşturulan her zaman çağrılır. Yöntem listeler yalnızca bir kez yöntemi başlangıcında oluşturarak ve PersonInformation oluşturma döngüsü sırasında bu listeye dizin kolayca iyileştirilebilir görebilirsiniz.  
  
4.  GetPeople alternatif bir sürümü ile örnek uygulama kodu sağlanır ve en iyi duruma getirilmiş işlevi koşullu derleme simgesi derleme özellikleri ekleyerek çağırabilirsiniz. Çözüm Gezgini penceresinde, kişilerin projesine sağ tıklayın ve ardından **özellikleri**. Tıklatın **yapı** yazın ve özellik sayfası menüsü **OPTIMIZED_GETPEOPLE** koşullu derleme simge metin kutusunda. GetPeople en iyi duruma getirilmiş sürümü özgün yöntemi sonraki derlemede değiştirir.  
  
5.  Performans oturumunu yeniden çalıştırın. Performans Gezgini araç çubuğunda tıklatın **başlatma profil oluşturma ile**. Tıklatın **alma kişiler** ve ardından **verileri dışa aktar**. Görünür ve sonra da kişiler Trax uygulamayı kapatın Not Defteri penceresini kapatın.  
  
     Yeni bir profil oluşturma veri dosyası oluşturulur ve bir **Özet** görünür yeni veri görünümü [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ana penceresi.  
  
6.  İki profil çalışmalarını karşılaştırmak, performans Explorer'ın iki veri dosyalarını seçin, dosyaları sağ tıklatın ve ardından **karşılaştırmak performans raporları**. Bir karşılaştırma raporu penceresi görünür [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ana penceresi. **Delta** sütun işlevlerin önceki performans değerindeki değişikliği gösterir **temel** sonraki değerine **karşılaştırma** değeri. Değerleri karşılaştırmak için seçebileceğiniz **sütun** açılan liste. Seçin **dahil örnekleri %**.  
  
     GetPeople ve GetNames yöntemleri önemli ölçüde performans artışı Göster dikkat edin.  
  
## <a name="profiling-by-using-the-instrumentation-method"></a>İzleme metodunu kullanarak profil oluşturma  
 Araçları içinde ve profil oluşturucu araştırma işlevleri profili ikili dosyaları özel yerleşik sürümlerine ekler profil bir yöntemdir. Araştırmalar giriş ve çıkış Araçlı modüllerdeki işlevlerin ve bu işlevlerin tüm çağrı sitede zamanlama bilgi toplayın. İzleme işlemi, diske yazma ve bir ağ üzerinden iletişim kurarken gibi girdi/çıktı işlemleri ile ilgili sorunlar araştırma için yararlıdır. Araçları sağlar: örnekleme daha ayrıntılı bilgi, ancak işlem yürütme daha kullanışsız ve büyük bir miktarını yük doğurur. İzleme eklenmiş ikili dosyalar da hata ayıklama veya ikili dosyaları serbest bırakır ve dağıtım için tasarlanmamıştır büyüktür.  
  
 Kılavuzun bu bölümünde şu durum, daha önce profili PeopleTrax uygulamada en iyi duruma getirebilirsiniz daha fazla kod bulmak için izleme metodunu kullanacağız. Özet görünümü zaman çizelgesi filtre kullanarak biz bizim analiz dışarı aktarma veri senaryosunda kişilerin listesini bir not defteri dosyasına yazılır profili uygulamamızdaki odaklanır.  
  
#### <a name="to-profile-an-existing-application-by-using-the-instrumentation-method"></a>İzleme metodunu kullanarak var olan bir uygulama profiline  
  
1.  Gerekirse, PeopleTrax uygulamayı Visual Studio'da açın.  
  
     Yönetici olarak çalıştırdığınız ve çözüm için yapı yapılandırması ayarlandığından emin olun **sürüm**.  
  
2.  Performans Gezgini tıklayın **Araçları**.  
  
3.  Performans Gezgini araç çubuğunda tıklatın **başlatma profil oluşturma ile**.  
  
     Profil Oluşturucu Proje oluşturulur ve uygulama profilini başlatır. PeopleTrax uygulama penceresi görünür.  
  
4.  Tıklatın **alma kişiler**.  
  
     PeopleTrax veri kılavuzu verileri ile doldurur.  
  
5.  Yaklaşık 10 saniye bekleyin ve ardından **verileri dışa aktar**.  
  
     **Not Defteri'ni** başlatır ve PeopleTrax kişilerden listesini içeren yeni bir dosya görüntüler. Bekleyen etkinleştirir, verileri daha kolay tanımlamak için filtre yordamı dışarı aktarın.  
  
6.  Kapat **not defteri**ve ardından kapatın **PeopleTrax** uygulama.  
  
     [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]bir performans oturumu raporu (*.vsp) oluşturur.  
  
#### <a name="to-analyze-instrumented-profiling-results"></a>İzleme eklenmiş profil oluşturma sonuçlarını analiz etmek için  
  
1.  Zaman Çizelgesi grafiği **Özet** rapor görünümünü profil oluşturma süresi boyunca program CPU kullanımını çalışma gösterir. Dışarı aktarma veri işlemi büyük yoğun veya Plato grafiğin sağ tarafında olması gerekir. Biz görüntülemek ve dışarı aktarma işlemine toplanan verileri çözümlemek için Performans oturumunu filtreleyebilirsiniz. Ayırıcının sol tarafındaki dışarı aktarma veri işlemi başladığı grafikte için tıklatın. Yeniden işlemi sağ tarafındaki'ı tıklatın. Ardından **seçime göre filtre** zaman çizelgesi sağındaki bağlantılar listesinde.  
  
     **Etkin yolunuzda** ağaç Göster <xref:System.String.Concat%2A> PeopleTrax.Form1.ExportData yöntemi tarafından çağrılan yöntemi zaman büyük bir yüzdesini kullanıyor. Çünkü **System.String.Concat** ayrıca en üstünde olduğu **işlevleri ile en tek tek iş** işlevinde harcanan zamanı azaltmak listesi noktasıdır bir olası en iyi duruma getirme.  
  
2.  Çift **System.String.Concat** işlevi Ayrıntılar görünümünde daha fazla bilgi için Özet tablolardan herhangi birinde.  
  
3.  PeopleTrax.Form1.ExportData Concat çağıran yalnızca yöntemi olduğunu görebilirsiniz. Tıklatın **PeopleTrax.Form1.ExportData** içinde **işlevleri çağırma** yöntemi seçmek için listesidir işlev Ayrıntıları görünümü hedef olarak.  
  
4.  İşlev kod Görünümü penceresinde yöntemi inceleyin. Değişmez değer hiçbir çağrıları olduğuna dikkat edin **System.String.Concat**. Bunun yerine, derleyici çağrıları değiştirir += işleneninin birkaç kullanımı vardır **System.String.Concat**. .NET Framework içindeki bir dizeye herhangi bir değişiklik ayrılacak yeni bir dize neden. .NET Framework içeren bir <xref:System.Text.StringBuilder> dize birleştirme için en iyi duruma getirilmiş sınıfı  
  
5.  Bu sorun alanını en iyi duruma getirilmiş kod ile değiştirin, OPTIMIZED_EXPORTDATA koşullu derleme simgesi olarak PeopleTrax projeye ekleyin.  
  
6.  Çözüm Gezgini'nde, PeopleTrax projesine sağ tıklayın ve ardından **özellikleri**.  
  
     PeopleTrax proje özelliklerini formu görüntülenir.  
  
7.  Tıklatın **yapı** sekmesi.  
  
8.  İçinde **koşullu derleme simgeleri** metin kutusunda, **OPTIMIZED_EXPORTDATA**.  
  
9. Proje özelliği formu kapatmak ve seçin **Tümünü Kaydet** sorulduğunda.  
  
 Uygulamayı yeniden çalıştırdığınızda, performans işaretli yenilikleri görürsünüz. Kullanıcı görünür geliştirmeleri performans olsa bile, profil oluşturma oturumu yeniden çalıştırmanız tavsiye edilir. İlk sorun başka bir sorun soyutlamaması çünkü bir sorunu düzelttikten sonra verileri gözden geçirme önemlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel bakış](../profiling/overviews-performance-tools.md)   
 [Başlarken](../profiling/getting-started-with-performance-tools.md)   
 [/ Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](/cpp/build/reference/z7-zi-zi-debug-information-format)