---
title: "Değişiklik günlüğü (Unity için Visual Studio Araçları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea490b7e-fc0d-44b1-858a-a725ce20e396
caps.latest.revision: "12"
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload: unity
ms.openlocfilehash: 45a06d17b2a3033af64c9d9a007af4a74dedabba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="change-log-visual-studio-tools-for-unity"></a>Değişiklik günlüğü (Unity için Visual Studio Araçları)
Unity için Visual Studio Araçları günlük değiştirin.  

## <a name="3502"></a>3.5.0.2
 Yayımlanan 2017-12-04

### <a name="new-features"></a>Yeni Özellikler  

-   **Tümleştirme:**  

    -   Artık Unity'de bir betik eklediğinizde veya kaldırdığınızda Unity projeleri Visual Studio'da otomatik olarak yeniden yükleniyor.

-   **Hata Ayıklayıcı:**  

    -   Unity Düzenleyicisi'ni hata ayıklamak için Xamarin ve Mac için Visual Studio tarafından paylaşılan Mono hata ayıklayıcı kullanmak için bir seçenek eklenmiştir.

    -   Taşınabilir hata ayıklama simge dosyaları için destek eklendi.

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Tümleştirme:**  

    -   Kurulum bağımlılıkları sorunlar giderildi.

    -   Sabit Unity API Yardım menü görünmüyor.
    
-   **Proje oluşturma:**  

    -   Sabit player proje oluşturma IL2CPP/.NET 4.6 arka ucu ile UWP oyun üzerinde çalışırken.
    
    -   Yanlış derleme filename eklenen ek .dll uzantısına sabit.
    
    -   Belirli bir proje API uyumluluk düzeyi yerine genel bir sabit kullanımı.
    
    -   Varsayılan 'true' olarak AllowAttachedDebuggingOfEditor Unity bayrağı zorlamaz.

## <a name="3402"></a>3.4.0.2
 Yayımlanan 2017-09-19

### <a name="new-features"></a>Yeni Özellikler  

-   **Proje oluşturma:**  

    -   Assembly.json derleme birimler için destek eklendi.

    -   Unity derlemeler için proje klasörünü kopyalama durduruldu.

-   **Hata Ayıklayıcı:**  

    -   Sonraki deyim yeni Unity çalışma ayarı için destek eklendi.

    -   Decimal türü yeni Unity çalışma zamanı desteği eklendi.

    -   Örtük/açık dönüşümler desteği eklendi.

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Değerlendirme:**  

    -   Örtük boyutuyla sabit dizi oluşturma.

    -   Sabit derleyici Yereller öğeleriyle oluşturulur.

-   **Proje oluşturma:**  

    -   4.6 API düzeyi için Microsoft.CSharp sabit başvuru.

## <a name="3302"></a>3.3.0.2
 Yayımlanan 2017-08-15

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Proje oluşturma:**  

    -   Visual Studio çözümü oluşturma sabit Unity 5.5 ve önceki sürümleri.

## <a name="3300"></a>3.3.0.0
 Yayımlanan 2017-08-14

### <a name="new-features"></a>Yeni Özellikler  

-   **Değerlendirme:**  

    -   Yapılar oluşturma ile yeni Unity çalışma zamanı için destek eklendi.

    -   İşaretçileri eklenen minimalist desteği.

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Değerlendirme:**  

    -   Temelleri sabit yöntemi çağrısının.

    -   Sabit alan değerlendirme BeforeFieldInit ile işaretlenmiş türleriyle.

    -   İkili işleçler (çıkar) ile sabit olmayan desteklenen çağırır.

    -   Visual Studio izleme öğeleri eklerken, sabit sorunları.

-   **Proje oluşturma:**  

    -   Derleme adı başvuruları mcs.rsp dosyalarla sabit.

    -   Sabit API düzeylerini tanımlar.    

## <a name="3200"></a>3.2.0.0
 Yayımlanan 2017-05-10

### <a name="new-features"></a>Yeni Özellikler  

-   **Yükleyici:**  

    -   MEF önbelleği temizleme için destek eklendi.

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Kod Düzenleyicisi:**  

    -   Sabit sınıflandırma/tamamlama özel özniteliklere sahip.

    -   Unity iletilerle titremeyi sabit.

## <a name="3100"></a>3.1.0.0
 Yayımlanan 2017-04-07

### <a name="new-features"></a>Yeni Özellikler  

-   **Hata Ayıklayıcı:**  

    -   Yeni Unity çalışma zamanı için destek eklenmiştir (.NET 4.6 ile / C# 6 uyumluluğu).

-   **Proje oluşturma:**  

    -   .NET 4.6 profili desteği eklendi.

    -   Mcs.rsp dosyaları için destek eklendi.

    -   Unity 5.6 kullanıldığında, her zaman güvenli derleme anahtarı etkinleştirin.

    -   "Player" proje oluşturma için destek eklenmiştir Windows mağazası platform ve il2cpp arka ucu kullanırken.

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Kod Düzenleyicisi:**  

    -   Otomatik tamamlama yöntemiyle ekledikten sonra şapka konumu sabit.

-   **Proje oluşturma:**  

    -   Kaldırılan derleme sürüm sonrası işleme.

## <a name="3001"></a>3.0.0.1
 Yayımlanan 2017-03-07

### <a name="this-version-includes-all-new-features-and-bug-fixes-introduced-with-28x-series"></a>Bu sürüm, tüm yeni özellikleri ve hata düzeltmeleri 2.8.x serisiyle sunulan içerir.

## <a name="2820---30-preview-3"></a>2.8.2.0 - 3.0 preview 3
 Yayımlanan 2017-01-25

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Proje oluşturma:**  

    -   Regresyon, burada eklentileri projeleri, iki kez başvurulan burada ikili DLL olarak ilk proje olarak sonra başvuru sabit.

## <a name="2810---30-preview-2"></a>2.8.1.0 - 3.0 preview 2
 Yayımlanan 2017-01-23

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Kod Düzenleyicisi:**  

    -   Bir öznitelik bildirimi parantezi tamamlama olmadan başlatırken bir kilitlenme sabit.

-   **Hata Ayıklayıcı:**  

    -   Yeni Unity derleyici/çalışma zamanında altında eş ile sabit işlevi kesme noktaları.

    -   Eklenen uyarı (karşılık gelen kaynak konumu bulunduğunda) unbindable bir kesme noktası durumunda.

-   **Proje oluşturma:**  

    -   Özel ve yerelleştirilmiş karakterleri csproj nesil sabit.

    -   Sabit başvuruları dışında (ör. Facebook SDK) kitaplığı gibi varlıklar.

-   **Çeşitli:**  

    -   Unity yüklemeden veya kaldırmadan zaman çalışmasını engellemek için onay eklendi.

    -   Uzak Unity belgelerine hedeflemek için https olarak değiştirdi.

## <a name="2800---30-preview"></a>2.8.0.0 - 3.0 Önizleme
 Yayımlanan 2016-11-17

### <a name="new-features"></a>Yeni Özellikler  

-   **Genel:**  

    -   Visual Studio 2017 yükleyici desteği eklendi.

    -   Visual Studio 2017 uzantısı desteği eklendi.

    -   Eklenen yerelleştirme desteği.    

-   **Kod Düzenleyicisi:**  

    -   Ek C# Unity iletileri için IntelliSense.

    -   Ek C# kod coloration Unity iletileri için.

-   **Hata Ayıklayıcı:**  

    -   Desteği eklendi `is`, `as`, doğrudan cast, `default`, `new` ifadeler.

    -   Dize concat ifadeler için destek eklendi.

    -   Tamsayı değerlerini onaltılık gösterme desteği eklendi.

    -   Yeni geçici değişkenleri (ifadeler) oluşturmak için destek eklendi.

    -   Örtük ilkel dönüşümler desteği eklendi.

    -   Daha iyi bir tür bekleniyor ya da bulunamadı, hata iletileri eklendi.

-   **Proje oluşturma:**  

    -   CSharp soneki proje adlarından kaldırıldı.

    -   Bir sistem geniş msbuild hedefleri dosyası kaldırılan başvuru.

-   **Sihirbazlar:**  

    -   Unity Düzenleyicisi veya Util.cs gibi olmayan davranışa türleri iletilerinde desteği eklendi.

    -   Ekleme ve Unity iletilerini biçimlendirmek için Roslyn için geçiş yaptı.

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Hata Ayıklayıcı:**  

    -   Genel türler değerlendirirken Unity kilitlenen hatanın düzeltildiğini.

    -   Boş değer atanabilir türler sabit işlenmesini.

    -   Numaralandırmalar sabit işlenmesini.

    -   İç içe geçmiş üye türleri sabit işlenmesini.

    -   Sabit koleksiyonu dizin oluşturucusu erişim.

    -   Hata ayıklama yineleyici çerçeveler yeni C# derleyici ile sabit desteği.

-   **Proje oluşturma:**  

    -   Derleme Unity Web player hedeflerken engelledi sabit hata.

    -   Bir web ile bir komut dosyası derlenirken derleme engelledi sabit hata dosya adı kodlanmış.

## <a name="2300"></a>2.3.0.0  
 Yayımlanan 2016-07-14  

### <a name="new-features"></a>Yeni Özellikler  

-   **Genel:**  

    -   Visual Studio'nun hata listesinde Unity konsol devre dışı bırakmak için bir seçenek günlüklerini eklendi.  

    -   Oluşturulan proje özellikleri değiştirilmesine izin vermek için bir seçenek eklenmiştir.  

-   **Hata Ayıklayıcı:**  

    -   Eklenen metin, XML, HTML ve JSON görselleştiriciler dize.  

-   **Sihirbazlar:**  

    -   MonoBehaviors eksik eklendi.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Genel:**  

    -   Visual Studio ayarları görüntülenmesini içindeki denetimleri engelledi ReSharper ile bir çakışma sabit.  

    -   Bazı durumlarda hata ayıklama engelledi Xamarin ile bir çakışma sabit.  

-   **Hata Ayıklayıcı:**  

    -   Hata ayıklama sırasında dondurmak Visual Studio neden bir sorun düzeltilmiştir.  

    -   Visual Studio 2015'te işlevi kesme noktaları ile ilgili bir sorun düzeltilmiştir.  

    -   Birkaç ifade değerlendirme sorunlar giderildi.  

## <a name="2200"></a>2.2.0.0  
 Yayımlanan 2016-02-04  

### <a name="new-features"></a>Yeni Özellikler  

-   **Sihirbazlar:**  

    -   Eklenen akıllı aramada **uygulama MonoBehavior** Sihirbazı.  

    -   Yapılan sihirbazları bağlam kullanan; Örneğin, NetworkBehavior iletileri yalnızca NetworkBehavior ile çalışırken kullanılabilir.  

    -   Sihirbazlar NetworkBehavior iletiler için destek eklendi.  

-   **KULLANICI ARABİRİMİ:**  

    -   MonoBehavior iletileri görünürlüğünü yapılandırmak için bir seçenek eklenmiştir.  

    -   Unity projelerine ilgili olmayan Visual Studio özellik sayfaları kaldırıldı.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Proje oluşturma:**  

    -   Sabit başvuruları UnityEngine ve UnityEditor Unity 4.6 üzerinde.  

    -   Unity OSX üzerinde çalışırken, proje dosyalarını sabit nesil.  

    -   Sabit işleme hashmark (#) karakterleri içeren proje adları.  

    -   Oluşturulan projeleri için C# 4 kısıtlı.  

-   **Hata Ayıklayıcı:**  

    -   Bir sorunu ifade değerlendirme ile Unity coroutine içinde hata ayıklama sırasında sabit.  

    -   Hata ayıklama sırasında dondurmak Visual Studio neden bir sorun düzeltilmiştir.  

-   **KULLANICI ARABİRİMİ:**  

    -   Bir uyumsuzluk sabit [sekmeleri Studio](https://tabsstudio.com/) Visual Studio uzantısı.  

-   **Yükleyici:**  

    -   HKLM Kayıt defteri girişleri oluşturarak VSTU (tüm kullanıcılar için yüklenir) makine genelinde yüklenmesini destekler.  

    -   Giderilen sorunlar VSTU aynı sürümü Visual Studio'nun birden çok farklı sürümleri için yüklendiğinde VSTU kaldırılması ile. Örneğin, VSTU **2015** 2.1.0.0 ve VSTU **2013** 2.1.0.0 her ikisi de yüklenmedi.  

## <a name="2100"></a>2.1.0.0  
 Yayımlanan 2015-09-08  

### <a name="new-features"></a>Yeni Özellikler  

-   Unity 5.2 desteği  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Menü öğeleri Unity görüntülemek < 4.2  

-   Bir hata iletisi artık Visual Studio XML IntelliSense'i dosyalarını kilitler görüntülenir.  

-   Tanıtıcı <\<değiştirilir >> koşullu bağımsız değişkeni bir Boole değeri olmadığında koşullu kesme noktaları.  

-   Windows mağazası uygulamaları için UnityEngine ve UnityEditor derlemeleri sabit başvurular.  

-   Hata ayıklayıcıda adımlarken sabit: adım için genel özel durum.  

-   Visual Studio 2015'te düzeltilen isabet sayısı kesme noktaları.  

## <a name="2000"></a>2.0.0.0  
 Yayımlanan 2015-07-20  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Unity tümleştirme:**  

    -   Dönüştürme DLL ve kendi hata ayıklama simgeleri (PDB) alırken Visual Studio 2015 ile oluşturulan hata ayıklama simgeleri düzeltilmiştir.  

    -   Her zaman MDB dosyaları DLL ve kendi hata ayıklama simgeleri (PDB) alırken ne zaman bir MDB dosyası da sağlanır dışında oluşturur.  

    -   Sabit kirliliği Unity proje dizininin obj dizinine sahip.  

    -   Başvuruları System.Xml.Link ve System.Runtime.Serialization sabit nesil.  

    -   Proje dosyası oluşturma API birden çok aboneleri için destek eklendi kanca oluşturur.  

    -   Üretilecek dosyalardan birini kilitli olduğunda bile her zaman tam proje dosyası oluşturma.  

    -   Desteği eklendi * uzantısı joker karakter filtre C# projesinde dahil edilecek dosya belirtirken.  

-   **Visual Studio tümleştirmesi:**  

    -   Bir uyumluluk sorunu üretkenlik güç araçları ile düzeltilmiştir.  

    -   Olaylar ve temsilciler bildirimleri MonoBehaviors oluşturma sabit.  

-   **Hata Ayıklayıcı:**  

    -   Hata ayıklama sırasında olası dondurma sabit.  

    -   Bir sorun olduğu Yereller belirli yığın çerçeveleri görüntülenmez sabit.  

    -   Boş diziler inceleniyor sabit.  

## <a name="1990---20-preview-2"></a>1.9.9.0 - 2.0 preview 2
 Yayımlanan 2015-04-02  

### <a name="new-features"></a>Yeni Özellikler  

-   **Unity Proje Gezgini:**  

    -   Sınıf Unity proje Gezgini'nde bir dosyayı yeniden adlandırma, otomatik olarak yeniden adlandırın (bkz **seçenekleri** iletişim).  

    -   Otomatik olarak yeni oluşturulan komut dosyalarını Unity proje Gezgini'nde seçin.  

    -   Etkin komut dosyası Unity proje Gezgini'nde izlemek (bkz **seçenekleri** iletişim).  

    -   Visual Studio Çözüm Gezgini'nde çift eşitleme (bkz **seçenekleri** iletişim).  

    -   Visual Studio simgeler Unity proje Gezgini'nde benimser.  

-   **Hata Ayıklayıcı:**  

    -   Kaydedilen ya da kısa süre önce kullanılan hata ayıklama hedeflerini listesinden etkin hata ayıklama hedefi seçin (bkz **seçenekleri** iletişim).  

    -   MonoBehavior yöntemlere işlevi kesme noktaları oluşturmak ve bunları birden çok MonoBehavior sınıflarına uygulayabilirsiniz.  

    -   Nesne Kimliği olun hata ayıklayıcısı'ndaki destekler.  

    -   Destek kesme noktası isabet hata ayıklayıcısında sayısı.  

    -   Hata ayıklayıcıda (Experimental. sonu üzerinde özel durum desteği Bkz: **seçenekleri** iletişim).  

    -   Hata ayıklayıcıdaki ifadeler değerlendirirken nesneler ve diziler oluşturulmasını destekler.  

    -   Destek null karşılaştırma olduğunda Hata ayıklayıcıdaki ifadeler değerlendirme.  

    -   Hata ayıklayıcı izleme Windows eski üyeler filtreler.  

-   **Yükleyici:**  

    -   En iyi duruma getirilmiş için Visual Studio Araçları Unity uzantı kaydı.  

    -   Visual Studio Araçları için Unity 5 için Unity paketini yükleyin.  

-   **Belgeler:** belgeleri oluşturma performansını artırma.  

-   **Sihirbazlar:** yeni MonoBehavior yöntemler Unity 4.6 ve Unity 5 desteği.  

-   **Unity:** arama güvensiz bayrakları ve özel proje dosyası oluşturma sırasında .rsp dosyaları tanımlar.  

-   **Kullanıcı Arabirimi:** eklenen Unity için Visual Studio Araçları **seçenekleri** Visual Studio'da iletişim kutusu.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   **Unity Proje Gezgini:**  

    -   Dosyaları taşınmış veya Visual Studio Çözüm Gezgini'nden yeniden adlandırılmış sonra Unity Proje Gezgini yenileyin.  

    -   Seçimleri Unity proje Gezgini'nde dosyaları yeniden adlandırırken korur.  

    -   Otomatik önlemek genişletip dosyaları çift olduğunda Unity proje Gezgini'nde tıklattınız daraltabilirsiniz.  

    -   Yeni seçilen dosyaların Unity proje Gezgini'nde görünür olduğundan emin olun.  

-   **Hata Ayıklayıcı:**  

    -   Visual Studio'nun donmasına ayıklayıcıdaki ifadeler değerlendirirken olası engeller.  

    -   Yöntem çağrılarını hata ayıklayıcısında uygun etki alanı üzerinde gerçekleşmesi.  

-   **Unity:**  

    -   Unity 5 UnityVS.OpenFile konumunu düzeltin.  

    -   Unity 5 pdb2mdb konumunu düzeltin.  

    -   Proje dosyası oluşturma sırasında olası bir özel durumla engeller.  

    -   Olası dondurma Unity OSX üzerinde çalışırken engeller.  

    -   İç özel durumları işleme.  

    -   Unity konsol günlükleri VS hata listesine gönderin.  

-   **Belgeler:** yeni unity belgeler için belge oluşturmanın düzeltin.  

-   **Proje:** taşıyın ve gerektiğinde bile klasörlerde Unity .meta dosyalarını yeniden adlandırın.  

-   **Sihirbazlar:** MonoBehavior yöntem parametreleri sırasını kodu oluştururken düzeltin.  

-   **Kullanıcı Arabirimi:** desteği Visual Studio Temalar bağlam menüsü ve simgeler.  

## <a name="1980---20-preview"></a>1.9.8.0 - 2.0 Önizleme
 Yayımlanan 2014-11-12  

### <a name="new-features"></a>Yeni Özellikler  

-   Visual Studio 2015 için destek.  

-   Visual Studio 2015'te Unity gölgelendiriciler kod Coloration.  

-   Geliştirilmiş görsel olarak hata ayıklama sırasında değerler:  

    -   Daha iyi görselleştirme ArrayLists, listeler, Hashtable'da ve sözlük.  

    -   Ortak olmayan üyeler ve statik üyeler kategorileri izleme ve yerel görünüm olarak gösterir.  

    -   Özellik için geçerli değer alanının yalnızca değerlendirilecek Unity'nın SerializedProperty geliştirilmiş görüntüsünü.  

    -   Sınıflar ve yapılar için DebuggerDisplayAttribute desteği.  

    -   DebuggerTypeProxyAttribute desteği.  

-   Kodlama kuralları kullanıcı cevaben bizim sihirbazları kullanarak MonoBehaviour yöntemleri ekleme olun.  

-   Derleme zamanı metin şablonları için destek oluşturulan UnityVS projelerinde uygulayın.  

-   ResX kaynaklar için destek oluşturulan UnityVS projelerinde uygulayın.  

-   Açılış gölgelendiriciler Unity Visual Studio'dan destekler.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Oyun içinde Unity sonra Attach başlatmadan önce yuvaların ve Play Visual Studio'da tetiklendi. Bu bazı sorunlar Unity ve VS arasındaki bağlantıyı kararlılığını ile Attach ve Play kullanırken giderir.  

-   Unity'nın komut dosyası motoru hata ayıklayıcı arabiriminde Unity donmasına yatkın yöntemleri çağırmaktan kaçının. Hata ayıklayıcı eklerken bu Unity dondurma giderir.  

-   Hiçbir semboller kullanılabilir olduğunda callstacks görüntüleme düzeltin.  

-   İçin yoksa, günlüğü geri aramasını kaydetmez.  

## <a name="1920"></a>1.9.2.0  
 Yayımlanan 2014-10-09  

### <a name="new-features"></a>Yeni Özellikler  

-   Unity oynatıcıları algılanması geliştirin.  

-   Bizim dosya açan kullanırken, dosya adının yanı sıra, satır numarası geçirmek Unity olun.  

-   Hiçbir yerel belge ise çevrimiçi Unity belgeleri varsayılan.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Bir etki alanı yeniden sonra bir kesme noktası basarsa zaman olası Unity kilitlenme düzeltin.  

-   Yapılandırmamızın kapatırken Unity konsolunda gösterilen özel durumlar düzeltin veya windows hakkında bir etki alanı sonra yeniden yükleyin.  

-   Yerel olarak çalıştıran 64 bit Unity algılanması düzeltin.  

-   Unity sürüm sihirbazların başına MonoBehaviours filtreleme düzeltin.  

-   Burada uzantısı filtresi boşsa tüm varlıklar proje dosyalarında bulunan hatayı düzeltin.  

## <a name="1910"></a>1.9.1.0  
 Yayımlanan 2014-09-22  

### <a name="new-features"></a>Yeni Özellikler  

-   Bağlama kesme kaynak konumları için en iyi duruma getirme.  

-   Hata ayıklayıcı ifade değerlendirmesi aşırı yüklenmiş yöntemleri için destek.  

-   Kutulama temelleri ve değer türlerini ifade değerlendirmesindeki hata ayıklayıcı desteği.  

-   Anonim yöntemler hata ayıklama sırasında C# yerel değişkenler ortamı yeniden oluşturmayı destekler.  

-   Silin ve silme veya Visual Studio'dan dosyaları yeniden adlandırma .meta dosyalarını yeniden adlandırın.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Visual Studio Temalar işlenmesini düzeltin. Daha önce siyah Temalar iletişim kutuları boş görünebilir (bağlantı sorunları [#932637](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/932637/) ve [#936439](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/936439/)).  

-   Düzeltme Unity Dondur Unity yeniden derlenmesi sırasında hata ayıklayıcı bağlanırken (bağlantı sorunları [#947119](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/947119/) ve [#969211](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/969211/)).  

-   Kesme noktaları uzaktan düzenleyiciler veya başka bir sistem üzerinde derlenmiş oynatıcıları hata ayıklama sırasında düzeltin.  

-   Bir kesme noktası gelindiğinde olası Visual Studio çökmeyle düzeltin.  

-   Kesme noktaları olarak gösteren önlemek için bağlama düzeltme kesme noktaları kaldırıldı.  

-   Kapsam dışında görünür dinamik değişkenleri önlemek için hata ayıklayıcı değişken kapsamı işlenmesini düzeltin.  

-   Hata ayıklayıcı ifade hesaplanmasında statik üyeleri arama düzeltme (sorunu bağlanmak [#953379](https://connect.microsoft.com/VisualStudio/feedbackdetail/view/953379/)).  

-   Statik alanları ve özellikleri göstermek için hata ayıklayıcı ifade değerlendirmesindeki türlerini görüntüleme düzeltin.  

-   Unity proje adları Visual Studio (Connect sorun #948666) engelliyor özel karakterler içeriyorsa çözüm nesil düzeltin.  

-   Seçeneğini işaretli (Connect sorun #933357) sonra konsol olayların gönderilmesi hemen durdurmak için Visual Studio Araçları Unity paketini düzeltin.  

-   Başvurular düzgün UnityEngine.UI gibi yeni API'leri başvurular oluşturulan UnityVS projelerinde yeniden algılanması düzeltin.  

-   Visual Studio bozuk yüklemeleri önlemek için yüklemeden önce kapatıldığından emin gerektirecek şekilde yükleyici düzeltin.  

-   VSTU tüm sürümleri arasında paylaşılan bir uygun tek başına bileşeni olarak Unity başvuru derlemelerini yüklemek için yükleyici düzeltin.  

-   Açma komut dosyaları VSTU ile Unity 64 bit sürümlerinde düzeltin.  

## <a name="1900"></a>1.9.0.0  
 Yayımlanan 2014-07-29  

### <a name="new-features"></a>Yeni Özellikler  

-   Unity hata ayıklayıcı Ekle penceresinde bir özel IP ve bağlantı noktası hata ayıklamak için girin olanağı ekleyin.  

-   Unity veya arka planda çalışmaya ayarlamak için yapılandırma seçeneği ekleyin.  

-   Çözüm ve proje dosyalarını veya yalnızca proje dosyalarını oluşturmak için yapılandırma seçeneği ekleyin.  

-   Başlangıç hedef: Unity Attach veya Attach Unity ve Kullan'ı seçin.  

-   Çok boyutlu diziler hata ayıklayıcı görüntü.  

-   Yeni Unity bağlantı noktalarını hata ayıklama Player işleyin.  

-   Unity'nın 4.6 GUI derlemeleri gibi yeni Unity derlemelerine başvurular işleyin.  

-   Hata ayıklarken yerel değişkenler düzgün görüntülemek için kapanışlar deconstructs.  

-   Hata ayıklama sırasında oluşturulan yineleyiciler değişkenleri bağımsız değişkenleriyle deconstructs.  

-   Bir projeyi yeniden yüklediyseniz sonra Unity proje Gezgini'nin durum korur.  

-   Geçerli belgeyle Unity Proje Gezgini eşitlemek için bir komut ekleyin.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Hata ayıklayıcı başlatmadan önce koşullar ayarlanan koşullu kesme noktaları düzeltin.  

-   Uyarılarını önlemek amacıyla UnityEngine referansı düzeltin.  

-   Unity Beta için ayrıştırma sürümleri düzeltin.  

-   Burada değişkenleri yerel değişkenleri penceresinde bir kesme noktası basarsa zaman gösterilmeyebiliyor sorununu düzeltin veya atlama.  

-   Visual Studio 2013'te değişkenleri araç ipuçları düzeltin.  

-   Unity 4.5 IntelliSense belgelerine nesil düzeltin.  

-   Unity düzeltme / Visual Studio iletişimi bir etki alanından sonra yeniden (play/stop Unity içinde).  

-   Visual Studio Temalar bölümlerinin işleme düzeltin.  

> [!IMPORTANT]
>  C# Unity ekosistemi - yeni örnek varlıkları baskın dilde olacak C# ' ta, Unity belgeleri varsayılan C# - biz bizim UnityScript ve hata için temel destek C# deneyimi daha iyi odaklanmak kaldırılmıştır. Sonuç olarak, VSTU çözümleri C# yalnızca sunulmuştur ve yüklemek için çok daha hızlıdır.  

## <a name="1820"></a>1.8.2.0  
 Yayımlanan 2014-01-07  

### <a name="new-features"></a>Yeni Özellikler  

-   Unity'nın komut dosyası altyapısının ağ katmanında bir soruna geçici bir çözüm düzenleyicileri uzak bulma için Mavericks üzerinde çalışır.  

-   Uzak Unity oynatıcıları bulmak için yeni bağlantı noktalarını işler.  

-   Başvuru belirli UnityEngine derlemesi geçerli hedef oluşturun.  

-   Oluşturulan projelerinde içerecek şekilde filtre dosyaları için ayarı ekleyin.  

-   Visual Studio hata listesi gönderen konsol günlüklerine devre dışı bırakmak için bu ayarı ekleyin. Olabilir olarak yalnızca bir geri çağırma konsol günlükleri almak için Unity kayıtlı PlayMaker veya konsol Pro kullanıyorsanız, bu yararlıdır.  

-   Mdb hata ayıklama simgeleri oluşturulmasını devre dışı bırakmak için bu ayarı ekleyin. Bu kendiniz mdb oluşturma yararlıdır.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Unity VS'den dosyaları açıldığında bir gerileme düzeltme > = 4.2 IntelliSense kaybetmek.  

-   Özel Temalar işlemek için bizim VS iletişim kutuları düzeltin.  

-   UPE bağlam menüsünü kapatma düzeltin.  

-   Sürüm özel oluşturulan derlemeyi eşitlenmemiş ise, Unity çökmesi engeller.  

## <a name="1810"></a>1.8.1.0  
 Yayımlanan 2013-11-21  

### <a name="new-features"></a>Yeni Özellikler  

-   Unity 4.3 API'leri ile MonoBehaviour sihirbazları ayarladı.  

-   MonoBehaviour sihirbazları Unity API'leri kullandığınız sürüme bağlı olarak filtre.  

-   Unity için projelerine System.Xml.Linq Başvuru Ekle > 4.1.  

-   Stacktrace başlangıcını iletide içermeyecek şekilde Debug.Log bizim çağrıları prettify.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Burada size Visual Studio'da JavaScript dosyaların varsayılan işleme ile neden hatanın düzeltildiğini.  

-   Bu süre içinde VS, için gerçek görünen bir beyaz piksel sabit.  

-   SCM tarafından salt okunur olarak işaretlenmiş olması durumunda UnityVS.VersionSpecific derleme sabit silinmesini.  

-   Yuva UnityVS paketinde oluştururken sabit özel durumlar.  

-   Bir kilitlenme Visual Studio'da stok görüntüleri Visual Studio derlemelerden yüklenirken sabit.  

-   Bir hata UnityVS.VersionSpecific nesil kaynak yapılar birlik için sabit.  

-   Olası dondurma yuva Unity paketini açarken sabit.  

-   Adında bir tire (-) projesiyle Unity işlenmesi düzeltilmiştir.  

-   ALT + sekme sırası Unity 4.2 ve üzeri karıştırır değil Unity açma komut dosyaları sabit.  

## <a name="1800"></a>1.8.0.0  
 Yayımlanan 2013-09-24  

### <a name="new-features"></a>Yeni Özellikler  

-   Hata ayıklayıcı bağlantı hızı önemli ölçüde geliştirildi.  

-   Dosya ve satır Unity 4.2 ve üzeri için Gezinti otomatik olarak işler.  

-   Koşullu kesme noktaları.  

-   Proje dosya oluşturucu artık T4 şablonları işler.  

-   MonBehavior sihirbazları yeni API ile güncelleştirin.  

-   Unity türleri C# belgeleri IntelliSense.  

-   Aritmetik ve mantıksal ifadeleri değerlendirme.  

-   Uzaktan hata ayıklama preview için Uzak Düzenleyicileri'nin daha iyi bulma.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Bir hata burada biz sızıntısı bir iş parçacığı içinde VS hata ayıklayıcı bağlantı kesildikten sonra sabit.  

-   VS üzerinde görünen bir beyaz piksel sabit.  

-   Durum çubuğu simgesine tıklama işleme sabit.  

-   Eklenti klasörlerde derlemeler ile başvuruları nesil sabit.  

-   Özel durumlar durumunda UnityVS paketinden yuva sabit oluşturma.  

-   UnityVS yeni sürümlerini algılama sabit.  

-   Lisans dolduğunda Lisans Yöneticisi'ni istemi sabit.  

-   İşlem listesi boş işlem penceresine VS, attach ayıklayıcısında işleme bir hata sabit.  

-   Sabit değişen değerleri Boole değerlerini yerel görünümünde.  

## <a name="1220"></a>1.2.2.0  
 Yayımlanan 2013-07-09  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   İfade değerlendirici tam adlarını işleyin.  

-   Özel durum işleme için ilgili bir dondurma burada Unity komut dosyası altyapısı bize yanlış stackframe veri gönderiyor sabit.  

-   Derleme işlemi Web hedefler için sabit.  

-   Visual Studio başlatıldığından ve başlangıçta açmak için dosya listesini silinmiş bir dosyayı içindeydi meydana gelmiş olabilir bir hata sabit.  

-   Benzer olmayan komut dosyalarını işlemek için sabit UnityVS.OpenFile gölgelendiriciler derlenmiş.  

-   Biz şimdi Boo.Lang ve UnityScript.Lang tüm C# projeleri başvuru.  

-   Proje özel karakterleri varsa projelerinde başvuruları sabit nesil.  

-   Geçici çözüm bir VS sorun nerede projeleri yöntem çağrıları için atıldı birden çok NullReferenceException MessageBox tetikler.  

-   Sabit işleme Unity 4.2 Beta derlemelerin.  

## <a name="1210"></a>1.2.1.0  
 Yayımlanan 2013-04-09  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Yerel kod tamamlama bir g/ç hatası durumunda Unity derlemelerde dağıtımını sabit (salt okunur dosyalar gibi ya da Visual Studio tarafından kilitlenmiş dosyaları).  

-   Visual Studio'da zaten açılmışsa burada Unity bir komut dosyasının açılması dosya odaklanmak değil bir gerileme sabit.  

-   Yeni özel durum işleme performans sorununu düzeltti.  

-   Kesme noktaları bazı dış DLL'lerde sabit bağlaması.  

## <a name="1200"></a>1.2.0.0  
 Yayımlanan 2013-03-25  

### <a name="new-features"></a>Yeni Özellikler  

-   Hata ayıklayıcı bağlantı hızı önemli ölçüde geliştirildi.  

-   Büyük projeler için en iyi duruma getirilmiş Unity Proje Gezgini.  

-   (Veya değil) ayırmak için Visual Studio ayarları dikkate işlenen ve işlenmeyen özel durum.  

-   ToString yerel değişkenlerde çağırmak için Visual Studio ayarı kabul.  

-   Ekleme yeni menü hata ayıklama Unity oynatıcıları hata ayıklamak için kullanabileceğiniz ekleme Unity hata ayıklayıcı ->.  

-   Çözüm dosyası oluşturma sırasında UnityVS çözüme eklenen özel projeleri korur.  

-   Ekleme yeni bir klavye kısayolu CTRL + ALT + M Unity işlevi veya üye Unity belgelerine şapka konumunda görüntülemek için CTRL + H ->.  

-   Derleyici yanıt dosyaları (rsp), Visual Studio'da derleme yapılırken dikkate alın.  

-   Oluşturucu yöntemleri hata ayıklama sırasında değişkenleri göstermek için oluşturulan derleyici türleri deconstruct.  

-   Unity paylaşılan bir klasöre yapılandırma gereksinimini ortadan kaldırarak uzaktan hata basitleştirin. Artık Windows Unity projenize erişimi yeterlidir.  

-   Özel bir Unity profili standart bir .net hedef profil olarak yükleyin. Bu, tüm ReSharper gösterebilirsiniz hatalı pozitif sonuç giderir.  

-   Hata ayıklayıcı üzerinde olmayan düzgün bölün olmaz şekilde altyapısı hata, komut dosyası Unity geçici iş parçacığı kayıtlı.  

-   Burada dosya açık isteği kilitlenen çalışırken açık dosyalar, yapabilmek için talep vs'de bir yarış durumu önlemek için dosyayı açan rework.  

-   UnityVS VS oluştururken projeyi derleme yenilemek şimdi soran ve dosyada olmayan artık kaydedin.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Bizim özel .net profili sabit  

-   Tema tümleştirme sabit, bu ile VS 2012 koyu tema bizim sorunları giderir.  

-   VS 2012 kısayoluna sabit hızlı davranışı.  

-   Hata ayıklama sırasında meydana gelebilir sürüm bir sorun düzeltilmiştir ve bir ana olmayan iş parçacığı bir kesme noktası isabet.  

-   İnt gibi türü diğer adların sabit UnityScript ve hata tamamlama  

-   Yeni bir UnityScript veya hata dizesi yazılırken sabit özel durum.  

-   Bir çözüm değildir yüklendiğinde bütünlüğünü menüleri sabit özel durumları.  

-   Sabit hata UV'leri 48: çift tırnağı bazen yazarak hataya ve tüm işlevi (kod tamamlama, sözdizimi vurgulama vb.) bölün.  

-   Sabit hata UV'leri 46: açılan komut dosyası (UnityScript) hata listesi, Visual Studio tıklatıldığında yineleniyor.  

-   Sabit hata UV'leri 42: durum çubuğunda Unity bağlantı logosu VS 2012 fare olayları işleme değil.  

-   Sabit hata UV'leri 44: CTRL + SHIFT + Q VS 2012 hızlı MonoBehaviours için kullanılabilir değil.  

-   Sabit hata UV'leri-40: pencere VS2012 "koyu" tema devre dışı olduğunda Unity proje Gezgini'nde seçili öğeleri okunamaz.  

-   Sabit hata UV'leri 39: sorunu belirtece dönüştürmek kaçışlı dizeleri.  

-   Sabit hata UV'leri-35: çağırma ToString değişkenleri incelerken nesneler üzerinde.  

-   Sabit hata UV'leri 27: Git simgesi penceresi tutarsızlık VS2012 "koyu" tema ile.  

-   Sabit hata UV'leri-11: Eş Yereller.  

## <a name="1100---beta-release"></a>1.1.0.0 - beta sürümü  
 Yayımlanan 2014-10-09  

## <a name="10130"></a>1.0.13.0  
 Yayımlanan 2013-01-21  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Geçersiz iş parçacığı olayları hedef ayıklayıcı gönderiyorsa, oluşabilir Visual Studio'nun kilitlenmesine sabit. Bu genellikle, bir uzak Unity OSX üzerinde hata ayıklama olacağını.  

-   Bir özel durum hata ayıklayıcı kapanıyorsa meydana gelmiş olabilir bir Visual Studio kilitlenmesine sabit.  

-   C# MonoBehavior ad alanında olduğunda bizim MonoBehavior Yardımcıları sabit.  

-   Visual Studio 2012'de UnityScript için hata ayıklayıcı araç ipuçları sabit.  

-   Proje oluşturma yalnızca debug sabitleri Unity değiştiği sabit.  

-   Klavye gezinti Unity proje Gezgini'nde sabit.  

-   Sabit UnityScript renklendirme Atlanan dizeleri.  

-   Proje adı Unity dışında kullanıldığında daha iyi tahmin etmeye bizim dosya açan sabit. Kullanıcı, bir üçüncü bölümü dosya açan UnityVS için temsilciler Unity kullandığında gerekli olmasıdır.  

-   Sabit işleme, Unity UnityVS için gönderilen uzun ileti. Bundan önce uzun iletileri UnityVS Mesajlaşma bizim parçası kilitlenebiliyordu. Sonuç olarak, bazen UnityVS bir dosyayı Unity açmak olmayacaktır.  

## <a name="10120"></a>1.0.12.0  
 Yayımlanan 2013-01-03  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Visual Studio bir kesme noktası silerken, oluşabilir sabit Visual Studio'nun kilitlenmesine.  

-   Bir hata, Unity oyun komut dosyaları yeniden derlenmesi sonra burada bazı kesme noktası isabet değil sabit.  

-   Kesme noktaları ilişkisiz Visual Studio düzgün şekilde bildirmek için hata ayıklayıcı sabit.  

-   Yerel programların hatalarını ayıklamak için Visual Studio hata ayıklayıcısı engelleyen bir kayıt sorun düzeltilmiştir.  

-   UnityScript değerlendirirken gerçekleşir ve ifadeler kayıt t bir özel durum sabit.  

-   Burada Unity .net API düzeyi değiştirme proje dosyalarının bir güncelleştirme tetikleyecek olmayan bir gerileme sabit.  

-   Burada kullanıcı kodu günlük geri çağırma işleyicisinde katılmak API sistemimizde sorun düzeltilmiştir.  

## <a name="10110"></a>1.0.11.0  
 Yayımlanan 2012-11-28  

### <a name="new-features"></a>Yeni Özellikler  

-   Unity 4 resmi desteği.  

-   Unity Proje Gezgini gelen komut dosyalarını düzenleme.  

-   Visual Studio'nun gitmek için penceresinde tümleştirme.  

-   Hata listesinde tıklatarak kaplamaları için bu, ilk stackframe simgelerle için bilgi konsol iletisi ayrıştırma.  

-   Ekleme bir [API](../cross-platform/customize-project-files-created-by-vstu.md) proje oluşturma katılmak kullanıcı izin vermek için.  

-   Ekleme bir [API](../cross-platform/share-the-unity-log-callback-with-vstu.md) LogCallback katılmak kullanıcı izin vermek için.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Visual Studio 2012 Unity proje Gezgini'nde, sabit regresyonu arka planda.  

-   Tam .net profili kullanıcılar için proje oluşturma sabit.  

-   Kullanıcılar için proje oluşturma Web hedef sabit.  

-   Sabit proje oluşturma dahil etmek için hata ayıklama ve izleme derleme simgeler Unity olarak yapar.  

-   Özel karakterler bizim Git simgesi penceresinde kullanırken sabit kilitlenme.  

-   Visual Studio'nun durum çubuğunda bizim simgesi ekliyoruz olamaz, sabit kilitlenme.  

## <a name="10100"></a>1.0.10.0  
 Yayımlanan 2012-10-09  

### <a name="bug-fixes"></a>Hata Düzeltmeleri  

-   Unity Proje Gezgini arka planı Visual Studio 2010'da düzeltilmiştir.  

-   Hata ayıklayıcısını, hata ayıklayıcı arabirimi önceden kilitlenen bir Unity ekleyin UnityVS çalıştıysanız meydana gelmiş olabilir bir Visual Studio dondurma sabit.  

-   Bir kesme noktası ayarlayın ve AppDomain yeniden oluşacak olduğunda meydana gelebilir bir Visual Studio dondurma sabit.  

-   Dosyaları kilitleme engellemek için ve Unity oluşturma işlemi karıştırır Unity derlemeler nasıl alınır sabit.  

## <a name="1090"></a>1.0.9.0  
 Yayımlanan 2012-10-03  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Sabit proje oluşturma zaman Unity Proje Gerçek JavaScript varlıklarını içerir.  

-   İfade değerlendirme işleme sabit bir hata oluştu.  

-   Sabit değer türleri alanları için yeni değerleri ayarlama.  

-   Sabit olası yan kod düzenleyicisinden ifadeler üzerinde hareket ederken etkiler.  

-   İfade değerlendirme için yüklenen derlemelerde türleri nasıl aranır sabit.  

-   Sabit hata UV'leri 21: Değerlendirme atamanın Unity nesneler üzerinde etkisi yoktur.  

-   Sabit hata UV'leri 21: bir yöntem çağırma Unity matematik API hesaplanırken geçersiz bir işaretçi.  

## <a name="1080"></a>1.0.8.0  
 Yayımlanan 2012-09-26  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Sabit bizim betik açan edinilen projesini olacak şekilde yoluna emin olan yoldur Visual Studio ve komut dosyaları açabilirsiniz.  

-   Sabit bir hata ile hata ayıklama oturumu çalışırken oluşturulan kesme noktaları Visual Studio'nun kilitlenmesine neden olabilir.  

-   Sabit UnityVS Visual Studio 2010'ne kaydedilir.  

## <a name="1070"></a>1.0.7.0  
 Yayımlanan 2012-09-14  

### <a name="new-features"></a>Yeni Özellikler  

-   Visual Studio 2012 desteği.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Unity'nin davranışını eşleşecek şekilde Düzenleyicisi ve eklenti proje dosyalarını sabit nesil.  

-   .Pdb simgelerin çeviri Unity 4 sabit.  

> [!IMPORTANT]
>  Visual Studio 2012 destek nedeniyle, biz birkaç dosyalarını yeniden adlandırın ve bazı diğer taşıyabilirsiniz gerekiyordu. Unity almak için UnityVS paketi şimdi UnityVS 2010 veya UnityVS 2012'de, sırasıyla Visual Studio 2010 ve Visual Studio 2012 için olarak adlandırılmıştır. Bu sürüm ayrıca UnityVS proje dosyalarını yeniden oluşturulur gerektirir.  

## <a name="1060---internal-build"></a>1.0.6.0 - iç derleme  
 Yayımlanan 2012-09-12  

## <a name="1050"></a>1.0.5.0  
 Yayımlanan 2012-09-10  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Komut dosyaları veya gölgelendiriciler geçersiz xml karakter varken proje dosyalarını sabit nesil.  

-   Sabit algılama Unity varlık sunucuya bağlanıldığında Unity örnekleri. Bu Unity ve Visual Studio hata ayıklayıcısı otomatik olarak bağlanmaya dosyaları açmaya hataları tetiklendi.  

## <a name="1040"></a>1.0.4.0  
 Yayımlanan 2012-09-05  

### <a name="new-features"></a>Yeni Özellikler  

-   Hata ayıklama simgeleri ın Unity otomatik dönüştürme.  

     Varlık klasörünüzde ilişkili .pdb bir .NET .dll derleme varsa, yalnızca derleme yeniden içeri aktarın ve UnityVS .pdb Unity'nın komut dosyası altyapısı anlar ve, adıma, .NET derlemelerden içine kullanabileceksiniz bir hata ayıklama simgeleri dosyasına dönüştürme UnityVS.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Hata ayıklama yöntemleri ya da Unity içinde özellikleri tarafından oluşturulan özel durumları nedeniyle sırada UnityVS kilitlenme sabit.  

## <a name="1030"></a>1.0.3.0
 Yayımlanan 2012-09-04  

### <a name="new-features"></a>Yeni Özellikler  

-   Unity dosyaları açmaya UnityVS kullanımını devre dışı bırakmak için yeni yapılandırma seçeneği.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   UnityEditor başvurular sabit nesil olmayan Düzenleyicisi projeleri için.  

-   Sabit tanımı olmayan Düzenleyicisi projeleri için UNITY_EDITOR simgesi.  

-   Bizim özel durum çubuğu tarafından kilitlenmesine neden sabit rastgele VS.  

## <a name="1020"></a>1.0.2.0  
 Yayımlanan 2012-08-30  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   PythonTools hata ayıklayıcı sabit çakışıyor.  

-   Mono.Cecil sabit başvurular.  

-   Sabit hatanın nasıl komut dosyası derlemelerde alınan Unity ile Unity 4 b7.  

## <a name="1010"></a>1.0.1.0  
 Yayımlanan 2012-08-28  

### <a name="new-features"></a>Yeni Özellikler  

-   Önizleme Unity 4.0 Beta desteği.  

### <a name="bug-fixes"></a>Hata düzeltmeleri  

-   Özel durumları atma özellikleri denetleme sabit.  

-   Temel nesnelere nesneleri incelerken azalan sabit.  

-   Ekleme noktasını MonoBehavior Sihirbazı'nda için sabit boş açılır listesi.  

-   Dll varlık klasörün içindeki sabit tamamlanmasını UnityScript ve hata.  

## <a name="1000---initial-release"></a>1.0.0.0 - ilk sürüm  
 Yayımlanan 2012-08-22
