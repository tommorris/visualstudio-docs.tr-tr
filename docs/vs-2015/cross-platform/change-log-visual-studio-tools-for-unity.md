---
title: Değişiklik günlüğü (Unity için Visual Studio Araçları) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- tgt-pltfrm-cross-plat
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea490b7e-fc0d-44b1-858a-a725ce20e396
caps.latest.revision: 14
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: f4bec82e3e00a7b7e308bf0170ecb0fee01e2176
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694353"
---
# <a name="change-log-visual-studio-tools-for-unity"></a>Değişiklik günlüğü (Unity için Visual Studio Araçları)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [değişiklik günlüğü (Unity için Visual Studio Araçları)](https://docs.microsoft.com/visualstudio/cross-platform/change-log-visual-studio-tools-for-unity).  
  
  
Değişiklik günlüğü Unity için Visual Studio Araçları.  
  
## <a name="23"></a>2.3  
 Yayımlanan 2016-07-14  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   **Genel:**  
  
    -   Visual Studio hata listesinde Unity konsolundan devre dışı bırakmak için bir seçenek günlükleri eklendi.  
  
    -   Oluşturulan proje özellikleri değiştirilmesine izin verme seçeneği eklendi.  
  
-   **Hata Ayıklayıcı:**  
  
    -   Eklenen metin, XML, HTML ve JSON görselleştiriciler dize.  
  
-   **Sihirbazlar:**  
  
    -   MonoBehaviors eksik eklendi.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   **Genel:**  
  
    -   Denetim içinde görüntülenmesini Visual Studio ayarları önleyen ReSharper ile bir çakışma çözüldü.  
  
    -   Bazı durumlarda hata ayıklamayı engelleyen Xamarin ile bir çakışma çözüldü.  
  
-   **Hata Ayıklayıcı:**  
  
    -   Visual Studio'nun hata ayıklama sırasında donmasıyla sonuçlanabiliyor nedeni bir sorun düzeltildi.  
  
    -   Visual Studio 2015'te işlev kesme noktaları ile bir sorun düzeltildi.  
  
    -   Birden fazla ifade değerlendirme sorunları düzeltildi.  
  
## <a name="22"></a>2.2  
 Yayımlanan 2016-02-04  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   **Sihirbazlar:**  
  
    -   Eklenen akıllı arama **uygulama MonoBehavior** Sihirbazı.  
  
    -   Yapılan sihirbazları bağlamı kullanan; Örneğin, NetworkBehavior iletileri yalnızca bir NetworkBehavior ile çalışırken kullanılabilir.  
  
    -   Sihirbazlar NetworkBehavior iletiler için destek eklendi.  
  
-   **UI:**  
  
    -   MonoBehavior iletilerin görünürlüğünü yapılandırmak için bir seçenek eklenmiştir.  
  
    -   Visual Studio Unity projeleri için ilgili olmayan özellik sayfalarını kaldırıldı.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   **Proje oluşturma:**  
  
    -   UnityEngine ve Unity 4.6 üzerinde UnityEditor sabit başvuruları.  
  
    -   Sabit Unity OSX üzerinde çalışırken proje dosyalarının oluşturulmasını.  
  
    -   Proje adları hashmark (#) karakterleri içeren sabit işlenmesi.  
  
    -   Oluşturulan projeleri C# 4'e sınırlı.  
  
-   **Hata Ayıklayıcı:**  
  
    -   Bir sorun, bir Unity eş yordam içinde hata ayıklama sırasında ifade değerlendirme ile düzeltildi.  
  
    -   Visual Studio'nun hata ayıklama sırasında donmasıyla sonuçlanabiliyor nedeni bir sorun düzeltildi.  
  
-   **UI:**  
  
    -   Bir uyumsuzluk sabit [sekmeleri Studio](https://tabsstudio.com/) Visual Studio uzantısı.  
  
-   **Yükleyici:**  
  
    -   HKLM Kayıt defteri girişleri oluşturarak VSTU (tüm kullanıcılar için yüklenir) makineye yüklenmesini destekler.  
  
    -   Visual Studio'nun birden çok farklı sürümleri için VSTU sürümüyle aynı sürümü yüklendiğinde VSTU kaldırılması ile sorunlar düzeltildi. Örneğin, VSTU **2015** 2.1.0.0 ve VSTU **2013** 2.1.0.0 hem takıldı.  
  
## <a name="21"></a>2.1  
 Yayımlanan 2015-09-08  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity 5.2 için destek  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Unity üzerinde menü öğeleri görüntüle < 4.2  
  
-   Bir hata iletisi artık Visual Studio XML IntelliSense dosyalarını kilitler görüntülenir.  
  
-   Tanıtıcı <\<sorunu gidermeye çalışırken değiştirdiği >> koşullu bağımsız değişkeni bir boolean değeri değil, koşullu kesme noktaları.  
  
-   Windows Store uygulamaları için UnityEngine ve UnityEditor derlemelere başvuruları sabit.  
  
-   Hata ayıklayıcıda adımlanırken düzeltildi: Adımlanamıyor, genel özel durum.  
  
-   Visual Studio 2015'te sabit isabet sayısı kesme noktaları.  
  
## <a name="20"></a>2,0  
 Yayımlanan 2015-07-20  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   **Unity tümleştirmesi:**  
  
    -   Bir DLL ve onun hata ayıklama simgeleri (PDB) içeri aktarırken Visual Studio 2015 ile oluşturulan hata ayıklama sembolleri dönüştürme sabit.  
  
    -   Her zaman MDB dosyaları bir DLL ve onun hata ayıklama simgeleri (PDB) içeri aktarılırken ne zaman bir MDB dosyası ayrıca sağlanan dışında oluşturun.  
  
    -   Sabit kirlilik Unity proje dizininin obj dizinine sahip.  
  
    -   Başvuruları System.Xml.Link ve System.Runtime.Serialization sabit oluşturma.  
  
    -   Kancaları. birden fazla aboneye proje dosyası oluşturma API desteği eklendi.  
  
    -   Oluşturulacak dosyalardan biri kilitli olduğunda bile her zaman tam proje dosyası oluşturma.  
  
    -   İçin destek eklendi * uzantı joker karakter filtre belirtmek için C# projesinde dahil edilecek dosyalar.  
  
-   **Visual Studio tümleştirmesi:**  
  
    -   Productivity Power Tools ile bir uyumluluk sorunu düzeltildi.  
  
    -   Olaylar ve temsilciler bildirimleri MonoBehaviors oluşturma düzeltildi.  
  
-   **Hata Ayıklayıcı:**  
  
    -   Hata ayıklama sırasında olası dondurma düzeltildi.  
  
    -   Burada Yereller belirli yığın çerçevelerinde görüntülenmez bir sorun düzeltildi.  
  
    -   Boş bir dizi inceleyerek düzeltildi.  
  
## <a name="20-preview-2"></a>2.0 preview 2  
 Yayımlanan 2015-04-02  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   **Unity Proje Gezgini:**  
  
    -   Unity proje Gezgininde dosya yeniden adlandırılırken, sınıf otomatik olarak yeniden adlandırın (bkz **seçenekleri** iletişim).  
  
    -   Otomatik olarak yeni oluşturulan betiklerini, Unity proje Gezgininde seçin.  
  
    -   Unity proje Gezgininde etkin betik izleyin (bkz **seçenekleri** iletişim).  
  
    -   Visual Studio Çözüm Gezgini'nde çift-eşitleme (bkz **seçenekleri** iletişim).  
  
    -   Unity proje Gezgininde Visual Studio simgeler benimseyin.  
  
-   **Hata Ayıklayıcı:**  
  
    -   Etkin hata ayıklama hedefi kaydedilmiş veya yakın zamanda kullanılan hata ayıklama hedefleri listesinden seçin (bkz **seçenekleri** iletişim).  
  
    -   İşlev kesme noktaları MonoBehavior yöntemlerde oluşturabilir ve bunları birden çok MonoBehavior sınıflarına uygulayabilirsiniz.  
  
    -   Nesne Kimliği yap hata ayıklayıcıda destekler.  
  
    -   Destek kesme noktası isabet sayısı hata ayıklayıcısı.  
  
    -   (Deneysel. hata ayıklayıcıda kesme üzerinde özel durum desteği Bkz: **seçenekleri** iletişim).  
  
    -   Hata ayıklayıcıdaki ifadeler değerlendirildiğinde nesneler ve diziler oluşturulmasını destekler.  
  
    -   Null karşılaştırma desteği, Hata ayıklayıcıdaki ifadeler değerlendirme.  
  
    -   Eski üyeler hata ayıklayıcı gözlem pencerelerinde filtreleyin.  
  
-   **Yükleyici:**  
  
    -   En iyi duruma getirilmiş Visual Studio Araçları için Unity uzantısı kaydı.  
  
    -   Visual Studio Araçları için Unity 5 için Unity paketini yükleyin.  
  
-   **Belgeler:** belgesi oluşturma performansını artırın.  
  
-   **Sihirbazlar:** Unity 4.6 ve Unity 5 yeni MonoBehavior yöntemleri destekler.  
  
-   **Unity:** güvenli olmayan bayrakları arama ve özel proje dosyası oluşturma sırasında .rsp dosyaları tanımlar.  
  
-   **Kullanıcı Arabirimi:** eklenen Unity için Visual Studio Araçları **seçenekleri** Visual Studio'da iletişim kutusu.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   **Unity Proje Gezgini:**  
  
    -   Taşınmış ya da Visual Studio Çözüm Gezgini'nden yeniden adlandırılmış dosyaları sonra Unity proje Gezgini'ni yenileyin.  
  
    -   Unity proje Gezgininde dosya yeniden adlandırılırken seçimleri koruyun.  
  
    -   Otomatik önlemek genişletip Unity proje Gezgininde tıkladı dosyaları çift olduğunda daraltabilirsiniz.  
  
    -   Yeni seçilen dosyaları Unity proje Gezgininde görünür olduğundan emin olun.  
  
-   **Hata Ayıklayıcı:**  
  
    -   Visual Studio Hata ayıklayıcıdaki ifadeler değerlendirildiğinde dondurma olası engelleme.  
  
    -   Yöntem çağrıları hata ayıklayıcısı doğru etki alanında olması emin olun.  
  
-   **Unity:**  
  
    -   Unity 5 UnityVS.OpenFile konumunu düzeltin.  
  
    -   Unity 5 pdb2mdb konumunu düzeltin.  
  
    -   Proje dosyası oluşturma sırasında olası bir özel durumu engellersiniz.  
  
    -   Unity OSX üzerinde çalışırken olası dondurma engelleyin.  
  
    -   İç özel durumları işler.  
  
    -   İçin VS hata listesi Unity konsol günlükleri gönderin.  
  
-   **Belgeler:** düzeltmek için yeni unity belgeleri belgeleri oluşturma.  
  
-   **Proje:** taşıyın ve gerektiğinde, hatta klasörlerinde Unity .meta dosyalarını yeniden adlandırın.  
  
-   **Sihirbazlar:** MonoBehavior yöntemi parametrelerinin sırasını kodu oluştururken düzeltin.  
  
-   **Kullanıcı Arabirimi:** desteği Visual Studio temaları bağlam menüsü ve simgeler.  
  
## <a name="20-preview"></a>2.0 Önizlemesi  
 Yayımlanan 2014-11-12  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Visual Studio 2015 için destek.  
  
-   Visual Studio 2015'te Unity gölgelendiriciler için kod Coloration.  
  
-   Geliştirilmiş görsel olarak hata ayıklama sırasında değerleri:  
  
    -   Daha iyi görselleştirme ArrayLists, listeler, Hashtable'da ve sözlük.  
  
    -   Genel olmayan üyeler ve statik üyeler İzlemedeki ve yerel görünümlerle kategorileri gösterme.  
  
    -   Unity'nın SerializedProperty yalnızca özellik için geçerli bir değer alanı değerlendirmek için geliştirilmiş görüntüsü.  
  
    -   Sınıflar ve yapılar DebuggerDisplayAttribute desteği.  
  
    -   DebuggerTypeProxyAttribute desteği.  
  
-   Kodlama kuralları kullanıcı cevaben bizim sihirbazları kullanarak MonoBehaviour yöntemleri ekleme yapın.  
  
-   UnityVS oluşturulan projeleri derleme zamanı metin şablonları için destek uygular.  
  
-   ResX kaynakları için destek oluşturulan UnityVS projelerinde uygulayın.  
  
-   Unity Visual Studio'dan gölgelendiricileri açma desteği.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   İliştirme işleminden sonra Unity oyun başlatmadan önce yuvaların ve Visual Studio'da Play tetiklendi. Bu bazı sorunlar ile Unity VS arasında bağlantı kararlılığını İliştir ve Yürüt kullanırken düzeltir.  
  
-   Unity'nın komut dosyası altyapısı hata ayıklayıcı arabiriminde Unity dondurulamıyor meyillidir yöntemleri çağırmaktan kaçının. Bu, hata ayıklayıcı eklerken Unity dondurma düzeltir.  
  
-   Sembol kullanılabilir olduğunda çağrı yığınını görüntüleme düzeltin.  
  
-   İçin yoksa, günlük geri kaydetmeyin.  
  
## <a name="192"></a>1.9.2  
 Yayımlanan 2014-10-09  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity oyuncuların algılanması geliştirin.  
  
-   Bizim dosya açan kullanırken, dosya adının yanı sıra, satır numarası geçirmek Unity olun.  
  
-   Çevrimiçi Unity belgeleri için varsayılan olarak yerel bir belge yok ise.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Bir etki alanı yeniden sonra bir kesme noktasına ulaşma olası Unity kilitlenme düzeltildi.  
  
-   Bizim yapılandırma kapatırken Unity konsolunda gösterilen özel durumları düzeltin veya windows hakkında bir etki alanı sonra yeniden yükleyin.  
  
-   Yerel olarak çalışan 64 bit Unity algılanması düzeltin.  
  
-   Sihirbazlar Unity sürümünde her Monobehaviour filtreleme düzeltin.  
  
-   Burada uzantı filtresi boşsa tüm varlıkları proje dosyalarında bulunan hatası düzeltildi.  
  
## <a name="191"></a>1.9.1  
 Yayımlanan 2014-09-22  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Bağlama kesme noktası için kaynak konumları iyileştirin.  
  
-   Hata ayıklayıcı ifade değerlendirmesindeki aşırı yüklenmiş yöntemler için destek.  
  
-   Kutulama temelleri ve hata ayıklayıcı ifade değerlendirmesindeki değer türleri için destek.  
  
-   Anonim yöntemler hata ayıklama sırasında C# yerel değişkenler ortamın oluşturulması destekler.  
  
-   Silin ve Visual Studio'dan dosyaları yeniden adlandırma veya silme .meta dosyalarını yeniden adlandırın.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Visual Studio temasından işlenmesini düzeltin. Daha önce siyah Temalar iletişim kutuları boş görünebilir (bağlanma sorunlarını [#932637](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/932637/) ve [#936439](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/936439/)).  
  
-   Düzeltme Unity dondurma Unity yeniden derlenmesi sırasında hata ayıklayıcı bağlanırken (bağlanma sorunlarını [#947119](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/947119/) ve [#969211](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/969211/)).  
  
-   Uzak düzenleyiciler veya başka bir sistem üzerinde derlenmiş oyuncuların hata ayıklanırken kesme noktaları düzeltin.  
  
-   Bir kesme noktası isabet edildiğinde olası bir Visual Studio kilitlenme sorunu düzeltildi.  
  
-   Kesme noktaları olarak gösteren önlemek için bağlama düzeltme kesme noktaları kaldırıldı.  
  
-   Kapsam dışına görüntülenen dinamik değişkenleri önlemek için hata ayıklayıcı değişken kapsamı işlenmesini düzeltin.  
  
-   Hata ayıklayıcı ifade değerlendirmesinde arama statik üyeleri düzeltme (bağlanma sorunu [#953379](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/953379/)).  
  
-   Statik alanlar ve Özellikler göstermek için hata ayıklayıcı ifade değerlendirmesindeki türlerini görüntüleme düzeltin.  
  
-   Unity proje adları Visual Studio'nın (Connect sorun #948666) engelliyor özel karakterler içerdiğinde çözüm oluşturulmasını düzeltme.  
  
-   Unchecked (Connect sorun #933357) seçeneğini sonra konsol olay göndermeye hemen durdurmak için Visual Studio Araçları Unity paketini düzeltin.  
  
-   Başvurular düzgün UnityEngine.UI gibi yeni API'ler başvuruları UnityVS oluşturulan projelerde yeniden algılanması düzeltin.  
  
-   Yükleyici bozuk yüklemeleri önlemek için yüklemeden önce Visual Studio kapalı olduğunu gerektirecek şekilde düzeltin.  
  
-   VSTU tüm sürümleri arasında paylaşılan bir uygun bir tek başına bileşeni Unity başvuru derlemelerini yüklemek için yükleyici düzeltin.  
  
-   Betikleri açma VSTU ile Unity 64 bit sürümlerinde düzeltin.  
  
## <a name="19"></a>1.9  
 Yayımlanan 2014-07-29  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity hata ayıklayıcı Ekle penceresinde, bir özel IP ve bağlantı noktası hata ayıklamak için girin olanağı eklendi.  
  
-   Arka planda çalışıp için Unity ayarlamak için yapılandırma seçeneği ekleyin.  
  
-   Çözüm ve proje dosyaları ya da yalnızca proje dosyaları oluşturmak için yapılandırma seçeneği ekleyin.  
  
-   Başlangıç hedef: Unity Ekle veya Unity ve Play Ekle öğesini seçin.  
  
-   Çok boyutlu diziler hata ayıklayıcı görüntü.  
  
-   Yeni Unity Player'da hata ayıklama bağlantı noktalarını işler.  
  
-   Unity'nün 4.6 GUI derlemeleri gibi yeni Unity derlemelere başvuruları işleyin.  
  
-   Hata ayıklarken yerel değişkenler düzgün görüntülenmesi için kapanışlar deconstructs.  
  
-   Oluşturulan Yineleyicilerin değişkenleri, hata ayıklama sırasında bağımsız değişkenleriyle deconstructs.  
  
-   Bir projeyi yeniden sonra Unity Proje Gezgini'nın durumu korur.  
  
-   Unity Proje Gezgini geçerli belge ile eşitlemek için bir komut ekleyin.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Koşullu kesme noktaları hata ayıklayıcıyı başlatmadan önce koşulları ayarlayın düzeltin.  
  
-   UnityEngine uyarılarından kaçınmak için başvurular düzeltin.  
  
-   Unity betalar için ayrıştırma sürümleri düzeltin.  
  
-   Burada değişkenler yerel değişkenler penceresinde bir kesme noktasına ulaşma olduğunda gösterilmeyebiliyor sorunu düzeltin veya Adımlama.  
  
-   Değişkenleri araç ipuçları, Visual Studio 2013'te düzeltin.  
  
-   Unity 4.5 IntelliSense belgelerini oluşturulmasını düzeltme.  
  
-   Unity düzeltme / bir etki alanından sonra Visual Studio iletişim (play/stop Unity) yeniden yükleyin.  
  
-   Visual Studio temasından bölümlerini işlenmesini düzeltin.  
  
> [!IMPORTANT]
>  C# Unity ekosisteminde - yeni örnek varlıkları hakim dili olan C# ' de, Unity belgeleri varsayılan C# - C# deneyimi daha fazla odaklanması UnityScript ve hata için temel destek kaldırdık. Sonuç olarak, VSTU çözümleri artık yalnızca C# değildir ve yüklemek için daha hızlıdır.  
  
## <a name="182"></a>1.8.2  
 Yayımlanan 2014-01-07  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity'nın komut dosyası altyapısının ağ katmanında bir soruna geçici bir çözüm üzerinde Mavericks düzenleyicileri uzak bulma için çalışır.  
  
-   Uzak Unity oyuncuların bulmak için yeni bağlantı noktaları işleyin.  
  
-   Hedef yapı geçerli belirli UnityEngine bütünleştirilmiş kod başvurusu.  
  
-   Oluşturulan projeleri içerecek şekilde filtre dosyalara ayarı ekleyin.  
  
-   Visual Studio hata listesi gönderen konsol günlüklerine devre dışı bırakma ayarı ekleyin. Nedeni olarak yalnızca bir geri çağırma konsol günlükleri almak için Unity içinde kayıtlı PlayMaker veya konsol Pro kullanıyorsanız, bu yararlıdır.  
  
-   Mdb hata ayıklama sembolleri oluşturmayı devre dışı bırakma ayarı ekleyin. Kendiniz mdb oluşturma, bu yararlıdır.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Unity VS'den açılmış dosyalar bir gerileme düzeltildi > = 4.2 IntelliSense kaybeder.  
  
-   Özel Temalar işlemek için sunduğumuz VS iletişim kutuları düzeltin.  
  
-   Bağlam menüsüne UPE kapatma düzeltin.  
  
-   Unity kilitlenme eşitlenmemiş, derleme sürüm özel oluşturulmuş engelleyin.  
  
## <a name="181"></a>1.8.1  
 Yayımlanan 2013-11-21  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   MonoBehaviour sihirbazları Unity 4.3 API'leri ile ayarlanır.  
  
-   MonoBehaviour sihirbazları Unity API'leri sürüme bağlı olarak filtre.  
  
-   System.Xml.Linq başvuru için Unity projeleri Ekle > 4.1.  
  
-   Stacktrace başına iletisinde içermeyecek şekilde Debug.Log bizim çağrısına prettify.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Burada şu JavaScript dosyaları Visual Studio'da varsayılan işleme ile neden bir hata düzeltildi.  
  
-   Bu süre içinde VS, gerçek görünen bir beyaz piksel düzeltildi.  
  
-   Sabit bir SCM tarafından salt okunur olarak işaretlenmiş olması durumunda UnityVS.VersionSpecific derlemeyi silme işlemi.  
  
-   Yuva UnityVS paketi oluştururken sabit özel durumlar.  
  
-   Visual Studio derlemelerden stok görüntüleri yüklenirken Visual Studio'da bir kilitlenme sorunu düzeltildi.  
  
-   Unity derlemeleri kaynak UnityVS.VersionSpecific oluşturulmasında içinde bir hata düzeltildi.  
  
-   Bir yuva Unity pakette açılırken olası dondurma düzeltildi.  
  
-   Unity proje bir tire (-) ile işlenmesini adında düzeltildi.  
  
-   ALT + sekme sırasını Unity 4.2 ve üzeri karıştırmamaya Unity'de açılış betikleri düzeltildi.  
  
## <a name="180"></a>1.8.0  
 Yayımlanan 2013-09-24  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Hata ayıklayıcı bağlantı hızını önemli ölçüde geliştirildi.  
  
-   Dosya ve satır Unity 4.2 ve üzeri için Gezinti otomatik olarak işler.  
  
-   Koşullu kesme noktaları.  
  
-   Proje dosya oluşturucu artık T4 şablonlarını işler.  
  
-   MonBehavior sihirbazları yeni API'ler ile güncelleştirin.  
  
-   C# IntelliSense belgelerini Unity türleri için.  
  
-   Aritmetik ve mantıksal ifadeleri değerlendirme.  
  
-   Uzaktan hata ayıklama preview için Uzak düzenleyicileri daha iyi bulma.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Biz burada sızıntı bir iş parçacığı VS hata ayıklayıcı bağlantısını kestikten sonra düzeltildi.  
  
-   VS'de görünen bir beyaz piksel düzeltildi.  
  
-   Durum çubuğu simgesine tıklama işleme düzeltildi.  
  
-   Eklentileri klasörlerdeki derlemeleri ile başvuruları nesil düzeltildi.  
  
-   Yuva özel durumları durumunda UnityVS paketinden sabit oluşturma.  
  
-   Yeni sürümlerini UnityVS algılanması düzeltildi.  
  
-   Lisans süresi dolduğunda Lisans Yöneticisi'nin istemi düzeltildi.  
  
-   İşlem listesi boş VS işlem penceresi için ek hata ayıklayıcı işleme bir hata düzeltildi.  
  
-   Yerel görünümünde Boole değerleri, sabit değişen değerler.  
  
## <a name="122"></a>1.2.2  
 Yayımlanan 2013-07-09  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   İfade değerlendirici tam adlarını işleyin.  
  
-   Özel durum işleme için ilgili bir dondurma burada Unity komut dosyası altyapısı bize yanlış stackframe veri gönderiyor düzeltildi.  
  
-   Web hedefler için derleme işlemi düzeltildi.  
  
-   Visual Studio başlatıldığından ve silinen bir dosyayı başlangıçta açmak için dosya listesi olduğu meydana gelmiş olabilir bir hata düzeltildi.  
  
-   Benzer olmayan komut dosyalarını işlemek için sabit UnityVS.OpenFile gölgelendiricileri derlenmiş.  
  
-   Biz artık Boo.Lang ve UnityScript.Lang tüm C# içinden projeleri başvuru.  
  
-   Proje özel karakterler varsa projelerinde başvuruları sabit oluşturma.  
  
-   Yöntem çağrıları için projeleri burada elden geçici bir VS sorunu birden çok NullReferenceException MessageBox tetikleyecektir.  
  
-   Unity 4.2 Beta derlemelerin sabit işleme.  
  
## <a name="121"></a>1.2.1  
 Yayımlanan 2013-04-09  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Unity derlemeleri için kod tamamlama g/ç hatası durumunda yerel dağıtımını sabit (salt okunur dosyaları gibi veya Visual Studio tarafından kilitlenmiş dosyaları).  
  
-   Visual Studio'da zaten açıldıysa burada Unity'de bir betiğin açılması dosya odaklanmak değil bir gerileme düzeltildi.  
  
-   Yeni özel durum işleme performans sorunu düzeltildi.  
  
-   Sabit bağlama dış bazı DLL'lerde kesme noktaları.  
  
## <a name="12"></a>1.2  
 Yayımlanan 2013-03-25  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Hata ayıklayıcı bağlantı hızını önemli ölçüde geliştirildi.  
  
-   Daha büyük projeler için en iyi duruma getirilmiş Unity Proje Gezgini.  
  
-   (Veya etkinleştirmezsiniz) ayırmak için Visual Studio ayarları dikkate işlenen ve işlenmeyen özel durumlar.  
  
-   ToString yerel değişkenlerde çağırmak için Visual Studio ayarı oluşuyor.  
  
-   Ekleme yeni menü hata ayıklama -> Unity oyuncuların hata ayıklamak için kullanabileceğiniz ekleme Unity hata ayıklayıcı.  
  
-   Çözüm dosyası oluşturma sırasında UnityVS çözüm eklenen özel projeler korur.  
  
-   Ekleme yeni klavye kısayolu CTRL + ALT + M, giriş işareti konumuna Unity işlevi veya üye için Unity belgeleri görüntülemek için CTRL + H ->.  
  
-   Derleyici yanıt dosyaları (rsp), Visual Studio ile derleme yapılırken dikkate alın.  
  
-   Oluşturucu yöntemleri hata ayıklama sırasında değişkenleri göstermek için derleyicinin ürettiği türleri ayrıştırma.  
  
-   Uzak bir paylaşılan klasöre Unity yapılandırma gereksinimini ortadan kaldırarak hata ayıklama basitleştirin. Şimdi Windows için Unity projeniz erişimi yeterlidir.  
  
-   Özel Unity profil, bir standart .net hedef profil yükleyin. Bu, ReSharper gösterebilirsiniz tüm hatalı pozitif sonuçları düzeltir.  
  
-   Geçici bir Unity altyapısı hata, hata ayıklayıcı olmayan düzgün bir şekilde kesme olmaz şekilde komut iş parçacığı kayıtlı.  
  
-   Burada dosya açık istekte kilitlenme sırasında dosyaları açmak için talep vs'de bir yarış durumu önlemek için dosyayı açan yeniden.  
  
-   UnityVS VS oluşturulurken proje oluşturma yenilemek şimdi isteyen ve değil dosya artık kaydedin.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Sabit özel bizim .net profili  
  
-   Tema oluşturma tümleştirme sabit, bu VS 2012 koyu tema ile bizim sorunları giderir.  
  
-   VS 2012'de sabit hızlı davranışı kısayol.  
  
-   Hata ayıklama sırasında gerçekleşebilir Adımlama bir sorun düzeltildi ve ana olmayan iş parçacığı bir kesme noktasına ulaşılmasına neden olur.  
  
-   Tür diğer adları gibi tamsayı sabit UnityScript ve hata tamamlama  
  
-   Yeni UnityScript veya hata dize yazarken sabit özel durum.  
  
-   Bir çözümü yüklenmedi, Unity menüleri sabit durumlar.  
  
-   Hata düzeltildi UV'leri 48: çift tırnak bazen hataya yazıp tüm işlevi (kod tamamlama, sözdizimi vurgulama vs.) Kes.  
  
-   UV'leri 46 hata düzeltildi: açılan komut dosyası (UnityScript) hata listesi, Visual Studio tıklandığında çoğaltılabilir.  
  
-   Hata düzeltildi UV'leri 42: durum çubuğunda Unity bağlantı logosu VS 2012'de fare olayları işleme değil.  
  
-   Hata düzeltildi UV'leri 44: CTRL + SHIFT + Q hızlı MonoBehaviours için VS 2012'de kullanılabilir değil.  
  
-   Hata düzeltildi UV'leri 40: pencere VS2012 "koyu" tema etkin olduğunda Unity proje Gezgininde seçilen öğeler okunamaz.  
  
-   Hata düzeltildi UV'leri 39: Atlanan dizeleri sorunu belirteç oluşturma.  
  
-   Hata düzeltildi UV'leri-35: değişkenleri incelerken nesneler üzerinde çağırmak ToString.  
  
-   Hata düzeltildi UV'leri 27: Goto sembol penceresi tutarsızlık VS2012 "koyu" tema ile.  
  
-   Hata düzeltildi UV'leri-11: Eş yordamlarda yerel öğeler.  
  
## <a name="11--beta-release"></a>1.1 – beta sürümü  
 Yayımlanan 2014-10-09  
  
## <a name="1013"></a>1.0.13  
 Yayımlanan 2013-01-21  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Geçersiz iş parçacığı olayları hedef hata ayıklanan gönderiyorsa, meydana gelmiş olabilir bir Visual Studio kilitleniyor düzeltildi. Bu genellikle, uzak bir Unity OSX üzerinde hata ayıklama olacağını.  
  
-   Bir özel durum hata ayıklayıcı kapanıyorsa gerçekleşebilir, Visual Studio kilitleniyor düzeltildi.  
  
-   Bir C# MonoBehavior bir ad alanında olduğunda, bizim MonoBehavior Yardımcıları düzeltildi.  
  
-   Visual Studio 2012'de UnityScript için sabit bir hata ayıklayıcı araç ipuçları.  
  
-   Yalnızca hata ayıklama sabitleri Unity'de değiştiği proje oluşturma düzeltildi.  
  
-   Unity Proje Gezgini sabit klavye gezintisi.  
  
-   Kaçış dizileri için sabit UnityScript renklendirme.  
  
-   Proje adı Unity dışında kullanıldığında daha iyi tahmin bizim dosya açan düzeltildi. Kullanıcı, bir üçüncü bölümü dosya açan temsilciler için UnityVS, Unity kullandığında, gereklidir.  
  
-   Sabit işleme için UnityVS Unity'de gönderilen uzun iletisi. Bundan önce uzun iletileri UnityVS Mesajlaşma bizim parçası kilitlenebiliyordu. Sonuç olarak, bazen UnityVS dosya Unity'de açın mıydı.  
  
## <a name="1012"></a>1.0.12  
 Yayımlanan 2013-01-03  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Visual Studio bir kesme noktası silerken, oluşabilir sabit Visual Studio kilitleniyor.  
  
-   Unity oyun betikleri yeniden derlenen sonra nerede bazı kesme noktaları isabet değil, bir hata düzeltildi.  
  
-   Hata ayıklayıcı kesme noktaları ilişkisiz Visual Studio doğru şekilde bildirmek için düzeltildi.  
  
-   Yerel programlarda hata ayıklamak için Visual Studio hata ayıklayıcısını engelleyen bir kayıt sorun düzeltildi.  
  
-   UnityScript değerlendirirken gerçekleşir ve ifadeleri önyük özel durum düzeltildi.  
  
-   Burada .net API düzeyini Unity proje dosyalarının bir güncelleştirme tetikleyecek değil bir gerileme düzeltildi.  
  
-   Burada kullanıcı kodu içinde günlük geri çağırma işleyiciyi katılmamayı bir API sorun düzeltildi.  
  
## <a name="1011"></a>1.0.11  
 Yayımlanan 2012-11-28  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity 4 resmi desteği.  
  
-   Unity Proje Gezgini betiklerin işleme.  
  
-   Visual Studio penceresinde gitmek için tümleştirme.  
  
-   Bilgi konsol iletisi hata listesinde tıklayarak kaplamaları için bu, ilk stackframe simgelerle için ayrıştırılıyor.  
  
-   Ekleme bir [API](../cross-platform/customize-project-files-created-by-vstu.md) proje oluşturma işleminde katılmasına izin vermek için.  
  
-   Ekleme bir [API](../cross-platform/share-the-unity-log-callback-with-vstu.md) içinde LogCallback katılmasına izin vermek için.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Unity Proje Gezgini Visual Studio 2012'de, sabit regresyon arka planda.  
  
-   Tam .net Profil kullanıcılar için proje oluşturma düzeltildi.  
  
-   Web hedefinin kullanıcılar için proje oluşturma düzeltildi.  
  
-   Sabit proje oluşturma dahil etmek için hata ayıklama ve izleme derleme simgeleri Unity olarak yapar.  
  
-   Özel karakterler bizim Goto sembol penceresinde kullanırken sabit kilitlenme.  
  
-   Size sunduğumuz simgesi Visual Studio durum çubuğunda eklenemiyor, sabit kilitlenme.  
  
## <a name="1010"></a>zamanlarını 1.0.10  
 Yayımlanan 2012-10-09  
  
### <a name="bug-fixes"></a>Hata Düzeltmeleri  
  
-   Unity Proje Gezgini arka planını Visual Studio 2010'da düzelttik.  
  
-   UnityVS, hata ayıklayıcı arabirim önceden kilitlenmiş bir Unity için hata ayıklayıcının çalıştılarsa meydana gelmiş olabilir bir Visual Studio dondurma düzeltildi.  
  
-   Bir kesme noktası ayarlandı ve AppDomain yeniden ortaya çıkabilecek meydana gelmiş olabilir bir Visual Studio dondurma düzeltildi.  
  
-   Sabit dosyalar kilitlenmesini önlemek ve Unity yapı işlemi karıştırır Unity'de derlemeleri nasıl alınır.  
  
## <a name="109"></a>zamanlarını 1.0.9  
 Yayımlanan 2012-10-03  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Sabit proje oluşturma, Unity projesi gerçek JavaScript varlıkları içerir.  
  
-   İfade değerlendirmesinde işleme sabit bir hata oluştu.  
  
-   Yeni değerler alanlara değer türlerinin ayarlama düzeltildi.  
  
-   Sabit olası yan kod düzenleyicisinden ifadeleri üzerine gelindiğinde etkiler.  
  
-   Sabit ifade değerlendirmesi için yüklü bütünleştirilmiş kodlarında türler nasıl aranır.  
  
-   Hata düzeltildi UV'leri 21: Değerlendirme atamasının Unity nesneler üzerinde etkisi yoktur.  
  
-   Hata düzeltildi UV'leri 21: Unity matematik API için bir yöntem çağırmayla hesaplanırken geçersiz işaretçi.  
  
## <a name="108"></a>zamanlarını 1.0.8  
 Yayımlanan 2012-09-26  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Sabit bizim betik açan projeyi yolunu elde emin olan yoldur hem Visual Studio hem de komut dosyaları açamaz.  
  
-   Sabit bir hata ile kesme noktaları hata ayıklama oturumu, çalışırken oluşturulan Visual Studio'nun kilitlenmesine neden olabilir.  
  
-   Visual Studio 2010'da UnityVS nasıl kayıtlı düzeltildi.  
  
## <a name="107"></a>1.0.7  
 Yayımlanan 2012-09-14  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Visual Studio 2012 desteği.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Unity'nın davranışı eşleştirmek için düzenleyici ve eklentileri proje dosyalarının oluşturulmasını sabit.  
  
-   Çeviri .pdb simgeleri Unity 4'te düzeltilmiştir.  
  
> [!IMPORTANT]
>  Visual Studio 2012 desteği nedeniyle birkaç dosyalarını yeniden adlandırın ve başka gezinme vardı. Unity içeri aktarmak için UnityVS paket artık UnityVS 2010 veya UnityVS 2012'de, sırasıyla Visual Studio 2010 ve Visual Studio 2012 için olarak adlandırılır. Bu sürüm ayrıca UnityVS proje dosyalarını yeniden oluşturulduğunu gerektirir.  
  
## <a name="106---internal-build"></a>1.0.6 - iç yapı  
 Yayımlanan 2012-09-12  
  
## <a name="105"></a>1.0.5  
 Yayımlanan 2012-09-10  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Sabit betikleri ve gölgelendiricileri geçersiz xml karakter değilse, proje dosyalarının oluşturulmasını.  
  
-   Unity varlık sunucuya bağlanıldığında Unity örnekleri sabit algılanması. Bu, Unity ve Visual Studio hata ayıklayıcı otomatik bağlantısı dosyaları açmak için hataları tetiklenir.  
  
## <a name="104"></a>1.0.4  
 Yayımlanan 2012-09-05  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity hata ayıklama sembolleri otomatik dönüştürme.  
  
     Bir .NET .dll derlemesi ile kendi ilgili .pdb varlık klasörünüzde varsa, yalnızca derlemenin yeniden içeri aktarın ve UnityVS, Unity'nın komut dosyası altyapısı anlar ve sizin için adım, .NET derlemeleri halinde mümkün olacaktır bir hata ayıklama sembolleri dosyasına .pdb dönüştürür UnityVS.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Yöntemleri veya özellikleri içinde Unity tarafından oluşturulan özel durumları nedeniyle hata ayıklama sırasında UnityVS kilitlenme sorunu düzeltildi.  
  
## <a name="103"></a>1.0.3  
 Yayımlanan 2012-09-04  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity'de dosyaları açmak için UnityVS kullanımını devre dışı bırakmak için yeni yapılandırma seçeneği.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Sabit UnityEditor başvuruları nesil olmayan Düzenleyicisi projeler için.  
  
-   Sabit olmayan Düzenleyicisi projeleri UNITY_EDITOR sembolünün tanımı.  
  
-   Çökme, özel durum çubuğu tarafından neden rastgele VS sabit.  
  
## <a name="102"></a>1.0.2  
 Yayımlanan 2012-08-30  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   PythonTools hata ayıklayıcı sabit çakışıyor.  
  
-   Mono.Cecil sabit başvurular.  
  
-   Hata düzeltildi nasıl betik derlemelerde alınan Unity'de Unity 4 b7 ile.  
  
## <a name="101"></a>1.0.1  
 Yayımlanan 2012-08-28  
  
### <a name="new-features"></a>Yeni Özellikler  
  
-   Unity 4.0 Beta önizlemesi desteği.  
  
### <a name="bug-fixes"></a>Hata düzeltmeleri  
  
-   Özel durumları atma özelliklerini inceleme düzeltildi.  
  
-   Temel nesnelere nesneleri incelerken azalan düzeltildi.  
  
-   Ekleme noktasını MonoBehavior Sihirbazı için sabit boş açılan listesi.  
  
-   Dll içindeki varlık klasörünü sabit tamamlanmasını UnityScript ve hata.  
  
## <a name="10--initial-release"></a>1.0 – ilk sürümü  
 Yayımlanan 2012-08-22

