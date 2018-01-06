---
title: "&lt;Dosya&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#file
- http://www.w3.org/2000/09/xmldsig#DigestValue
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <file> element [ClickOnce application manifest]
- manifests [ClickOnce], file element
ms.assetid: 56e3490c-eed5-4841-b1bf-eefe778b6ac9
caps.latest.revision: "24"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 9e3e6429f32c8939960816e576f9aabefd4763e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfilegt-element-clickonce-application"></a>&lt;Dosya&gt; öğesi (ClickOnce uygulaması)
İndirilen ve uygulama tarafından kullanılan tüm nonassembly dosyaları tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<file  
    name  
    size  
    group  
    optional  
    writeableType  
>  
    <typelib  
        tlbid  
        version  
        helpdir  
        resourceid  
        flags  
    />  
    <comClass  
        clsid  
        description  
        threadingModel  
        tlbid  
        progid  
        miscStatus  
        miscStatusIcon  
        miscStatusContent  
        miscStatusDocPrint  
        miscStatusThumbnail  
    />  
    <comInterfaceExternalProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <comInterfaceProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <windowClass  
        versioned  
    />  
</file>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `file` Öğesidir isteğe bağlıdır. Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`name`|Gerekli. Dosyanın adını tanımlar.|  
|`size`|Gerekli. Boyutu dosyasının bayt cinsinden belirtir.|  
|`group`|İsteğe bağlı `optional` özniteliği belirtilmemişse veya kümesine `false`; gereklidir `optional` olan `true`. Bu dosyayı ait olduğu grubu adı. Ad geliştirici tarafından seçilen herhangi bir Unicode dize değeri olabilir ve ile isteğe bağlı dosyaları indirmek için kullanılan <xref:System.Deployment.Application.ApplicationDeployment> sınıfı.|  
|`optional`|İsteğe bağlı. Bu dosya gerekip gerekmediğini uygulama ilk çalıştırıldığında veya isteğe bağlı olarak uygulama talep edene kadar dosya yalnızca sunucuda bulunup bulunmaması gerektiğini belirtir. Varsa `false` veya tanımlanmamışsa, uygulamayı ilk kez çalıştırdığınızda veya dosya indirilir. Varsa `true`, `group` geçerli olması uygulama bildirimi için belirtilmelidir. `optional`TRUE olamaz, `writeableType` değeriyle belirtilen `applicationData`.|  
|`writeableType`|İsteğe bağlı. Bu dosyayı bir veri dosyası olduğunu belirtir. Şu anda yalnızca geçerli değer: `applicationData`.|  
  
## <a name="typelib"></a>tür kitaplığı  
 `typelib` Dosya öğesinin isteğe bağlı bir alt öğedir. COM bileşenine ait tür kitaplığı açıklar. Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`tlbid`|Gerekli. Tür Kitaplığı'na atanan GUID.|  
|`version`|Gerekli. Tür kitaplığı sürüm numarası.|  
|`helpdir`|Gerekli. Bileşeni için Yardım dosyalarını içeren dizini. Sıfır uzunluklu olabilir.|  
|`resourceid`|İsteğe bağlı. Yerel ayar kimliği (LCID) onaltılık dize gösterimi. Dörde onaltılık basamaktan 0 x öneki ve baştaki sıfırlar olmadan oluşur. LCID nötr alt dili tanımlayıcısına sahip olabilir.|  
|`flags`|İsteğe bağlı. Bu tür kitaplığı için tür kitaplık bayrakları dize gösterimi. Özellikle de "Kısıtlı", "Denetim", "Gizli" ve "HASDISKIMAGE" olmalı.|  
  
## <a name="comclass"></a>comClass  
 `comClass` İsteğe bağlı bir alt öğedir `file` öğesi, ancak olup gerekli olmadığını [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama oranla Kayıtsız COM kullanarak dağıtmak için bir COM bileşeni içerir Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`clsid`|Gerekli. Sınıf kimliği bir GUID olarak ifade edilen COM bileşeni.|  
|`description`|İsteğe bağlı. Sınıf adı.|  
|`threadingModel`|İsteğe bağlı. İşlem içi COM sınıfları tarafından kullanılan iş parçacığı modeli. Bu özellik null ise, iş parçacığı modeli kullanılır. Bileşen istemci ana iş parçacığı oluşturulur ve diğer iş parçacıklarından çağrıları bu iş parçacığı için hazırlanırlar. Aşağıdaki listede, geçerli değerleri gösterir:<br /><br /> `Apartment`, `Free`, `Both`, ve `Neutral`.|  
|`tlbid`|İsteğe bağlı. Bu COM bileşeni için tür kitaplığı için GUID.|  
|`progid`|İsteğe bağlı. COM bileşeni ile ilişkili sürümüne bağımlı program tanımlayıcısı. Biçimi bir `ProgID` olan `<vendor>.<component>.<version>`.|  
|`miscStatus`|İsteğe bağlı. Derlemedeki çoğaltır tarafından sağlanan bilgileri `MiscStatus` kayıt defteri anahtarı. Varsa değerleri `miscStatusIcon`, `miscStatusContent`, `miscStatusDocprint`, veya `miscStatusThumbnail` öznitelikleri bulunamadı, karşılık gelen varsayılan değer listelenen `miscStatus` eksik öznitelikleri için kullanılır. Değer aşağıdaki tablodan öznitelik değerlerini virgülle ayrılmış bir listesi olabilir. COM sınıfı gerektiren bir OCX sınıfı ise bu özniteliğin kullanabilirsiniz `MiscStatus` kayıt defteri anahtarı değerleri.|  
|`miscStatusIcon`|İsteğe bağlı. Derlemedeki DVASPECT_ICON tarafından sağlanan bilgileri çoğaltır. Simge bir nesnenin sağlayabilir. Değer aşağıdaki tablodan öznitelik değerlerini virgülle ayrılmış bir listesi olabilir. COM sınıfı gerektiren bir OCX sınıfı ise bu özniteliğin kullanabilirsiniz `Miscstatus` kayıt defteri anahtarı değerleri.|  
|`miscStatusContent`|İsteğe bağlı. Derlemedeki DVASPECT_ICON tarafından sağlanan bilgileri çoğaltır. Bir ekran veya yazıcı için bunu görüntülenebilir bir bileşik belge sağlayabilir. Değer aşağıdaki tablodan öznitelik değerlerini virgülle ayrılmış bir listesi olabilir. COM sınıfı gerektiren bir OCX sınıfı ise bu özniteliğin kullanabilirsiniz `MiscStatus` kayıt defteri anahtarı değerleri.|  
|`miscStatusDocPrint`|İsteğe bağlı. Derlemedeki DVASPECT_ICON tarafından sağlanan bilgileri çoğaltır. Bir yazıcıya gibi çıkarırsa, görüntülenebilecek bir nesne temsili ekranda sağlayabilir. Değer aşağıdaki tablodan öznitelik değerlerini virgülle ayrılmış bir listesi olabilir. COM sınıfı gerektiren bir OCX sınıfı ise bu özniteliğin kullanabilirsiniz `MiscStatus` kayıt defteri anahtarı değerleri.|  
|`miscStatusThumbnail`|İsteğe bağlı. Derlemedeki DVASPECT_ICON tarafından sağlanan bilgileri çoğaltır. Bir nesnenin küçük resmini tarama aracı içinde görüntülenebilir sağlayabilir. Değer aşağıdaki tablodan öznitelik değerlerini virgülle ayrılmış bir listesi olabilir. COM sınıfı gerektiren bir OCX sınıfı ise bu özniteliğin kullanabilirsiniz `MiscStatus` kayıt defteri anahtarı değerleri.|  
  
## <a name="cominterfaceexternalproxystub"></a>comInterfaceExternalProxyStub  
 `comInterfaceExternalProxyStub` İsteğe bağlı bir alt öğedir `file` öğesi, varsa gerekli olabilir ancak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama oranla Kayıtsız COM kullanarak dağıtmak için bir COM bileşeni içerir Öğe aşağıdaki öznitelikleri içerir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`iid`|Gerekli. Bu proxy tarafından hizmet kimliği (IID) arabirim. IID çevreleyen ayraç olması gerekir.|  
|`baseInterface`|İsteğe bağlı. İçinden arabirimi başvurulan arabirimi IID `iid` türetilir.|  
|`numMethods`|İsteğe bağlı. Arabirimi tarafından uygulanan yöntemleri sayısı.|  
|`name`|İsteğe bağlı. Bu arabirim adı kodda görünür.|  
|`tlbid`|İsteğe bağlı. Tarafından belirtilen arabirimin açıklamasını içeren tür kitaplığı `iid` özniteliği.|  
|`proxyStubClass32`|İsteğe bağlı. Bir 32-bit proxy DLL'ler CLSID IID'yi eşler.|  
  
## <a name="cominterfaceproxystub"></a>comInterfaceProxyStub  
 `comInterfaceProxyStub` İsteğe bağlı bir alt öğedir `file` öğesi, varsa gerekli olabilir ancak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama oranla Kayıtsız COM kullanarak dağıtmak için bir COM bileşeni içerir Öğe aşağıdaki öznitelikleri içerir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`iid`|Gerekli. Bu proxy tarafından hizmet kimliği (IID) arabirim. IID çevreleyen ayraç olması gerekir.|  
|`baseInterface`|İsteğe bağlı. İçinden arabirimi başvurulan arabirimi IID `iid` türetilir.|  
|`numMethods`|İsteğe bağlı. Arabirimi tarafından uygulanan yöntemleri sayısı.|  
|`Name`|İsteğe bağlı. Bu arabirim adı kodda görünür.|  
|`Tlbid`|İsteğe bağlı. Tarafından belirtilen arabirimin açıklamasını içeren tür kitaplığı `iid` özniteliği.|  
|`proxyStubClass32`|İsteğe bağlı. Bir 32-bit proxy DLL'ler CLSID IID'yi eşler.|  
|`threadingModel`|İsteğe bağlı. İsteğe bağlı. İşlem içi COM sınıfları tarafından kullanılan iş parçacığı modeli. Bu özellik null ise, iş parçacığı modeli kullanılır. Bileşen istemci ana iş parçacığı oluşturulur ve diğer iş parçacıklarından çağrıları bu iş parçacığı için hazırlanırlar. Aşağıdaki listede, geçerli değerleri gösterir:<br /><br /> `Apartment`, `Free`, `Both`, ve `Neutral`.|  
  
## <a name="windowclass"></a>windowClass  
 `windowClass` İsteğe bağlı bir alt öğedir `file` öğesi, varsa gerekli olabilir ancak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama oranla Kayıtsız COM kullanarak dağıtmak için bir COM bileşeni içerir Öğe, uygulanan bir sürüme sahip bir COM bileşeni tarafından tanımlanan bir pencere sınıfı gösterir. Öğe aşağıdaki öznitelikleri içerir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`versioned`|İsteğe bağlı. Pencere sınıfı içeren bütünleştirilmiş kodun sürümünü içeren iç pencere sınıf kaydında kullanılan adı olup olmadığını denetler. Bu özniteliğin değeri olabilir `yes` veya `no`. Varsayılan, `yes` değeridir. Değer `no` yalnızca aynı pencere sınıfı bir yan yana bileşeni ve bir eşdeğer-yana olmayan bileşeni tarafından tanımlanır ve bunları aynı pencere sınıfı olarak davranmak istiyorsanız kullanılmalıdır. Pencere sınıfı kaydı hakkında genel kurallar uygulamak not — yalnızca uygulanan bir sürüm olmadığı için pencere sınıfı kaydeder ilk bileşen, kaydettirebilir.|  
  
## <a name="hash"></a>hash  
 `hash` İsteğe bağlı bir alt öğedir `file` öğesi. `hash` Öğesi özniteliklere sahip değildir.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]bir uygulamadaki tüm dosyaların algoritmik bir karma dosyaların hiçbiri dağıtımdan sonra değişmediğinden emin olmak için güvenlik denetimi olarak kullanır. Varsa `hash` öğesi dahil değildir, bu onay işlemi gerçekleştirilmez. Bu nedenle, atlama `hash` öğesi önerilmez.  
  
 Bir bildirim değil karma bir dosya içeriyorsa, bu bildirim dijital olarak olamaz kullanıcıların bütün bir dosyanın içeriğini doğrulayamadığı için imzalı.  
  
## <a name="dsigtransforms"></a>dsig:TRANSFORMS  
 `dsig:Transforms` , Gerekli bir alt öğedir `hash` öğesi. `dsig:Transforms` Öğesi özniteliklere sahip değildir.  
  
## <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` , Gerekli bir alt öğedir `dsig:Transforms` öğesi. `dsig:Transform` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Algorithm`|Bu dosya için Özet hesaplamak için kullanılan algoritma. Şu anda tarafından kullanılan tek değer [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] olan `urn:schemas-microsoft-com:HashTransforms.Identity`.|  
  
## <a name="dsigdigestmethod"></a>dsig  
 `dsig:DigestMethod` , Gerekli bir alt öğedir `hash` öğesi. `dsig:DigestMethod` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Algorithm`|Bu dosya için Özet hesaplamak için kullanılan algoritma. Şu anda tarafından kullanılan tek değer [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] olan `http://www.w3.org/2000/09/xmldsig#sha1`.|  
  
## <a name="dsigdigestvalue"></a>DigestValue  
 `dsig:DigestValue` , Gerekli bir alt öğedir `hash` öğesi. `dsig:DigestValue` Öğesi özniteliklere sahip değildir. Belirtilen dosya için hesaplanan karma kendi metin değeridir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öğe uygulamayı oluşturan tüm nonassembly dosyaları tanımlar ve özellikle karma değerlerini dosya doğrulama. Bu öğe dosyayla ilişkili Bileşen Nesne Modeli (COM) yalıtım verileri de içerir. Bir dosya değişirse, ayrıca uygulama bildirim dosyasının değişikliği yansıtacak şekilde güncelleştirilmesi gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir `file` bildiriminde bir uygulamada kullanılarak dağıtılan bir uygulama için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
```  
<file name="Icon.ico" size="9216">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>lVoj+Rh6RQ/HPNLOdayQah5McrI=</dsig:DigestValue>  
  </hash>  
</file>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama Bildirimi](../deployment/clickonce-application-manifest.md)