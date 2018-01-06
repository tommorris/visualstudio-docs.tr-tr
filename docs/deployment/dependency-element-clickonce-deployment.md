---
title: "&lt;bağımlılık&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#osVersionInfo
- urn:schemas-microsoft-com:asm.v2#os
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#dependency
- http://www.w3.org/2000/09/xmldsig#DigestValue
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
- urn:schemas-microsoft-com:asm.v2#dependentAssembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <dependency> element [ClickOnce deployment manifest]
ms.assetid: 9b4d2082-0347-4922-ac70-85f11b913039
caps.latest.revision: "27"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 8716da20c989a1a8d1e36d9e071e9802a06219bf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltdependencygt-element-clickonce-deployment"></a>&lt;bağımlılık&gt; öğesi (ClickOnce dağıtımı)
Yüklenecek uygulamayı sürümü ve uygulama bildirimi konumunu tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <dependency>   
   <dependentAssembly  
      preRequisite  
      visible  
      dependencyType  
      codeBase  
      size  
   >   
      <assemblyIdentity   
         name   
         version   
         publicKeyToken   
         processorArchitecture   
         language  
         type  
      />   
      <hash>  
         <dsig:Transforms>  
            <dsig:Transform  
                Algorithm  
            />  
         </dsig:Transforms>  
         <dsig:DigestMethod />  
         <dsig:DigestValue>  
         </dsig:DigestValue>  
      </hash>  
  
   </dependentAssembly>   
</dependency>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `dependency` Öğesi gereklidir. Özniteliklere sahiptir. Birden çok dağıtım bildirimi olabilir `dependency` öğeleri.  
  
 `dependency` Öğesi genellikle ifade ana uygulamayla ilgili bağımlılıkları içinde bulunan derlemeler üzerinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Main.exe uygulamanız DotNetAssembly.dll olarak adlandırılan bir derlemeyi kullanırsa, bu derleme bağımlılık bölümünde listelenmesi gerekir. Bağımlılık, ancak aynı zamanda bağımlılıkları, belirli bir ortak dil çalışma zamanı sürümü bağımlılıkları gibi diğer türleri bir derlemeyi genel derleme önbelleğinde (GAC) veya bir COM nesnesi hızlı. Bir değmeden dağıtım teknolojisi olduğundan [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] olamaz başlatma indirme ve yükleme bağımlılıkları, ancak bu tür engellemez uygulamanın çalışmasını bir veya daha fazla belirtilen bağımlılık yoksa.  
  
## <a name="dependentassembly"></a>dependentAssembly  
 Gerekli. Bu öğeyi içeren `assemblyIdentity` öğesi. Aşağıdaki tablo öznitelikleri gösterir `dependentAssembly` destekler.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`preRequisite`|İsteğe bağlı. Bu derlemeyi GAC'ye zaten bulunuyor olmalıdır belirtir. Geçerli değerler `true` ve `false`. Varsa `true`ve belirtilen derlemeyi GAC'ye yok, uygulama çalışmaz.|  
|`visible`|İsteğe bağlı. Bağımlılıklarını içeren üst düzey uygulama kimliği tanımlar. Tarafından dahili olarak kullanılan [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama depolama ve etkinleştirmeyi yönetmek için.|  
|`dependencyType`|Gerekli. Bu bağımlılık ve uygulama arasındaki ilişki. Geçerli değerler şunlardır:<br /><br /> -   `install`. Bileşen güncel uygulamadan ayrı bir yükleme temsil eder.<br />-   `preRequisite`. Bileşen geçerli uygulama için gereklidir.|  
|`codebase`|İsteğe bağlı. Uygulama bildirimini tam yolu.|  
|`size`|İsteğe bağlı. Uygulama bildiriminin bayt cinsinden boyutu.|  
  
## <a name="assemblyidentity"></a>assemblyIdentity  
 Gerekli. Bu öğe bir alt öğesi değil `dependentAssembly` öğesi. İçeriği `assemblyIdentity` aynı açıklandığı gibi olmalıdır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi. Aşağıdaki tabloda özniteliklerini gösterilmektedir `assemblyIdentity` öğesi.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Uygulamanın adını tanımlar.|  
|`Version`|Gerekli. Uygulamanın sürüm numarasını şu biçimde belirtir:`major.minor.build.revision`|  
|`publicKeyToken`|Gerekli. Derleme veya uygulama altında imzalandığı ortak anahtarın SHA-1 karma son 8 baytını temsil eden 16 karakter onaltılık dizeyi belirtir. İmzalamak için kullanılan ortak anahtar 2048 bit olmalı veya daha büyük.|  
|`processorArchitecture`|Gerekli. Mikro belirtir. Geçerli değerler `x86` 32-bit Windows için ve `IA64` 64-bit Windows için.|  
|`Language`|İsteğe bağlı. Derlemenin iki parçalı dil kodlarını tanımlar. Örneğin, EN-US, İngilizce (ABD) anlamına gelir. Varsayılan, `neutral` değeridir. Bu öğe `asmv2` ad alanı.|  
|`type`|İsteğe bağlı. Geriye dönük uyumluluk Windows yan yana ile yüklemek için teknolojisi. Yalnızca izin verilen değer `win32`.|  
  
## <a name="hash"></a>hash  
 `hash` İsteğe bağlı bir alt öğedir `file` öğesi. `hash` Öğesi özniteliklere sahip değildir.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]bir uygulamadaki tüm dosyaların algoritmik bir karma dosyaların hiçbiri dağıtımdan sonra değişmediğinden emin olmak için güvenlik denetimi olarak kullanır. Varsa `hash` öğesi dahil değildir, bu onay işlemi gerçekleştirilmez. Bu nedenle, atlama `hash` öğesi önerilmez.  
  
## <a name="dsigtransforms"></a>dsig:TRANSFORMS  
 `dsig:Transforms` , Gerekli bir alt öğedir `hash` öğesi. `dsig:Transforms` Öğesi özniteliklere sahip değildir.  
  
## <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` , Gerekli bir alt öğedir `dsig:Transforms` öğesi. Aşağıdaki tabloda özniteliklerini gösterilmektedir `dsig:Transform` öğesi.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Algorithm`|Bu dosya için Özet hesaplamak için kullanılan algoritma. Şu anda tarafından kullanılan tek değer [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] olan `urn:schemas-microsoft-com:HashTransforms.Identity`.|  
  
## <a name="dsigdigestmethod"></a>dsig  
 `dsig:DigestMethod` , Gerekli bir alt öğedir `hash` öğesi. Aşağıdaki tabloda özniteliklerini gösterilmektedir `dsig:DigestMethod` öğesi.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Algorithm`|Bu dosya için Özet hesaplamak için kullanılan algoritma. Şu anda tarafından kullanılan tek değer [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] olan `http://www.w3.org/2000/09/xmldsig#sha1`.|  
  
## <a name="dsigdigestvalue"></a>DigestValue  
 `dsig:DigestValue` , Gerekli bir alt öğedir `hash` öğesi. `dsig:DigestValue` Öğesi özniteliklere sahip değildir. Belirtilen dosya için hesaplanan karma kendi metin değeridir.  
  
## <a name="remarks"></a>Açıklamalar  
 Dağıtım bildirimleri genellikle sahip tek bir `assemblyIdentity` adı ve sürümü uygulama bildiriminin tanımlayan öğesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği kod bir `dependency` öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi.  
  
```  
<!-- Identify the assembly dependencies -->  
<dependency>  
  <dependentAssembly dependencyType="install" allowDelayedBinding="true" codebase="MyApplication.exe" size="16384">  
    <assemblyIdentity name="MyApplication" version="0.0.0.0" cultural="neutral" processorArchitecture="msil" />  
    <hash>  
      <dsig:Transforms>  
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
      </dsig:Transforms>  
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
       <dsig:DigestValue>YzXYZJAvj9pgAG3y8jXUjC7AtHg=</dsig:DigestValue>  
    </hash>  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir derlemeyi GAC'ye yüklü bir bağımlılık belirtir.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="GACAssembly" version="1.0.0.0" language="neutral" processorArchitecture="msil" />  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde, belirli bir ortak dil çalışma zamanı sürümünde bir bağımlılığı belirtir.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50215.0" />  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir işletim sistemi bağımlılığını belirtir.  
  
```  
<dependency>  
   <dependentOS supportUrl="http://www.microsoft.com" description="Microsoft Windows Operating System">  
      <osVersionInfo>  
         <os majorVersion="4" minorVersion="10" />  
      </osVersionInfo>  
   </dependentOS>  
</dependency>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)   
 [\<bağımlılık > öğesi](../deployment/dependency-element-clickonce-application.md)