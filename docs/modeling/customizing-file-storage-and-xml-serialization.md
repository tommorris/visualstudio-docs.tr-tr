---
title: "Dosya depolama ve XML serileştirme özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.xmlbehavior
helpviewer_keywords: Domain-Specific Language, serialization
ms.assetid: 76c53ef1-e3b9-45da-b425-1bddb3c01395
caps.latest.revision: "17"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: eae3a0ffd77fa4b399b2d62d3139e7bd8a405d48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="customizing-file-storage-and-xml-serialization"></a>Dosya Depolamayı ve XML Serileştirmeyi Özelleştirme
Kullanıcı bir örneği kaydettiğinde veya *modeli*, içinde bir etki alanına özgü dil (DSL) [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bir XML dosyası oluşturulmuş veya güncelleştirilmiş. Dosya depolama modelinde yeniden oluşturmak için yeniden.  
  
 Ayarlar altında ayarlayarak, serileştirme düzenini özelleştirebilirsiniz **Xml serileştirme davranışı** DSL Explorer'da. Bir düğüm altında **Xml serileştirme davranışı** her etki alanı sınıfı, özellik ve ilişki. İlişkileri kendi kaynak sınıflar altında bulunur. Şekil, bağlayıcı ve diyagramı sınıfları karşılık gelen düğümleri de vardır.  
  
 Ayrıca, daha gelişmiş özelleştirmesi için program kod yazabilirsiniz.  
  
> [!NOTE]
>  Model belirli bir biçimde kaydetmek istiyor, ancak bu formdan yeniden yüklemeniz gerekmez, çıktı modelinden özel serileştirme düzenini yerine üretmek için metin şablonları kullanarak göz önünde bulundurun. Daha fazla bilgi için bkz: [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md).  
  
## <a name="model-and-diagram-files"></a>Model ve şema dosyaları  
 Her model, genellikle iki dosyasında kaydedilir:  
  
-   Model dosyası gibi bir ada sahip **Model1.mydsl**. Model öğelerini ve ilişkileri ve özellikleri depolar. Dosya uzantısı gibi **.mydsl** tarafından belirlenen **FileExtension** özelliği **Düzenleyicisi** DSL tanımı'ndaki düğüm.  
  
-   Diyagram dosyası gibi bir ada sahip **Model1.mydsl.diagram**. Şekilleri, bağlayıcılar ve konumlarına, renkler, satır kalınlıklarını ve diğer ayrıntılarını diyagram görünümünü depolar. Kullanıcı silerse bir **.diagram** dosyası, önemli bilgiler modelinde değil kayıp. Diyagramın düzenini kaybolur. Model dosyası açıldığında, varsayılan şekilleri ayarlayın ve bağlayıcılar oluşturulur.  
  
#### <a name="to-change-the-file-extension-of-a-dsl"></a>DSL dosya uzantısını değiştirmek için  
  
1.  DSL tanımını açın. DSL Explorer'da Düzenleyicisi düğümünü tıklatın.  
  
2.  Özellikler penceresinde Düzenle **FileExtension** özelliği. İlk içermez "." dosya adı uzantısı.  
  
3.  Çözüm Gezgini'nde, iki öğe şablon dosyalarında adını değiştirmek **DslPackage\ProjectItemTemplates**. Bu dosyalar bu biçiminde adlara sahiptir:  
  
     `myDsl.diagram`  
  
     `myDsl.myDsl`  
  
## <a name="the-default-serialization-scheme"></a>Varsayılan seri hale getirme düzeni  
 Bu konu için örnek oluşturmak için aşağıdaki DSL tanımını kullanıldı.  
  
 ![DSL tanımı diyagramı &#45; Aile Ağacı Modeli](../modeling/media/familyt_person.png "FamilyT_Person")  
  
 Bu DSL ekranda aşağıdaki görünüme sahip bir model oluşturmak için kullanıldı.  
  
 ![Aile ağacı diyagramı, araç ve Gezgini](../modeling/media/familyt_instance.png "FamilyT_Instance")  
  
 Bu model kaydedildi ve XML metin Düzenleyicisi'nde yeniden açılır:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<familyTreeModel xmlns:dm0="http://schemas.microsoft.com/VisualStudio/2008/DslTools/Core" dslVersion="1.0.0.0" Id="f817b728-e920-458e-bb99-98edc469d78f" xmlns="http://schemas.microsoft.com/dsltools/FamilyTree">  
  <people>  
    <person name="Henry VIII" birthYear="1491" deathYear="1547" age="519">  
      <children>  
        <personMoniker name="/f817b728-e920-458e-bb99-98edc469d78f/Elizabeth I" />  
        <personMoniker name="/f817b728-e920-458e-bb99-98edc469d78f/Mary" />  
      </children>  
    </person>  
    <person name="Elizabeth I" birthYear="1533" deathYear="1603" age="477" />  
    <person name="Mary" birthYear="1515" deathYear="1558" age="495" />  
  </people>  
</familyTreeModel>  
  
```  
  
 Aşağıdaki noktaları serileştirilmiş modeli hakkında dikkat edin:  
  
-   İlk harfi küçük harfli olması dışında her XML düğümü, bir etki alanı sınıf adı aynı olan bir adı vardır. Örneğin, `familyTreeModel` ve `person`.  
  
-   Etki alanı adı ve BirthYear gibi özellikleri XML düğümlerini öznitelikler olarak serileştirilir. Yeniden, özellik adının ilk karakteri küçük harfe dönüştürülür.  
  
-   İlişki kaynak ucu içinde iç içe geçmiş bir XML düğümü olarak her ilişki serileştirilir. Düğüm kaynağı rolü özelliği, ancak bir küçük harf ilk karakter ile aynı ada sahip.  
  
     Örneğin, tanımında DSL adlı bir rol **kişiler** adresindeki kaynaklanan **FamilyTree** sınıfı.  XML'de, bu adlı düğüm tarafından temsil edilen `people` içinde iç içe `familyTreeModel` düğümü.  
  
-   İlişkiyi altındaki iç içe geçmiş bir düğüm olarak katıştırma her ilişki hedef sonuna serileştirilir. Örneğin, `people` düğümü içeren birkaç `person` düğümleri.  
  
-   Her bir başvuru ilişkisi hedef sonuna olarak serileştirilmiş bir *ad*, hedef öğe başvuru kodlar.  
  
     Örneğin, altında bir `person` düğümü olabilir bir `children` ilişki. Bu düğüm adlar gibi içerir:  
  
    ```  
    <personMoniker name="/f817b728-e920-458e-bb99-98edc469d78f/Elizabeth I" />  
    ```  
  
## <a name="understanding-monikers"></a>Anlama adlar  
 Adlar, model ve şema dosyaları farklı bölümleri arasında çapraz göstermek için kullanılır. Bunlar ayrıca kullanılan `.diagram` model dosyası düğümler başvurmak için dosya. Ad iki tür vardır:  
  
-   *Kimliği adlar* hedef öğe GUID teklif. Örneğin:  
  
    ```  
    <personShapeMoniker Id="f79734c0-3da1-4d72-9514-848fa9e75157" />  
  
    ```  
  
-   *Anahtar adları tam* hedef öğe ad anahtar olarak adlandırılan bir atanan etki alanı özelliğinin değeri tarafından tanımlayın. Hedef öğe ad ilişkileri katıştırma ağacında üst öğesi ad tarafından öneki.  
  
     Aşağıdaki örnekler, var. DSL, adlandırılmış şarkı sınıfı bir katıştırma ilişkisi bir etki alanı albüm adlı bir etki alanı sınıftır gelen alınır:  
  
    ```  
    <albumMoniker title="/My Favorites/Jazz after Teatime" />  
    <songMoniker title="/My Favorites/Jazz after Teatime/Hot tea" />  
  
    ```  
  
     Tam anahtar adları, bir etki alanı özelliği için hedef sınıf varsa, kullanılacak seçeneği **ad anahtarı** ayarlanır `true` içinde **Xml serileştirme davranış**. Örnekte, etki alanındaki sınıflar "Albümü" ve "Şarkı" "Title" adlı etki alanı özellikleri için bu seçeneği ayarlayın.  
  
 Tam anahtar adları kimliği adlar okunması kolaydır. Kişiler tarafından okunacak XML modeli dosyalarınızın düşünüyorsanız, tam anahtar adları kullanmayı düşünün. Ancak, aynı ad anahtara sahip birden fazla öğe ayarlanacak kullanıcı için mümkündür. Yinelenen anahtarlar doğru yeniden değil dosya neden olabilir. Bu nedenle, tam anahtar adları kullanarak başvuruda bulunulan bir etki alanı sınıf tanımlarsanız, kullanıcı yinelenen adları olan bir dosyayı kaydetmelerini engelleyerek yollarını düşünmelisiniz.  
  
#### <a name="to-set-a-domain-class-to-be-referenced-by-id-monikers"></a>Bir etki alanı sınıf kimliği takma adlarıyla başvurulacak ayarlamak için  
  
1.  Olduğundan emin olun **ad anahtarı** olan `false` sınıfı ve temel sınıflarının her etki alanı özelliği.  
  
    1.  DSL Explorer'da genişletin **Xml serileştirme Behavior\Class veri\\***\<etki alanı sınıfı >***\Element veri**.  
  
    2.  Doğrulayın **ad anahtarı** olan `false` her etki alanı özelliği.  
  
    3.  Etki alanı sınıfın temel sınıf varsa, o sınıfta yordamı yineleyin.  
  
2.  Ayarlama **seri kimliği**  =  `true` etki alanı sınıfı için.  
  
     Bu özellik altında bulunan **Xml serileştirme davranış**.  
  
#### <a name="to-set-a-domain-class-to-be-referenced-by-qualified-key-monikers"></a>Tam anahtar takma adlarıyla başvurulacak bir etki alanı sınıf ayarlamak için  
  
-   Ayarlama **ad anahtarı** var olan bir etki alanı sınıfının bir etki alanı özelliği için. Özelliğin türü olmalıdır `string`.  
  
    1.  DSL Explorer'da genişletin **Xml serileştirme Behavior\Class veri\\***\<etki alanı sınıfı >***\Element veri**ve ardından seçin etki alanı özelliği.  
  
    2.  Özellikler penceresinde ayarlayın **ad anahtarı** için `true`.  
  
-   \-veya -  
  
     Kullanarak yeni bir etki alanı sınıfı oluşturmak **adlı etki alanı sınıf** aracı.  
  
     Bu aracı adı olarak adlandırılan bir etki alanı özelliği var. yeni bir sınıf oluşturur. **Öğesi adını** ve **ad anahtarı** bu etki alanı özellik özelliklerini başlatılır `true`.  
  
-   \-veya -  
  
     Bir devralma ilişkisi etki alanı sınıfından bir bilinen ad anahtar özelliğine sahip başka bir sınıf oluşturun.  
  
### <a name="avoiding-duplicate-monikers"></a>Yinelenen adlar önleme  
 Tam anahtar adlar kullanırsanız, bir kullanıcının modeldeki iki öğe anahtar özelliği aynı değere sahip mümkündür. Örneğin, bir sınıf özelliği adı kişi, DSL varsa, kullanıcı ile aynı iki öğe adları ayarlayabilirsiniz. Model olabilmesine rağmen dosyasına kaydedilir, doğru bir şekilde yeniden değil.  
  
 Bu durumu önlemek birkaç yöntem vardır:  
  
-   Ayarlama **öğesi adını**  =  `true` anahtar etki alanı özelliği. DSL tanımı diyagramda etki alanı özelliğini seçin ve sonra Özellikler penceresinde değer ayarlayın.  
  
     Kullanıcı sınıfının yeni bir örneğini oluşturduğunda, bu değeri otomatik olarak farklı bir değer atanması etki alanı özelliği neden olur. Varsayılan davranış sınıf adının sonuna bir numara ekler. Bu kullanıcı için yinelenen adının değiştirilmesi engellemez, ancak kullanıcı değeri model kaydetmeden önce ayarlamaz zaman durumda yardımcı olur.  
  
-   DSL doğrulamasını etkinleştirin. DSL Gezgini'nde Editor\Validation seçin ve ayarlama **kullanan...**  özelliklerine `true`.  
  
     Belirsizlikleri için denetler bir otomatik olarak oluşturulan doğrulama yöntemi yoktur. Yöntem `Load` doğrulama kategorisi. Bu kullanıcı, dosyayı yeniden açmak mümkün olmayabileceğini alırsınız emin olur.  
  
     Daha fazla bilgi için bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).  
  
### <a name="moniker-paths-and-qualifiers"></a>Ad yolları ve niteleyicileri  
 Tam anahtar özniteliğinde ad anahtarı ile sona erer ve kendi üst katıştırma ağacında ad ile önek. Örneğin, bir albümü özniteliğinde ise:  
  
```  
<albumMoniker title="/My Favorites/Jazz after Teatime" />  
  
```  
  
 Ardından, albüm içinde şarkıya biri olabilir:  
  
```  
<songMoniker title="/My Favorites/Jazz after Teatime/Hot tea" />  
```  
  
 Albümleri Kimliğine göre bunun yerine başvuruluyorsa, ancak ardından adlar aşağıdaki gibi olur:  
  
```  
<albumMoniker Id="77472c3a-9bf9-4085-976a-d97a4745237c" />  
<songMoniker title="/77472c3a-9bf9-4085-976a-d97a4745237c/Hot tea" />  
```  
  
 Bir GUID benzersiz olduğundan, hiçbir zaman kendi üst ad tarafından konduğundan emin dikkat edin.  
  
 Belirli bir etki alanına özellik her zaman bir model içinde benzersiz bir değer olacaktır biliyorsanız, ayarlayabileceğiniz **olduğu bilinen ad niteleyicisi** için `true` bu özellik için. Bu, üst ad kullanmadan bir niteleyici kullanılacak neden olur. Örneğin, her ikisini de ayarlarsanız **olduğu bilinen ad niteleyicisi** ve **ad anahtarı** için başlık etki alanı özelliği albüm sınıfının modelinin ad veya tanımlayıcı adlar albüm ve onun katıştırılmış için kullanılmaz alt öğe:  
  
```  
<albumMoniker name="Jazz after Teatime" />  
<songMoniker title="/Jazz after Teatime/Hot tea" />  
  
```  
  
## <a name="customizing-the-structure-of-the-xml"></a>XML yapısını özelleştirme  
 Aşağıdaki özelleştirmeler için genişletin **Xml serileştirme davranışı** DSL Gezgininde düğümü. Bir etki alanı sınıfının altında özellikleri ve bu sınıfta kaynaklanan ilişkileri listesini görmek için öğe verileri düğümünü genişletin. Bir ilişki seçin ve Özellikler penceresinde onun seçeneklerini ayarlayın.  
  
-   Ayarlama **atlayın öğesi** yalnızca hedef öğelerin listesini bırakarak kaynak rol düğüm atlamak için doğru şekilde. Kaynak ve hedef sınıflarını arasında birden fazla ilişki varsa bu seçeneği ayarlanmamış.  
  
    ```  
  
    <familyTreeModel ...>  
      <!-- The following node is omitted by using Omit Element: -->  
      <!-- <people> -->  
        <person name="Henry VIII" .../>  
        <person name="Elizabeth I" .../>  
      <!-- </people> -->  
    </familyTreeModel>  
  
    ```  
  
-   Ayarlama **kullanım tam Form** düğümler ilişki örneği temsil eden hedef düğümleri eklemek için. Etki alanı özellikleri için bir etki alanı ilişki eklediğinizde, bu seçenek otomatik olarak ayarlanır.  
  
    ```  
  
    <familyTreeModel ...>  
      <people>  
        <!-- The following node is inserted by using Use Full Form: -->  
        <familyTreeModelHasPeople myRelationshipProperty="x1">  
          <person name="Henry VIII" .../>  
        </familyTreeModelHasPeople>  
        <familyTreeModelHasPeople myRelationshipProperty="x2">  
          <person name="Elizabeth I" .../>  
        </familyTreeModelHasPeople>  
      </people>  
    </familyTreeModel>  
  
    ```  
  
-   Ayarlama **gösterimi** = **öğesi** yerine bir öğe olarak bir öznitelik değeri olarak kaydedilmiş bir etki alanı özelliğe sahip olmaktır.  
  
    ```  
    <person name="Elizabeth I" birthYear="1533">  
      <deathYear>1603</deathYear>  
    </person>  
    ```  
  
-   Öznitelikleri ve ilişkileri serileştirilir sırasını değiştirmek için öğe verileri altında öğeye sağ tıklayın ve kullanmak **Yukarı Taşı** veya **Aşağı Taşı** menü komutları.  
  
## <a name="major-customization-using-program-code"></a>Program kodunu kullanarak önemli özelleştirme  
 Bölümü veya tümü serileştirme algoritmalarının değiştirebilirsiniz.  
  
 Kodda araştırmak öneririz **Dsl\Generated Code\Serializer.cs** ve **SerializationHelper.cs**.  
  
#### <a name="to-customize-the-serialization-of-a-particular-class"></a>Belirli bir sınıfın serileştirme özelleştirmek için  
  
1.  Ayarlama **olan özel** altında bu sınıf için düğümü **Xml serileştirme davranış**.  
  
2.  Tüm Şablonları dönüştürme, çözümü derlemek ve sonuçta elde edilen derleme hatalarını araştırın. Her hata yakın açıklamaları sağlamak zorunda hangi kod açıklanmaktadır.  
  
#### <a name="to-provide-your-own-serialization-for-the-whole-model"></a>Tüm model için kendi serileştirme sağlamak için  
  
1.  Dsl\GeneratedCode\SerializationHelper.cs yöntemleri geçersiz kıl  
  
## <a name="options-in-xml-serialization-behavior"></a>Xml serileştirme davranış seçenekleri  
 DSL Gezgini'nde, her etki alanı, ilişki, şekil, bağlayıcı ve diyagramı sınıf için bir alt düğüm Xml serileştirme davranışı düğümü içerir. Her düğümleri altında özellikleri ve ilişkileri bu öğede kaynaklanan listesini içerir. İlişkileri kendi sağ hem kendi kaynak sınıflar altında gösterilir.  
  
 Aşağıdaki tabloda, bu bölümde DSL tanımının ayarlayabilirsiniz seçenekleri özetler. Her durumda DSL Gezgini'nde bir öğe seçin ve Özellikler penceresinde seçeneklerini ayarlayın.  
  
### <a name="xml-class-data"></a>XML sınıfı verileri  
 Bu öğeleri DSL Explorer altında bulunan **Xml serileştirme Behavior\Class veri**.  
  
|||  
|-|-|  
|Özellik|Açıklama|  
|Özel öğe şeması vardır|TRUE ise, etki alanı sınıfı bir özel öğe şeması olduğunu gösterir|  
|Özel|Bu ayar **doğru** , bu etki alanı sınıfı için kendi seri hale getirme ve seri durumdan çıkarma kod yazmak istiyorsanız.<br /><br /> Çözümü derlemek ve ayrıntılı yönergeler bulmak için hataları inceleyin.|  
|Etki alanı sınıfı|Bu sınıf veri düğümü uygulandığı etki alanı sınıf. Salt okunur.|  
|Öğe adı|Bu sınıfın öğeler için XML düğüm adı. Varsayılan değer, etki alanı sınıf adı küçük sürümüdür.|  
|Ad öznitelik adı|Başvuru içerecek şekilde ad öğelerinde kullanılan özniteliğin adı. Boşsa, anahtar özellik veya kimliği adı kullanılır.<br /><br /> Bu örnekte, "ad" dir:`<personMoniker name="/Mike Nash"/>`|  
|Ad öğe adı|Bu sınıf öğelerine başvuran adları için kullanılan xml öğesi adı.<br /><br /> Varsayılan değer "Ad" ile sonekine sınıf adı küçük bir sürümüdür. Örneğin, `personMoniker`.|  
|Ad türü adı|Bu sınıfın öğelerine adlar için oluşturulan xsd türünün adı. XSD bulunduğu **Dsl\Generated kod\\\*Schema.xsd**|  
|Kimliği serileştirme|TRUE ise, öğesi GUID'si dosyasına dahil edilir. Bu işaretlenen bir özellik varsa true olmalıdır **ad anahtarı** ve bu sınıf için başvuru ilişkileri DSL tanımlar.|  
|Tür adı|Belirtilen etki alanı sınıfından xsd oluşturulan xml türünün adı.|  
|Notlar|Bu öğeyle ilişkili resmi olmayan notları|  
  
### <a name="xml-property-data"></a>XML özellik verileri  
 XML özellik düğümleri altında sınıfı düğüm bulunamadı.  
  
|||  
|-|-|  
|Özellik|Açıklama|  
|Etki alanı özelliği|Xml serileştirme yapılandırma verilerini uygulandığı özelliği. Salt okunur.|  
|Ad anahtarı|TRUE ise, özellik bu sınıfın örnekleri, etki alanı başvuru takma adlar oluşturma için anahtar olarak kullanılır.|  
|Ad niteleyici|TRUE ise, özellik niteleyici içinde adlar oluşturmak için kullanılır. False ise ve SerializeId bu etki alanı sınıfı için doğru değilse, takma ad katıştırma ağacında üst öğenin nitelenen.|  
|Gösterimi|Öznitelik, özellik bir xml özniteliği olarak serileştirilmiş Öğesi, bu ise sıralanmış bir öğe; Yoksay, onu değilse serileştirilir.|  
|XML adı|Xml özniteliği veya özelliğini temsil eden öğesi için kullanılan ad. Varsayılan olarak, etki alanı özellik adı küçük bir sürümünü budur.|  
|Notlar|Bu öğeyle ilişkili resmi olmayan notları|  
  
### <a name="xml-role-data"></a>XML rol verileri  
 Rol veri düğümleri altında kaynak sınıfı düğüm bulunamadı.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|Özel takma sahip|Bu oluşturmak ve bu ilişkinin çapraz takma ad çözme için kendi kodunuzu sağlamak istiyorsanız, true olarak ayarlayın.<br /><br /> Ayrıntılı yönergeler için çözümü derleme ve hata iletileri çift tıklayın.|  
|Etki alanı ilişkisi|Bu seçenekler uygulandığı ilişki belirtir. Salt okunur.|  
|Öğe atlayın|TRUE ise, kaynak role karşılık gelen XML düğümü şemadan atlanır.<br /><br /> Kaynak ve hedef sınıflarını arasında birden fazla ilişki varsa, bu rolü düğüm iki ilişki ait bağlantıları arasında ayırır. Bu nedenle, bu seçenek bu durumda ayarlamayın öneririz.|  
|Rol öğe adı|Kaynak rolünden türetilmiş XML öğesi adını belirtir. Rol özellik adı varsayılan değerdir.|  
|Tam biçimini kullanın|TRUE ise, her bir hedef öğe veya takma ilişkiyi gösteren bir XML düğümünde içine alınır. Bu ilişki, kendi etki alanı özellikleri varsa true olarak ayarlanmalıdır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gezinme ve bir modeli Program kodunda güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Bir etki alanına özgü dili kod oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)