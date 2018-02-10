---
title: "ASP.NET uygulamaları derleneceği AspNetCompiler görevi kullanılarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#AspNetCompiler
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, AspNetCompiler task
- AspNetCompiler task [MSBuild]
ms.assetid: f811c019-a67b-4d54-82e6-e29549496f6e
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- aspnet
ms.openlocfilehash: b1528cd71c689876cd2c496e9cfdaaf0a97f0186
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="aspnetcompiler-task"></a>AspNetCompiler Görevi
`AspNetCompiler` Görev sarmalar aspnet_compiler.exe, bir yardımcı derleneceği [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulamalar.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `AspNetCompiler` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AllowPartiallyTrustedCallers`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Bu parametre ise `true`,, güçlü ad derlemeyi kısmen güvenilen arayanlara izin verir.|  
|`Clean`|İsteğe bağlı `Boolean` parametresi<br /><br /> Bu parametre ise `true`, uygulamanın temiz oluşturulacak. Önceden derlenmiş bileşenler derlenecek. Varsayılan değer `false` şeklindedir. Bu parametre karşılık gelen **- c** üzerinde aspnet_compiler.exe geçin.|  
|`Debug`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Bu parametre ise `true`, hata ayıklama bilgilerini (. PDB dosyası) derleme sırasında yayınlanır. Varsayılan değer `false` şeklindedir. Bu parametre karşılık gelen **-d** üzerinde aspnet_compiler.exe geçin.|  
|`DelaySign`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Bu parametre ise `true`, derleme tam olarak oluşturduğunuzda imzalı değil.|  
|`FixedNames`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Bu parametre ise `true`, derlenmiş derlemeleri sabit adlar verilir...|  
|`Force`|İsteğe bağlı `Boolean` parametresi<br /><br /> Bu parametre ise `true`, zaten var olması durumunda görev hedef dizin üzerine yazar. Varolan içerik kaybolur. Varsayılan değer `false` şeklindedir. Bu parametre karşılık gelen **-f** üzerinde aspnet_compiler.exe geçin.|  
|`KeyContainer`|İsteğe bağlı `String` parametresi.<br /><br /> Güçlü ad anahtar kapsayıcısı belirtir.|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Güçlü ad anahtar dosyası fiziksel yolunu belirtir..|  
|`MetabasePath`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulamanın tam IIS metatabanı yolu belirtir. Bu parametre birleştirilemez `VirtualPath` veya `PhysicalPath` parametreleri. Bu parametre karşılık gelen **-m** üzerinde aspnet_compiler.exe geçin.|  
|`PhysicalPath`|İsteğe bağlı `String` parametresi.<br /><br /> Derlenecek uygulamanın fiziksel yolu belirtir. Bu parametre eksikse, IIS metatabanı uygulamayı bulmak için kullanılır. Bu parametre karşılık gelen **-p** üzerinde aspnet_compiler.exe geçin.|  
|`TargetFrameworkMoniker`|İsteğe bağlı `String` parametresi.<br /><br /> Aspnet_compiler.exe hangi .NET Framework sürümünü kullanılması gerektiğini belirten TargetFrameworkMoniker belirtir. Yalnızca .NET Framework adlar kabul eder.|  
|`TargetPath`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama derlenmiş olan fiziksel yolu belirtir. Belirtilmezse, yerinde önceden derlenmiş uygulamasıdır.|  
|`Updateable`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Bu parametre ise `true`, önceden derlenmiş uygulama güncelleştirilebilir olacaktır.  Varsayılan değer `false` şeklindedir. Bu parametre karşılık gelen **-u** üzerinde aspnet_compiler.exe geçin.|  
|`VirtualPath`|İsteğe bağlı `String` parametresi.<br /><br /> Derlenecek uygulamanın sanal yolu. Varsa `PhysicalPath` belirtilen fiziksel yol uygulamayı bulmak için kullanılır. Aksi takdirde, IIS metatabanı kullanılır ve uygulamanın varsayılan sitede olduğu varsayılır. Bu parametre karşılık gelen **- v** üzerinde aspnet_compiler.exe geçin.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.ToolTask> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde `AspNetCompiler` derleneceği görev bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="PrecompileWeb">  
        <AspNetCompiler  
            VirtualPath="/MyWebSite"  
            PhysicalPath="c:\inetpub\wwwroot\MyWebSite\"  
            TargetPath="c:\precompiledweb\MyWebSite\"  
            Force="true"  
            Debug="true"  
        />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
