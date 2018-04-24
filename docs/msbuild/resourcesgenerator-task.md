---
title: ResourcesGenerator görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5ea13b4d097792baf2da46745be2f64a565fdf2e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator Görevi
<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> Görev katıştırır bir veya daha fazla kaynak (.jpg, .ico, .bmp, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi ve diğer uzantı türleri) .resources dosyasına.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`OutputPath`|Gerekli **dize** parametresi.<br /><br /> Çıktı dizini yolunu belirtir. Yolu mutlak bir yol değil, kök proje dizininde göreli bir yol olarak kabul edilir.|  
|`OutputResourcesFile`|Gerekli **ITaskItem []** çıkış parametresi.<br /><br /> Oluşturulan .resources dosyasının adını ve yolunu belirtir. Yolu mutlak bir yol değil ise .resources dosyası kök proje dizininde göre oluşturulur.|  
|`ResourcesFiles`|Gerekli **ITaskItem []** parametresi.<br /><br /> Oluşturulan .resources dosyasında katıştırmak için bir veya daha fazla kaynak belirtir.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir tek .bmp kaynakla .resources dosyası oluşturur. .Bmp kaynak için göreli proje kök dizini bir dizin oluşturulur.  
  
```xml  
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
 [WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)