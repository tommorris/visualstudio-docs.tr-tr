---
title: "Bağımlılık diyagramları ile kod doğrulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, validating
- validation, dependency diagrams
- validation, code
- code exploration, validating
- architecture, validating
- Visual Studio Ultimate, validating code
- validation, architecture
- validation, dependencies
- MSBuild, tasks
- MSBuild, dependency diagrams
- MSBuild, validating code
ms.assetid: 70cbe55d-4b33-4355-b0a7-88c770a6f75c
caps.latest.revision: "82"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: c6c5954cdb4979ede5e43d2052801ca399f128fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="validate-code-with-dependency-diagrams"></a>Bağımlılık diyagramları ile kod doğrulama

**En son haberleri**: bkz [bu blog gönderisine](https://blogs.msdn.microsoft.com/visualstudioalm/2016/11/30/live-dependency-validation-in-visual-studio-2017/).

[Video: mimarisi bağımlılıklarınızı gerçek zamanlı doğrula](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4) 

## <a name="why-use-dependency-diagrams"></a>Bağımlılık diyagramları neden kullanılır?

Kod tasarımıyla çakışma değil emin olmak için Visual Studio'da bağımlılık diyagramları ile kodunuzu doğrulayın. Bu, şu konularda size yardımcı olabilir:  
  
-   Kodunuzda ve iç bağımlılıkları arasındaki çakışmaları bağımlılık diyagramı bulun.  
  
-   Önerilen değişiklikler tarafından etkilenebilecek bağımlılıkları bulun.  
  
     Örneğin, olası mimari değişiklikleri göstermek ve etkilenen bağımlılıkları görmek için kodu doğrulamak için bağımlılık diyagramı düzenleyebilirsiniz.  
  
-   Kodu yeniden düzenleyin veya kodu farklı bir tasarıma geçirin.  
  
     Kodu farklı bir mimariye taşıdığınız zaman iş gerektiren kodu veya bağımlılıkları bulun.  
  
 **Gereksinimler**  
  
-   Visual Studio  
  
-   Team Foundation Build sunucunuzda visual Studio Team Foundation Build ile otomatik olarak kodu doğrulamak için  
  
-   Bir bağımlılık diyagramı içeren modelleme projesine sahip bir çözüm. Bu bağımlılık diyagram doğrulamak istediğiniz Visual C# .NET veya Visual Basic .NET projelerinde yapılara bağlı olması gerekir. Bkz: [kodunuzdan bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md).  
  
 Bu özellik, Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Kod bir açık bağımlılık diyagramı Visual Studio'da veya bir komut isteminden el ile doğrulayabilir. Ayrıca yerel yapıları veya Team Foundation Yapısı'nı çalıştırırken kodu otomatik olarak doğrulayabilirsiniz. Bkz: [kanal 9 Video: tasarım ve bağımlılık diyagramları kullanarak Mimarinizi geçerli](http://go.microsoft.com/fwlink/?LinkID=252073).  
  
> [!IMPORTANT]
>  Team Foundation Build ile katman doğrulama çalıştırmak istiyorsanız, derleme sunucunuzda Visual Studio aynı sürümünü de yüklemeniz gerekir.  
  
-   [Bir öğeyi doğrulama destekleyip desteklemediğini görmek](#SupportsValidation)  
  
-   [Diğer .NET derlemelerini ve doğrulama için projeleri içerir](#IncludeReferences)  
  
-   [El ile kod doğrulama](#ValidateManually)  
  
-   [Otomatik olarak kod doğrulama](#ValidateAuto)  
  
-   [Katman doğrulama sorunlarını giderme](#TroubleshootingValidation)  
  
-   [Anlama ve katman doğrulama hatalarını çözümleme](#UnderstandingValidationErrors)  

## <a name="live-dependency-validation"></a>Canlı bağımlılık doğrulama

Visual Studio'nun bu sürümünde, gerçek zamanlı olarak bağımlılık doğrulama oluşur ve hataları hemen Visual Studio Hata Listesi penceresi gösterilir.

* Canlı doğrulama C# ve Visual Basic.NET için desteklenir. 

* Canlı bağımlılık doğrulama kullanırken tam çözüm analizini etkinleştirmek için hata listesinde görüntülenir altın çubuğundan seçenekleri ayarlarını açın. 
 - Çözümünüzdeki tüm mimari sorunları görmeniz ilgilenen değilse bu altın çubuğu kalıcı olarak sayabilirsiniz.
 - Tam çözüm analizini etkinleştirmezseniz, analiz düzenlenmekte olan dosyalar için yapılır.<p /> 

* Canlı doğrulamasını etkinleştirmek için projeleri yükseltme yaparken, bir iletişim kutusu dönüştürme ilerlemesini gösterir.

* Canlı bağımlılık doğrulama için bir proje güncelleştirirken, NuGet paketinin sürümünü, tüm projeleri için aynı olması için yükseltilir ve kullanımı en yüksek sürümde. 

* Yeni bir bağımlılık doğrulama proje Tetikleyicileri project güncelleştirmesi ekleniyor. 
  
##  <a name="SupportsValidation"></a>Bir öğeyi doğrulama destekleyip desteklemediğini görmek  
 Web siteleri, Office belgeleri, düz metin dosyaları ve birden çok uygulama arasında paylaşılan projelerin dosyalarını Katmanları bağlayabilirsiniz, ancak doğrulama işlemi bunları içermez. Doğrulama hataları, aralarında hiçbir bağımlılığın görünmediği ayrı katmanlara bağlanmış projelere veya derlemelere olan başvurular için görünmez. Kod bu başvuruları kullanmazsa böyle başvurular bağımlılık olarak düşünülmez.  
  
1.  Bir veya daha fazla katmanları bağımlılık diyagramda seçin, seçiminize sağ tıklayın ve ardından **bağlantıları görüntüleme**.  
  
2.  İçinde **Katman Gezgini**, bakmak **doğrulamayı destekler** sütun. Değer false ise, öğe doğrulamayı desteklemez.  
  
##  <a name="IncludeReferences"></a>Diğer .NET derlemelerini ve doğrulama için projeleri içerir  
 Bağımlılık diyagramı öğeleri sürüklediğinizde, karşılık gelen .NET derlemeleri veya projeleri başvurular otomatik olarak eklenen **katman başvuruları** modelleme projesi klasöründe. Bu klasör, doğrulama sırasında analiz edilen derlemeler ve projeler için başvurular içerir. Diğer .NET derlemelerini ve doğrulama projelerde bağımlılık diyagrama sürükleyerek olmadan el ile ekleyebilirsiniz.  
  
1.  İçinde **Çözüm Gezgini**, modelleme projesine sağ tıklayın veya **katman başvuruları** klasörünü ve ardından **Başvuru Ekle**.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusu, derlemeleri veya projeleri seçin ve ardından **Tamam**.  
  
##  <a name="ValidateManually"></a>El ile kod doğrulama  
 Çözüm öğeleri bağlantılı bir açık bağımlılık diyagramı varsa, çalıştırabilirsiniz **doğrulama** diyagramdan kısayol komutu. Komut isteminde çalıştırmak için de kullanabilirsiniz **msbuild** komutunu **/p: ValidateArchitecture** özel özellik kümesine **doğru**. Örneğin, kodda değişiklik yaparken bağımlılık çakışmalarını önceden yakalayabilmek için düzenli olarak katman doğrulama gerçekleştirin.  
  
#### <a name="to-validate-code-from-an-open-dependency-diagram"></a>Bir açık bağımlılık diyagramdan kodunu doğrulamak için   
  
1.  Diyagram yüzeyine sağ tıklayın ve ardından **Mimariyi Doğrula**.  
  
    > [!NOTE]
    >  Varsayılan olarak, **yapı eylemi** bağımlılık diyagramı (.layerdiagram) dosyasındaki özelliği ayarlanmış **doğrulama** böylece diyagram doğrulama işleminde dahil.  
  
     **Hata listesi** penceresi oluşan hataları bildirir. Doğrulama hataları hakkında daha fazla bilgi için bkz: [anlayın ve çözümleme katman doğrulama hatalarını](#UnderstandingValidationErrors).  
  
2.  Her hatanın kaynağını görüntülemek için hatayı çift tıklatın **hata listesi** penceresi.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]kod Haritası kullanarak hatanın kaynağı yerine gösterebilir. Bu kod bağımlılık diyagram tarafından belirtilmemiş bir derleme üzerinde bir bağımlılığa sahip veya kod bağımlılık diyagramı tarafından belirlenen bir bağımlılığı eksik ortaya çıkar. Kod haritası veya bağımlılık mevcut olup olmadığını belirlemek için kodu gözden geçirin. Kod eşlemeleri hakkında daha fazla bilgi için bkz: [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md).  
  
3.  Hataları yönetmek için bkz: [doğrulama hatalarını yönetme](#ManageErrors).  
  
#### <a name="to-validate-code-at-the-command-prompt"></a>Kodu komut isteminde doğrulamak için  
  
1.  Açık [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komut istemi.  
  
2.  Aşağıdakilerden birini seçin:  
  
    -   Çözümde belirli modelleme projesine karşı kodu doğrulamak için Çalıştır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] aşağıdaki özel özelliğine sahip.  
  
        ```  
        msbuild <FilePath+ModelProjectFileName>.modelproj /p:ValidateArchitecture=true  
        ```  
  
         - veya -  
  
         Modelleme içeren klasöre gidin (.modelproj) dosyası ve bağımlılık diyagramı proje ve ardından çalıştırın [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] aşağıdaki özel özelliğiyle:  
  
        ```  
        msbuild /p:ValidateArchitecture=true   
        ```  
  
    -   Çözümdeki tüm modelleme projeleri karşı kodu doğrulamak için Çalıştır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] aşağıdaki özel özelliğiyle:  
  
        ```  
        msbuild <FilePath+SolutionName>.sln /p:ValidateArchitecture=true   
        ```  
  
         - veya -  
  
         Gereken bir bağımlılık diyagramı içeren modelleme projesine içeren ve ardından çalıştırın çözüm klasöre Gözat [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] aşağıdaki özel özelliğiyle:  
  
        ```  
        msbuild /p:ValidateArchitecture=true  
        ```  
  
     Oluşan hatalar listelenecektir. Hakkında daha fazla bilgi için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], bkz: [MSBuild](../msbuild/msbuild.md) ve [MSBuild görevi](../msbuild/msbuild-task.md).  
  
 Doğrulama hataları hakkında daha fazla bilgi için bkz: [anlayın ve çözümleme katman doğrulama hatalarını](#UnderstandingValidationErrors).  
  
###  <a name="ManageErrors"></a>Doğrulama hatalarını yönetme  
 Geliştirme işlemi sırasında, doğrulama esnasında bildirilen çakışmaların bazılarını gizlemek isteyebilirsiniz. Örneğin, zaten çözdüğünüz veya özel senaryonuzla ilgili olmayan hataları gizlemek isteyebilirsiniz. Bir hatayı bastırmak, bir iş öğesi oturum açmak için iyi bir uygulama olur [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)].  
  
> [!WARNING]
>  Zaten için TFS kaynak kodu denetimi (oluşturmak veya bir iş öğesine bağlamak için SCC) bağlı gerekir. Farklı bir TFS SCC bağlantı açmaya çalışırsanız, Visual Studio geçerli çözümü otomatik olarak kapatılır. Zaten uygun SCC oluşturmak veya bir iş öğesine bağlamak denemeden önce bağlı olduğunuzdan emin olun. Visual Studio daha sonraki sürümlerde menü komutlarını bir SCC bağlı değilseniz kullanılabilir değil.  
  
##### <a name="to-create-a-work-item-for-a-validation-error"></a>Doğrulama hatası için bir öğesi oluşturmak üzere  
  
-   İçinde **hata listesi** penceresi, hata sağ tıklayın, fareyle **iş öğesi oluşturma**ve ardından oluşturmak istediğiniz iş öğesi türüne tıklayın.  
  
 Doğrulama hatalarını yönetmek için bu görevleri kullanın **hata listesi** penceresi:  
  
|**Hedef**|**Aşağıdaki adımları izleyin**|  
|------------|----------------------------|  
|Doğrulama sırasında seçili hataları gizleme|Bir veya birden çok seçili hataya sağ tıklayın, fareyle **doğrulama hatalarını Yönet**ve ardından **bastırmak hataları**.<br /><br /> Gizlenen hatalar üstü çizili biçimde görünür. Doğrulamayı daha sonra çalıştırdığınızda bu hatalar görünmez.<br /><br /> Gizlenen hatalar dosyası için ilgili bağımlılık diyagram dosyası .bastırmalar izlenir.|  
|Seçili hataların gizlenmesini durdurma|Seçili gizlenen hata veya hatalara sağ tıklayın, fareyle **doğrulama hatalarını Yönet**ve ardından **Dur gizleme hatalarının**.<br /><br /> Doğrulamayı daha sonra çalıştırdığınızda seçili gizlenen hatalar görünecektir.|  
|Tüm gizlenen hataları geri **hata listesi** penceresi|Herhangi bir yere sağ **hata listesi** penceresinde, noktasına **doğrulama hatalarını Yönet**ve ardından **tüm gizlenen hataları göster**.|  
|Tüm gizlenen hataları gizleyin **hata listesi** penceresi|Herhangi bir yere sağ **hata listesi** penceresinde, noktasına **doğrulama hatalarını Yönet**ve ardından **tüm gizlenen Hataları Gizle**.|  
  
##  <a name="ValidateAuto"></a>Otomatik olarak kod doğrulama  
 Her yerel bir yapı çalıştırışınızda katman doğrulama gerçekleştirebilirsiniz. Takınınız Team Foundation Yapısı kullanıyorsa, özel bir MSBuild görevi oluşturarak belirtebileceğiniz geçitli iadelerle katman doğrulaması gerçekleştirebilir ve doğrulama hatalarını toplamak için yapı raporları kullanabilirsiniz. Geçitli iade etme yapıları oluşturmak için bkz: [değişiklikleri doğrulamak için Geçitli iade derleme süreci kullanma](http://msdn.microsoft.com/Library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec).  
  
#### <a name="to-validate-code-automatically-during-a-local-build"></a>Kodu yerel yapı sırasında otomatik olarak doğrulamak için  
  
-   Modelleme projesi (.modelproj) dosyası açmak için metin düzenleyicisi kullanın ve ardından aşağıdaki özelliği ekleyin:  
  
```  
<ValidateArchitecture>true</ValidateArchitecture>  
```  
  
 \-veya -  
  
1.  İçinde **Çözüm Gezgini**, bağımlılık diyagramı veya diyagramları içeren modelleme projesine sağ tıklayın ve ardından **özellikleri**.  
  
2.  İçinde **özellikleri** penceresindeki ayarlayın modelleme projesinin **Mimariyi Doğrula** özelliğine **doğru**.  
  
     Bu, doğrulama işlemi içinde modelleme projesini içerir.  
  
3.  İçinde **Çözüm Gezgini**, doğrulama için kullanmak istediğiniz bağımlılık diyagramı (.layerdiagram) dosyasına tıklayın.  
  
4.  İçinde **özellikleri** penceresinde olduğundan emin olun diyagramın **yapı eylemi** özelliği ayarlanmış **doğrulama**.  
  
     Bu, bağımlılık diyagram doğrulama işleminde içerir.  
  
 Hata Listesi penceresini hatalarını yönetmek için bkz: [doğrulama hatalarını Yönet](#ManageErrors).  
  
#### <a name="to-validate-code-automatically-during-a-team-foundation-build"></a>Kodu Team Foundation Yapısı sırasında otomatik olarak doğrulamak için  
  
1.  İçinde **Takım Gezgini**, yapı tanımına çift tıklayın ve ardından **işlem**.  
  
2.  Altında **oluşturma işlemi parametreleri**, genişletin **derleme**, aşağıdakileri yazın **MSBuild bağımsız değişkenleri** parametre:  
  
     `/p:ValidateArchitecture=true`  
  
 Doğrulama hataları hakkında daha fazla bilgi için bkz: [anlayın ve çözümleme katman doğrulama hatalarını](#UnderstandingValidationErrors). Hakkında daha fazla bilgi için [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)], bkz:  
  
-   [Uygulama oluşturma](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)  
  
-   [Yapı işleminiz için varsayılan şablonu kullanın](http://msdn.microsoft.com/Library/43930b12-c21b-4599-a980-2995e3d16e31)  
  
-   [Üzerinde UpgradeTemplate.xaml dayalı bir eski yapı değiştirme](http://msdn.microsoft.com/Library/ee1a8259-1dd1-4a10-9563-66c5446ef41c)  
  
-   [Derleme işlem şablonunu özelleştirme](http://msdn.microsoft.com/Library/b94c58f2-ae6f-4245-bedb-82cd114f6039)  
  
-   [Bir çalışan yapı ilerlemeyi izleme](http://msdn.microsoft.com/Library/e51e3bad-2d1d-4b7b-bfcc-c43439c6c8ef)  
  
##  <a name="TroubleshootingValidation"></a>Katman doğrulama sorunlarını giderme  
 Aşağıdaki tabloda katman doğrulama sorunları ve bunların çözümü açıklanmaktadır. Bu sorunlar, kod ve tasarım arasındaki çakışmalarla sonuçlanan hatalardan ayrılır. Bu hatalar hakkında daha fazla bilgi için bkz: [anlayın ve çözümleme katman doğrulama hatalarını](#UnderstandingValidationErrors).  
  
|**Sorunu**|**Olası neden**|**Çözümleme**|  
|---------------|------------------------|--------------------|  
|Doğrulama hataları beklendiği gibi gerçekleşmez.|Doğrulama, Çözüm Gezgini'nde diğer bağımlılık diyagramlarından kopyalanır ve aynı modelleme projesinde olan bağımlılık diyagramlarındaki çalışmaz. Bu şekilde kopyalanır bağımlılık diyagramları özgün bağımlılık diyagram olarak aynı başvurular içeriyor.|Yeni bir bağımlılık diyagramı modelleme projesine ekleyin.<br /><br /> Öğeleri Kaynak bağımlılığı diyagramdan yeni diyagrama kopyalayın.|  
  
##  <a name="UnderstandingValidationErrors"></a>Anlama ve katman doğrulama hatalarını çözme  
 Kod bir bağımlılık diyagramı karşı doğrulama kodu tasarım ile çakışıyor olduğunda doğrulama hataları oluşur. Örneğin, aşağıdaki durumlar doğrulama hatalarının oluşmasına neden olabilir:  
  
-   Yapı yanlış katmana atanmış. Bu durumda, yapıyı taşıyın.  
  
-   Sınıf gibi bir yapı, başka bir sınıfı mimarinizle çakışacak şekilde kullanıyor. Bu durumda, bağımlılığı kaldırmak için kodu yeniden düzenleyin.  
  
 Bu hataları çözmek için doğrulama sırasında daha fazla hata görünmeyene kadar kodu güncelleştirin. Bu görevi yinelemeli bir şekilde gerçekleştirebilirsiniz.  
  
 Aşağıdaki bölümde, bu hatalarda kullanılan sözdizimi belirtilmekte, bu hataların anlamı açıklanmakta ve bunları çözmek veya yönetmek için yapabilecekleriniz önerilmektedir.  
  
|**Sözdizimi**|**Açıklama**|  
|----------------|---------------------|  
|*ArtifactN*(*ArtifactTypeN*)|*ArtifactN* bağımlılık diyagramdaki bir katman ile ilişkilendirilmiş bir yapıdır.<br /><br /> *ArtifactTypeN* türü *ArtifactN*, gibi bir **sınıfı** veya **yöntemi**, örneğin:<br /><br /> MySolution.MyProject.MyClass.MyMethod(Method)|  
|*NamespaceNameN*|Bir ad alanının adı.|  
|*LayerNameN*|Bağımlılık diyagramındaki bir katman adı.|  
|*DependencyType*|Arasındaki bağımlılık ilişkisinin türü *Artifact1* ve *Artifact2*. Örneğin, *Artifact1* sahip bir **çağrıları** ile ilişkisi *Artifact2*.|  
  
|**Hata sözdizimi**|**Hata açıklaması**|  
|----------------------|---------------------------|  
|DV0001: **Geçersiz bağımlılık**|Bu sorun kod öğesi (ad alanı, tür, üye) başka bir katmana eşlenen bir kod öğesi bir katman başvuruları eşlenen, ancak bu katmanlar içeren bağımlılık doğrulama diyagramda bu katmanları arasındaki bağımlılığı ok yok bildirilir. Bir bağımlılık kısıtlama ihlali budur.|  
|DV1001: **geçersiz ad alanı adı**|Bu sorunu "İzin verilen Namespace adları" özelliği bu kodu öğe tanımlandığı ad alanı içermeyen bir katman ile ilişkili bir kod öğesinde bildirilir. Adlandırma bir kısıtlama ihlali budur. Ad alanları ile ilişkili öğeleri katmandır hangi kodda noktalı listesi olmasını sözdizimi "Namespace adlarının izin" olduğuna dikkat edin tanımlanacak verilir.|  
|DV1002: **unreferenceable ad alanında bağımlılık**|Bu sorun, bir katman ile ilişkili ve katman "Unreferenceable Namespace" özelliğinde tanımlanan bir ad alanında tanımlı başka bir kod öğe başvuran bir kod öğesinde bildirilir. Adlandırma bir kısıtlama ihlali budur. "Unreferenceable ad alanları" özelliği bu katman ile ilişkilendirilmiş kod öğelerinde başvurulması olmayan ad alanlarını noktalı virgülle ayrılmış listesi olarak tanımlanır unutmayın.|  
|DV1003: **izin verilmeyen ad alanı adı**|Bu sorun, bu kod öğenin tanımlandığı ad "Namespace adları izin verilmeyen" özelliği içeren bir katman ile ilişkili bir kod öğesinde bildirilir. Adlandırma bir kısıtlama ihlali budur. "Ad alanı adı izin verilmeyen" özelliği hangi kodunda Bu katman ile ilgili bir öğe değil tanımlanmalıdır ad alanları noktalı virgülle ayrılmış listesi olarak tanımlanır unutmayın.|  
|DV3001: **eksik bağlantı**|Katman '*LayerName*'bağlandığı'*yapı*' hangi bulunamıyor. Eksik bir derleme başvurunuz mu var?|*LayerName* , bulunamayan bir yapıya bağlantılar. Örneğin, sınıfla kurulan bir bağlantı kayıp olabilir; çünkü modelleme projesinde sınıfı içeren derlemeye yapılan bir başvuru yoktur.|  
|DV9001: **mimari çözümleme iç hatalar bulundu**|Sonuçlar tamamlanmamış olabilir. Daha fazla bilgi için ayrıntılı yapı olay günlüğü veya çıkış penceresine bakın.|Daha fazla ayrıntı için yapı olay günlüğü veya çıkış penceresine bakın.|  

 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Geliştirme sırasında sisteminizi doğrulama](../modeling/validate-your-system-during-development.md)   
 [Video: mimarisi bağımlılıklarınızı gerçek zamanlı doğrula](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)   
