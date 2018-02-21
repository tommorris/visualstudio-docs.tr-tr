---
title: "Özel belge özelliklerine genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], custom properties
- custom document properties
- document-level customizations [Office development in Visual Studio], custom properties
- Office documents [Office development in Visual Studio], custom properties
- _AssemblyLocation property
- _AssemblyName property
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 672eaf3ed82a80983b919a37b2aeff4c99621f43
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2018
---
# <a name="custom-document-properties-overview"></a>Özel Belge Özelliklerine Genel Bakış

Belge düzeyi projesi derlerken, Visual Studio projesindeki belgeye iki özel özellikleri ekler: \_AssemblyLocation ve \_AssemblyName. Bir belgeyi bir kullanıcı oturum açtığında, Microsoft Office uygulama için bu özel belge özellikleri denetler. Belgede varsa, uygulamayı yükleyen [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], özelleştirme başlatır. Daha fazla bilgi için bkz: [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md).

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="assemblyname"></a>\_AssemblyName

Bu özellik, bir arabirim Office çözüm yükleyici bileşenindeki CLSID içerir [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. 4E3C66D5 - 58 D 4-491E-A7D4-64AF99AF6E8B CLSID değerdir. Hiçbir zaman bu değeri değiştirmeniz gerekir.

## <a name="assemblylocation"></a>\_AssemblyLocation

Bu özellik özelleştirme için dağıtım bildirimi hakkında ayrıntılar sağlayan bir dize içeriyor. Bildirimleri hakkında daha fazla bilgi için bkz: [uygulama ve dağıtım bildirimlerini Office çözümlerinde](../vsto/application-and-deployment-manifests-in-office-solutions.md).

 The_AssemblyLocation özellik değeri çözümün nasıl dağıtıldığına bağlı olarak farklı biçimlerde olabilir:

- Çözüm, bir Web sitesi, UNC yolu ya da bir CD veya USB sürücü yüklenecek yayımladıysanız _AssemblyLocation özelliği biçimdedir *DeploymentManifestPath*|*SolutionID*. Aşağıdaki dize örneği şöyledir:

     File://deployserver/MyShare/ExcelWorkbook1.vsto | 74744e4b-e4d6-41eb-84f7-ad20346fe2d9

- Visual Studio'dan çözümü çalıştırıyorsanız veya, _AssemblyLocation özelliği biçimdedir *DeploymentManifestName*|*SolutionID*| vstolocal. Aşağıdaki dize örneği şöyledir:

     ExcelWorkbook1.vsto|74744e4b-e4d6-41eb-84f7-ad20346fe2d9 | vstolocal

 *SolutionID* GUID'dir, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] çözümü belirlemek için kullanır. *SolutionID* projeyi derlerken otomatik olarak oluşturulur. **Vstolocal** terim gösterir [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] derlemenin belgeyle aynı klasörden yüklenmesi.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)
[belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)
[Office çözümlerinde uygulama ve dağıtım bildirimleri ](../vsto/application-and-deployment-manifests-in-office-solutions.md) 
 [Nasıl yapılır: ClickOnce kullanarak Office çözümü yayımlama](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)
[nasıl yapılır: oluşturma ve özel belge özelliklerini değiştirme](../vsto/how-to-create-and-modify-custom-document-properties.md)
