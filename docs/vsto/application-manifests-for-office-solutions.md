---
title: Office çözümleri için uygulama bildirimleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 622d2066f6acfe1fdf344f06ee5bbbbdf3d9b410
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="application-manifests-for-office-solutions"></a>Office çözümleri için uygulama bildirimleri
  Bir uygulama bildirimi Microsoft Office çözümü yüklenmiş derlemeleri tanımlayan bir XML dosyasıdır. Microsoft Office geliştirme araçlarını Visual Studio [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] tanımlanan uygulama bildirim şeması [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest) başvuru.  
  
 Office çözümleri için uygulama bildirimleri kullanın aşağıdaki [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] öğeleri ve öznitelikleri.  
  
|Öğe|Açıklama|Öznitelikler|  
|-------------|-----------------|----------------|  
|[&#60;derleme&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/assembly-element-clickonce-deployment)|Gerekli. En üst düzey öğesi.|**ManifestVersion**|  
|[&#60;assemblyIdentity&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment)|Gerekli. Tanımlayan [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] uygulamanın birincil derleme.|**Adı**<br /><br /> **Sürüm**<br /><br /> **PublicKeyToken**<br /><br /> **ProcessorArchitecture**<br /><br /> **Dil**|  
|[&#60;trustInfo&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/trustinfo-element-clickonce-application)|Uygulama güvenlik gereksinimlerini tanımlar.|Yok.|  
|[&#60;entryPoint&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/entrypoint-element-clickonce-application)|Gerekli. Yürütme için uygulama kodu giriş noktası tanımlar.|**Adı**<br /><br /> **dependencyName**<br /><br /> **customHostSpecified**|  
|[&#60;bağımlılık&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/dependency-element-clickonce-deployment)|Gerekli. Uygulamayı çalıştırmak için gereken her bağımlılığı tanımlar. İsteğe bağlı olarak, önceden yüklenmiş gereken derlemeleri tanımlar.|Yok.|  
|[&#60;Dosya&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/file-element-clickonce-application)|Gerekli. Uygulama tarafından kullanılan her derleme olmayan dosya tanımlar. Dosyayla ilişkili Bileşen Nesne Modeli (COM) yalıtım verileri içerebilir.|**Adı**<br /><br /> **Boyutu**|  
  
 Office çözümleri için uygulama bildirimleri olmayan aşağıdaki öğeyi `co.v1` ad alanı.  
  
```xml  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>   
```  
  
 Bu uygulama bildirimleri aşağıdaki öğeleri ve öznitelikleri de `vstav3` ad alanı.  
  
```xml  
<addIn>  
  <entryPointsCollection>  
    <entryPoints>  
      <entryPoint>  
      </entryPoint>  
    </entryPoints>  
  </entryPointsCollection>  
  <update></update>  
  <postActions>  
    <postAction>  
      <postActionData>  
      </postActionData>  
    <postAction>  
  </postActions>  
  <application>  
    <customizations>  
      <customization>  
      </customization>  
    </customizations>  
  </application  
</addIn>  
```  
  
|Öğe|Açıklama|Öznitelikler|  
|-------------|-----------------|----------------|  
|[&#60;customHostSpecified&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/customhostspecified-element-office-development-in-visual-studio.md)|Gerekli. Bildirim özellikle Office çözümü işaretler.|Yok.|  
|[&#60;eklentisi&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/addin-element-office-development-in-visual-studio.md)|Gerekli. Giriş noktaları tek bir ad depolar.|Yok.|  
|[&#60;entryPointsCollection&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/entrypointscollection-element-office-development-in-visual-studio.md)|Gerekli. Bir veya daha fazla Office çözümleri için tüm derlemelerde gruplandırır.|**id**|  
|[&#60;giriş noktaları&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)|Gerekli. Office çözümünü çalıştıracak derlemeleri gruplandırır.|Yok.|  
|[&#60;entryPoint&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/entrypoint-element-office-development-in-visual-studio.md)|Gerekli. Office çözümünü çalıştırmak için derlemeyi tanımlar.|**class**<br /><br /> **Sözleşme**|  
|[&#60;Güncelleştirme&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/update-element-office-development-in-visual-studio.md)|Gerekli. Çözüm için güncelleştirmeleri yapılandırır.|**Etkin**<br /><br /> **süre sonu**|  
|[&#60;postActions&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/postactions-element-office-development-in-visual-studio.md)|İsteğe bağlı. Office çözümleri yüklendikten sonra çalıştıran tüm dağıtım sonrası eylemleri, gruplandırır.|Yok.|  
|[&#60;postAction&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/postaction-element-office-development-in-visual-studio.md)|İsteğe bağlı. Dağıtım sonrası eylemi tanımlar.|Yok.|  
|[&#60;postActionData&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)|İsteğe bağlı. Verileri bir dağıtım sonrası eylemi için yapılandırır.|Yok.|  
|[&#60;Uygulama&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/application-element-office-development-in-visual-studio.md)|Gerekli. Uygulamaya özgü bilgileri tek bir düğümde sarmalar.|Yok.|  
|[&#60;Özelleştirmeleri&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/customizations-element-office-development-in-visual-studio.md)|Gerekli. Uygulama ana bilgisayarı özel tüm bilgileri ayrı bir ad alanında depolar.|Yok.|  
|[&#60;özelleştirme&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/customization-element-office-development-in-visual-studio.md)|Gerekli. Uygulama ana bilgisayar özgü bilgileri ayrı bir ad alanında depolar.|**Xmlns**|  
|[&#60;Belge&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/document-element-office-development-in-visual-studio.md)|Yalnızca belge düzeyi çözümleri için gereklidir. Özelleştirme özgü bilgileri depolar.|**SolutionID**|  
|[&#60;appAddin&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/appaddin-element-office-development-in-visual-studio.md)|Yalnızca uygulama düzeyi çözümleri için gereklidir. Özelleştirme özgü bilgileri depolar.|**Uygulama**<br /><br /> **LoadBehavior**<br /><br /> **anahtar adı**|  
|[&#60;friendlyName&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)|İsteğe bağlı. VSTO görüntülenen eklenti adı yüklü VSTO eklentileri listesinde de depolar.|Yok.|  
|[&#60;Açıklama&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/description-element-office-development-in-visual-studio.md)|Yalnızca VSTO eklentileri için gereklidir. Yüklü programlar listesinde görüntülenen açıklama depolar.|Yok.|  
|[&#60;formRegions&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/formregions-element-office-development-in-visual-studio.md)|Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir.|Yok.|  
|[&#60;formRegion&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/formregion-element-office-development-in-visual-studio.md)|Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir.|**Ad**|  
|[&#60;vstoRuntime&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/vstoruntime-element-office-development-in-visual-studio.md)|Gerekli. Office çözümü tarafından desteklenen Office çalışma zamanı için Visual Studio Araçları belirli bir sürümünü açıklar.|**Sürüm**<br /><br /> **Sürüm**<br /><br /> **supportUrl**|  
  
## <a name="remarks"></a>Açıklamalar  
 Office çözümlerinde dağıtım bildirimleri ve uygulama el ile düzenleyebilirsiniz. Daha sonra uygulamayı yeniden imzalamak ve dağıtım bildirimlerini bildirim oluşturma ve düzenleme Aracı'nı kullanarak (*mage.exe* ve *mageui.exe*). Daha fazla bilgi için bkz: [nasıl yapılır: yeniden, uygulama ve dağıtım bildirimlerini imzalama](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="file-location"></a>Dosya konumu  
 Bir uygulama bildirimi tek bir çözüm sürümüne özeldir. Bu nedenle, uygulama bildirimleri ayrı ayrı dağıtım bildirimlerinden depolanması gerekir. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ilişkili sürümünde sonra adlı bir alt sürüme özgü dosyaları yerleştirir *uygulama dosyalarını* alt yayımlama klasörü dizininde.  
  
## <a name="file-name-syntax"></a>Dosya adı sözdizimi  
 Bir uygulama bildirim dosyasının adı tam adı ve uzantısı uygulamanın tanımlanan olmalıdır **assemblyIdentity** .manifest uzantısının ardından öğesi. Örneğin, başvurduğu bir uygulama bildirimi *OutlookAddIn1.dll* özelleştirme aşağıdaki dosya adı sözdizimi kullanır.  
  
 `OutlookAddIn1.dll.manifest`  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  