---
redirect_url: /visualstudio/ide/optimize-visual-studio-startup-time/
ms.openlocfilehash: 6ba351d5b395caaddd12021b09f8792cd19b2905
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
Başlık: "en iyi duruma getir çözümü yükleme Visual Studio'da | Microsoft Docs"MS.özel:" "ms.date: 31/08/2017 ms.reviewer:" "MS.Paket:" "ms.tgt_pltfrm:" "ms.topic:"makale"helpviewer_keywords: 
  - "başlangıç zamanı [Visual Studio]"
  - "en iyi duruma getirme başlangıç zamanı [Visual Studio]"
  - "başlangıç zamanı [Visual Studio] hızlandırmak" ms.assetid: 84989983-84bc-4f81-97a8-2131e3a25138 caps.latest.revision: 4 Yazar: "gewarren" ms.author: "gewarren" Yöneticisi: ghogen f1_keywords: 
  - "vs.performancecenter" ms.technology: 
  - "vs-IDE-genel"
---
# <a name="optimize-solution-loading-in-visual-studio"></a>Visual Studio'da yükleme çözümü en iyi duruma getirme
Çözümlerinin çoğu bu çözümler yüklenmesi için geçen süre etkileyen projeleri, çok sayıda içerir. Ancak, takım ortamlarda, geliştiriciler genellikle farklı bir alt kümesi bu projeleri üzerinde çalışması ve tüm bağımsız projeleri yük gerek yoktur.

Visual Studio 2017 destekleyen **basit çözüm yük**. Basit çözüm yük (LSL) modu etkinleştirildiğinde, Visual Studio 2017 küçük bir alt büyük Çözümdeki tüm projeleri yüklenirken yerine projelerinin yükler. Yaygın olarak kullanılan IDE özelliklerin çoğunu LSL modunda çalışır ve oluşturmak yeteneği sağlar arama ve hata ayıklama tüm çözüm üzerinde. (Ana desteklenmeyen özellik LSL modunda Düzenle ve devam edin.)  

> [!NOTE]
> Bu içerik için Visual Studio 2017 güncelleştirme 3 geçerlidir

30'dan fazla projeleri ile büyük çözümler için LSL iki kez olarak (ortalamada) Hızlı çözümler genellikle yükler. IDE özelliklerin çoğunu LSL modunda çalışırken, bazı IDE özelliklerin yüklenmesi için tüm projeleri gerektirebilir. Özellik kullanabilmesi için bu durumlarda, Visual Studio çözümün tamamında otomatik olarak yükler. En kötü durum senaryosunda, basit mod tüm projelerde yüklenirken sonlandırın. 

Yüklü olmayan bir proje üzerinde bir IDE özelliğini kullanırsanız, Visual Studio sizin için uygun proje yükler. Örneğin, bir sınıf diyagram açılmamış bir proje oluşturun veya açın çalışıyorsanız, Visual Studio uygun projeleri otomatik olarak yükler. Aşağıdaki bölümlerde ayrıntılı özellik listesi başvuruluyor.

Aşağıdaki bölümlerde basit çözüm yük ve ayrıca özelliğini etkinleştirmek isteyip istemediğinizi karar Yardım etkinleştirme gösterir.

## <a name="enable-or-disable-lightweight-solution-load"></a>Etkinleştirmek veya basit çözüm yükü devre dışı bırakma

Çözüm Gezgini'nde çözüm adını sağ tıklatın ve seçin **etkinleştirmek basit çözüm yük**. Seçeneği belirledikten sonra basit çözüm yük etkinleştirmek için çözümü kapatıp yeniden yükleme gerekir.

> [!NOTE]
> LSL devre dışı bırakmak için benzer adımları uygulayın. Basit çözüm yük devre dışı bırakmak için seçin **basit çözüm yük devre dışı**, ardından kapatın ve çözümü kapatıp yeniden açın. 

![Çözüm Gezgini](../ide/media/VSIDE_LSL_Solution_Setting.png)

## <a name="global_solution_load_settings"></a>Basit çözüm yük için genel ayarları yapılandırın

Genel olarak devre dışı bırakmak veya seçerek LSL tüm çözümleri için yapılandırma **Araçlar > Seçenekler > Projeler ve çözümler**.

![Araçlar Seçenekler iletişim kutusu](../ide/media/VSIDE_LightweightSolutionLoad.png)

## <a name="how-does-lightweight-solution-load-work-behind-the-scenes"></a>Basit çözüm yükleme arka planda nasıl çalışır?

Visual Studio çözümünüzü yüklediğinizde, daha önce açıldı ve yalnızca bu projeleri yükler projeleri hatırlıyor. Diğer tüm projeleri Çözüm Gezgini'nde görünür ancak yüklü değil. Bir proje genişletmek veya bir projeye sağ tıklayın hemen Visual Studio otomatik-bu projeye yükler. Otomatik Yükleme genellikle projelerinin saniyeden az alır ancak bazı projeler için uzun sürebilir. Ancak, Visual Studio çözümün tamamında çalışan arama, hata ayıklama, yapı ve kaynak denetimi gibi IDE özellikleri sağlar. Örneğin, yalnızca birkaç projeleri basit modda yüklenen olsa bile çözümün tamamında arasında arama yapabilirsiniz. 

Daha fazla projeleri genişletme gibi Visual Studio genişletilmiş projelerinin listesini hatırlıyor. Bir çözüm açıldığında, Visual Studio otomatik-daha önce genişletilen projeleri yükler.

## <a name="visual-studio-prompts-developers-likely-to-see-significant-performance-gains"></a>Önemli performans artışları görmek büyük olasılıkla geliştiriciler Visual Studio ister

Visual Studio telemetrisinden 30 projelerle büyük çözümlerde önemli ölçüde LSL modundan yararlanır. Sonuç olarak, büyük çözümlerde geliştiricilere LSL modu denemek ister. Düzenli aralıklarla kullanarak yukarı ilk zaman End LSL deneyin geliştiriciler çoğunluğu. 

## <a name="visual-studio-makes-recommendations-to-turn-on-lightweight-solution-load-based-on-heuristics"></a>Visual Studio üzerinde buluşsal yöntemler dayalı basit bir çözüm yükünü etkinleştirmek için öneriler yapar

Varsayılan olarak, Visual Studio üzerinde LSL yararlanmak büyük olasılıkla olan kullanıcılar için etkinleştirir. Birden çok çözümleri varsa, Visual Studio LSL modu önemli performans artışları görmek en olası çözümleri sunar. Basit mod seçeneğini belirlerseniz **sağlayan Visual Studio karar** (varsayılan seçenek), Visual Studio açmak çözüm üzerinde buluşsal yöntemler dayalı basit modunda. Bir ileti çubuğu çözüm basit modunda olup olmadığını gösterir. İleti çubuğu gösterir, daha fazla bilgi için seçeneğiniz vardır veya ayarlarını güncelleştirin.

![Açılan pencerede](../ide/media/VSIDE_LSL_Popup.png)

## <a name="ide-features-fully-supported-in-lightweight-mode"></a>IDE basit modunda tam olarak desteklenen özellikler

|Özellik|Basit modunda destekleniyor mu?|
|-|-|-|
|IntelliSense|Evet|
|Ara|Evet|
|Hata Ayıklama|Evet|
|Derleme|Evet|
|Kod Gezinti (Tanıma Git ve tüm başvuruları Bul)|Evet|
|Kod Mercek|Evet|
|Statik kod çözümleme|Evet|
|Dağıtma ve yayımlama|Evet|
|Ekleme & başvuruları kaldırma|Evet|
|Çoklu sürüm desteği|Evet|
|IntelliTrace|Evet|
|Dinamik birim testi|Evet|
|Intellitest|Evet|
|Microsoft Fakes|Evet|
|Düzenle ve Devam Et|Desteklenmez|
|Birim testi|Test projeleri çözüm yapı tarafından izlenen yüklenmesini gerektirir|

## <a name="scenarios-in-which-lightweight-solution-loads-the-appropriate-projects-to-complete-the-operation"></a>Senaryolar basit çözüm işlemi tamamlamak için uygun proje yükler

Çözümdeki bir proje üzerinde çalışmıyorsa proje basit modunda yüklü değil. Bazı özellikler için ek projeleri özellik senaryoyu desteklemek için otomatik olarak yüklenir. (Bu Biz bu senaryoların listesi en aza indirmek düşündüğünüz. ) Bu senaryoları için Visual Studio Proje yükler veya gerektiğinde proje yüklemek isteyip istemediğinizi sorar.

|Kategori|Sorun|
|-|-|-|
|Birim testi|Şu anda yüklü olmadığından projeleri test Projeler listesinde hem "Intellitest oluşturma" ve "Birim testi oluşturma" sihirbazları için görünmüyor. </br>(Proje yüklemek için proje düğümüne genişletebilirsiniz) testler oluşturmak istediğiniz projeleri yüklemeniz gerekir.|
|Sınıf diyagramları|Oluşturursanız veya bir projenin sınıf diyagramı açın, Visual Studio Proje doğrudan bağımlılıkları olan projeler otomatik olarak yükler. </br>Çözümün tamamında yüklü değilse, biz bağımlılık doğrulama diyagramı tarafından başvurulan eski yapılarının doğrulama kapatın.|

## <a name="scenarios-in-which-lightweight-solution-loads-the-entire-solution"></a>Senaryolar basit çözüm çözümün tamamında yükler 

Bazı özellikler için Visual Studio senaryoyu desteklemek için çözümün tamamında otomatik olarak yükler. Bu eylem her zaman tam işlevselliğini kazanması sağlar. Örneğin, bazı TFS işlemleri yüklenmesi için çözümün tamamında gerektirebilir. Tam işlevsellik sağlamak için Visual Studio çözümün tamamında yükler.

|Kategori|Senaryo|
|-|-|-|
|Çözüm düğümde TFS SCC komutu|Bir SCC komutu (içinde Çözüm Gezgini) çözümü düğümde tetikleniyorsa, Visual Studio komut tamamlamadan önce tüm çözüm otomatik olarak yükler.|
|Projenin yüklenmesi|Çözümünüzü .NET Core projeleri ve paylaşılan projeleri içeriyorsa, Visual Studio bu projeleri ilk çözüm yükleme sırasında kendisi her zaman otomatik olarak yükler. Bu projeleri basit mod şu anda desteklemez.|
|Çözüm Yapılandırma Yöneticisi|Çözüm configuration manager veya toplu iş derleme kullanırsanız, Visual Studio tam deneyimi sağlamak için çözümün tamamında otomatik olarak yükler.|
|NuGet Paket Yöneticisi|NuGet Paket Yöneticisi kullanıcı arabirimi veya NuGet Paket Yöneticisi konsolu açarsanız, Visual Studio tam deneyimi sağlamak için çözümün tamamında otomatik olarak yükler.|

## <a name="known-issues"></a>Bilinen sorunlar

Değil LSL modda çalışmaz ve ek projeleri veya çözümün tamamında yüklenmesini gerektiren bazı senaryolar vardır. Etkin bir şekilde bu gibi durumlarda adresleme üzerinde çalışıyoruz. 

|Kategori|Sorun|Geçici Çözüm|
|-|-|-|-|
|IntelliSense|IntelliSense (örneğin, yayın derlemesinde hata ayıklama tersi için değiştirme) bir yapılandırma değişikliği sonra güncelleştirilmemiş. Yapılandırma değişikliği nedeniyle kodu farklar etkisi bağlıdır.|Çözüm yapılandırmasını değiştirdikten sonra yeniden yükleyin.|
|C# /VB projeleri için sınırlamalar yeniden düzenleme|Proje dosyaları değiştirme kodu düzeltmeleri sessizce ilk kez başarısız olabilir.|Bu proje dosyaları için kod düzeltmeleri yapmanız gerekirse projeleri yük. Basit mod düzeltmelerin yüklü olmadığından projelerine yapmaz.|
|Birim testi bulma|Bir proje el ile yüklendiğinde ertelenmiş projelerde bulunan testlerini çalıştırmayın.|Seçili testleri yeniden çalıştırın ve testleri yeniden Bul projeyi yeniden oluşturun.|
|Dinamik birim testi (LUT)|LSL modunda LUT etkinleştirilmedi görebilirsiniz. LUT yüklenemedi test projelerden biri gerektiğinden etkinleştirilmedi.|Dinamik birim testi için çözüm etkinleştirmek için herhangi bir test projesinin yükleyin.|
|Çözüm Gezgini arama|1.    Çözüm Gezgini arama LSL modunda içindeki dosyaların arama yapma ve ilerleme sonuç yok (diğer bir deyişle, yalnızca dosyalar gösterilir arama ağaç ancak değil sınıfları, yöntemleri, vb. altında.).</br>2.    Bir projeye ait tüm dosyaların bir ağaç görünümü yerine düz bir liste olarak gösterilir. Dosyaları bir proje klasörüne ait olduğunda, yalnızca dosya adını arama görünümünde yerine dosyanın göreli yolu gösteriyoruz.</br>Arama görünümünde dosya öğeleri için bağlam menüleri yok.|Çözümün tamamında geleneksel Çözüm Gezgini arama almak için LSL olmayan modda yükleyin.</br>Visual Studio IDE arama de kullanabilirsiniz.|
|C++ projeleri için Nesne Tarayıcısı|Nesne Tarayıcısı sadece yüklenen projeleri için derleme/Wınmd başvuruları gösterir.|Nesne tarayıcısında bilgilerini görmek istediğiniz projeleri yükleyin.|

> [!Note]
> Ortaklarımızın sayesinde Resharper de dahil olmak üzere popüler uzantıları iyi basit çözüm yük ile çalışır.

Geliştiriciler için çözüm yük zaman performansını iyileştirmek için yenilikler hakkında Mutluluk duyuyoruz. Bu yeni bir özellik olduğundan, biz etkin olarak müşteri geri bildirimi sırasında arayan ve bilinen sorunları ele. Geri bildiriminiz işitme için umuyoruz. Visual Studio çözümü yükü en iyi duruma getirme ekibi e-postalslsupport@microsoft.com

## <a name="see-also"></a>Ayrıca bkz.
[Visual Studio performans ipuçları ve püf noktaları](../ide/visual-studio-performance-tips-and-tricks.md)  