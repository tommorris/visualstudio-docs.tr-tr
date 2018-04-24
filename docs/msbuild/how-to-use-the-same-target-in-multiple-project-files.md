---
title: 'Nasıl yapılır: birden çok proje dosyasında aynı hedefi kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, importing
- MSBuild, using the same target in multiple project files
ms.assetid: 163734bd-1bfd-4093-a730-7741fc21742d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 41c1ed02a32136d6c80e24f0644e0fab660e8ed0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-use-the-same-target-in-multiple-project-files"></a>Nasıl Yapılır: Birden Çok Proje Dosyasında Aynı Hedefi Kullanma
Birkaç yazmış varsa [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyalarını, bulunan, aynı görev ve hedeflerini farklı proje dosyalarında kullanmanız gerekebilir. Bu görevler veya hedefleri tam açıklamasını her proje dosyasında dahil olmak üzere yerine ayrı proje dosyasında bir hedef kaydedin ve sonra proje hedef kullanması gereken diğer projeyi alın.  
  
## <a name="using-the-import-element"></a>İçeri aktarma öğesi kullanma  
 `Import` Öğesi, bir proje dosyası başka bir proje dosyasına eklemek için kullanılır. İçeri aktarılmakta olan proje dosyası geçerli bir olmalıdır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası ve doğru biçimlendirilmiş XML içeriyor. `Project` Özniteliği alınan proje dosyası yolunu belirtir. Daha fazla bilgi için `Import` öğesi, bkz: [içeri aktarma öğesi (MSBuild)](../msbuild/import-element-msbuild.md).  
  
#### <a name="to-import-a-project"></a>Bir proje içeri aktarmak için  
  
1.  , İçeri aktarma proje dosyasında, tüm özellikler ve özellikleri için parametre olarak kullanılan öğeleri ve alınan proje öğelerinde tanımlayın.  
  
2.  Kullanım `Import` öğesi projeyi alın. Örneğin:  
  
     `<Import Project="MyCommon.targets"/>`  
  
3.  Aşağıdaki `Import` öğesi, tüm özellikler ve özelliklerinin varsayılan tanımları geçersiz kılmanız gerekir öğeleri ve öğeleri içe aktarılan projesinde tanımlayın.  
  
## <a name="order-of-evaluation"></a>Değerlendirme Sırası  
 Zaman [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] ulaştığında bir `Import` öğesi, alınan proje konumunu adresindeki alma projesine eklenen etkili bir şekilde `Import` öğesi. Bu nedenle, konumunu `Import` öğesi, özellikler ve öğeler değerlerini etkileyebilir. Özellikleri ve alınan proje ve özellikleri ve öğeleri tarafından alınan proje kullanan ayarlamak öğeleri anlamak önemlidir.  
  
 Proje oluşturduğunda, ilk olarak, öğeleri tarafından izlenen tüm özellikleri değerlendirilir. Örneğin, aşağıdaki XML alınan proje dosyası MyCommon.targets tanımlar:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Name>MyCommon</Name>  
    </PropertyGroup>  
  
    <Target Name="Go">  
        <Message Text="Name=$(Name)"/>  
    </Target>  
</Project>  
```  
  
 Aşağıdaki XML MyCommon.targets alır MyApp.proj tanımlar:  
  
```xml  
<Project  
    DefaultTargets="Go"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Name>MyApp</Name>  
    </PropertyGroup>  
    <Import Project="MyCommon.targets"/>  
</Project>  
```  
  
 Proje oluşturduğunda, aşağıdaki ileti görüntülenir:  
  
 `Name="MyCommon"`  
  
 Proje özelliği sonra alındığından `Name` MyApp.proj, tanımını tanımlanan `Name` içinde MyCommon.targets MyApp.proj tanımında geçersiz kılar. Proje adı tanımlı özellik önce içe aktarılırsa, yapı aşağıdaki iletisini görüntüler:  
  
 `Name="MyApp"`  
  
#### <a name="use-the-following-approach-when-importing-projects"></a>Projeleri içeri aktarırken aşağıdaki yaklaşımı kullanın  
  
1.  , Proje dosyası, tüm özellikler ve özellikleri için parametre olarak kullanılan öğeleri ve alınan proje öğelerinde tanımlayın.  
  
2.  Projeyi içeri aktarın.  
  
3.  Proje dosyasında tüm özelliklerini ve özelliklerinin varsayılan tanımları geçersiz kılmanız gerekir öğeleri ve alınan proje öğelerinde tanımlayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde ikinci kod örneği aktarır MyCommon.targets dosyasını gösterir. .Targets dosyasında yapı yapılandırmak için içeri aktarma proje özelliklerinden değerlendirir.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Flavor Condition="'$(Flavor)'==''">DEBUG</Flavor>  
        <Optimize Condition="'$(Flavor)'=='RETAIL'">yes</Optimize>  
        <appname>$(MSBuildProjectName)</appname>  
    <PropertyGroup>  
    <Target Name="Build">  
        <Csc Sources="hello.cs"  
            Optimize="$(Optimize)"  
            OutputAssembly="$(appname).exe"/>  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde MyCommon.targets dosyasını içe aktarır.  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <Flavor>RETAIL</Flavor>  
    </PropertyGroup>  
    <Import Project="MyCommon.targets"/>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçeri aktarma öğesi (MSBuild)](../msbuild/import-element-msbuild.md)   
 [Hedefler](../msbuild/msbuild-targets.md)