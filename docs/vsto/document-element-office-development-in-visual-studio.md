---
title: "&lt;Belge&gt; öğesi (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
ms.assetid: b4525a0e-8a03-4881-a3e2-8cc019029071
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 48995b4a40d4e67b0c0e2e44d66545c4c90dd26b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;Belge&gt; öğesi (Visual Studio'da Office Geliştirme)
  `document` Öğesinin `vstov4` ad alanı için belge düzeyi özelleştirmeleri özelleştirme özgü bilgileri depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<document solutionId />  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 Yalnızca belge düzeyi özelleştirmeleri için gereklidir. `document` Öğesidir içinde `vstov4` ad alanı. `document` Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`solutionId`|Gerekli. Belge düzeyi çözümü benzersiz şekilde tanımlamak için Office çalışma zamanı için Visual Studio Araçları tarafından kullanılan GUID. Bu değer _AssemblyLocation özel belge özelliği olarak depolanır. Daha fazla bilgi için bkz: [özel belge özelliklerine genel bakış](../vsto/custom-document-properties-overview.md).|  
  
 `document`hiç alt öğe yok.  
  
## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği gösterilmektedir `document` kullanılarak dağıtılan bir belge düzeyi Office çözümü öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği sağlanan daha büyük bir örneğin parçasıdır [uygulama bildirimleri Office çözümleri için](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```  
<vstov4:document   
  solutionId="73e" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  