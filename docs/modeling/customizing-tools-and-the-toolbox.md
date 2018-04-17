---
title: Araçlar ve araç kutusunu özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.selectiondialog
- vs.dsltools.dsldesigner.selecticondialog
- vs.dsltools.dsldesigner.selectcursordialog
helpviewer_keywords:
- Domain-Specific Language, toolbox
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0644aa33d0e091fc3a2ff856109fe9661e2dc805
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="customizing-tools-and-the-toolbox"></a>Araçları ve Araç Kutusunu Özelleştirme
Kullanıcıların kendi model ekleme izin vermek istediğiniz öğeleri için araç kutusu öğelerini tanımlamanız gerekir. Araçlar iki tür vardır: öğesi araçları ve bağlantı araçları. Oluşturulan Tasarımcısı'nda kullanıcı şekiller diyagrama sürüklemek için bir öğe aracı seçebilirsiniz ve bağlantıları arasında şekiller çizmek için bir bağlantı aracı seçebilirsiniz. Genel olarak, kullanıcı etki alanı sınıfların örnekleri için modellerini Ekle öğesi araçları sağlar ve bunları etki alanı ilişkilerini örneklerini eklemek bağlantı araçları sağlayabilirsiniz.  
  
 Bu konuda:  
  
-   [Araç kutusu nasıl tanımlanır](#ToolboxDef)  
  
-   [Öğe Araçlarını Özelleştirme](#customizing)  
  
-   [Bir aracından öğelerinin grupları oluşturma](#groups)  
  
-   [Bağlantı Araçları özelleştirme](#connections)  
  
##  <a name="ToolboxDef"></a> Araç kutusu nasıl tanımlanır  
 DSL Explorer'da Düzenleyici düğümü ve bunun altındaki düğümleri genişletin. Genellikle bu benzer bir hiyerarşi görürsünüz:  
  
```  
  
Editor  
     Toobox Tabs  
        MyDsl          //a tab  
           Tools  
               ExampleElement      // an element tool  
               ExampleRelationship // a connection tool  
  
```  
  
 DSL Explorer'ın bu bölümünde, şunları yapabilirsiniz:  
  
-   Yeni sekmeler oluşturun. Sekmeleri bölüm başlıkları araç kutusunda tanımlayın.  
  
-   Yeni Araçları oluşturun.  
  
-   Araçlar kopyalayıp yeniden açın.  
  
-   Listede araçları yukarı veya aşağı taşıma.  
  
-   Sekmeler ve araçları silin.  
  
> [!IMPORTANT]
>  Ekleme veya öğeleri DSL Explorer'da yapıştırmak için Yeni düğümün iki üst sağ tıklatın. Örneğin, bir aracı eklemek için sekmesini sağ tıklatın ve **Araçları** düğümü. Sekme eklemek için sağ tıklatın **Düzenleyicisi** düğümü.  
  
 **Araç kutusu simgesi** her aracının özelliği, 16 x 16 bit eşlem dosyası başvurur. Bu dosyalar genellikle tutulan **Dsl\Resources** klasör.  
  
 **Sınıfı** öğe aracına özelliğinin somut etki alanı sınıfına başvuruyor. Varsayılan olarak, bu sınıfın örnekleri, aracı oluşturur. Ancak, aracın öğeleri ya da farklı türdeki öğeleri grupları oluşturmak için kod yazabilirsiniz.  
  
 **Bağlantı Oluşturucu** öğeleri ne tür aracı bağlanabilir ve ilişkiler oluşturur aralarında tanımlayan bir bağlantı Oluşturucu başvurduğu bir bağlantı aracı özelliği. Bağlantı oluşturucular DSL Explorer'da düğümleri olarak tanımlanır. Bağlantı Oluşturucular, etki alanı ilişkilerini tanımlamak, ancak bunları özelleştirmek üzere kod yazabilirsiniz otomatik olarak oluşturulur.  
  
#### <a name="to-add-a-tool-to-the-toolbox"></a>Bir aracı araç kutusuna ekleme  
  
1.  Shape sınıfı oluşturulur ve bir etki alanı sınıfa eşlenen sonra genellikle bir öğe aracı oluşturun.  
  
     Bağlayıcı sınıfı oluşturulur ve bir başvuru ilişkisi eşlenen sonra genellikle bir bağlayıcı aracını oluşturun.  
  
2.  DSL Explorer'da genişletin **Düzenleyicisi** düğümü ve **araç kutusu sekmeleri** düğümü.  
  
     Araç kutusu sekmesi düğümünü sağ tıklatın ve ardından **ekleme yeni öğe aracı** veya **ekleme yeni bağlantı aracını**.  
  
3.  Ayarlama **araç kutusu simgesi** için 16 x 16 bit eşlem başvurmak için özellik.  
  
     Yeni bir simge tanımlamak istiyorsanız, Çözüm Gezgini'nde bir bit eşlem dosyası oluşturma **Dsl\Resources** klasör. Dosyanız aşağıdaki özellik değerlerini olmalıdır: **yapı eylemi** = **içerik**; **Çıktı dizinine Kopyala** = **kopyalamayın**.  
  
4.  **Bir öğe aracı için:** ayarlamak **sınıfı** şekle eşlenen bir somut etki alanı sınıf başvurmak için aracı özelliği.  
  
     **Bağlayıcı aracı:** ayarlamak **bağlantı Oluşturucu** aşağı açılan listesinde sunulan öğelerden biri aracı özelliği. Bir etki alanı ilişkisinin bir bağlayıcı eşlediğinizde bağlantı oluşturucular otomatik olarak oluşturulur. Yakın zamanda bağlayıcıyı oluşturduysanız, ilişkili bir bağlantı Oluşturucu normalde seçersiniz.  
  
5.  DSL sınamak için F5 veya CTRL + F5 tuşuna basın ve deneysel örneğinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], örnek model dosyasını açın. Yeni aracı araç kutusunda görünmesi gerekir. Yeni bir öğesi oluşturur doğrulamak için diyagram üzerine sürükleyin.  
  
     Aracı görünmüyorsa Deneysel durdurmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Windows **Başlat** çalıştırmak menüsünde **Microsoft Visual Studio 2010 deneysel örneği sıfırlama**. Üzerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **yapı** menüsünde tıklatın **çözümü yeniden derle**. DSL yeniden sınayın.  
  
##  <a name="customizing"></a> Öğe araçları özelleştirme  
 Varsayılan olarak, aracı belirtilen sınıf tek bir örneğini oluşturur, ancak bu iki yolla değişebilir:  
  
-   Öğe birleştirme yönergeleri, bunları yeni bu sınıfın örnekleri, kabul etmek etkinleştirme ve bunları yeni öğe oluşturulduğunda ek bağlantılar oluşturmak üzere etkinleştirme diğer sınıflarında tanımlayın. Örneğin, kullanıcının başka bir öğenin üzerine yorum bırakın izin verin ve dolayısıyla iki arasında bir referans bağlantı oluşturun.  
  
     Kullanıcı gönderebilir veya sürüklediği ve öğenin bırakır ne olur, bu özelleştirmeler de etkiler.  
  
     Daha fazla bilgi için bkz: [özelleştirme öğesi oluşturma ve taşıma](../modeling/customizing-element-creation-and-movement.md).  
  
-   Öğe gruplarını oluşturabilmesi için Aracı'nı özelleştirmek için kod yazma. Aracı geçersiz kılabilirsiniz ToolboxHelper.cs yöntemleri tarafından başlatılır. Daha fazla bilgi için bkz: [oluşturma grupları öğeleri bir aracından](#groups).  
  
##  <a name="groups"></a> Bir aracından öğelerinin grupları oluşturma  
 Her öğe aracı oluşturmanız gerekir öğeleri prototipi içerir. Varsayılan olarak, her öğe aracı, tek bir öğe oluşturur, ancak bir aracı ile ilgili nesneler bir grup oluşturmak mümkündür. Bunu yapmak için aracı ile başlatılamıyor. bir <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> ilgili öğeler içerir.  
  
 Aşağıdaki örnek, bir tür transistör olduğu DSL alınır. Her transistör üç adlandırılmış Terminal sahiptir. Transistörler öğesi aracı dört model öğelerini ve üç ilişki bağlantıları içeren bir prototip depolar. Kullanıcı aracı diyagram üzerine sürüklendiğinde prototip örneği ve model köküne bağlanır.  
  
 Bu kod tanımlanan bir yöntemini geçersiz kılar **Dsl\GeneratedCode\ToolboxHelper.cs**.  
  
 Program kodunu kullanarak model özelleştirme hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
  public partial class CircuitsToolboxHelper  
  {  
    /// <summary>  
    /// Toolbox initialization, called for each element tool on the toolbox.  
    /// This version deals with each Component subtype separately.  
    /// </summary>  
    /// <param name="store"></param>  
    /// <param name="domainClassId">Identifies the domain class this tool should instantiate.</param>  
    /// <returns>prototype of the object or group of objects to be created by tool</returns>  
    protected override ElementGroupPrototype CreateElementToolPrototype(Store store, Guid domainClassId)  
    {  
        if (domainClassId == Transistor.DomainClassId)  
        {  
            Transistor transistor = new Transistor(store);  
  
            transistor.Base = new ComponentTerminal(store);  
            transistor.Collector = new ComponentTerminal(store);  
            transistor.Emitter = new ComponentTerminal(store);  
  
            transistor.Base.Name = "base";  
            transistor.Collector.Name = "collector";  
            transistor.Emitter.Name = "emitter";  
  
            // Create an ElementGroup for the Toolbox.  
            ElementGroup elementGroup = new ElementGroup(store.DefaultPartition);  
            elementGroup.AddGraph(transistor, true);  
            // AddGraph includes the embedded parts  
  
            return elementGroup.CreatePrototype();  
        }  
        else  
        {  
            return base.CreateElementToolPrototype(store, domainClassId);  
}  }    }  
  
```  
  
##  <a name="connections"></a> Bağlantı Araçları özelleştirme  
 Genellikle, yeni bir bağlayıcı sınıfı oluşturduğunuzda, bir öğenin aracı oluşturun. Alternatif olarak, ilişki türünü belirlemek için iki uca türlerini sağlayarak bir aracı aşırı yüklenebilir. Örneğin, kişi kişi ilişkileri ve kişi Şehir ilişkileri oluşturabilirsiniz bir bağlantı aracını tanımlayabilirsiniz.  
  
 Bağlantı Araçları bağlantı oluşturucular çağırır. Bağlantı oluşturucular öğelerine oluşturulan Tasarımcısı'nda kullanıcıların nasıl bağlayabilirsiniz belirtmek için kullanın. Bağlantı oluşturucular bağlanabilir öğeleri ve bunlar arasında oluşturulan bağlantı türünü belirtin.  
  
 Etki alanı sınıflar arasındaki başvuru ilişkisi oluşturduğunuzda, bir bağlantı Oluşturucu otomatik olarak oluşturulur. Bağlantı aracını eşlediğinizde, bu bağlantı Oluşturucu kullanabilirsiniz. Bağlantı Araçları oluşturma hakkında daha fazla bilgi için bkz: [araç kutusunu yapılandırma](../modeling/customizing-tools-and-the-toolbox.md).  
  
 Böylece farklı bir kaynak ve hedef türleri aralığı ile ilgilidir ve farklı türde ilişki oluşturmak için varsayılan bağlantı Oluşturucusu değiştirebilirsiniz.  
  
 Ayrıca, bağlantı için kaynak ve hedef sınıflarını belirtmek yapılacak bağlantı türünü tanımlayın ve bir bağlantı oluşturulması ile ilgili diğer eylemleri bağlantı oluşturucular için özel kod yazabilirsiniz.  
  
### <a name="the-structure-of-connection-builders"></a>Bağlantı oluşturucular yapısı  
 Bir bağlantı oluşturucular içermelidir veya daha fazla bağlantı etki alanı ilişkisinin ve kaynak ve hedef öğeleri belirtin yönergeleri bağlanın. Örneğin, Görev akışı çözüm şablonunda görebilirsiniz **CommentReferencesSubjectsBuilder** içinde **DSL Explorer**. Bu bağlantı Oluşturucu bir bağlantı içeren adlı yönergesi bağlanmak **CommentReferencesSubjects**, etki alanı ilişkisinin eşlenen **CommentReferencesSubjects**. Bu bağlantıyı bağlamak yönergeyi içeren işaret eden bir kaynak rol yönergesi `Comment` etki alanı sınıf ve işaret eden bir hedef rolü yönergesi `FlowElement` etki alanı sınıfı.  
  
### <a name="using-connection-builders-to-restrict-source-and-target-roles"></a>Kaynak kısıtlamak üzere bağlantı oluşturucular kullanma ve hedef rolleri  
 Belirli sınıfları Kaynak rolü veya belirtilen etki alanı ilişkisinin hedefi rolü örneğini kısıtlamak için bağlantı oluşturucular kullanabilirsiniz. Örneğin, başka bir etki alanı sınıfı bir etki alanı ilişkisi olan bir temel etki alanı sınıfı olabilir, ancak aynı rolleri, ilişki sağlamak için temel sınıfın tüm türetilen sınıflar istemeyebilirsiniz. Görev akışı çözümde dört somut etki alanı sınıfları vardır (**StartPoint**, **EndPoint**, **MergeBranch**, ve **eşitleme**) doğrudan soyut etki alanı sınıfından devralan **FlowElement**, ve iki etki alanı sınıflarını somut (**görev** ve **ObjectInState**), dolaylı olarak ondan devralır. Ayrıca bir **akış** başvuru alır ilişki **FlowElement** etki alanı sınıflarda kendi kaynak rolü ve hedef rolü. Ancak, bir örneğini bir **EndPoint** etki alanı sınıfının bir örneğini kaynağı olmalıdır bir **akış** ilişki, ya da örneği gerekir bir **StartPoint** sınıfı hedef örneği bir **akış** ilişki. **FlowBuilder** bağlantı Oluşturucu adlı yönergesi bağlanma bağlantısı vardır **akış** hangi etki alanı sınıfları kaynak rol oynayabilir belirtir (**görev**,  **MergeBranch**, **StartPoint**, ve **eşitleme**) ve hedefi rolü çalabilir (**MergeBranch**,  **Uç nokta**, ve **eşitleme**).  
  
### <a name="connection-builders-with-multiple-link-connect-directives"></a>Yönergeleri bağlantı oluşturucular birden çok bağlantı ile bağlanma  
 Birden fazla bağlantı ekleyebilirsiniz yönergesi için bir bağlantı Oluşturucu bağlanın. Bu, bazı kullanıcıların etki alanı modeli karmaşıklığını gizleme ve tutun yardımcı olabilir **araç** çok dolmasını gelen. Bağlantı ekleyebilirsiniz birkaç farklı bir etki alanına ilişkiler için yönergeleri için tek bir bağlantı Oluşturucu bağlanın. Ancak, bunlar yaklaşık aynı işlevi gerçekleştirir, etki alanı ilişkilerini birleştirmelisiniz.  
  
 Görev akışı çözümüne **akış** bağlantısı aracı her ikisi de örneklerini çizmek için kullanılan **akış** ve **NesneAkış** etki alanı ilişkilerini. **FlowBuilder** bağlantı oluşturucusu olması, ayrıca **akış** bağlantıyı bağlamak daha önce açıklanan yönergesi, iki bağlantıyı bağlamak adlı yönergeleri **NesneAkış**. Bu yönergeleri belirtin örneği bir **NesneAkış** ilişki örnekleri arasında çizilmiş **ObjectInState** etki alanı sınıfı veya örneği bir **ObjectInState**  örneği bir **görev**, ancak iki örneği arasında değil bir **görev**, veya örneğinden bir **görev** bir örneği**ObjectInState**. Ancak, bir örneğini bir **akış** ilişki iki örnekleri arasında çizilmiş bir **görev**. Derleme ve Görev akışı çözümü çalıştırırsanız, o çizim gördüğünüz bir **akış** örneğinden bir **ObjectInState** örneği bir **görev** bir örneğini oluşturur bir **NesneAkış**, ancak çizim bir **akış** iki örnekleri arasında bir **görev** bir örneğini oluşturur bir **akış**.  
  
### <a name="custom-code-for-connection-builders"></a>Bağlantı oluşturucular için özel kod  
 Bağlantı oluşturucular özelleştirmesini farklı türlerini tanımlamak dört onay kutularını kullanıcı arabiriminde vardır:  
  
-   **özel kabul** bir kaynak veya hedef rolü yönergesi onay kutusu  
  
-   **özel bağlanma** bir kaynak veya hedef rolü yönergesi onay kutusu  
  
-   **özel Bağlan kullanan** Bağlan yönergesi onay kutusu  
  
-   **olan özel** Bağlantı oluşturucu özelliği  
  
 Bu özelleştirmeler için bazı program kodu girmeniz gerekir. Sağlamanız gerekir hangi kod bulmak için bu kutularından birinin denetleyin ve tüm şablonları dönüştürme çözümünüzü oluşturun. Bir hata raporu neden olur. Eklemeniz gereken hangi kodunu açıklayan bir yorum görmek için hata raporu çift tıklatın.  
  
> [!NOTE]
>  Özel kod eklemek için bir parçalı sınıf tanımı bir kod dosyasında GeneratedCode klasörlerde kod dosyalarından ayrı oluşturun. Çalışmanızı kaybetmemek için oluşturulan kod dosyaları düzenlemeniz gerekir değil. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).  
  
#### <a name="creating-custom-connection-code"></a>Özel bağlantı kod oluşturma  
 Yönergesi, her bir bağlantının bağlanmak **kaynak rol yönergeleri** sekmesini tanımlar, türleri sürükleyebilirsiniz. Benzer şekilde, **hedef rolü yönergeleri** sekmesini tanımlar için ne türleri sürükleyebilirsiniz. Her türü için daha fazla yönergesi (Bu bağlantıyı bağlamak için) bağlantı ayarlayarak izin verip vermeyeceğinizi belirtebilirsiniz **özel kabul** bayrak ve ek kod sağlama.  
  
 Ayrıca, bağlantı yapıldığında neler özelleştirebilirsiniz. Örneğin, yalnızca için veya belirli bir sınıfın Sürükle oluştuğu durum özelleştirebilirsiniz tüm durumlarda, bir bağlantıyı bağlamak yönergesi yönetir, ya da tüm FlowBuilder bağlantısı Oluşturucu. Bu seçeneklerin her biri için uygun düzeyinde özel bayraklar ayarlayabilirsiniz. Tüm Şablonları dönüştürme ve çözümü derlemek deneyin, hata iletileri, oluşturulan kodda olan açıklamaları doğrudan. Bu açıklamalar sağlamanız gerekir tanımlayın.  
  
 Bileşenleri diyagramı örnek arasındaki bağlantı noktalarını yapılan bağlantılar kısıtlamak amacıyla bağlantı etki alanı ilişkisinin için bağlantı oluşturucuyu özelleştirilir. Yalnızca gelen bağlantıları yapabileceğiniz aşağıda gösterilmiştir `OutPort` öğelerine `InPort` öğeleri, ancak bileşenler birbirine içinde içe kullanabilirsiniz.  
  
 **İç içe geçmiş bileşen bir OutPort gelen bağlantı**  
  
 ![Bağlantı oluşturucu](../modeling/media/connectionbuilder_3.png "ConnectionBuilder_3")  
  
 Bu nedenle, bir bağlantı için bir OutPort iç içe geçmiş bileşen gelebilir belirtmek isteyebilirsiniz. Böyle bir bağlantı belirtmek için ayarladığınız **kullanan özel kabul** üzerinde **InPort** kaynağı rol türü ve **OutPort** türü hedef rolünde olarak **DSL ayrıntıları**  aşağıdaki çizimde gösterildiği gibi penceresi:  
  
 **Bağlantıyı bağlamak DSL Explorer'da yönergesi**  
  
 ![Bağlantı oluşturucu resmi](../modeling/media/connectionbuilder_4a.png "ConnectionBuilder_4a")  
  
 **Bağlantıyı bağlamak DSL Ayrıntıları penceresinde yönergesi**  
  
 ![](../modeling/media/connectionbuilder_4b.png "ConnectionBuilder_4b")  
  
 Ardından ConnectionBuilder sınıftaki yöntemlerin sağlamanız gerekir:  
  
```  
  public partial class ConnectionBuilder  
  {  
    /// <summary>  
    /// OK if this component has children  
    /// </summary>  
    private static bool CanAcceptInPortAsSource(InPort candidate)  
    {  
       return candidate.Component.Children.Count > 0;  
    }  
  
    /// <summary>  
    /// Only if source is on parent of target.  
    /// </summary>  
    private static bool CanAcceptInPortAndInPortAsSourceAndTarget                (InPort sourceInPort, InPort targetInPort)  
    {  
      return sourceInPort.Component == targetInPort.Component.Parent;  
    }  
// And similar for OutPorts...  
```  
  
 Program kodunu kullanarak model özelleştirme hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 Örneğin, kullanıcılar üst-alt bağlantılarıyla döngüler oluşturmasını önlemek için benzer bir kod kullanabilirsiniz. Kullanıcıların bunları herhangi bir anda ihlal yapılamıyor çünkü bu kısıtlamaları 'sabit' kısıtlamaları olarak kabul edilir. Kullanıcılar, geçici olarak kaydedilemez geçersiz yapılandırmaları oluşturarak atlayabilirsiniz 'geçici' doğrulama denetimleri de oluşturabilirsiniz.  
  
### <a name="good-practice-in-defining-connection-builders"></a>İyi uygulamada bağlantı oluşturucuları tanımlama  
 Yalnızca kavramsal olarak ilişkili oldukları, farklı türde ilişkileri oluşturmak için bir bağlantı Oluşturucu tanımlamanız gerekir. Görev akışı örnek akışı görevler arasında ve ayrıca görevleri ve nesneler arasında oluşturmak için aynı Oluşturucusu'nu kullanın. Ancak, açıklamalar ve görevler arasında ilişkiler oluşturmak için aynı oluşturucusunu kullanmak kafa karıştırıcı olabilir.  
  
 Birden çok türde ilişki için bir bağlantı Oluşturucu tanımlarsanız, birden fazla türü aynı çifti kaynak ve hedef nesne ile aynı olamaz emin olmalısınız. Aksi takdirde, sonuçlar öngörülemez olacaktır.  
  
 'Sabit' kısıtlamaları uygulamak için özel kod kullanın, ancak kullanıcıların geçici olarak geçersiz bağlantıları hale getiremezsiniz olup olmayacağını göz önünde bulundurmanız gerekir. Bunlar gerekir, böylece kullanıcılar değişiklikleri kaydetmeye çalıştığınızda kadar bağlantıları doğrulanmaz kısıtlamaları değiştirebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğe oluşturma ve taşıma özelleştirme](../modeling/customizing-element-creation-and-movement.md)   
 [Kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md)   
 [Nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Gezinme ve bir modeli Program kodunda güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Bağlantı hattı diyagramları örnek DSL](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)