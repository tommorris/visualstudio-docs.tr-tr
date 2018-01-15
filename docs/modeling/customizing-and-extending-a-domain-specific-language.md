---
title: "Özelleştirme ve bir etki alanına özgü dil genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language Tools, creating solutions
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7c0ecd953a0a4cb744f726fc6a62bee564d15579
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="customizing-and-extending-a-domain-specific-language"></a>Etki Alanına Özgü Dili Özelleştirme ve Genişletme
Visual Studio modelleme ve görselleştirme SDK (VMSDK) modelleme araçları tanımlamak birkaç düzeyleri sağlar:  
  
1.  DSL tanımı diyagramı kullanarak bir etki alanına özgü dil (DSL) tanımlayın. DSL hızla, grafiksel gösterimi, okunabilir bir XML form ve kod ve diğer yapıları oluşturmak için gereken temel araçlar da oluşturabilirsiniz.  
  
     Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md).  
  
2.  DSL DSL tanımının daha gelişmiş özellikleri kullanarak hassas ayar yapma. Örneğin, kullanıcı bir öğeyi oluşturduğunda görünür ek bağlantılar yapabilirsiniz. Bu teknikler çoğunlukla DSL tanımında elde edilir ve bazı birkaç satırlık bir program kodu gerektirir.  
  
3.  Modelleme Araçları, program kodunu kullanarak genişletir. VMSDK DSL tanımından oluşturulan kod uzantılarınızın tümleştirileceğini kolaylaştırmak için tasarlanmıştır.  Daha fazla bilgi için bkz: [bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md).  
  
> [!NOTE]
>  DSL tanımları dosya güncelleştirildiğinde tıklamayı değil **tüm şablonları dönüştürme** çözümünüzü yeniden önce araç çubuğundaki Çözüm Gezgini.  
  
##  <a name="customShapes"></a>Bu bölümde  
  
|Bu etkiyi elde etmek için|Bu konuya bakın|  
|----------------------------|-------------------------|  
|Kullanıcının bir şekli renk ve stil özelliklerini ayarlama izin verin.|Şekil veya bağlayıcı sınıfı sağ tıklayın, fareyle **eklemek açığa**ve bir öğeyi tıklatın.<br /><br /> Bkz: [sunu diyagramda özelleştirme](../modeling/customizing-presentation-on-the-diagram.md).|  
|Model öğesi farklı sınıflardaki ilk yükseklik ve genişlik, rengi, araç ipuçları gibi özellikleri paylaşımı diyagramda benzer.|Şekil veya bağlayıcı sınıflar arasında devralmayı kullanın. Türetilmiş şekiller ve türetilmiş etki alanı sınıflar arasındaki eşlemeleri üst eşleme ayrıntılarını devralır.<br /><br /> Ya da farklı bir etki alanı sınıfları map aynı şekli sınıfı.|  
|Model öğesinin bir sınıf tarafından farklı şekillerdeki bağlamları görüntülenir.|Birden fazla shape sınıfı aynı etki alanı sınıfına eşleyin. Çözümü yapılandırdığınızda, hata raporunu izleyin ve kullanmak için hangi şekli karar vermek için istenen kodunu sağlayın.|  
|Şekil rengine veya yazı tipi gibi diğer özelliklere geçerli durumunu gösterir.|Bkz: [şekilleri ve bağlayıcıları modeli yansıtacak şekilde güncelleştirme](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md).<br /><br /> Sunulan özellikler güncelleştiren bir kural oluşturun. Bkz: [kuralları modelindeki değişiklikleri yaymak](../modeling/rules-propagate-changes-within-the-model.md).<br /><br /> Ya da bağlantı okları veya yazı tipi gibi özellikleri açığa olmayan güncelleştirmek için OnAssociatedPropertyChanged() kullanın.|  
|Durumu göstermek için şekil değişikliklerini simgesi.|Oluşturma öğesi eşleme görünürlüğünü DSL Ayrıntıları penceresinde ayarlayın. Aynı konumda bulunan birden fazla görüntü dekoratörler bulun. Bkz: [şekilleri ve bağlayıcıları modeli yansıtacak şekilde güncelleştirme](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md).<br /><br /> Veya geçersiz kılma `ImageField.GetDisplayImage()`. Örnekte bkz <xref:Microsoft.VisualStudio.Modeling.Diagrams.ImageField>.|  
|Herhangi bir şekli bir arka plan görüntüsü Ayarla|Bağlantılı bir ImageField eklemek için InitializeInstanceResources() geçersiz kılar. Bkz: [sunu diyagramda özelleştirme](../modeling/customizing-presentation-on-the-diagram.md).|  
|Herhangi bir derinliğe iç içe şekiller|Özyinelemeli bir ağaç katıştırma ayarlayın. Şekilleri içerecek şekilde BoundsRules tanımlayın. Bkz: [sunu diyagramda özelleştirme](../modeling/customizing-presentation-on-the-diagram.md).|  
|Bir öğenin sınırında sabit noktalarda bağlayıcılar ekleyin.|Diyagramda küçük bağlantı noktaları tarafından temsil edilen katıştırılmış terminal öğelerini tanımlayın. Bağlantı noktaları yerinde düzeltmek için BoundsRules kullanın. Bağlantı hattı diyagramı örneğine bakın [Görselleştirme ve modelleme SDK](http://go.microsoft.com/fwlink/?LinkID=186128).|  
|Metin alanı diğer değerleri türetilmiş bir değer görüntüler.|Metin oluşturma öğesi hesaplanan veya özel depolama bir etki alanı özelliğine eşleyin. Daha fazla bilgi için bkz: [hesaplanan ve özel depolama özellikleri](../modeling/calculated-and-custom-storage-properties.md).|  
|Model öğelerini şekiller arasında veya değişiklikleri yaymak|Bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).|  
|Kaynakları gibi diğer değişiklikleri yaymak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mağaza dışına uzantıları.|Bkz: [olay işleyicileri Model dışındaki değişiklikleri yaymak](../modeling/event-handlers-propagate-changes-outside-the-model.md).|  
|Özellik penceresi ilgili öğesinin özelliklerini görüntüler.|Özellik iletme ayarlayın. Bkz: [Özellikler penceresini özelleştirme](../modeling/customizing-the-properties-window.md).|  
|Özellik kategorileri|Özellikler penceresini Kategoriler adlı bölümlere ayrılmıştır. Ayarlama **kategori** , etki alanı özellikleri. Özellikleri aynı kategori adı ile aynı bölümünde görüntülenir. Ayrıca ayarlayabilirsiniz **kategori** ilişki rolünün.|  
|Etki alanı özellikleri kullanıcı erişimini denetleme|Ayarlama **olan gözatılamaz** bir etki alanı özelliği Özellikler penceresinde çalışma zamanında görünmesini engellemek için false. Hala metin dekoratörler eşleyebilirsiniz.<br /><br /> **Kullanıcı Arabirimi salt okunurdur** kullanıcıların bir etki alanı özelliği değiştirmesini engeller.<br /><br /> Etki alanı özelliği program erişimi etkilenmez.|  
|Ad, simge ve düğümler DSL'ın model Gezgini'nde görünürlüğünü değiştirin.|Bkz: [Model Gezgini özelleştirme](../modeling/customizing-the-model-explorer.md).|  
|Kopyalama, kesme ve yapıştırma etkinleştir|Ayarlama **etkinleştirmek kopyalayıp yapıştırın** özelliği **Düzenleyicisi** DSL Gezgininde düğümü.|  
|Bir öğenin kopyalanan veriler referans bağlantıları ve hedeflerine kopyalayın. Örneğin, bir öğeye bağlı yorumlar kopyalayın.|Ayarlama **yayar kopyalama** (DSL tanımı diyagramdaki etki alanı ilişkisinin bir tarafı satırında tarafından temsil edilen) kaynak rolünün özelliği.<br /><br /> Daha karmaşık efektler elde etmek için ProcessOnCopy geçersiz kılmak için kod yazma.<br /><br /> Bkz: [kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md).|  
|Silme, üst öğesini değiştirme veya bir öğe silindiğinde ile ilgili öğeleri yeniden bağlayın.|Ayarlama **yayar silme** bir ilişki rolü değeri. Daha karmaşık efektler için geçersiz kılma `ShouldVisitRelationship` ve `ShouldVisitRolePlayer` yöntemleri `MyDslDeleteClosure` , tanımlanmış sınıf **DomainModel.cs**<br /><br /> Bkz: [silme davranışı özelleştirme](../modeling/customizing-deletion-behavior.md)|  
|Şekil düzenini ve kopyalama ve sürükle ve bırak görünümünü korur.|Şekilleri ve bağlayıcıları kopyalanan eklemek `ElementGroupPrototype`. Geçersiz kılmak için en uygun yöntemi`ElementOperations.CreateElementGroupPrototype()`<br /><br /> Bkz: [kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md).|  
|Geçerli imleç konumu gibi seçtiğiniz bir konumda şekiller yapıştırın.|Geçersiz kılma `ClipboardCommandSet.ProcessOnCopy()` konuma özgü sürümünü kullanmak üzere `ElementOperations.Merge().` bkz [kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md).|  
|Ek bağlantılar Yapıştır üzerinde oluşturma|ClipboardCommandSet.ProcessOnPasteCommand() geçersiz kıl|  
|Etkinleştirme sürükleyip bu diyagramdan, diğer DSL'ler ve Windows öğeleri|Bkz: [nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)|  
|Üst sürüklediğiniz ise gibi bir şekil ya da bir bağlantı noktası gibi bir alt şekli üzerine sürüklediğiniz aracı izin verir.|Üst öğeye bırakılan nesneyi iletmek için hedef nesne sınıfı üzerinde birleştirme bir Element Directive tanımlayın. Bkz: [öğesi oluşturma ve taşıma özelleştirme](../modeling/customizing-element-creation-and-movement.md).|  
|Şekil veya bir şekli sürüklediğiniz ve ek bağlantıları için aracı izin ver veya oluşturulan nesneler. Örneğin, bir açıklama için bağlı olduğu bir öğenin izin vermek için.|Oluşturulacak bağlantıları tanımlamak ve hedef etki alanı sınıf üzerinde birleştirme bir Element Directive tanımlayın. Karmaşık durumlarda, özel kod ekleyebilirsiniz. Bkz: [öğesi oluşturma ve taşıma özelleştirme](../modeling/customizing-element-creation-and-movement.md).|  
|Öğeleri grubunu bir aracıyla oluşturun. Örneğin, sabit bir bağlantı noktası kümesi ile bir bileşen.|ToolboxHelper.cs araç kutusunu başlatma yöntemi geçersiz kılın. Bir öğe grubunu prototip (öğe ve ilişki bağlantılarını içeren EGP) oluşturun. Bkz: [araçları ve araç kutusunu özelleştirme](../modeling/customizing-tools-and-the-toolbox.md).<br /><br /> Asıl ve bağlantı noktası şekiller EGP içeriyor ya da EGP örneği oluşturulduğunda, bağlantı noktası şekiller konum BoundsRules tanımlayın. Bkz: [BoundsRules şekil konumunu ve boyutunu sınırlamak](../modeling/boundsrules-constrain-shape-location-and-size.md).|  
|İlişki çeşitli türlerde örneği oluşturmak için bir bağlantı aracını kullanın.|Aracı tarafından çağrılan bağlantı Oluşturucu bağlantı bağlanma yönergeleri (LCD) ekleyin. LCD'ler iki öğe türleri arasında ilişki türü belirlenemedi. Bu öğe durumlarına bağlı yapmak için özel kod ekleyebilirsiniz. Bkz: [araçları ve araç kutusunu özelleştirme](../modeling/customizing-tools-and-the-toolbox.md).|  
|Yapışkan araçları - kullanıcı birçok şekiller veya bağlayıcılar art arda oluşturmak için herhangi bir aracı çift tıklayabilirsiniz.|DSL Gezgini'nde seçin `Editor` düğümü. Özellikler penceresinde ayarlayın **kullanan Yapışkan araç kutusu öğelerini**.|  
|Menü komutları tanımlayın|Bkz: [nasıl yapılır: standart menü komutu değiştirme](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md)|  
|Model doğrulama kuralları ile sınırlayın|Bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md)|  
|Kod, yapılandırma dosyaları ya da belgeler DSL oluşturur.|[Etki Alanına Özgü Dilden Kod Oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)|  
|Modelleri nasıl kaydedileceğini özelleştirme dosyasına.|Bkz: [dosya depolama ve XML serileştirme özelleştirme](../modeling/customizing-file-storage-and-xml-serialization.md)|  
|Modelleri veritabanları veya diğer medya kaydedin.|Geçersiz kılma *YourLanguage*DocData<br /><br /> Bkz: [dosya depolama ve XML serileştirme özelleştirme](../modeling/customizing-file-storage-and-xml-serialization.md)|  
|Bunlar bir uygulamanın parçası olarak çalışmak üzere birkaç DSL'ler tümleştirin.|Bkz: [Visual Studio Modelbus kullanarak modelleri tümleştirme](../modeling/integrating-models-by-using-visual-studio-modelbus.md).|  
|Uzantı denetlemek ve üçüncü taraflar tarafından genişletilmesi, DSL izin verin.|[MEF kullanarak DSL'nizi genişletme](../modeling/extend-your-dsl-by-using-mef.md)<br /><br /> [DSL Kitaplığı Kullanarak DSL'ler Arasında Sınıfları Paylaşma](../modeling/sharing-classes-between-dsls-by-using-a-dsl-library.md)<br /><br /> [Salt Okunur Kesimler Oluşturmak için Kilitleme İlkesi Tanımlama](../modeling/defining-a-locking-policy-to-create-read-only-segments.md)|
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir etki alanına özgü dil tanımlama](../modeling/how-to-define-a-domain-specific-language.md)   
 [Bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)   
 [Visual Studio için Modelleme SDK'sı - Etki Alanına Özgü Diller](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

