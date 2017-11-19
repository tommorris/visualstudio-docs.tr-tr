---
title: "&lt;entryPoint&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#commandLine
- urn:schemas-microsoft-com:asm.v2#entryPoint
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <entryPoint> element [ClickOnce application manifest]
- manifests [ClickOnce], entryPoint element
ms.assetid: 10ad3083-10c1-4189-a870-9bba2eab244f
caps.latest.revision: "33"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: eb280684f0c06391bc6c0596093c01f260f685d3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="ltentrypointgt-element-clickonce-application"></a>&lt;entryPoint&gt; öğesi (ClickOnce uygulaması)
Olması gereken derleme tanımlayan yürütülmesi bu [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamayı bir istemci bilgisayarda çalıştırın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <entryPoint  
   name  
>  
   <assemblyIdentity  
      name  
      version  
      processorArchitecture  
      language  
   />  
   <commandLine  
      file  
      parameters  
   />  
   <customHostRequired />  
   <customUX />  
</entryPoint>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `entryPoint` Öğesi gereklidir ve yer `urn:schemas-microsoft-com:asm.v2` ad alanı. Yalnızca olabilir bir `entryPoint` uygulama bildiriminde tanımlanan öğe.  
  
 `entryPoint` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`name`|İsteğe bağlı. Bu değer, .NET Framework tarafından kullanılmaz.|  
  
 `entryPoint`Aşağıdaki öğeler vardır.  
  
## <a name="assemblyidentity"></a>assemblyIdentity  
 Gerekli. Rolü `assemblyIdentity` ve özniteliklerini tanımlanmış [ \<assemblyIdentity > öğesi](../deployment/assemblyidentity-element-clickonce-application.md).  
  
 `processorArchitecture` Bu öğesinin özniteliği ve `processorArchitecture` tanımlanan öznitelik `assemblyIdentity` başka bir uygulama bildirimi eşleşmesi gerekir.  
  
## <a name="commandline"></a>komut satırı  
 Gerekli. Bir alt öğesi olması gerekir `entryPoint` öğesi. Alt öğeleri yoktur ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`file`|Gerekli. Yerel bir referans için başlangıç derlemesine [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Bu değer, eğik çizgi (/) veya ters eğik çizgi içeremez (\\) yol ayırıcıları.|  
|`parameters`|Gerekli. Giriş noktasıyla yapılacak eylemi açıklar. Geçerli tek değer `run`; boş bir dize sağlanırsa, `run` varsayılır.|  
  
## <a name="customhostrequired"></a>customHostRequired  
 İsteğe bağlı. Eklediyseniz, bu dağıtımın özel bir konağın içinde dağıtılan bir bileşeni içerdiğini belirtir ve tek başına bir uygulama değildir.  
  
 Bu öğe varsa, `assemblyIdentity` ve `commandLine` öğeleri değil de bulunmalıdır. Olmaları durumunda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yükleme sırasında bir doğrulama hatası yükseltirsiniz.  
  
 Bu öğe, öznitelik ve alt öğesi vardır.  
  
## <a name="customux"></a>customUX  
 İsteğe bağlı. Uygulama yüklü olduğundan ve özel bir yükleyici tarafından tutulan ve oluşturmaz Başlat menüsü girişi, kısayol veya Ekle veya programlar girişini kaldırmak olduğunu belirtir.  
  
```  
<customUX xmlns="urn:schemas-microsoft-com:clickonce.v1" />  
```  
  
 CustomUX öğesini içeren bir uygulama kullanan özel bir yükleyici sağlamalısınız <xref:System.Deployment.Application.InPlaceHostingManager> yükleme işlemlerini gerçekleştirmek için. Bu öğeye sahip bir uygulama, bildirim veya setup.exe önkoşul önyükleyici çift tıklatarak yüklenemez. Özel yükleyici Başlat menüsü girişleri, kısayolları ve Program Ekle veya Kaldır girişleri oluşturabilirsiniz. Özel yükleyici Program Ekle veya Kaldır giriş oluşturmaz, tarafından sağlanan abonelik tanımlayıcısı depolamalısınız <xref:System.Deployment.Application.GetManifestCompletedEventArgs.SubscriptionIdentity%2A> özelliği ve etkinleştir çağırarak daha sonra uygulamayı kaldırmak için kullanıcı <xref:System.Deployment.Application.InPlaceHostingManager.UninstallCustomUXApplication%2A> yöntemi. Daha fazla bilgi için bkz: [izlenecek yol: ClickOnce uygulaması için bir özel yükleyici oluşturma](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öğe için derleme ve giriş noktasını tanımlar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
 Kullanamazsınız `commandLine` çalışma zamanında uygulamanıza parametreleri geçirmek için. Sorgu dizesi parametreleri için erişmek için bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamanın dağıtımından <xref:System.AppDomain>. Daha fazla bilgi için bkz: [nasıl yapılır: çevrimiçi bir ClickOnce uygulamasında sorgu dize bilgilerini alma](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği gösterilmektedir bir `entryPoint` için bir uygulama bildirimi öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md) konu.  
  
```  
<!-- Identify the main code entrypoint. -->  
<!-- This code runs the main method in an executable assembly. -->  
  <entryPoint>  
    <assemblyIdentity   
      name="MyApplication"   
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)