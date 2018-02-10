---
title: "MSBuild. Hedefler dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 02/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- .Targets files
- MSBuild, .Targets files
ms.assetid: f6d98eb4-d2fa-49b7-8e3c-bae1ca3cf596
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bacd57684350553c0ad44f6e25578299894c264c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-targets-files"></a>MSBuild .Targets Dosyaları
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] öğeleri, özellikler, hedefleri ve görevleri ortak senaryolar için içeren birkaç .targets dosyaları içerir. Bu dosyalar çoğu otomatik olarak içeri aktarılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje Bakım ve okunabilirliği kolaylaştırmak için dosyaları.  

 Projeleri genellikle kendi derleme işlemi tanımlamak için bir veya daha fazla .targets dosyaları içeri aktarın. Örneğin bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] tarafından oluşturulan proje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Microsoft.Common.targets içe aktaran Microsoft.CSharp.targets içeri aktaracak. [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Proje kendisini tanımlayın özgü özellikleri ve öğeleri bu projeye, ancak standart yapı için kuralları bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] proje içe aktarılan .targets dosyaları tanımlanır.  

 `$(MSBuildToolsPath)` Değeri bu ortak .targets dosyaları yolunu belirtir. Varsa `ToolsVersion` 4.0, dosyaları şu konumda:`WindowsInstallationPath\Microsoft.NET\Framework\v4.0.30319\`  

> [!NOTE]
>  Kendi hedefleri oluşturma hakkında daha fazla bilgi için bkz: [hedefleri](../msbuild/msbuild-targets.md). Nasıl kullanılacağı hakkında bilgi için `Import` öğesi bir proje dosyası başka bir proje dosyasına eklemek için bkz: [içeri aktarma öğesi (MSBuild)](../msbuild/import-element-msbuild.md) ve [nasıl yapılır: birden çok proje dosyasında aynı hedefi kullanma](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md).  

## <a name="common-targets-files"></a>Ortak. Hedef dosyaları  

|. Hedef dosya|Açıklama|  
|-------------------|-----------------|  
|Microsoft.Common.targets|İçin standart derleme işlemindeki adımları tanımlayan [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ve [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projeleri.<br /><br /> Aşağıdaki deyim içeren Microsoft.CSharp.targets ve Microsoft.VisualBasic.targets'daki dosyaları tarafından alınan:`<Import Project="Microsoft.Common.targets" />`|  
|Microsoft.CSharp.targets|Visual C# projeleri için standart derleme işlemindeki adımları tanımlar.<br /><br /> Aşağıdaki deyim içeren Visual C# proje dosyalarını tarafından (.csproj), alınan:`<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`|  
|Microsoft.VisualBasic.targets|Visual Basic projeleri için standart derleme işlemindeki adımları tanımlar.<br /><br /> Aşağıdaki deyim içeren Visual Basic proje dosyalarını tarafından (.vbproj), alınan:`<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`|

## <a name="directorybuildtargets"></a>Directory.Build.targets
Directory.Build.targets projeler bir dizini altında özelleştirmeleri sağlayan bir kullanıcı tarafından tanımlanan bir dosyadır. Bu dosya sürece Microsoft.Common.targets otomatik olarak içeri aktarılır özelliği **ImportDirectoryBuildTargets** ayarlanır **false**.

## <a name="see-also"></a>Ayrıca Bkz.  
 [İçeri aktarma öğesi (MSBuild)](../msbuild/import-element-msbuild.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)  
 [MSBuild](../msbuild/msbuild.md)
