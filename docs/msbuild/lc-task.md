---
title: "LC görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#LC
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, LC task
- LC task [MSBuild]
ms.assetid: d5a53472-6f2a-42b8-a6db-593ca99c9790
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bf308bb5693363406bb954cdb63ab5fd25772cb9
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="lc-task"></a>LC Görevi
.Licx dosyasından bir .license dosyası oluşturur LC.exe sarmalar. LC.exe hakkında daha fazla bilgi için bkz: [Lc.exe (lisans derleyici)](/dotnet/framework/tools/lc-exe-license-compiler).  
  
## <a name="parameters"></a>Parametreler  
 Parametre için aşağıdaki tabloda açıklanmaktadır `LC` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`LicenseTarget`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> .Licenses dosyaları oluşturulan yürütülebilir dosya belirtir.|  
|`NoLogo`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Microsoft başlangıç başlığı görüntüsünü bastırır.|  
|`OutputDirectory`|İsteğe bağlı `String` parametresi.<br /><br /> Çıkış .licenses dosyalarının yerleştirileceği dizini belirtir.|  
|`OutputLicense`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> .Licenses dosyası adını belirtir. Bir ad belirtmezseniz, kullanılan .licx dosyası adı ve .licenses dosyası .licx dosyası içeren dizinde yerleştirilir.|  
|`ReferencedAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> .License dosyası oluşturulurken yüklemek için başvurulan bileşenlerini belirtir.|  
|`SdkToolsPath`|İsteğe bağlı `String` parametresi.<br /><br /> Resgen.exe gibi SDK Araçları yolunu belirtir.|  
|`Sources`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> .licenses dosyası dahil etmek için lisanslı bileşenleri içeren öğeleri belirtir. Daha fazla bilgi için belgelerine bakın `/complist` anahtarının [Lc.exe (lisans derleyici)](/dotnet/framework/tools/lc-exe-license-compiler).|  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.ToolTask> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `LC` lisansları derlemek için görev.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
<!-- Item declarations, etc -->  
  
    <Target Name="CompileLicenses">  
        <LC  
            Sources="@(LicxFile)"  
            LicenseTarget="$(TargetFileName)"  
            OutputDirectory="$(IntermediateOutputPath)"  
            OutputLicenses="$(IntermediateOutputPath)$(TargetFileName).licenses"  
            ReferencedAssemblies="@(ReferencePath);@(ReferenceDependencyPaths)">  
  
            <Output  
                TaskParameter="OutputLicenses"  
                ItemName="CompiledLicenseFile"/>  
        </LC>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)