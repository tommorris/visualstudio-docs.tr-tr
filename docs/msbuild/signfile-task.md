---
title: "SignFile görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#SignFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, SignFile task
- SignFile task [MSBuild]
ms.assetid: edef1819-ddeb-4e09-95de-fc7063ba9388
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 020272e3bc90a70c780a614e834fc8b25be62ec4
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="signfile-task"></a>SignFile Görevi
Belirtilen sertifika kullanarak belirtilen dosyayı açar.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `SignFile` görev.  
  
 SHA-256 sertifikaları yalnızca .NET 4.5 sahip makinelerde izin verilen ve daha yüksek olduğunu unutmayın.  
  
> [!WARNING]
>  Visual Studio 2013 güncelleştirme 3'ten başlayarak, bu görev dosyası için hedef framework sürümü belirtmenize olanak sağlayan yeni bir imza içeriyor. MSBuild işlem SHA-256 kullandığından mümkün karmaları nerede olursa olsun yalnızca hedef çerçevesini .NET 4.5 olduğunda yeni imza kullanmak için kullanmaları ya da daha yüksek. Hedef çerçevesini .NET 4.0 veya aşağıda, SHA-256 karma kullanılmayacak.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`CertificateThumbprint`|Gerekli `String` parametresi.<br /><br /> İmzalama için kullanılacak sertifikayı belirtir. Bu sertifika, geçerli kullanıcının kişisel deposunda olması gerekir.|  
|`SigningTarget`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Sertifika ile imzalamak için dosyaları belirtir.|  
|`TimestampUrl`|İsteğe bağlı `String` parametresi.<br /><br /> Bir zaman sunucu URL'sini belirtir.|  
|`TargetFrameworkVersion`|Hedef için kullanılan .NET Framework sürümü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [görev taban sınıfı](../msbuild/task-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `SignFile` belirtilen dosyalarını imzalamak için görev `FilesToSign` tarafından belirtilen sertifika ile öğe koleksiyonu `Certificate` özelliği.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.exe" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.5" />  
    </Target>  
</Project>  
```  
  
> [!NOTE]
>  Sertifika parmak izi sertifika SHA-1 karmasıdır. Daha fazla bilgi için bkz: [güvenilen kök CA sertifika SHA-1 karması elde](http://msdn.microsoft.com/en-us/dd641990-9a88-4228-a245-017797131a87).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Exec` belirtilen dosyalarını imzalamak için görev `FilesToSign` tarafından belirtilen sertifika ile öğe koleksiyonu `Certificate` özelliği. Oluşturma işlemi sırasında Windows Installer dosyalarını imzalamak için bunu kullanabilirsiniz.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.msi" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <Exec Command="signtool.exe sign /f CertFile /p Password "@(FileToSign)" "/>  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.0" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)