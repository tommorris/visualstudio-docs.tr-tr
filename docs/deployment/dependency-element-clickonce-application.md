---
title: '&lt;bağımlılık&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
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
helpviewer_keywords:
- manifests [ClickOnce], dependency element
- <dependency> element [ClickOnce application manifest]
ms.assetid: 09d6a1e0-60f8-4fbd-843b-8e49ee3115a3
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: be31fafb64b44d6d98917edb11f82a69fbc41c76
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ltdependencygt-element-clickonce-application"></a>&lt;bağımlılık&gt; öğesi (ClickOnce uygulaması)
Uygulama için gerekli olan bir platform veya derleme bağımlılığı tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <dependency>  
   <dependentOS  
      supportURL  
      description  
   >  
      <osVersionInfo>  
         <os  
            majorVersion  
            minorVersion  
            buildNumber  
            servicePackMajor  
            servicePackMinor  
            productType  
            suiteType  
         />   
      </osVersionInfo>  
   </dependentOS>  
   <dependentAssembly  
      dependencyType  
      allowDelayedBinding  
      group  
      codeBase  
      size  
   >  
      <assemblyIdentity  
         name  
         version  
         processorArchitecture  
         language  
      >  
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
  
      </assemblyIdentity>  
   </dependentAssembly>  
</dependency>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `dependency` Öğesi gereklidir. Birden çok örneği olabilir `dependency` aynı uygulama bildiriminde.  
  
 `dependency` Öğesi özniteliklere sahip ve aşağıdaki alt öğeleri içerir.  
  
### <a name="dependentos"></a>dependentOS  
 İsteğe bağlı. İçeren `osVersionInfo` öğesi. `dependentOS` Ve `dependentAssembly` öğeleri karşılıklı olarak birbirini dışlar: birini veya diğerini için bulunmalıdır bir `dependency` öğesi, ancak ikisini birden değil.  
  
 `dependentOS` Aşağıdaki öznitelikleri destekler.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`supportUrl`|İsteğe bağlı. Bağımlı platform için destek URL'sini belirtir. Gerekli platform bulunursa bu URL kullanıcıya gösterilir.|  
|`description`|İsteğe bağlı. Açıklar, okunabilir formunda tarafından tanımlanan işletim sistemini `dependentOS` öğesi.|  
  
### <a name="osversioninfo"></a>OSVERSIONINFO  
 Gerekli. Bu öğe bir alt öğesi değil `dependentOS` öğesi ve içeren `os` öğesi. Bu öğe özniteliklere sahiptir.  
  
### <a name="os"></a>işletim sistemi  
 Gerekli. Bu öğe bir alt öğesi değil `osVersionInfo` öğesi. Bu öğe aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`majorVersion`|Gerekli. İşletim Sisteminin ana sürüm numarasını belirtir.|  
|`minorVersion`|Gerekli. İşletim sistemi alt sürüm numarasını belirtir.|  
|`buildNumber`|Gerekli. İşletim sistemi yapı sayısını belirtir.|  
|`servicePackMajor`|Gerekli. İşletim sistemi hizmet paketi ana sayısını belirtir.|  
|`servicePackMinor`|İsteğe bağlı. İşletim sistemi hizmet paketi küçük sayısını belirtir.|  
|`productType`|İsteğe bağlı. Ürün türü değerini tanımlar. Geçerli değerler `server`, `workstation`, ve `domainController`. Örneğin, Windows 2000 Professional için bu öznitelik değeri olan `workstation`.|  
|`suiteType`|İsteğe bağlı. Sistem veya sistemin yapılandırma türünü kullanılabilir bir ürün paketine tanımlar. Geçerli değerler `backoffice`, `blade`, `datacenter`, `enterprise`, `home`, `professional`, `smallbusiness`, `smallbusinessRestricted`, ve `terminal`. Örneğin, Windows 2000 Professional için bu öznitelik değeri olan `professional`.|  
  
### <a name="dependentassembly"></a>dependentAssembly  
 İsteğe bağlı. İçeren `assemblyIdentity` öğesi. `dependentOS` Ve `dependentAssembly` öğeleri karşılıklı olarak birbirini dışlar: birini veya diğerini için bulunmalıdır bir `dependency` öğesi, ancak ikisini birden değil.  
  
 `dependentAssembly` Aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`dependencyType`|Gerekli. Bağımlılık türünü belirtir. Geçerli değerler `preprequisite` ve `install`. Bir `install` derleme parçası olarak yüklü [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. A `prerequisite` derleme genel derleme önbelleğinde (GAC) önce mevcut olmalı [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama yükleyebilir.|  
|`allowDelayedBinding`|Gerekli. Derleme program aracılığıyla çalışma zamanında yüklenebilir olup olmadığını belirtir.|  
|`group`|İsteğe bağlı. Varsa `dependencyType` özniteliği `install`, yalnızca yükleme isteğe bağlı derlemeleri adlandırılmış bir grup belirler. Daha fazla bilgi için bkz: [izlenecek yol: ClickOnce dağıtım API'sini kullanarak Tasarımcısı ile isteğe bağlı derlemeleri indirme](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md).<br /><br /> Varsa kümesine `framework` ve `dependencyType` özniteliği olarak ayarlanmış `prerequisite`, derleme .NET Framework'ün bir parçası olarak atar. Genel Derleme Önbelleği (GAC) Bu derleme için yüklerken işaretlenmemişse [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] ve sonraki sürümler.|  
|`codeBase`|Ne zaman gerekli `dependencyType` özniteliği `install`. Bağımlı derleme yolu. Mutlak bir yol veya bildirim kodunun göreli bir yol temel olabilir. Bu yol, geçerli olması için geçerli bir URI derleme bildirimi sırada olmalıdır.|  
|`size`|Ne zaman gerekli `dependencyType` özniteliği `install`. Bağımlı derlemenin bayt cinsinden boyutu.|  
  
### <a name="assemblyidentity"></a>assemblyIdentity  
 Gerekli. Bu öğe bir alt öğesi değil `dependentAssembly` öğesi ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`name`|Gerekli. Uygulamanın adını tanımlar.|  
|`version`|Gerekli. Uygulamanın sürüm numarasını şu biçimde belirtir: `major.minor.build.revision`|  
|`publicKeyToken`|İsteğe bağlı. Son 8 baytını temsil eden bir 16 karakter onaltılık dize belirtir `SHA-1` karma altında uygulama imzalanan derleme veya ortak anahtar değeri. Kataloğu imzalamak için kullanılan ortak anahtar 2048 bit veya daha fazla olmalıdır.|  
|`processorArchitecture`|İsteğe bağlı. İşlemci belirtir. Geçerli değerler `x86` 32-bit Windows için ve `I64` 64-bit Windows için.|  
|`language`|İsteğe bağlı. Örneğin EN-US, derlemenin iki parçalı dil kodlarını tanımlar.|  
  
### <a name="hash"></a>hash  
 `hash` İsteğe bağlı bir alt öğedir `assemblyIdentity` öğesi. `hash` Öğesi özniteliklere sahip değildir.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir uygulamadaki tüm dosyaların algoritmik bir karma dosyaların hiçbiri dağıtımdan sonra değişmediğinden emin olmak için güvenlik denetimi olarak kullanır. Varsa `hash` öğesi dahil değildir, bu onay işlemi gerçekleştirilmez. Bu nedenle, atlama `hash` öğesi önerilmez.  
  
### <a name="dsigtransforms"></a>dsig:TRANSFORMS  
 `dsig:Transforms` , Gerekli bir alt öğedir `hash` öğesi. `dsig:Transforms` Öğesi özniteliklere sahip değildir.  
  
### <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` , Gerekli bir alt öğedir `dsig:Transforms` öğesi. `dsig:Transform` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Algorithm`|Bu dosya için Özet hesaplamak için kullanılan algoritma. Şu anda tarafından kullanılan tek değer [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] olan `urn:schemas-microsoft-com:HashTransforms.Identity`.|  
  
### <a name="dsigdigestmethod"></a>dsig  
 `dsig:DigestMethod` , Gerekli bir alt öğedir `hash` öğesi. `dsig:DigestMethod` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Algorithm`|Bu dosya için Özet hesaplamak için kullanılan algoritma. Şu anda tarafından kullanılan tek değer [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] olan `http://www.w3.org/2000/09/xmldsig#sha1`.|  
  
### <a name="dsigdigestvalue"></a>DigestValue  
 `dsig:DigestValue` , Gerekli bir alt öğedir `hash` öğesi. `dsig:DigestValue` Öğesi özniteliklere sahip değildir. Belirtilen dosya için hesaplanan karma kendi metin değeridir.  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamanız tarafından kullanılan tüm derlemelere karşılık gelen olmalıdır `dependency` öğesi. Bağımlı derlemeleri genel derleme önbelleğinde platform derlemesi olarak önceden gerekir derlemeleri içermez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir `dependency` öğelerinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi. Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md) konu.  
  
```  
<dependency>  
  <dependentOS>  
    <osVersionInfo>  
      <os   
        majorVersion="4"   
        minorVersion="10"   
        buildNumber="0"   
        servicePackMajor="0" />  
    </osVersionInfo>  
  </dependentOS>  
</dependency>  
<dependency>  
  <dependentAssembly  
    dependencyType="preRequisite"  
    allowDelayedBinding="true">  
    <assemblyIdentity  
      name="Microsoft.Windows.CommonLanguageRuntime"  
      version="4.0.20506.0" />  
  </dependentAssembly>  
</dependency>  
  
<dependency>  
  <dependentAssembly  
    dependencyType="install"  
    allowDelayedBinding="true"  
    codebase="MyApplication.exe"  
    size="4096">  
    <assemblyIdentity  
      name="MyApplication"  
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <hash>  
      <dsig:Transforms>  
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
      </dsig:Transforms>  
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>  
    </hash>  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)   
 [\<bağımlılık > öğesi](../deployment/dependency-element-clickonce-deployment.md)