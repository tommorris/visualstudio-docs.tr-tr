---
title: Seçenekler, Metin Düzenleyici, C/C++, Gelişmiş
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C\C++.Advanced
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Advanced
- VS.ToolsOptionsPages.Text_Editor.C/C++.Advanced
helpviewer_keywords:
- Text Editor Options dialog box, advanced
ms.assetid: 67c82ae5-fddd-49df-baec-8e7498b156f3
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: e3129df5ad051641499276fd5ee76fa0afde8a7d
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234452"
---
# <a name="options-text-editor-cc-advanced"></a>Seçenekler, Metin Düzenleyici, C/C++, Gelişmiş
Bu seçeneklerinde değişiklik yaparak C veya C++ programlama zaman IntelliSense ve gözatma veritabanı ile ilgili davranışı değiştirebilirsiniz.

 İçinde bu sayfaya erişmek için **seçenekleri** iletişim kutusunda, sol bölmede, genişletin **metin düzenleyici**, genişletin **C/C++** ve ardından **Gelişmiş**.

> [!NOTE]
> Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).


## <a name="browsingnavigation"></a>Gözatma gezinme
 Bu seçenekler dışında hiçbir zaman bir çözüm veritabanı etkinliğini kabul edilemez miktarda sistem kaynağı tüketir çok büyük olduğu nadir durumlarda seçmeniz gerekir.

 **Veritabanı devre dışı**

 Veritabanı (SDF), diğer tüm gözatma/gezinti seçenekleri ve tüm IntelliSense özellikleri dışında gözatma kod tüm kullanımını # otomatik tamamlama include devre dışı bırakılır.

 **Veritabanı güncelleştirmeleri devre dışı bırak**

 Veritabanı salt okunur açılacak ve hiçbir güncelleştirme dosyaları düzenlenebilir olarak gerçekleştirilir. Özelliklerinin çoğu çalışmaya devam edecektir. Ancak, düzenlemeler yaptığınız gibi verileri eski olur ve hatalı sonuçlar elde edersiniz.

 **Veritabanı otomatik güncelleştirmeleri devre dışı bırak**

 Kaynak dosyaları değiştirildiğinde veritabanına gözatma kodu otomatik olarak güncelleştirilmez. Ancak, açarsanız **Çözüm Gezgini**projesi için kısayol menüsünü açın ve ardından **yeniden tara çözüm**, tüm güncel olmayan dosyaları denetlenir ve veritabanı güncelleştirilir.

 **Örtük dosyaları devre dışı**

 Veritabanı gözatma kod projede belirtilen olmayan dosyalar için veri toplamak değil. Proje, kaynak dosyaları ve açıkça belirtilen üstbilgi dosyaları içerir. Örtük dosyaları açık dosyalar tarafından (örneğin, afxwin.h, windows.h ve atlbase.h) eklenir. Normalde, sistem bu dosyaları bulur ve ayrıca (gidin dahil) çeşitli göz atma özellikleri için dizin oluşturur. Bu seçeneği seçerseniz, bu dosyaları dizinli değil ve bazı özellikleri için kullanılamaz. Bu seçeneği seçerseniz, "Örtük temizleme devre dışı bırak" ve "Devre dışı bırakmak için dış bağımlılıklar" da örtük olarak seçilir.

 **Örtük temizleme devre dışı bırak**

 Veritabanı gözatma kod temiz değil yukarı artık başvurulmayan örtük dosyaları. Bu seçenek, artık kullanıldığında veritabanından kaldırılmasını örtük dosyaları önler. Örneğin, eklediğiniz bir `#include` mapi.h Kaynak dosyalarınız birine başvuran yönerge, mapi.h bulundu ve dizini oluşturulmuş. Daha sonra kaldırırsanız #include ve dosyanın başka bir yerde başvurulan değil, ilgili bilgileri, en sonunda bu seçeneği seçmezseniz kaldırılacak. (Bkz **yeniden tara çözüm aralığı** seçeneği.) Açıkça çözümü yeniden tara olduğunda bu seçeneği göz ardı edilir.

 **Dış bağımlılıkları klasörleri devre dışı bırakın**

 Her proje için dış bağımlılıklar klasörü oluşturulamadı veya değil. İçinde **Çözüm Gezgini**, her projesi bu proje için tüm örtük dosyalarını içeren bir dış bağımlılıklar klasörünü içerir. Bu seçeneği seçerseniz, o klasördeki görünmüyor.

 **Veritabanını yeniden oluşturun**

 Hiçbir şey veritabanından çözüm yüklendiğinde bir sonraki başlatılışında gözatma kodu yeniden oluşturun. Bu seçeneği seçerseniz, böylece yeniden oluşturulması için veritabanını neden çözüm yük sonraki açışınızda SDF veritabanı dosyası silinir ve tüm dosyaları dizine.

 **Çözüm aralığı yeniden tara**

 Belirttiğiniz aralığı için 'Şimdi çözümü yeniden tara' iş zamanlanır. 0 ile 5000 dakika arasında belirtmeniz gerekir. Varsayılan değer 60 dakikadır. Çözümü yeniden taranıp olsa da, dosya zaman damgalarını bir dosya IDE dışında değiştirildi olup olmadığını belirlemek için denetlenir. (IDE içinde yapılan değişiklikleri otomatik olarak izlenir ve dosyaları güncelleştirilir.) Örtük olarak eklenen dosyalar, bunlar tüm hala başvurulan olup olmadığını belirlemek için denetlenir.

## <a name="diagnostic-logging"></a>Tanılama Günlüğü
 Microsoft, bir sorunu tanılamak için Gelişmiş bilgileri toplamak için ister durumunda bu seçenekleri sunulur. Günlük bilgilerini kullanıcılar için yararlı değildir ve devre dışı bırakmanızı öneririz.

 **Günlük kaydını etkinleştir**

 Çıktı penceresi için tanılama günlük kaydını etkinleştirir.

 **Günlük düzeyi**

 0 ile 5 günlük ayrıntı düzeyini ayarlayın.

 **Oturum açma filtresi**

 Filtreler, bir bit maskesi kullanılarak olay türleri görüntülenir.

 Aşağıdaki seçeneklerden birini toplamını kullanarak ayarlayın:

-   0 - yok

-   1 - genel

-   2 - boş

-   4 - iş öğesi

-   8 - IntelliSense

-   16 - ACPerf

-   32 - ClassView

## <a name="fallback-location"></a>Geri dönüş konumu
 Geri dönüş konumu, birincil konumu (Çözüm aynı dizin) kullanıldığında değil SDF ve IntelliSense destek dosyalarını (örneğin, iPCH) nereye yerleştirilir ' dir. Bu durum, kullanıcı çözüm dizinine yazma iznine sahip değil veya yavaş bir aygıtta çözüm dizindir meydana gelebilir. Varsayılan geri dönüş konumu kullanıcının temp dizininde şeklindedir.

 **Her zaman geri dönüş konumu kullanın**

 Veritabanını ve IntelliSense dosyaları tarama kodu her zaman, "geri dönüş konumu olarak", .sln dosyasını değil yanındaki belirlediğiniz bir klasörde saklanması gerektiğini gösterir. IDE hiçbir zaman çözüm dizini yanındaki SDF veya iPCH dosyaları yerleştirmek dener ve her zaman geri dönüş konumu kullanır.

 **Geri dönüş konumu kullandıysanız uyarma**

 Bilgi sahibi değil ya da 'Geri dönüş konumu' kullanılırsa istenir. Normalde, IDE geri dönüş konumu kullanmanız gerekiyordu bunu size bildirir. Bu seçenek, bu uyarıyı devre dışı bırakır.

 **Geri dönüş konumu**

 Bu değer, veritabanı veya IntelliSense dosyaları tarama kodunu depolamak için ikincil konum olarak kullanılır. Varsayılan olarak, geçici dizininize geri dönüş konumu ' dir. IDE aynı anda çözüm adları ile sorunları önler çözüm tam yolunu karmasını yanı sıra çözüm adını içeren bir alt altında belirtilen yol (veya geçici dizin) oluşturur.

## <a name="intellisense"></a>IntelliSense
 **Otomatik hızlı bilgi**

 İşaretçiyi metin üzerine getirdiğinizde Quıckınfo araç ipuçları sağlar.

 **IntelliSense devre dışı bırak**

 Tüm IntelliSense özellikleri devre dışı bırakır. IDE VCPkgSrv.exe işlemleri IntelliSense isteklere hizmet oluşturmaz ve IntelliSense özellikleri (Quıckınfo, üye listesi, otomatik tamamlama, Param Yardım) çalışır. Anlam renklendirme ve başvuru vurgulama de devre dışı bırakılır. Bu seçenek yalnızca (gezinti çubuğu, ClassView ve özellik penceresi dahil) veritabanı üzerinde kullanan gözatma özelliklerini devre dışı değil.

 **Otomatik güncelleştirmeyi devre dışı bırak**

 IntelliSense için gerçek bir isteği yapılana kadar IntelliSense güncelleştirme ertelendi. Bu gecikme bir dosyada ilk IntelliSense işleminin daha uzun bir yürütme süresi neden olabilir, ancak çok yavaş veya kaynak kısıtlı makinelerde bu seçeneği belirlemek yararlı olabilir. Bu seçeneği seçerseniz, ayrıca dolaylı olarak "Hata Bildirimi'ni devre dışı bırak" ve "Dalgalı çizgiler devre dışı bırak" seçenekleri belirleyin.

 **Hata bildirimini devre dışı bırak**

 Dalgalı çizgiler ve Hata Listesi penceresi aracılığıyla IntelliSense hataların devre dışı bırakır raporlama. Ayrıca, hata raporlama ile ilişkili arka plan ayrıştırma devre dışı bırakır. Bu seçeneği seçerseniz, ayrıca dolaylı olarak "Dalgalı çizgiler devre dışı bırak" seçeneği belirleyin.

 **Dalgalı çizgiler devre dışı bırak**

 IntelliSense hata dalgalı çizgiler devre dışı bırakır. Kırmızı "dalgalı çizgiler" Düzenleyicisi penceresinde gösterme, ancak hata hala Hata Listesi penceresi görünür.

 **Devre dışı # otomatik tamamlama include**

 Otomatik Tamamlama, devre dışı bırakır `#include` deyimleri.

 **Eğik içinde kullanmak # otomatik tamamlama include**

 Otomatik Tamamlama, tetikler `#include` deyimleri zaman "/" kullanılır. Ters eğik çizgi varsayılan sınırlayıcısı olan '\'. Derleyici kabul ya da, bu nedenle ne kod temeliniz kullanan belirtmek için bu seçeneği kullanın.

 **Çeviri birimleri en fazla önbelleğe**

 IntelliSense istekleri için herhangi bir zamanda etkin tutulacak çeviri birimleri maksimum sayısı. 2-15 arasında bir değer belirtmeniz gerekir. Bu sayı doğrudan üst sınırını (bir verilen örneği Visual Studio için) çalışacak VCPkgSrv.exe işlemleri ile ilgilidir. Varsayılan değer 2'dir, ancak kullanılabilir bellek varsa, bu değeri artırmak ve büyük olasılıkla IntelliSense üzerinde biraz daha iyi performans elde etmek.

 Çeviri birimleri hakkında daha fazla bilgi için bkz: [çeviri aşamaları](/cpp/preprocessor/phases-of-translation).

 **Üye listesi nokta-oku**

 Değiştirir '.' ile 'üye listesi için -> uygulanabilir olduğunda'.

 **Agresif üye listesini devre dışı bırak**

 Üye listesi türü veya değişken adını yazarken görünmüyor. Yürütme karakter birini yalnızca yazdıktan sonra listesi tanımlandığı gibi görünür, **üye liste yürütme karakterleri** seçeneği.

 **Üye listesi anahtar sözcükleri devre dışı bırak**

 Dil anahtar sözcükleri gibi `void`, `class`, `switch` üye listesi öneri görünmüyor.

 **Üye listesi kod parçacıkları devre dışı bırak**

 Kod parçacıkları üye listesi öneri görünmüyor.

 **Anlam renklendirme devre dışı bırak**

 Dil anahtar sözcükleri, dizeleri ve açıklamaları hariç tüm kod renklendirme devre dışı bırakır.

 **Akıllı üye listesi tamamlama**

 Tam olarak belirtilmiş bir sözcük sonunda Enter tuşuna seçtiğinizde bir satır ekler.

 **Üye listesi filtre modu**

 Eşleştirme algoritması türünü ayarlar. **Belirsiz** en olası eşleşen bir yazım-benzer, ancak aynı eşleşmeleri bulmak için denetleyici için benzer bir algoritma kullandığından bulur. **Akıllı filtreleme** bir sözcük başlangıcında olmadığınız halde alt dizeler eşleşir. **Önek** word en başından aynı alt dizeler üzerinde yalnızca eşleşir.

 **Üye listesi yürütme karakterleri**

 Kabul edilebilmesi şu anda vurgulanan üye listesi öneri neden karakter belirtir. Ekleyin veya bu listeden karakterleri kaldırın.

## <a name="references"></a>Referanslar
 **Çözümleme devre dışı bırak**

 Performans nedeniyle, 'Tüm başvuruları Bul' her adayı doğrulamak için IntelliSense kullanmak yerine varsayılan ham metinsel arama sonuçlarını görüntüler. Tüm daha doğru sonuçlar işlemleri bulmak için bu onay kutusunu temizleyebilirsiniz. Bir arama başına temelinde filtrelemek için sonuç listesi için kısayol menüsünü açın ve ardından "Çözümleme sonuçlarını." seçin

 **Onaylanmamış Gizle**

 'Tüm başvuruları Bul' sonuçlarında onaylanmamış öğeleri gizleyin. Unset "devre dışı bırak Çözümleme" seçeneği, bu seçenek sonuçlarında onaylanmamış öğeleri gizlemek için kullanabileceğiniz varsa.

 **Başvuru vurgulama devre dışı bırak**

 ## <a name="text-editor"></a>Metin Düzenleyici
 **Etkinleştirme kapsamları genişletin**

 Etkinleştirilirse, yazarak süslü ayraçlar seçili metinle surround ' {' metin düzenleyicisine.

 **Etkinleştirme öncelik genişletin**

 Etkinleştirilirse, yazarak seçili metni parantez ile çevrelendiğinden ' (' metin düzenleyicisine.

## <a name="see-also"></a>Ayrıca Bkz.

- [Dile Özgü Düzenleyici Seçeneklerini Ayarlama](../../ide/reference/setting-language-specific-editor-options.md)
