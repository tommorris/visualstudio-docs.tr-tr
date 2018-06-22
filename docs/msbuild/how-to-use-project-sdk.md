---
title: 'Nasıl yapılır: MSBuild proje SDK başvurusu | Microsoft Docs'
ms.custom: ''
ms.date: 01/25/2018
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, SDKs, SDK
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b4d5d404574c00332a63d4927de3198f096145c4
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302672"
---
# <a name="how-to-use-msbuild-project-sdks"></a>Nasıl yapılır: MSBuild proje SDK'ları kullanın

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 15.0 "proje SDK", kavramı sunulan özellikler ve içeri aktarılacak hedefleri gerektiren yazılım geliştirme setlerini kullanan basitleştirir.

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>
</Project>
```

Projenin değerlendirme sırasında [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] üst ve alt projenizin örtük içeri aktarmalar ekler:

```xml
<Project>
    <!-- Implicit top import -->
    <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />

    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>

    <!-- Implicit bottom import -->
    <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

## <a name="referencing-a-project-sdk"></a>Proje SDK başvurma

 Proje SDK başvurmak için üç yolu vardır

1. Kullanım `Sdk` özniteliği `<Project/>` öğe:

    ```xml
    <Project Sdk="My.Custom.Sdk">
        ...
    </Project>
    ```

    Üst ve alt yukarıda açıklanan şekilde projenin örtük alma eklenir.  Biçimi `Sdk` özniteliği `Name[/Version]` sürüm olduğu isteğe bağlıdır.  Örneğin, belirtebilirsiniz `My.Custom.Sdk/1.2.3`.

2. Üst düzey kullanmak `<Sdk/>` öğe:

    ```xml
    <Project>
        <Sdk Name="My.Custom.Sdk" Version="1.2.3" />
        ...
    </Project>
   ```

   Üst ve alt yukarıda açıklanan şekilde projenin örtük alma eklenir.  `Version` Özniteliği gerekli değildir.

3. Kullanım `<Import/>` projenize başka bir yerindeki öğe:

    ```xml
    <Project>
        <PropertyGroup>
            <MyProperty>Value</MyProperty>
        </PropertyGroup>
        <Import Project="Sdk.props" Sdk="My.Custom.Sdk" />
        ...
        <Import Project="Sdk.targets" Sdk="My.Custom.Sdk" />
    </Project>
   ```

   İçeri aktarmalar projenizde açıkça dahil sırasını üzerinde tam denetim sağlar.

   Kullanırken `<Import/>` öğesi, isteğe bağlı bir belirtebilirsiniz `Version` de özniteliği.  Örneğin, belirtebilirsiniz `<Import Project="Sdk.props" Sdk="My.Custom.Sdk" Version="1.2.3" />`.

## <a name="how-project-sdks-are-resolved"></a>Proje SDK'ları nasıl çözümleneceğini

İçeri aktarma değerlendirirken [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dinamik olarak SDK temel adı ve sürümünü belirtilen proje yolunu çözümler.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Ayrıca proje SDK'ları makinenizde bulun eklentileri olan kayıtlı SDK Çözümleyicileri listesine sahiptir.  Bu eklentilerin şunları içerir:

1. Yapılandırılmış paketinizi sorgular NuGet tabanlı bir çözümleyici kimliği ve belirttiğiniz SDK sürümü ile eşleşen NuGet paketlerini akışları.<br/>
   Bu Çözümleyici, yalnızca belirttiğiniz isteğe bağlı bir sürüm ve tüm özel Proje SDK kullanılabilir etkindir.  
2. .NET CLI ile yüklenen SDK'ları çözümler .NET CLI çözümleyici.<br/>
   Bu çözümleyici proje SDK'ları gibi konumlandırır `Microsoft.NET.Sdk` ve `Microsoft.NET.Sdk.Web` ürün parçası olan.
3. MSBuild ile yüklenen SDK'ları çözümler varsayılan çözümleyici.

SDK'sı NuGet tabanlı çözümleyici destekleyen bir sürümünü belirtme, [global.json](https://docs.microsoft.com/en-us/dotnet/core/tools/global-json) proje SDK sürümü tek bir yerde yerine her proje denetlemenize izin verir:

```json
{
    "msbuild-sdks": {
        "My.Custom.Sdk": "5.0.0",
        "My.Other.Sdk": "1.0.0-beta"
    }
}
```

Derleme sırasında her proje SDK yalnızca bir sürümü kullanılabilir.  İki farklı sürümü aynı proje SDK başvurduğunuzdan, MSBuild bir uyarı yayma.  İçin önerilen **değil** bir sürüm belirtilmişse projelerinizde bir sürüm belirtin, `global.json`.  

## <a name="see-also"></a>Ayrıca Bkz.

 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [Yapınızın özelleştirme](../msbuild/customize-your-build.md)   
 [Paketler, meta verileri ve çerçeveleri](/dotnet/core/packages)   
 [.NET Core csproj biçimine eklemeler](/dotnet/core/tools/csproj)
