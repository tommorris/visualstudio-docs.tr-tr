---
title: "FileClassifier görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- classifying a resource set to embed in an assembly [WPF MSBuild]
- non-localizable resources [WPF MSBuild], classifying to embed in an assembly
- FileClassifier task [WPF MSBuild]
ms.assetid: 14e03310-fcc0-4bb2-a84d-cda12be66367
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4cf6f11246d3304a066d22f408fb715e4591582e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="fileclassifier-task"></a>FileClassifier Görevi
<xref:Microsoft.Build.Tasks.Windows.FileClassifier> Kaynak kaynaklar bütünleştirilmiş kod içine katıştırılır o olarak bir dizi görev sınıflandırır. Bir kaynak yerelleştirilebilir değilse, ana uygulama derlemeye katıştırılır; Aksi takdirde, uydu derlemeye katıştırılır.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`CLREmbeddedResource`|Kullanılmayan.|  
|`CLRResourceFiles`|Kullanılmayan.|  
|`CLRSatelliteEmbeddedResource`|Kullanılmayan.|  
|`Culture`|İsteğe bağlı **dize** parametresi.<br /><br /> Derleme için kültürü belirtir. Bu değer **null** yapı yerelleştirilemeyen ise. Varsa **null**, varsayılan değer küçük değer: **CultureInfo.InvariantCulture** döndürür.|  
|`MainEmbeddedFiles`|İsteğe bağlı **ITaskItem []** çıkış parametresi.<br /><br /> Ana derlemeye katıştırılmış yerelleştirilemeyen kaynaklar belirtir.|  
|`OutputType`|Gerekli **dize** parametresi.<br /><br /> Belirtilen kaynak dosyalarıyla katıştırmak için dosya türünü belirtir. Geçerli değerler **exe**, **winexe**, veya **Kitaplığı**.|  
|`SatelliteEmbeddedFiles`|İsteğe bağlı **ITaskItem []** çıkış parametresi.<br /><br /> Belirtilen kültür için uydu derlemesini katıştırılmış yerelleştirilebilir dosyaları belirtir **kültür** parametresi.|  
|`SourceFiles`|Gerekli **ITaskItem []** parametresi.<br /><br /> Sınıflandırmak için dosyaların listesini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa **kültür** parametresi ayarlanmadığında kullanılarak belirtilen tüm kaynakların **SourceFiles** parametresi yerelleştirilemeyen; ileilişkiliolduklarısüreceAksihalde,bunlaryerelleştirilebilir **Yerelleştirilebilir** ayarlamak için öznitelik **false**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tek bir kaynak dosyası bir kaynak olarak sınıflandırır ve French-Canadian (fr-CA) kültür için bir uydu derleme katıştırır.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask  
    TaskName="Microsoft.Build.Tasks.Windows.FileClassifier"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <ItemGroup>  
    <Resource Include="Resource1.bmp" />  
  </ItemGroup>  
  <Target Name="FileClassifierTask">  
    <FileClassifier  
      SourceFiles="Resource1.bmp"  
      Culture="fr-CA"  
      OutputType="exe" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF MSBuild başvurusu](../msbuild/wpf-msbuild-reference.md)   
 [Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)