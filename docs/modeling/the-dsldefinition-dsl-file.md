---
title: DslDefinition.dsl dosya | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, definition file
ms.assetid: f3fc3ed7-2438-4e5a-b3d7-fe7e0e8a134c
caps.latest.revision: "22"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 3e1f9bc81c0d13acd1fb9ac1a22f33262e4644f8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="the-dsldefinitiondsl-file"></a>DslDefinition.dsl Dosyası
Bu konuda Dsl projenin DslDefinition.dsl dosyasında yapısını açıklayan bir [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] tanımlar çözüm bir *etki alanına özgü dil*. Sınıflar ve ilişkiler diyagram, şekil, bağlayıcılar, seri hale getirme biçimi ile birlikte bir etki alanına özgü dil DslDefinition.dsl dosya tanımlar ve **araç** etki alanına özgü dil ve kendi düzenleme araçları. Bir etki alanına özgü dil çözümde bu araçlara tanımlayan kodu DslDefinition.dsl dosyasındaki bilgiler göre oluşturulur.  
  
 Genellikle, kullandığınız *etki alanına özgü dil Tasarımcısı* DslDefinition.dsl dosyasını düzenleyin. Ancak, kendi ham form XML ve bir DslDefinition.dsl dosyasını bir XML düzenleyicisinde açın. Dosyayı içeren hangi bilgilerin ve hata ayıklama ve uzantı amaçlarıyla nasıl düzenlendiğini anlamak daha yararlı olabilir.  
  
 Bu konudaki örnekler bileşen diyagramı çözüm şablonu alınır. Bir örnek görmek için bileşen modelleri çözüm şablona dayalı bir etki alanına özgü dil çözümü oluşturun. Çözüm oluşturduktan sonra DslDefinition.dsl dosya etki alanına özgü dil Tasarımcısı'nda görünür. Dosyayı kapatın, içinde sağ tıklatın **Çözüm Gezgini**, işaret **birlikte Aç**, tıklatın **XML Düzenleyicisi**ve ardından **Tamam**.  
  
## <a name="sections-of-the-dsldefinitiondsl-file"></a>DslDefinition.dsl dosyasının bölümlerinin  
 Kök öğe \<Dsl >, ad alanı, etki alanına özgü dil adı özniteliklerini tanımlamak ve sürüm oluşturma için birincil ve ikincil sürüm numarası. `DslDefinitionModel` Şema için geçerli bir DslDefinition.dsl dosya yapısı ve içeriği tanımlar.  
  
 Alt öğeleri \<Dsl > kök öğesi aşağıdaki gibidir:  
  
 Sınıflar  
 Bu bölümde oluşturulan kodda bir sınıf oluşturur her etki alanı sınıfı tanımlar.  
  
 İlişkiler  
 Bu bölümde her ilişki modelde tanımlar. Kaynak ve hedef bir ilişkinin iki tarafında temsil eder.  
  
 Türler  
 Bu bölümde, her tür ve ad alanını tanımlar. Etki alanı özellikleri, iki tür vardır. `DomainEnumerations`modelde tanımlanır ve DomainModel.cs türleri oluşturur. `ExternalTypes`başka bir yerde tanımlanan türlerini başvurun (gibi `String` veya `Int32`) ve hiçbir şey oluşturmaz.  
  
 Şekiller  
 Bu bölümde modeli Tasarımcısı'nda nasıl göründüğünü açıklayan şekiller tanımlar. Bu geometrik şekilleri modelin diyagramı bölümünde sınıflarda eşlenir.  
  
 Bağlayıcılar  
 Bu bölümde Tasarımcısı'nda görünen bağlayıcıları görünümünü tanımlar. Bu geometrik stili açıklamalar diyagramı bölümünde modelindeki belirli ilişkiler eşlenir.  
  
 XmlSerializationBehavior  
 Bu bölümde, serileştirme düzenini tanımlar ve her sınıf bir dosyaya nasıl kaydedileceği hakkında ek bilgi sağlar.  
  
 ExplorerBehavior  
 Bu bölümde tanımlar nasıl **DSL Explorer** kullanıcı bir model düzenlerken penceresi görüntülenir.  
  
 ConnectionBuilders  
 Bu bölümde her bağlayıcı aracını (her iki sınıf arasında bağlantılar sağlama aracı bağlanabilir) için bir bağlantı Oluşturucu tanımlar. Bu bölümde, bir kaynak ve hedef sınıf bağlanabilir olup olmadığını belirler.  
  
 Diyagram  
 Bu bölümde bir diyagram tanımlar ve arka plan rengi gibi özellikleri ve kök sınıfı belirtmek için kullanın. (Kök sınıfı bir bütün olarak diyagramı tarafından temsil edilen etki alanı sınıftır.) Diyagram bölüm ayrıca şekli veya her bir etki alanı sınıf veya ilişki temsil eden bağlayıcı belirtin, ShapeMap ve ConnectorMap öğeleri içerir.  
  
 Tasarımcı  
 Bu bölümde, bir araya getirir bir tasarımcı (Düzenleyici) tanımlayan bir **araç**, doğrulama ayarları, bir diyagram ve seri hale getirme düzeni. Tasarımcı bölümü de genellikle aynı zamanda kök diyagramın sınıftır modelinin kök sınıfı tanımlar.  
  
 Gezgini  
 Bu bölümde tanımlayan **DSL Explorer** davranışı (XmlSerializationBehavior bölümünde tanımlanmış).  
  
## <a name="monikers-in-the-dsldefinitiondsl-file"></a>DslDefinition.dsl dosyasındaki adlar  
 DslDefinition.dsl dosya belirli öğeleri çapraz başvuru yapmak için takma adlar kullanabilirsiniz. Örneğin, kaynak alt bölüm ve bir hedef alt her ilişki tanımını içerir. Her alt bölümde bu ilişki ile bağlantılı nesne sınıfının ad içerir:  
  
```  
<DomainRelationship ...        Name="LibraryHasMembers" Namespace="ExampleNamespace" >    <Source>      <DomainRole ...>  
       <RolePlayer>  
         <DomainClassMoniker Name="Library" />  
       </RolePlayer>  
     </DomainRole>  
   </Source>  
```  
  
 Genellikle, başvurulan öğenin ad alanı (Bu örnekte, `Library` etki alanı sınıfı) başvuran öğesinde (Bu durumda, LibraryHasMembers etki alanı ilişkisinin) ile aynıdır. Bu durumda, yalnızca sınıf adını ad vermeniz gerekir. Aksi halde, tam form /Namespace/Name kullanmanız gerekir:  
  
```  
  
<DomainClassMoniker Name="/ExampleNameSpace/Library" />  
  
```  
  
 Ad sistem XML ağacında eşdüzey farklı adlara sahip olmasını gerektirir. Örneğin, iki sınıf aynı ada sahip bir etki alanına özgü dil tanımı kaydetmeye çalışırsanız, bu nedenle, doğrulama hataları oluşur. Böylece, doğru daha sonra yeniden yükleyebilirsiniz DslDefinition.dsl dosyayı kaydetmeden önce her zaman böyle yinelenen ad hataları düzeltmeniz gerekir.  
  
 Her tür kendi ad türü: DomainClassMoniker, DomainRelationshipMoniker, vb.  
  
## <a name="types"></a>Türler  
 Types bölümündeki DslDefinition.dsl dosyasını içeren tüm türleri tür özellik belirtir. Bu tür iki tür ayrılır: System.String gibi dış türleri ve numaralandırılmış türler.  
  
### <a name="external-types"></a>Dış türleri  
 Bazı yalnızca kullanılsa standart ilkel türler, bir dizi bileşen diyagramı örnek listeler.  
  
 Her dış türü tanımı yalnızca bir ad ve dize ve sistem gibi bir ad alanı oluşur:  
  
```  
<ExternalType Name="String" Namespace="System" />  
```  
  
 Türlerinin tam adlarını eşdeğer derleyici anahtar sözcükler "dize" gibi yerine kullanılır.  
  
 Dış türleri standart kitaplığı türle kısıtlı değildir.  
  
### <a name="enumerations"></a>Numaralandırmalar  
 Tipik bir numaralandırma belirtimi bu örneğe benzer:  
  
```  
<DomainEnumeration IsFlags="true" Name="PageSort"          Namespace="Fabrikam.Wizard">  
  <Literals>  
    <EnumerationLiteral Name="Start" Value="1"/>  
    <EnumerationLiteral Name="Decision" Value="2"/>  
  </Literals>  
</DomainEnumeration>  
```  
  
 `IsFlags` Tarafından oluşturulan kodu öneki olup olmadığını kontrol eder özniteliği `[Flags]` numaralandırma değerlerinin Bitsel birleştirilebilir olup olmadığını belirler ortak dil çalışma zamanı (CLR) özniteliği. Bu öznitelik ayarlanırsa true değişmez değerler için iki güç değerler belirtmeniz gerekir.  
  
## <a name="classes"></a>Sınıflar  
 Herhangi bir etki alanına özgü dil tanımı'ndaki öğelerin çoğu doğrudan veya dolaylı olarak örneklerini `DomainClass`. Alt sınıflarının `DomainClass` dahil `DomainRelationship`, `Shape`, `Connector`, ve `Diagram`. `Classes` DslDefinition.dsl dosyasının bölümü etki alanı sınıfları listeler.  
  
 Her sınıfı bir özellikler kümesi vardır ve bir taban sınıf olabilir. Bileşen Diyagramı örnekte `NamedElement` sahip bir Özet sınıf bir `Name` türü dize olan özellik:  
  
```  
<DomainClass Id="ee3161ca-2818-42c8-b522-88f50fc72de8"  Name="NamedElement" Namespace="Fabrikam.CmptDsl5"      DisplayName="Named Element"  InheritanceModifier="Abstract">  
  <Properties>  
    <DomainProperty Id="ef553cf0-33b5-4e34-a30b-cfcfd86f2261"   Name="Name" DisplayName="Name"  DefaultValue="" Category="" IsElementName="true">  
      <Type>  
        <ExternalTypeMoniker Name="/System/String" />  
      </Type>  
    </DomainProperty>  
  </Properties>  
</DomainClass>  
```  
  
 `NamedElement`bazı başka sınıfların gibi tabanıdır `Component`, ek olarak kendi özellikleri olan `Name` kaynağından devralındı özelliği `NamedElement`. BaseClass alt düğüm ad başvurusu içeriyor. Başvurulan sınıf aynı ad alanında olduğundan, yalnızca kendi ad ad gereklidir:  
  
```  
<DomainClass Name="Component" Namespace="Fabrikam.CmptDsl5"              DisplayName="Component">  
  <BaseClass>  
    <DomainClassMoniker Name="NamedElement" />  
  </BaseClass>  
  <Properties>  
    <DomainProperty Name="Kind" DisplayName="Kind" >  
      <Type>  
        <ExternalTypeMoniker Name="/System/String" />  
      </Type>  
    </DomainProperty>  
  </Properties>  
```  
  
 (İlişkileri, şekiller, bağlayıcılar ve diyagramları dahil) her etki alanı sınıfı bu öznitelikler ve alt düğümleri sahip olabilir:  
  
-   **Kimliği.** Bu öznitelik bir GUID değeridir. Dosyasındaki bir değer belirtmezseniz, etki alanına özgü dil Tasarımcısı bir değer oluşturur. (Bu belgedeki örneklerde kullanılan, bu öznitelik genellikle alanından tasarruf etmek için atlandı.)  
  
-   **Ad ve Namespace.** Bu öznitelikler oluşturulan kodda sınıfının ad alanı ve adını belirtin. Birlikte bunların etki alanına özgü dil içinde benzersiz olması gerekir.  
  
-   **InheritanceModifier.** Bu, "Özet", "korumalı" veya hiçbiri özniteliğidir.  
  
-   **Görünen adı.** Bu öznitelik görünen addır **özellikleri** penceresi. DisplayName öznitelik alanları ve noktalama içerebilir.  
  
-   **GeneratesDoubleDerived.** Bu öznitelik ayarlanırsa true, iki sınıf oluşturulur ve bir alt sınıfı, diğer biridir. Oluşturulan tüm yöntemleri Bankası'nda, ve oluşturucular alt sınıfta. Bu öznitelik ayarlayarak, özel kodda oluşturulan tüm yöntemi geçersiz kılabilirsiniz.  
  
-   **HasCustomConstructor**. Bu öznitelik ayarlanırsa böylece kendi sürüm yazabilirsiniz true Oluşturucusu oluşturulan koddan atlanır.  
  
-   **Öznitelikleri**. Bu öznitelik oluşturulan sınıfın CLR öznitelikleri içerir.  
  
-   **BaseClass**. Bir taban sınıf belirtirseniz, aynı türde olmalıdır. Örneğin, bir etki alanı sınıf tabanı olarak başka bir etki alanı sınıf olmalıdır ve bir bölme şekli bir bölme şekli olmalıdır. Bir taban sınıf belirtmezseniz, oluşturulan kod sınıfında standart framework sınıfından türetilir. Örneğin, bir etki alanı sınıf öğesinden türetilen `ModelElement`.  
  
-   **Özellikler**. Bu öznitelik işlem denetiminde saklanır ve model kaydedildiğinde kalıcı özellikleri içerir.  
  
-   **ElementMergeDirectives**. Her öğe birleştirme yönergesi başka bir sınıfın başka bir örnek üst sınıfın bir örneğine nasıl eklenir denetler. Bu konunun ilerleyen bölümlerinde öğesi birleştirme yönergeleri hakkında daha fazla ayrıntı bulabilirsiniz.  
  
-   Bir C# sınıfı içinde listelenen her etki alanı sınıfı için oluşturulan `Classes` bölümü. C# sınıfları Dsl\GeneratedCode\DomainClasses.cs içinde oluşturulur.  
  
### <a name="properties"></a>Özellikler  
 Her bir etki alanı özellik bir ad ve bir türe sahip. Ad etki alanı sınıfı ve geçişli tabanları içinde benzersiz olmalıdır.  
  
 Türü listelenenler birine başvurmalıdır `Types` bölümü. Genellikle, bilinen ad ad alanı eklemeniz gerekir.  
  
```  
<DomainProperty Name="Name" DisplayName="Name"  DefaultValue="" Category="" IsElementName="true">  
  <Type>  
    <ExternalTypeMoniker Name="/System/String" />  
  </Type>  
</DomainProperty>  
```  
  
 Her bir etki alanı özellik de bu özniteliklere sahip olabilir:  
  
-   **IsBrowsable**. Bu öznitelik özellik görüntülenip görüntülenmeyeceğini belirler **özellikleri** kullanıcı üst sınıfın bir nesnesi tıklattığında penceresi.  
  
-   **IsUIReadOnly**. Bu öznitelik kullanıcı özelliğinde değiştirip değiştiremeyeceğini belirler **özellikleri** penceresi veya bir oluşturma öğesi özelliği sunulur.  
  
-   **Tür**. Bu öznitelik Normal, hesaplanmış veya CustomStorage ayarlayabilirsiniz. Bu öznitelik için hesaplanan ayarlarsanız değerini belirleyen özel kod sağlamanız gerekir ve özelliği salt okunur olacaktır. Bu öznitelik için CustomStorage ayarlarsanız, hem alır ve değerlerini ayarlar kodu sağlamanız gerekir.  
  
-   **IsElementName**. Bu öznitelik ayarlanırsa üst sınıfının bir örneği oluşturulduğunda true değeri otomatik olarak benzersiz bir değere ayarlanır. Bu öznitelik ayarlanabilir bir dize türünde olmalıdır her sınıf yalnızca bir özellik için true. Bileşen Diyagramı örnekte `Name` özelliğinde `NamedElement` sahip `IsElementName` true olarak ayarlanmış. Her bir kullanıcının oluşturduğu bir `Component` öğesi (devralan `NamedElement`), adı "Component6." gibi bir otomatik olarak başlatılır  
  
-   `DefaultValue`. Bu öznitelik belirttiyseniz, bu öznitelik için yeni bu sınıfın örnekleri, belirttiğiniz değeri atanır. Varsa `IsElementName` , DefaultValue özniteliği belirtir. yeni bir dize ilk bölümü ayarlanmadı.  
  
-   **Kategori** altında özelliği görünür üstbilgisi **özellikleri** penceresi.  
  
## <a name="relationships"></a>İlişkiler  
 `Relationships` Bölümü etki alanına özgü dil tüm ilişkileri listeler. Her `Domain Relationship` ikili ve yönlendirilmiş, hedef sınıf üyeleri için bir kaynak sınıfı üyeleri bağlama. Kaynak ve hedef sınıflarını genellikle etki alanı sınıflardır, ancak diğer ilişkileri ilişkileri de izin verilir.  
  
 Örneğin, bağlantı ilişki OutPort sınıfı üyeleri InPort sınıf üyelerine bağlar. Her bağlantı örneğine ilişkisinin bir OutPort örneği bir InPort örneğine bağlar. İlişki olduğundan çok-çok, her OutPort kaynaklarının birçok bağlantı bağlantılarıyla sahip olabilir ve her InPort örneği hedeflemek birçok bağlantı bağlantılar olabilir.  
  
### <a name="source-and-target-roles"></a>Kaynak ve hedef rolleri  
 Her ilişki aşağıdaki özniteliklere sahip kaynak ve hedef rollerini içerir:  
  
-   `RolePlayer` Özniteliği bağlantılı örnekleri etki alanı sınıfının başvuruyor: OutPort kaynağı için hedef için InPort.  
  
-   `Multiplicity` Özniteliğine sahip dört olası değerler (ZeroMany, ZeroOne, tek ve OneMany). Bu öznitelik, bir rol player ile ilişkilendirilebilir Bu ilişkinin bağlantı sayısını ifade eder.  
  
-   `PropertyName` Özniteliği, diğer uçtaki nesnelere erişmek için sınıf çalma rolündeki kullanılan adını belirtir. Bu ad, şablon veya özel kod, ilişkinin çapraz geçiş için kullanılır. Örneğin, `PropertyName` kaynak rolünün özniteliği `Targets`. Bu nedenle, aşağıdaki kod çalışır:  
  
    ```  
    OutPort op = ...; foreach (InPort ip in op.Targets) ...  
    ```  
  
     Kurala göre çeşitlilik ZeroMany veya OneMany ise çoğul özellik adları.  
  
     Bir role çokluğu karşıt rolü kaç olabilir başvuruyor bu rolünün her örneği ile ilişkili olabilir. Örneğin, ComponentHasPorts ilişkisi hedef rolüne sahip `RolePlayer` bağlantı noktası için ayarlanmış özniteliği `PropertyName` bileşeni için ayarlanan öznitelik ve `Multiplicity` özniteliği için ZeroOne ayarlayın. Bu nedenle, bu rolü kullanmak için uygun kodu verilmiştir:  
  
    ```  
    ComponentPort p = ...; Component c = p.Component; if (c != null) ...  
    ```  
  
-   Rolün `Name` içinde ilişki sınıfı Bu bağlantı sonuna başvurmak için kullanılan addır. Her bir bağlantının her sonunda yalnızca bir örnek olduğundan kurala göre bir rol her zaman tekil, adıdır. Aşağıdaki kod çalışır:  
  
    ```  
    Connection connectionLink = ...; OutPort op = connectionLink.Source;  
    ```  
  
-   Varsayılan olarak, `IsPropertyGenerator` özniteliği true. False olarak ayarlanırsa, bir özellik rol Player sınıf üzerinde oluşturulur. (Bu durumda, `op.Targets`, işe yaramayacaktır gibi). Ancak, ilişkinin çapraz geçiş yapamaz veya özel kod ilişkiyi açıkça kullanıyorsa bağlantılar kendilerini erişim sağlamak için özel kod kullanılacak hala mümkündür:  
  
    ```  
    OutPort op = ...; foreach (InPort ip in Connection.GetTargets(op)) ...  
    foreach (Connection link in Connection.GetLinksToTargets(op)) ...  
    ```  
  
### <a name="relationship-attributes"></a>İlişki öznitelikleri  
 Öznitelikler ve tüm sınıflar için kullanılabilir alt düğümleri ek olarak, her ilişki bu özniteliklere sahiptir:  
  
-   **IsEmbedding**. Bu Boole öznitelik ilişkisi katıştırma ağacının bir parçası olup olmadığını belirtir. Her model katıştırma ilişkileri olan bir ağaç oluşturması gerekir. Bir modelin kökü olmadığı sürece her etki alanı sınıfı bu nedenle en az bir katıştırma ilişki hedefi olmalıdır.  
  
-   **AllowsDuplicates**. Varsayılan olarak yanlış olduğunda, bu Boole öznitelik hem kaynak hem de hedef "birçok" çeşitlilik olan ilişkileri uygular. Bu dil kullanıcılarının aynı ilişki birden fazla bağlantı tarafından tek bir kaynak ve hedef öğe çiftlerine bağlanıp bağlanmadığını belirler.  
  
## <a name="designer-and-toolbox-tabs"></a>Tasarımcısı ve araç kutusu sekmeleri  
 Ana bölümünü **Tasarımcısı** DslDefinition.dsl dosyasının bölümüdür **ToolboxTab** öğeleri. Bir Tasarımcısı birkaç bu öğelerin her biri temsil oluşturulan tasarımcının headed bölümünde bulunabilir **araç**. Her **ToolboxTab** öğesi bir veya daha fazla içerebilir **ElementTool** öğeleri **ConnectionTool** öğeleri ya da her ikisini de.  
  
 Öğe araçları, belirli bir etki alanı sınıfının örnekleri oluşturabilirsiniz. Kullanıcı bir öğeyi aracı diyagram üzerine sürüklendiğinde sonucu öğesi birleştirme yönergeleri Bu konunun ilerleyen bölümlerinde ilgili bölümde açıklandığı gibi öğesi birleştirme yönergeleri tarafından belirlenir.  
  
 Her bağlantı aracını belirli bağlantı Oluşturucu çağırabilirsiniz. Bir bağlantı Oluşturucu ilişkinin burada fare bağlantı oluşturucular bölümde açıklandığı gibi kullanıcı bağlı olarak birden fazla türü oluşturabilirsiniz.  
  
 Ne tür bir araç doğrudan şekiller veya bağlayıcılar oluşturur. Her bir etki alanı sınıf veya bir etki alanı ilişkisinin başlatır; Şekil ve bağlayıcı eşlemeleri sonra o etki alanı sınıf veya etki alanı ilişkisinin nasıl görüntüleneceğini belirler.  
  
## <a name="paths"></a>Yolları  
 Etki alanına yollarını DslDefinition.dsl dosyasında çeşitli konumlarda görünür. Bu yolları bir dizi öğesinden bir bağlantı başka bir model (diğer bir deyişle, bir etki alanına özgü dil örneğini) belirtin. Yol sözdizimi basit ancak ayrıntılı değildir.  
  
 Yollar görünür DslDefinition.dsl dosyasında `<DomainPath>...</DomainPath>` etiketler. Birden çok bağlantılar aracılığıyla yolları gidebilirsiniz rağmen çoğu örnekler uygulamada yalnızca bir bağlantı çapraz geçiş.  
  
 Bir yol kesimleri dizisini oluşur. Her segmentinde bir bağlantı için bir nesne ya da bir nesneye bir bağlantıdan bir atlama ' dir. Bu nedenle, atlama genellikle uzun bir yol için alternatif. İlk atlama bir nesneden bir bağlantıdır, ikinci atlama bağlantısının diğer ucundaki nesnesine, üçüncü atlama sonraki bağlantı vb. için. Bazen bu sıra için bir ilişki kendisini kaynak ya da başka bir ilişki hedefi olduğu istisnadır.  
  
 Her segmentinde bir ilişki adı ile başlar. Bir nesne bağlantısını atlama ilişki bir nokta ve özellik adı önündeki: "`Relationship . Property`". Bir bağlantı nesnesi atlama ilişki ünlem işareti ve rol adı önündeki: "`Relationship ! Role`".  
  
 Bileşen Diyagramı örneği için InPort ShapeMap ParentElementPath bir yolu içerir. Bu yol aşağıdaki gibi başlatır:  
  
```  
    ComponentHasPorts.Component  
```  
  
 Bu örnekte, InPort ComponentPort öğesinin bir alt kümesi ve bir ilişki ComponentHasPorts sahip. Özelliği, bileşen adı verilir.  
  
 C# bu modeline göre yazarken, tek bir adımda bir bağlantı üzerinden her, ilişkili sınıfları ilişki oluşturur özelliğini kullanarak atlayabilirsiniz:  
  
```  
     InPort port; ...  Component c = port.Component;  
```  
  
 Bununla birlikte, her iki atlama yolu sözdiziminde açıkça yapmanız gerekir. Bu gereksinimden dolayı Ara Bağlantı daha kolay erişebilirsiniz. Aşağıdaki kod bağlantısından atlama bileşenine gerçekleştirir:  
  
```  
    ComponentHasPorts.Component / ! Component  
```  
  
 (Önceki segment ile aynı olduğu ilişki adı atlayabilirsiniz.)  
  
## <a name="element-merge-directives"></a>Öğe birleştirme yönergeleri  
 Ne zaman dil kullanıcının sürüklediği bir öğeden **araç** diyagram üzerine aracın sınıfının bir örneği oluşturulur. Ayrıca, bağlantılar, örneği ve varolan model öğeleri arasında yapılır. Dil Kullanıcı onlardan sürüklendiğinde bileşenleri veya açıklamalar gibi bazı öğeler oluşturulan **araç** üzerine diyagramı boş bir parçası. Dil kullanıcı bunları diğer ana bilgisayar öğeleri sürüklendiğinde diğer öğeleri oluşturulur. Örneğin, dil kullanıcı, bir bileşenin üzerine sürüklendiğinde OutPort veya InPort oluşturulur.  
  
 Yalnızca bir öğe birleştirme yönergesi yeni öğe sınıfı için ana sınıf varsa, bileşeni gibi olası ana sınıfının yeni bir öğesi kabul eder. Örneğin, ad DomainClass düğümle "Component" = içerir:  
  
```  
<DomainClass Name="Component" ...> ...  
    <ElementMergeDirective>  
      <Index>  
        <DomainClassMoniker Name="ComponentPort" />  
      </Index>  
      <LinkCreationPaths>  
        <DomainPath>ComponentHasPorts.Ports</DomainPath>  
      </LinkCreationPaths>  
    </ElementMergeDirective> ...  
```  
  
 Dizin düğümü altında sınıfı ad kabul edilebilir öğesi sınıfının başvurur. Bu durumda, ComponentPort Özet temel sınıf InPort ve OutPort ' dir. Bu nedenle, bu öğelerin ya da kabul edilebilir.  
  
 ComponentModel, dil kök sınıfının öğesi birleştirme yönergeleri bileşenleri ve açıklamalar için vardır. Kök sınıf diyagramı boş bölümlerini temsil ettiği için dil kullanıcı bu sınıfların öğeleri doğrudan diyagram üzerine sürükleyin. Ancak, ComponentModel ComponentPort için hiçbir öğe birleştirme yönergesi yoktur. Bu nedenle, dil kullanıcı diyagramına doğrudan InPorts veya OutPorts sürükleyin olamaz.  
  
 Böylece yeni öğe tümleştirmek veya varolan modeline birleştirme hangi bağlantı veya bağlantılar oluşturulan öğesi birleştirme yönergesi belirler. Bir ComponentPort için ComponentHasPorts örneği oluşturulur. DomainPath yeni öğe eklenecek bağlantı noktaları, ilişki ve üst sınıfın özelliği tanımlar.  
  
 Birden fazla bağlantı oluşturma yolunu ekleyerek bir öğe birleştirme yönergesi birden fazla bağlantı oluşturabilirsiniz. Yollarından biri, gömülü olması gerekir.  
  
 Bir bağlantı oluşturma yolunda birden fazla segment kullanabilirsiniz. Bu durumda, son segmenti hangi bağlantı oluşturulmalıdır tanımlar. Önceki kesimleri üst sınıfı'ndan yeni bağlantı oluşturulması gerektiğini nesnesine gidin.  
  
 Örneğin, bu öğenin birleştirme yönergesi bileşen sınıfı ekleyebilirsiniz:  
  
```  
<DomainClass Name="Component" ...> ...  
  <ElementMergeDirective>  
    <Index>  
       <DomainClassMoniker Name="Comment"/>  
    </Index>  
    <LinkCreationPaths>  
       <DomainPath>          ComponentModelHasComponents . ComponentModel / !ComponentModel         / ComponentModelHasComments.Comments       </DomainPath>  
       <DomainPath>CommentsReferenceComponents.Comments</DomainPath>  
    </LinkCreationPaths>  
  </ElementMergeDirective>  
```  
  
 Dil kullanıcılar yorum bileşen üzerine sürükleyin ve bileşen bağlantı otomatik olarak oluşturulan yeni yorum sahip.  
  
 Gelen ilk bağlantı oluşturma yolu gider `Component` için `ComponentModel` ve katıştırma ilişki örneği oluşturur `ComponentModelHasComments`. İkinci bağlantı oluşturma yolunu yeni yorum ana bileşeni başvuru ilişkisi CommentsReferenceComponents bağlantısını oluşturur. Tüm bağlantı oluşturma yollarını ana sınıf ile başlamalı ve bir bağlantıda yeni oluşturulmuş sınıfı doğrultusunda bu adımları bitmelidir.  
  
## <a name="xmlclassdata"></a>XmlClassData  
 Sağlanan ek bilgileri (ilişkileri ve diğer alt dahil) her etki alanı sınıfı olabilir bir `XmlClassData` altında görünür düğüm `XmlSerializationBehavior` DslDefinition.dsl dosyasının bölümü. Bu bilgiler, özellikle bir model bir dosyaya kaydedildiğinde sınıfının örnekleri serileştirilmiş formunda nasıl depolandığını ilgilidir.  
  
 Oluşturulan çoğunu kod `XmlSerializationBehavior` etkileri olan `Dsl\GeneratedCode\Serializer.cs`.  
  
 Her `XmlClassData` düğüm, bu alt düğümleri ve öznitelikleri içerir:  
  
-   Veri uygulandığı sınıfı başvuruda bulunan bir ad düğümü.  
  
-   **XmlPropertyData** sınıfında tanımlanan her bir özellik için.  
  
-   **XmlRelationshipData** sınıfta kaynaklanan her ilişki için. (İlişkileri de kendi XmlClassData düğümünüz.)  
  
-   **TypeName** oluşturulan kod içinde serileştirme yardımcı sınıfı adını belirler dize özniteliği.  
  
-   **ElementName** serileştirilmiş bu sınıfın örnekleri, XML etiket belirler dize. İlk harfi küçük harfli olması dışında kurala göre ElementName genellikle sınıfı adıyla aynıdır. Örneğin, örnek bir model dosyası aşağıdakiler ile başlar:  
  
    ```  
    <componentModel ...  
    ```  
  
-   **MonikerElementName** kullanıcının serileştirilmiş modeli dosyalarında. Bu öznitelik bu sınıf başvuruda bulunan bir bilinen ad tanıtır.  
  
-   **MonikerAttributeName**, bir bilinen ad içinde XML özniteliğin adını tanımlar. Bu kullanıcının serileştirilmiş dosya parçadaki etki alanına özgü dil yazarı tanımlanan **MonikerElementName** "inPortMoniker" olarak ve **MonikerAttributeName** "path" olarak:  
  
    ```  
    <inPortMoniker path="//Component2/InPort1" />  
    ```  
  
### <a name="connectionbuilders"></a>ConnectionBuilders  
 Bir bağlantı Oluşturucu için her bağlantı aracı tanımlanır. Her bağlantı Oluşturucu her biri bir veya daha fazla SourceDirective öğelerini ve bir veya daha fazla TargetDirective öğelerini içeren bir veya daha fazla LinkConnectDirective öğeden oluşur. Bağlantı aracını tıklandıktan sonra kullanıcı bir bağlantı SourceDirective öğeleri listesinde görünür bir model öğesi eşlenen herhangi bir şekli başlatabilirsiniz. Bağlantının ardından TargetDirective öğeleri listesinde görünür bir öğe için eşlenmiş bir şekli üzerinde tamamlanabilir. Sınıf örneği ilişkinin bağlantısı nerede başlatıldı tarafından belirlenen LinkConnectDirective öğesi bağlıdır.  
  
### <a name="xmlpropertydata"></a>XmlPropertyData  
 A **DomainPropertyMoniker** özniteliği veri başvurduğu özelliği tanımlar. Bu öznitelik kapsayan ClassData'nın sınıfının bir özelliği olmalıdır.  
  
 **XmlName** özniteliği XML dosyasında görüneceğinden karşılık gelen öznitelik adı sağlar. İlk harfi küçük harfli olması dışında kurala göre bu dize özellik adı olarak aynıdır.  
  
 Varsayılan olarak, **gösterimi** özniteliği için öznitelik ayarlanır. Varsa **gösterimi** öğesi için bir alt kümesi düğümü XML'de oluşturulur. Varsa **gösterimi** olan Yoksay olarak ayarlanmış, özelliği olmayan serileştirilir.  
  
 **Ismonikerkey** ve **IsMonikerQualifier** öznitelikleri üst sınıfın örneklerini tanımlayan bir rol bir özellik verin. Ayarlayabileceğiniz **Ismonikerkey** içinde tanımlanan veya bir sınıf tarafından devralınmış bir özellik için true. Bu öznitelik üst sınıfın tek bir örneğini tanımlar. Ayarlamak için özellik `IsMonikerKey` genellikle, bir adı veya diğer anahtarı tanımlayıcısı. Örneğin, `Name` dize özelliğidir Namedelement'in ve türetilmiş sınıflarının ad anahtarı. Kullanıcının dosyaya bir modeli kaydettiğinde, bu öznitelik ilişkileri katıştırma ağacında eşdüzey arasında her örneği için benzersiz değerler içermelidir.  
  
 Serileştirilmiş model dosyasında tam ad, bir öğenin her noktada ad anahtarı tırnak içine almak ilişkileri katıştırma ağaç modeli kökünden bir yoludur. Örneğin, model kök dizininde sırayla katıştırılmış bileşenleri içinde InPorts katıştırılır. Bu nedenle geçerli bir ad değil:  
  
```  
<inPortMoniker name="//Component2/InPort1" />  
```  
  
 Ayarlayabileceğiniz **IsMonikerQualifier** özniteliği için bir dize özelliği ve tam adı, bir öğenin oluşturmak için başka bir yolunu sağlar. Örneğin, DslDefinition.dsl dosyasında **Namespace** ad niteleyici.  
  
### <a name="xmlrelationshipdata"></a>XmlRelationshipData  
 Bir seri hale getirilmiş modeli dosyası içinde bağlantılar (ilişkilerin katıştırma ve başvuru) ilişkinin kaynak ucu alt düğümleri tarafından temsil edilir. İlişkileri katıştırmak için bir alt ağacı alt düğümü içerir. İçin başvuru ilişkileri, ağacının başka bir bölümü başvuruda bulunan bir ad alt düğümü içerir.  
  
 **XmlRelationshipData** özniteliğini bir **XmlClassData** özniteliği, tam olarak nasıl alt düğümler kaynak öğesi içinde iç içe tanımlar. Bir kaynak etki alanı sınıftaki her ilişki varsa **XmlRelationshipData** özniteliği.  
  
 **DomainRelationshipMoniker** özniteliği bir sınıf üzerinde kaynaklanan ilişkileri tanımlar.  
  
 **RoleElementName** özniteliği alt düğüm duruma getirilmiş verilerde barındırır XML etiket adı sağlar.  
  
 Örneğin, DslDefinition.dsl dosya içerir:  
  
```  
<XmlClassData ElementName="component" ...>  
  <DomainClassMoniker Name="Component" />  
  <ElementData>  
    <XmlRelationshipData RoleElementName="ports">  
      <DomainRelationshipMoniker Name="ComponentHasPorts" />  
    </XmlRelationshipData>  
```  
  
 Bu nedenle, serileştirilmiş dosya içerir:  
  
```  
<component name="Component1"> <!-- parent ->  
   <ports> <!-- role ->  
     <outPort name="OutPort1"> <!-- child element ->  
       ...  
     </outPort>  
   </ports> ...  
```  
  
 Varsa **UseFullForm** özniteliği true, iç içe geçme fazladan bir katmanı sunulmuştur. Bu katman ilişkiyi temsil eder. Öznitelik ilişkisi özelliklere sahipse true olarak ayarlanmalıdır.  
  
```  
<XmlClassData ElementName="outPort">  
   <DomainClassMoniker Name="OutPort" />  
   <ElementData>  
     <XmlRelationshipData UseFullForm="true" RoleElementName="targets">  
       <DomainRelationshipMoniker Name="Connection" />  
     </XmlRelationshipData>  
   </ElementData>  
 </XmlClassData>  
```  
  
 Serileştirilmiş dosya içerir:  
  
```  
<outPort name="OutPort1">  <!-- Parent ->  
   <targets>  <!-- role ->  
     <connection sourceRoleName="X">  <!-- relationship link ->  
         <inPortMoniker name="//Component2/InPort1" /> <!-- child ->  
     </connection>  
    </targets>  
  </outPort>  
```  
  
 (Bağlantı ilişki öğe ve öznitelik adları sağlar, kendi XML sınıf veri yoktur.)  
  
 Varsa **OmitElement** özniteliği true olarak ilişki rol adı, seri duruma getirilmiş dosya kısaltmasıdır ve iki sınıf birden fazla ilişki varsa belirsizliği atlanır. Örneğin:  
  
```  
<component name="Component3">  
  <!-- only one relationship could get here: ->  
  <outPort name="OutPort1">    
     <targets> ...  
```  
  
### <a name="serialization-of-a-domain-specific-language-definition"></a>Bir etki alanına özgü dil tanımının seri hale getirme  
 DslDefinition.dsl dosyasının kendisini seri hale getirilmiş bir dosyadır ve bir etki alanına özgü dil tanımına uyan. XML serileştirme tanımları bazı örnekleri şunlardır:  
  
-   **DSL** RootClass düğümü ve sınıf diyagramı. DomainClass, DomainRelationship ve diğer öğelerin altında katıştırılmış `Dsl`.  
  
-   **Sınıfları** olan **RoleElementName** etki alanına özgü dil DomainClass arasındaki ilişki.  
  
```  
<Dsl Name="CmptDsl5" ...>  
  <Classes>  
    <DomainClass Name="NamedElement" InheritanceModifier="Abstract" ...  
```  
  
-   **XmlSerializationBehavior** özniteliği katıştırılmış altında `Dsl` özniteliği, ancak **OmitElement** üzerinde katıştırma ilişki özniteliği ayarlandı. Bu nedenle, Hayır `RoleElementName` özniteliği müdahalesi. Bunun aksine, bir **ClassData** özniteliği `RoleElementName` katıştırma ilişkisi özniteliğinin bir **XmlSerializationBehavior** özniteliğini ve bir **XmlClassData** özniteliği.  
  
```  
<Dsl Name="CmptDsl5" ...> ...  
  <XmlSerializationBehavior Name="ComponentsSerializationBehavior" >  
    <ClassData>  
      <XmlClassData ...>...</XmlClassData>  
      <XmlClassData ...>...</XmlClassData>  
```  
  
-   ConnectorHasDecorators arasında katıştırma ilişkisi olduğundan `Connector` ve `Decorator`. `UseFullForm`İlişki adı, her bağlantı için özellikler listesini ile bağlayıcı nesnesinden görüntülenmemesini ayarlandı. Ancak, `OmitElement` de ayarlayın böylece hiçbir `RoleElementName` içinde katıştırılmış birden çok bağlantı barındırır `Connector`:  
  
```  
<Connector Name="AssociationLink" ...>  
  <ConnectorHasDecorators Position="TargetTop" ...>  
    <TextDecorator Name="TargetRoleName"   />  
  </ConnectorHasDecorators>  
  <ConnectorHasDecorators Position="SourceTop" ...>  
    <TextDecorator Name="SourceRoleName"   />  
  </ConnectorHasDecorators>  
</Connector>  
```  
  
## <a name="shapes-and-connectors"></a>Şekiller ve bağlayıcılar  
 Şekil ve bağlayıcı tanımları, aşağıdaki ek etki alanı sınıflardan öznitelikler ve alt düğümleri devral:  
  
-   `Color`ve `Line``Style` öznitelikleri.  
  
-   **ExposesFillColorAsProperty** ve birkaç benzer öznitelikleri. Bu Boolean öznitelikleri kullanıcı tarafından karşılık gelen özellik değişken yapın. Genellikle, bir dil kullanıcı diyagramdaki bir şekli tıkladığında özellikler görünen **özellikleri** penceresinde bu şeklin eşlendiği etki alanı sınıf örneği bulunur. Varsa `ExposesFillColorAsProperty` şeklin bir özelliği de görünen true olarak ayarlanır.  
  
-   **ShapeHasDecorators**. Bu öznitelik örneği her metin, simge veya Genişlet/Daralt oluşturma öğesi için oluşur. (DslDefinition.dsl dosyasında `ShapeHasDecorators` içeren bir ilişki `UseFullForm` true olarak ayarlandığında.)  
  
## <a name="shape-maps"></a>Şekil eşlemeleri  
 Şekil eşlemeleri nasıl bir şekli tarafından temsil edilen ekranında, belirtilen etki alanı sınıfının örnekleri görüneceğini belirler. Şekil ve bağlayıcı eşlemeleri altında görünen `Diagram` DslDefinition.dsl dosyasının bölümü.  
  
 Aşağıdaki örnekte olduğu gibi `ShapeMap` öğelere sahip en az bir etki alanı sınıfının ad, bir şekli ad ve `ParentElementPath` öğe:  
  
```  
<ShapeMap>  
  <DomainClassMoniker Name="InPort" />  
  <ParentElementPath>  
    <DomainPath>ComponentHasPorts.Component/!Component</DomainPath>  
  </ParentElementPath>  
  <PortMoniker Name="InPortShape" />  
</ShapeMap>  
```  
  
 Sunucunun birincil işlevi `ParentElementPath` öğesi olduğundan nesnenin aynı sınıfını farklı bağlamdan farklı bir şekilde olarak yer alabilir. Örneğin, bir `InPort` bir yorum, ayrıca katıştırılmış `InPort` bu amaç için farklı bir şekil olarak görünebilir.  
  
 İkincisi, yolun şekli kendi üst ilişkilendirilme şekli belirler. Hiçbir katıştırma yapısı DslDefinition.dsl dosyasında şekiller arasında tanımlanır. Şekil eşlemeleri yapısından Infer gerekir. Bir şekli üst üst öğe yolu tanımlayan etki alanı öğesi eşlenen şekli ' dir. Bu durumda, yolun bileşenine tanımlayan `InPort` ait. Başka bir şekil eşlemesinde bileşen sınıfı için ComponentShape eşlenir. Bu nedenle, yeni `InPort` şekli alt yapılan kendi bileşenin şeklini `ComponentShape`.  
  
 InPort Şekli diyagrama yerine bağlıysa, üst öğe yolu diyagrama eşlenen bileşen modeli için başka bir adım öteye gerekir:  
  
```  
ComponentHasPorts . Component / ! Component /    ComponentModelHasComponents . ComponentModel / ! ComponentModel  
```  
  
 Modelin kökü bir şekli eşlemesi yok. Kök olan doğrudan diyagramdan, bunun yerine, başvurulan bir `Class` öğe:  
  
```  
<Diagram Name="ComponentDiagram" >  
    <Class>  
      <DomainClassMoniker Name="ComponentModel" />  
    </Class>...  
```  
  
### <a name="decorator-maps"></a>Oluşturma öğesi eşlemeleri  
 Bir oluşturma öğesi eşlemesi oluşturma öğesi şekildeki eşlenen sınıfına özelliğinde ilişkilendirir. Özellik bir numaralandırılmış ya da Boole türü ise değerini oluşturma öğesi görünür olup olmadığını belirleyebilirsiniz. Oluşturma öğesi metin oluşturma öğesi ise, özelliğin değerini görüntülenebilir ve kullanıcı onu düzenleyebilirsiniz.  
  
### <a name="compartment-shape-maps"></a>Bölme şekli eşlemeleri  
 Bölme şekli eşlemeleri şekli eşlemelerinin subtypes ' dir.  
  
## <a name="connector-maps"></a>Bağlayıcı eşlemeleri  
 En az bağlayıcı harita bağlayıcı ve bir ilişki başvuruyor:  
  
```  
<ConnectorMap>  
  <ConnectorMoniker Name="CommentLink" />  
  <DomainRelationshipMoniker Name="CommentsReferenceComponents" />  
</ConnectorMap>  
```  
  
 Bağlayıcı eşlemeleri oluşturma öğesi eşlemeleri de içerebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [Bir etki alanına özgü dil tanımlama](../modeling/how-to-define-a-domain-specific-language.md)   
 [Modelleri, Sınıfları ve İlişkileri Anlama](../modeling/understanding-models-classes-and-relationships.md)