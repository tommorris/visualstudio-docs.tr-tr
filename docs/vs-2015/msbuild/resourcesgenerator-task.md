---
title: ResourcesGenerator görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63ee00754683156dad2bd34a93ff43f820eb37c7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628182"
---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ResourcesGenerator görevi](https://docs.microsoft.com/visualstudio/msbuild/resourcesgenerator-task).  
  
  
<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> Görev bir veya daha fazla kaynak katıştırır (.jpg, .ico, .bmp, [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] ikili biçimi ve diğer uzantı türleri) bir .resources dosyasına.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`OutputPath`|Gerekli **dize** parametresi.<br /><br /> Çıktı dizini yolunu belirtir. Yol mutlak bir yol değil ise kök proje dizinine göreli bir yol olarak kabul edilir.|  
|`OutputResourcesFile`|Gerekli **Itaskıtem []** çıkış parametresi.<br /><br /> Oluşturulan .resources dosyasının adını ve yolunu belirtir. Yol mutlak bir yol değil, .resources dosyasının kök proje dizinine göreli oluşturulur.|  
|`ResourcesFiles`|Gerekli **Itaskıtem []** parametresi.<br /><br /> Oluşturulan bir .resources dosyasına eklemek için bir veya daha fazla kaynak belirtir.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tek .bmp kaynağı olan bir .resources dosyası oluşturur. Proje kök dizinine göreli bir dizine .bmp kaynak oluşturulur.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF MSBuild başvurusu](../msbuild/wpf-msbuild-reference.md)   
 [Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [WPF uygulaması (WPF) oluşturma](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)



