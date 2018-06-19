---
title: MSBuild sözlüğü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
ms.assetid: f767d8e4-24d8-4803-80eb-e857202dbe2c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 01020148db1c5d34b4108d2c7ab25aa74fb1b308
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31575084"
---
# <a name="msbuild-glossary"></a>MSBuild Sözlüğü
Bu koşulları, Microsoft Build Engine (MSBuild) ve bileşenlerini tanımlamak için kullanılır.  
  
## <a name="glossary"></a>Sözlük  
 AssemblyFoldersEx  
 Üçüncü taraf satıcılar her tasarım zamanı çözümleme başvuru derlemeleri bulmak için burada bakabilirsiniz destekledikleri framework sürümü için yollar depoladığınız kayıt defteri konumu.  
  
 toplu işleme  
 Toplu işleme anlamına gelir öğeleri olarak bilinen farklı kategorilere ayırma *toplu*, öğe meta verileri ve ardından hedef ya da görev bir kez her toplu kullanarak çalışan göre. Toplu işleme aynıdır MSBuild için--yapı döngü. Daha fazla bilgi için bkz: [Batching](../msbuild/msbuild-batching.md).  
  
 derleme kapsamı  
 Derleme kapsamı, bir proje ve bir birden çok proje derleme oluşturulan tüm alt projeleri için büyük olasılıkla görünen Örneğin, bir genel özelliği MSBuild nesne açıklar.  
  
 alt proje  
 Bkz: *proje, alt*.  
  
 Koşul  
 Birçok MSBuild öğeleri koşullu olarak tanımlanabilir; diğer bir deyişle, `Condition` özniteliği öğe görüntülenir. Koşullu öğeler içeriğini için koşulu değerlendirir yoksayılır `true`. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).  
  
 tanımı, öğesi  
 Bkz: *öğesi tanımı*.  
  
 öğe yayma  
 Derleme yürütme aşamasında öğeleri oluşturulabilir veya alt öğe görevleri tarafından değiştirilmiş `Output` olan öğenin `ItemName` özniteliği. Görev "yeni öğeler yayma" kabul edilir.  
  
 özellik yayma  
 Derleme yürütme aşamasında özellikleri oluşturulabilir veya alt öğe görevleri tarafından değiştirilmiş `Output` olan öğenin `PropertyName` özniteliği. Görev "yeni özellik yayma" kabul edilir.  
  
 Değerlendirme Aşaması  
 Değerlendirme, proje derlemesi ilk aşamasıdır. Tüm özellikleri ve öğeleri projede görünme sırasını değerlendirilir. İçeri aktarılan projeleri projede karşılaşılan olarak değerlendirilir. Yürütme aşamasında ve özellikler veya yayma bildirme veya öğeleri değerlendirme sırasında göz ardı edilir kadar hedefleri ve görevleri çalıştırılmaz.  
  
 yürütme aşaması  
 Yürütme proje derlemesi ikinci aşaması değil. Seçilen hedefleri yerleşiktir ve görevleri çalıştırın. Özellikleri ve öğeleri oluşturulabilir veya değiştiren değerlendirme değerlerine göre.  
  
 işlev, özellik  
 Bkz: *özelliği işlevi*.  
  
 işlev, öğesi  
 Item işlevi bakın.  
  
 öğe  
 Öğeler Yapı sistemine girdiler ve öğesi türlerine kendi öğesi adlarına göre gruplandırılır. Öğeleri genellikle dosyaları temsil eder. Öğesi türü tarafından adlandırılmış öğesi olduğundan koşullarını, ait oldukları *öğesi* ve *öğesi değeri* birbirinin yerine kullanılabilir. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
 öğesi tanımı  
 Öğesi tanım gruplarını herhangi bir öğe türüne varsayılan meta veri ekleme öğe tanımları içerir. İyi bilinen meta verileri gibi varsayılan meta veri belirtilen öğesi türünün tüm öğeleri ile ilişkilidir. Varsayılan meta veri açıkça bir öğe tanımında geçersiz kılınabilir. Daha fazla bilgi için bkz: [öğe tanımları](../msbuild/item-definitions.md).  
  
 Item işlevi  
 Öğe işlevleri projede öğeleri hakkında bilgi alın. Bu işlevler alma Distinct() öğeleri basitleştirmek ve öğeler arasında döngü daha hızlıdır. Öğe yolları ve dizeleri işlemek için işlevleri vardır. Daha fazla bilgi için bkz: [öğe işlevleri](../msbuild/item-functions.md)  
  
 öğe meta verileri  
 Bkz: *meta öğesi*.  
  
 öğe türü  
 Öğe türleri parametre olarak görevleri için kullanılabilir öğeleri listesi olarak adlandırılır. Görev öğesi değerleri yapı işleminin adımları gerçekleştirmek için kullanın. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
 Meta veriler, öğesi  
 Öğe meta verileri bir öğesiyle ilişkili ad-değer çiftleri koleksiyonudur. Meta veri öğesi için tanımlayıcı bilgileri sağlar ve bilinen meta verileri dışında isteğe bağlıdır. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
 meta verileri, bilinen  
 Önceden tanımlanmış bir değer kullanarak başlatılır salt okunur öğe meta verisi tanınmış meta verilerdir. İyi bilinen meta verileri bir dosyaya başvuruda bulunan bir öğeye ait açıklayıcı bilgileri sağlar. Örneğin, adlı iyi bilinen meta veri değeri `FullPath` başvurulan dosyasının tam yolu. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
 çoklu sürüm desteği  
 Hedef birçok farklı CLR'nin ve çerçeveleri MSBuild ve Visual Studio için derleme veya uygulama projesini yeteneği.  
  
 Profili  
 Tam framework kısmı. Bu, bir makineye yüklenmesi için gereken en aza indirmek için kullanılır.  
  
 Proje dosyası  
 Proje dosyası derleme denetimleri MSBuild komut dosyası içerir. Proje dosyaları genellikle "proj".csproj veya .vbproj gibi ile biten bir dosya uzantısına sahip. Proje dosyaları, özellik dosyaları ve hedef dosya alma.  
  
 özellik  
 Derleme işlemi denetlemek için kullanılan bir anahtar-değer çifti özelliğidir. Daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
 özelliği, ortamı  
 Bir ortam özelliği aynı ada sahip bir sistem ortam değişkeni değeri için otomatik olarak başlatılan bir özelliktir. Daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
 özellik dosyası  
 Bir özellik dosyası çoğunlukla özellik grupları ve yapı kılavuz öğesi gruplarını içeren bir proje dosyasıdır. Kurala göre dosya uzantısı .props içeriyor. Özellik dosyaları genellikle ilişkili proje dosyalarını başlangıcında alınır.  
  
 özelliği, işlevi  
 Bir özelliği bir sistem özelliği veya MSBuild komut değerlendirmek için kullanılan yöntemi işlevdir. Özellik yöntemleri Sistem saatini okumak, dizeleri karşılaştırmak, normal ifadeler eşleşen ve diğer eylemleri gerçekleştirmek için kullanılabilir. Daha fazla bilgi için bkz: [özellik işlevleri](../msbuild/property-functions.md).  
  
 iç içe özellik işlevi  
 Özellik işlevleri forma birleştirilmiş daha karmaşık işlevleri. Örneğin,  
  
 `$([MSBuild]::BitwiseAnd(32,   $([System.IO.File]::GetAttributes(tempFile))))`  
  
 Daha fazla bilgi için bkz: [özellik işlevleri](../msbuild/property-functions.md).  
  
 özelliği, genel  
 Genel yapı işlemi denetlemek için kullanılan bir anahtar-değer çifti özelliğidir. Genel özellikleri, bir komut isteminde veya kullanarak ayarlanır `Properties` özniteliği bir [MSBuild görevi](../msbuild/msbuild-task.md)ve bir yapı değerlendirme aşaması sırasında değiştirilemez. Daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
 özellik, yerel  
 Yerel derleme işlemi denetlemek için kullanılan bir anahtar-değer çifti özelliğidir. Bu terim yalnızca, genel bir özellik olmayan bir özellik ayırt etmek için kullanılır.  
  
 özelliği, kayıt defteri  
 Kayıt defteri özelliği sistem kayıt defteri alt anahtarı değeri okuyan özel bir sözdizimi kullanılarak ayarlanmış bir değere sahip. Daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
 ayrılmış özelliği  
 Derleme işlemi denetlemek için kullanılan bir anahtar-değer çifti buna ayrılmış bir özelliktir. Ayrılmış özellikler için önceden tanımlanmış değerler otomatik olarak başlatılır. Daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
 proje kapsamı  
 Proje kapsamı, yalnızca içeren proje dosyası ve bunu aktarır projeleri için görünür olan Örneğin, bir yerel özellik, MSBuild nesne açıklar.  
  
 Proje, alt  
 Bir alt proje MSBuild görevi tarafından bir proje derleme sırasında oluşturulur. Bir alt içeren veya MSBuild görevi içeren hedef alır projenin bu yeni projesidir. Tarafından değiştirilmiş sürece alt proje ana proje genel özelliklerini devralır `Properties` özniteliği.  
  
 yeniden dağıtılabilir dosya listesi  
 Yeniden dağıtım listesi: belirli bir çerçeve karşılık gelen bir derleme listesi.  
  
 başvuru derleme  
 Tasarım zamanı sırasında bir uygulama oluşturmak için kullanılan bir derleme. Bir referans derlemesini gerçek bir kod ve özel arabirimleri dosyadan kaldırabilir, yalnızca meta verileri ve genel arabirimler bırakarak sahip olabilir.  
  
 kayıt defteri özelliği  
 Bkz: *özelliği, kayıt defteri*.  
  
 Hedef  
 Bir hedef görevleri belirli bir sırada gruplandıran ve proje dosyası bölümlerini yapı işlemine giriş noktaları olarak kullanıma sunar. Daha fazla bilgi için bkz: [hedefleri](../msbuild/msbuild-targets.md).  
  
 Hedef, yapı  
 Çalıştıran hedef bakın.  
  
 Hedef, değerlendirme  
 Artımlı derleme nedeniyle, özellikler ve öğeler için olası değişiklikleri hedefleri çözümlenmesi gerekir. Hedef atlanır olsa bile, bu değişikliklerin yapılması gerekir. Bir hedef değerlendirirken, bu çözümlemesini ve bu değişiklikleri yaptıktan anlamına gelir. Daha fazla bilgi için bkz: [artımlı derlemeler](../msbuild/incremental-builds.md).  
  
 Hedef, yürütme  
 Bir hedef yürütme, değerlendirme ve hiç koşul sahip veya olan koşullar doğru olarak değerlendirilen tüm görevler yürütülürken anlamına gelir. Artımlı derleme sırasında hedefleri atlandı veya yürütülen olabilir, ancak her zaman değerlendirilir. Daha fazla bilgi için hedef, değerlendiriliyor.  
  
 çalıştıran hedef  
 False olarak değerlendiren bir koşul sahip bir hedef, yani çalıştırılmaz, yapı üzerinde hiçbir etkisi olmaz. Çalıştırma hedefleri yürütülen atlandı ya. Her iki durumda da, hedef değerlendirilir. Daha fazla bilgi için hedef, değerlendiriliyor.  
  
 Hedef, atlanıyor  
 Artımlı derleme belirlerse tüm çıkış dosyalarının güncel sonra hedef atlandı, diğer bir deyişle, hedef değerlendirilir, ancak hedef görevlerde yürütülmez. Daha fazla bilgi için hedef, değerlendiriliyor.  
  
 Hedef framework ad  
 Framework'te (gibi. açıklayan bir ad NETFramwork, Silverlight, vb.), sürüm ve hedeflemek istediğiniz profili (örneğin, istemci, sunucu, vb.).  
  
 Paketi hedefleme  
 Belirli bir çerçeve ve o çerçevesi için başvuru bütünleştirilmiş kümesi ile dağıtılmış derleme listesi.  
  
 Hedef dosya  
 Çoğunlukla hedefleri ve yapı Kılavuzu görevleri içeren bir proje dosyası hedefleri dosyasıdır. Kurala göre dosya uzantısı .targets içeriyor. Hedef dosyalar genellikle ilişkili proje dosyalarını sonunda içeri aktarılır.  
  
 görev  
 Görevlerdir birimleri yürütülebilir dosyasının kod [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeler derleme işlemleri gerçekleştirmek için kullanın. Örneğin, bir görev, girdi dosyalarını derlemek veya bir dış aracı çalıştırın. Daha fazla bilgi için bkz: [görevleri](../msbuild/msbuild-tasks.md).  
  
 transform  
 Bir dönüştürme için başka bir öğe koleksiyonunun bire bir dönüştürme ' dir. Öğe koleksiyonlarını dönüştürmek bir proje etkinleştirmeye ek olarak, bir dönüşüm kendi giriş ve çıkış arasında doğrudan bir eşleme tanımlamak bir hedef sağlar. Daha fazla bilgi için bkz: [dönüştüren](../msbuild/msbuild-transforms.md).  
  
 iyi bilinen meta verileri  
 Bkz: *meta verileri, bilinen*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild](../msbuild/msbuild.md)