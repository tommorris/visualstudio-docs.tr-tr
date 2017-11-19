---
title: "Geçersiz kılma ve oluşturulan sınıflar genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, providing overridable classes
ms.assetid: 30baa60d-a8ea-4611-96c1-8fcc3317cf21
caps.latest.revision: "15"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 81f218f9c0d9cd5d9c6abf8f4f9f0fb78181f4f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="overriding-and-extending-the-generated-classes"></a>Üretilen Sınıfları Geçersiz Kılma ve Genişletme
DSL tanımınızı, bir etki alanına özgü dil tabanlı araçlar güçlü bir dizi yapı bir platformdur. Birçok uzantıları ve uyarlamalar geçersiz kılma ve DSL tanımından oluşturulan sınıflar genişletme tarafından yapılabilir. Bu sınıfların yalnızca DSL tanımı diyagramda açıkça tanımlanmış etki alanı sınıfları, aynı zamanda araç kutusu, Gezgini, seri hale getirme ve benzeri tanımlayan diğer sınıflar içerir.  
  
## <a name="extensibility-mechanisms"></a>Genişletilebilirlik mekanizmaları  
 Çeşitli mekanizmalar oluşturulan kod genişletmeye olanak sağlanır.  
  
### <a name="overriding-methods-in-a-partial-class"></a>Kısmi bir sınıftaki yöntemleri geçersiz kılma  
 Kısmi sınıf tanımları birden fazla yerde tanımlanması için bir sınıf sağlar. Bu, oluşturulan kodu kendiniz yazmak koddan ayırmanıza olanak sağlar. El ile yazılmış kodunuzda sınıfları tarafından oluşturulan kodu devralınan geçersiz kılabilirsiniz.  
  
 Adlı bir etki alanı sınıf tanımlarsanız DSL tanımı'nda, örneğin, `Book`, geçersiz kılma yöntemleri ekler özel kod yazabilirsiniz:  
  
 `public partial class Book`  
  
 `{`  
  
 `protected override void OnDeleting()`  
  
 `{`  
  
 `MessageBox.Show("Deleting book " + this.Title);`  
  
 `base.OnDeleting();`  
  
 `} }`  
  
> [!NOTE]
>  Oluşturulan sınıf yöntemleri geçersiz kılmak için her zaman oluşturulan dosyalardan ayrılmış bir dosyada kodunuzu yazın. Genellikle, dosya da adlı bir klasörde yer alır. Oluşturulan kod değişiklik yaparsanız, DSL tanımı koddan yenilediğinizde bunlar kaybolur.  
  
 Geçersiz kılabilirsiniz hangi yöntemlerin bulmak için şunu yazın **geçersiz kılma** sınıfında ve ardından bir boşluk. IntelliSense araç ipucu yöntemleri geçersiz kılınabilir söyler.  
  
### <a name="double-derived-classes"></a>Çift türetilmiş sınıflar  
 Oluşturulan sınıflar yöntemlere çoğunu modelleme ad alanındaki sınıflar, sabit kümesinden devralınır. Ancak, bazı yöntemler oluşturulan kodda tanımlanır. Normalde, bu bunları çok geçersiz kılamaz anlamına gelir; Aynı sınıfın başka bir kısmi tanımında tanımlanan yöntemler kısmi bir sınıfta geçersiz kılamaz.  
  
 Bununla birlikte, ayarlayarak bu yöntemleri geçersiz kılabilirsiniz **oluşturur çift türetilmiş** etki alanı sınıfı için bayrak. Oluşturulacak Bu nedenler iki sınıf, diğer Özet temel sınıf olan bir. Tüm yöntem ve özellik tanımları taban sınıf içinde ve yalnızca oluşturucuyu türetilen sınıfta.  
  
 Örneğin, örnekteki Library.dsl, `CirculationBook` etki alanı sınıf `Generates``Double Derived` özelliğini `true`. Bu etki alanı sınıfı için oluşturulan kod iki sınıf içerir:  
  
-   `CirculationBookBase`, bir Özet olduğu ve tüm yöntemleri ve özellikleri içerir.  
  
-   `CirculationBook`, türetilen `CirculationBookBase`. Kendi oluşturucular dışında boş.  
  
 Herhangi bir yöntemini geçersiz kılmak için türetilmiş sınıf kısmi tanımının gibi oluşturduğunuz `CirculationBook`. Hem oluşturulan ve modelleme çerçevesinden devralınan yöntemleri geçersiz kılabilirsiniz.  
  
 Öğe, model öğelerini, ilişkileri, şekiller, diyagramları ve bağlayıcılar dahil olmak üzere tüm türleri ile bu yöntemi kullanabilirsiniz. Ayrıca, diğer oluşturulan sınıflar yöntemlerini geçersiz kılabilirsiniz. ToolboxHelper gibi her zaman çift türetilmiş bazı sınıfları oluşturulur.  
  
### <a name="custom-constructors"></a>Özel oluşturucular  
 Bir oluşturucu geçersiz kılamaz. Hatta çift türetilmiş sınıflarda, türetilen sınıfta oluşturucusu olması gerekir.  
  
 Kendi Oluşturucusu sağlamak istiyorsanız, ayarlayarak bunu yapabilirsiniz `Has Custom Constructor` DSL tanımında etki alanı sınıfı için. Tıkladığınızda **tüm şablonları dönüştürme**, oluşturulan kod bu sınıf için bir oluşturucu dahil edilmez. Eksik Oluşturucusu çağrısına içerecektir. Çözümü yapılandırdığınızda bu bir hata raporu neden olur. Bir açıklama sağlaması gerekir açıklayan oluşturulan kodu görmek için hata raporu çift tıklatın.  
  
 Oluşturulan dosyalarından ayrı bir dosyada bir parçalı sınıf tanımı yazma ve Oluşturucusu sağlayın.  
  
### <a name="flagged-extension-points"></a>Bayrak eklenmiş uzantı noktaları  
 Bayrak eklenmiş uzantı noktası, bir özellik ya da özel bir yöntem sağlayacaktır belirtmek için bir onay kutusu ayarlayabileceğiniz DSL tanımında bir yerdir. Özel oluşturucular bir örnektir. Diğer örnekler ayarı `Kind` bir etki alanı özelliğin hesaplanan veya özel depolama veya ayar **olan özel** bayrağı bir bağlantı Oluşturucu.  
  
 Bayrağını ayarlayın ve kod yeniden her durumda, bir yapı hatasına neden olur. Sağlamak zorunda açıklayan bir yorum görmek için hata çift tıklayın.  
  
### <a name="rules"></a>Kurallar  
 İşlem Yöneticisi, belirtilen bir olay, bir özellik değişikliği gibi meydana geldiği bir işlem sonundan önce çalışan kurallar tanımlamanıza olanak sağlar. Kurallar, genellikle deposundaki farklı öğeler arasındaki synchronism korumak için kullanılır. Örneğin, kurallar, diyagram model geçerli durumunu görüntüler emin olmak için kullanılır.  
  
 Kuralları bir sınıf başına temelinde tanımlanır, böylece kodu olması gerekmez, kural her nesne için kaydeder. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).  
  
### <a name="store-events"></a>Deposu olayları  
 Modelleme deposu ekleme ve silme işlemlerini öğelerinin özellik değerleri, yapılan değişiklikler dahil olmak üzere deposunda değişiklik belirli türlerdeki dinlemek için kullanan ve benzeri bir olay mekanizması sağlar. Olay işleyicileri değişiklikleri yapılmış olan işlem Kapat sonra adı verilir. Genellikle, bu olaylar, mağaza dışına kaynakları güncelleştirmek için kullanılır.  
  
### <a name="net-events"></a>.NET olayları  
 Bazı olaylar şekilleri için abone olabilirsiniz. Örneğin, bir şekli üzerinde fare tıklamaları dinlediği. Olayı her nesne için abone kod yazmanız gerekir. Bu kod InitializeInstanceResources() bir geçersiz kılma yazılabilir.  
  
 Bazı olaylar dekoratörler Şekli çizmek için kullanılan ShapeFields üzerinde oluşturulur. Bir örnek için bkz [nasıl yapılır: bir şekli veya oluşturma öğesi tıklama müdahale](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md).  
  
 Bu olaylar, genellikle bir işlem içinde gerçekleşmez. Deposunda değişiklik yapmak istiyorsanız, bir işlem oluşturmanız gerekir.