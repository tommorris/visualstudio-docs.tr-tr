---
title: UidManager görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e30a18cba63c121d86666bf86180d7fae20a0b3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="uidmanager-task"></a>UidManager Görevi
<xref:Microsoft.Build.Tasks.Windows.UidManager> Görev denetler, güncelleştirir veya tüm yerelleştirme için benzersiz tanımlayıcıları (Uıd'leri) kaldırır [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] kaynağında bulunan öğeleri [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`IntermediateDirectory`|İsteğe bağlı **dize** parametresi.<br /><br /> Kaynağı için kullanılan dizini belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] tarafından belirtilen dosyaları **MarkupFiles** parametresi.|  
|`MarkupFiles`|Gerekli **ITaskItem []** parametresi.<br /><br /> Kaynak belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] için denetleme, güncelleştirme veya kaldırma UID eklenecek dosyaları.|  
|`Task`|Gerekli **dize** parametresi.<br /><br /> Gerçekleştirmek istediğiniz UID yönetim görevini belirtir. Geçerli seçenekler şunlardır: **denetleyin**, **güncelleştirme**, veya **kaldırmak**.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır <xref:Microsoft.Build.Tasks.Windows.UidManager> denetlemek için görev belirtilen kaynak [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları içeren [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] uygun Uıd'leri olan öğeler.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UidManagerTask">  
    <UidManager  
      Task="Check"  
      MarkupFiles="Page1.xaml;Page2.xaml"  
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF MSBuild başvurusu](../msbuild/wpf-msbuild-reference.md)   
 [Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [Nasıl yapılır: bir uygulama yerelleştirme](/dotnet/framework/wpf/advanced/how-to-localize-an-application)