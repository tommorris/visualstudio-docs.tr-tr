---
title: T4 Derleme yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 9f586931bd14089beca787c24d92bc2605c4d5de
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="t4-assembly-directive"></a>T4 Derleme Yönergesi
İçinde bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tasarım zamanı metin şablonu `assembly` yönergesi şablon kodunuzu türlerinden kullanabilmesi için bir derleme yükler. Geçerli bir derleme başvurusu ekleme ile benzer bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi.  
  
 Metin şablonları yazma genel bir bakış için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).  
  
> [!NOTE]
>  İhtiyacınız olmayan `assembly` bir çalışma zamanı (önceden işlenmiş) metin şablonu yönerge. Bunun yerine, gerekli derlemeler ekleme **başvuruları** biri, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi.  
  
## <a name="using-the-assembly-directive"></a>Derleme Yönergesini Kullanma  
 Yönergenin sözdizimi aşağıdaki gibidir:  
  
```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 Derleme adı aşağıdakilerden biri olmalıdır:  
  
-   GAC içinde bir derleme tanımlayıcı adı gibi `System.Xml.dll`. Uzun formu gibi kullanabilir `name="System.Xml, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"`. Daha fazla bilgi için bkz. <xref:System.Reflection.AssemblyName>.  
  
-   Derlemenin mutlak yolu  
  
 Kullanabileceğiniz `$(variableName)` başvurmak için sözdizimi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gibi değişkenleri `$(SolutionDir)`, ve `%VariableName%` başvuru ortam değişkenlerine. Örneğin:  
  
```  
<#@ assembly name="$(SolutionDir)\MyProject\bin\Debug\SomeLibrary.Dll" #>  
```  
  
 Derleme yönergesinin önceden işlenmiş metin şablonu üzerinde etkisi yoktur. Bunun yerine, gerekli başvurularında dahil **başvuruları** bölümü, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="standard-assemblies"></a>Standart Derlemeler  
 Aşağıdaki derlemeler otomatik olarak yüklenir, böylece onlar için derleme yönergelerini yazmanıza gerek yoktur:  
  
-   `Microsoft.VisualStudio.TextTemplating.1*.dll`  
  
-   `System.dll`  
  
-   `WindowsBase.dll`  
  
 Özel bir yönerge kullanırsanız, yönerge işlemcisi ek derlemeler yükleyebilir. Örneğin, etki alanına özgü dil (DSL) için şablonlar yazarsanız, aşağıdaki derlemeler için derleme yönergeleri yazmak gerekmez:  
  
-   `Microsoft.VisualStudio.Modeling.Sdk.1*.dll`  
  
-   `Microsoft.VisualStudio.Modeling.Sdk.Diagrams.1*.dsl`  
  
-   `Microsoft.VisualStudio.TextTemplating.Modeling.1*.dll`  
  
-   DSL'nizi içeren derleme.  
  
##  <a name="msbuild"></a> MSBuild ve Visual Studio Proje özelliklerini kullanma  
 Visual Studio makrosu $(SolutionDir) gibi Msbuild'de çalışmıyor. Şablonları yapı makinenizde dönüştürmek isterseniz, bunun yerine proje özelliklerini kullanmanız gerekir.  
  
 Proje özelliği tanımlamak için .csproj veya .vbproj dosyanızı düzenleyin. Bu örnek adlı bir özelliğini tanımlar `myLibFolder`:  
  
```xml  
<!-- Define a project property, myLibFolder: -->  
<PropertyGroup>  
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>  
</PropertyGroup>  
  
<!-- Tell the MSBuild T4 task to make the property available: -->  
<ItemGroup>  
    <T4ParameterValues Include="myLibFolder">  
      <Value>$(myLibFolder)</Value>  
    </T4ParameterValues>  
  </ItemGroup>  
  
```  
  
 Artık proje özelliğinizi metin şablonlarında kullanabilirsiniz, böylece hem Visual Studio hem de MSBuild içinde doğru dönüştürme yapılır:  
  
```  
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [T4 Include Yönergesi](../modeling/t4-include-directive.md)