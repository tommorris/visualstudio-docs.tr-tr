---
title: "&lt;eklentisi&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <addIn> element
- addin element
- <addin> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 01e7ee9e7329f46c0a728d48c16fc11eaebea5a8
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
# <a name="ltaddingt-element-office-development-in-visual-studio"></a>&lt;eklentisi&gt; öğesi (Visual Studio'da Office Geliştirme)
  `addin` Öğesinin `vstav3` ad alanı, Microsoft Office VSTO eklentileri ve Visual Studio ile geliştirilen belge düzeyi özelleştirmeleri özgü bilgileri içerir.  

## <a name="syntax"></a>Sözdizimi  

```  
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
    <customization>  
    </customization>  
  </application  
</addIn>  
```  

## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `addin` Öğesinin `vstav3` ad alanı, Office çözümü ve Microsoft Office uygulaması hakkında bilgi içerir. Bu öğe aşağıdaki ad alanında olması gerekir: `vstav3=urn:schemas-microsoft-com:vsta.v3`. Alt öğeler de bu ad alanında olması gerekir.  

 `addin` Öğesi özniteliklere sahip değildir.  

 `addin` Öğe aşağıdaki alt öğeleri vardır.  

### <a name="entrypoints"></a>giriş noktaları  
 Gerekli. `entryPoints` Öğesi açıklanan [ &#60;giriş noktaları&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md).  

### <a name="update"></a>Güncelleştirme  
 Gerekli. `update` Öğesi açıklanan [ &#60;güncelleştirme&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/update-element-office-development-in-visual-studio.md).  

### <a name="postactions"></a>postActions  
 İsteğe bağlı. `postActions` Öğesi açıklanan [ &#60;postActions&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/postactions-element-office-development-in-visual-studio.md).  

### <a name="application"></a>uygulama  
 Gerekli. `application` Öğesi açıklanan [ &#60;uygulama&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/application-element-office-development-in-visual-studio.md).  

## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  

### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `addin` kullanılarak dağıtılan bir belge düzeyi Office çözümü öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  

### <a name="code"></a>Kod  

```  
<vstav3:addIn   
  xmlns:vstav3="urn:schemas-microsoft-com:vsta.v3">  
  <vstav3:entryPointsCollection>  
    <vstav3:entryPoints>  
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
    </vstav3:entryPoints>  
  </vstav3:entryPointsCollection>  
  <vstav3:update   
    enabled="true">  
    <vstav3:expiration   
      maximumAge="7"   
      unit="days" />  
  </vstav3:update>  
  <vstav3:application>  
    <vstov4:customizations   
      xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
      <vstov4:customization>  
        <vstov4:document   
          solutionId="73e" />  
      </vstov4:customization>  
    </vstov4:customizations>  
  </vstav3:application>  
</vstav3:addIn>  
```  

## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  

### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `addin` kullanılarak dağıtılan uygulama düzeyi Office çözümünü öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  

### <a name="code"></a>Kod  

```  
<vstav3:addIn   
  xmlns:vstav3="urn:schemas-microsoft-com:vsta.v3">  
  <vstav3:entryPointsCollection>  
    <vstav3:entryPoints>  
      <vstav3:entryPoint   
        class="ContosoOutlookAddIn.ThisAddIn">  
        <assemblyIdentity   
          name="ContosoOutlookAddIn"   
          version="1.0.0.0"   
          language="neutral"   
          processorArchitecture="msil" />  
      </vstav3:entryPoint>  
    </vstav3:entryPoints>  
  </vstav3:entryPointsCollection>  
  <vstav3:update   
    enabled="true">  
    <vstav3:expiration   
      maximumAge="7"   
      unit="days" />  
  </vstav3:update>  
  <vstav3:application>  
    <vstov4:customizations   
      xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
      <vstov4:customization>  
        <vstov4:appAddIn   
          application="Outlook"   
          loadBehavior="3"   
          keyName="ContosoOutlookAddIn">  
          <vstov4:friendlyName>  
            ContosoOutlookAddIn  
          </vstov4:friendlyName>  
          <vstov4:description>  
            ContosoOutlookAddIn - Outlook VSTO Add-in   
            created with Visual Studio Tools for Office  
          </vstov4:description>  
          <vstov4:formRegions>  
            <vstov4:formRegion  
                name="OutlookAddIn1.FormRegion1">  
              <vstov4:messageClass name="IPM.Note" />  
              <vstov4:messageClass name="IPM.Contact" />  
              <vstov4:messageClass name="IPM.Appointment" />  
            </vstov4:formRegion>  
          </vstov4:formRegions>  
        </vstov4:appAddIn>  
      </vstov4:customization>  
    </vstov4:customizations>  
  </vstav3:application>  
</vstav3:addIn>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
