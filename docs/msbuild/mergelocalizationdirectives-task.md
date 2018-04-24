---
title: MergeLocalizationDirectives görevi | Microsoft Docs
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
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9cb696aae19675a12aeb9aa6f2b76c8e6b710ea1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="mergelocalizationdirectives-task"></a>MergeLocalizationDirectives Görevi
<xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives> Görev birleştirir Yerelleştirme öznitelikleri ve bir veya daha fazla yorumlar [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] tüm derleme için tek bir dosya halinde ikili biçimi dosyaları.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`GeneratedLocalizationFiles`|Gerekli **ITaskItem []** parametresi.<br /><br /> Tek tek dosyalar için yerelleştirme yönergeleri dosyaların listesini belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi.|  
|`OutputFile`|Gerekli **dize** çıkış parametresi.<br /><br /> Derlenmiş yerelleştirme yönergeleri derleme çıktı yolunu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yerelleştirme öznitelikleri ve yorum ekleyebilirsiniz [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] içeriği. İle [!INCLUDE[TLA#tla_wpf](../msbuild/includes/tlasharptla_wpf_md.md)] yerelleştirme destek da Şerit Yerelleştirme öznitelikleri ve yorumlar ve oluşturulan derlemeden ayrı bir .loc dosya yerleştirin. Kullanarak bunu yapabilirsiniz **LocalizationPropertyStorage** özniteliği. Yerelleştirme öznitelikleri ve açıklamalar hakkında daha fazla bilgi ve **LocalizationPropertyStorage**, bkz: [Yerelleştirme öznitelikleri ve Yorumlar](/dotnet/framework/wpf/advanced/localization-attributes-and-comments).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek birkaç yerelleştirme açıklamalarını birleştirir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] tek .loc dosyasına ikili biçimi dosyaları.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MergeLocalizationDirectivesTask">  
    <MergeLocalizationDirectives   
      GeneratedLocalizationFiles="obj\debug\page1.loc;obj\debug\page2.loc;obj\debug\page3.loc"  
      OutputFile="obj\debug\WPFMSBuildSample.loc" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF MSBuild başvurusu](../msbuild/wpf-msbuild-reference.md)   
 [Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)