---
title: "&lt;entryPoint&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <entryPoint> element
- <entryPoint> element
- entryPoint element
ms.assetid: 0c9d22d0-0852-4260-89c6-b83f24e48793
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a5ef93ab759f4e64607685d3d44fddfbf6c2c2dc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltentrypointgt-element-office-development-in-visual-studio"></a>&lt;entryPoint&gt; öğesi (Visual Studio'da Office Geliştirme)
  Her `entryPoint` öğesinin `vstav3` ad alanını tanımlayan ne zaman çalıştırılması gerektiğini özelleştirme derlemesini bu [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] uygulama yüklenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<entryPoint class>  
    <assemblyIdentity />  
</entryPoint>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `entryPoint` Öğesi gereklidir ve yer `vstav3` ad alanı.  
  
 Her `entryPoint` öğesi yalnızca bir özelleştirme derlemesini içerebilir. Birden çok da olabilir `entryPoint` öğesi uygulama bildiriminde tanımlandı.  
  
 `entryPoint` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`class`|Gerekli. Yürütülecek özelleştirme derlemesi tanımlar. Bu öznitelik için söz dizimi *İsimUzayıAdı.SınıfAdı*.|  
  
 `entryPoint`Aşağıdaki öğe var.  
  
### <a name="assemblyidentity"></a>assemblyIdentity  
 Gerekli. `assemblyIdentity` Öğesinde `vstav3` ad alanı başvuruyor varolan bir `assemblyIdentity` öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] uygulama bildirimi.  
  
 Rolü `assemblyIdentity` ve özniteliklerini tanımlanmış [&#60; assemblyIdentity &#62; Öğe &#40; ClickOnce Uygulama &#41; ](/visualstudio/deployment/assemblyidentity-element-clickonce-application).  
  
## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `entryPoint` bildiriminde bir uygulamada kullanılarak dağıtılan bir belge düzeyi Office çözümü için [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.ThisWorkbook">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.Sheet1">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.Sheet2">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
<vstav3:entryPoint   
  class="ContosoExcelWorkbook.Sheet3">  
  <assemblyIdentity   
    name="ContosoExcelWorkbook"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
```  
  
## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir bir `entryPoint` kullanarak dağıtılmış uygulama düzeyi Office çözümü için bir uygulama bildirimi öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstav3:entryPoint   
  class="ContosoOutlookAddIn.ThisAddIn">  
  <assemblyIdentity   
    name="ContosoOutlookAddIn"   
    version="1.0.0.0"   
    language="neutral"   
    processorArchitecture="msil" />  
</vstav3:entryPoint>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  