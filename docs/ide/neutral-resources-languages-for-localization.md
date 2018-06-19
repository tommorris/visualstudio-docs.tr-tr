---
title: Yerelleştirme İçin Bağımsız Kaynak Dilleri
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 192b78df4f0d1f579fb9a08c913c84e5a1e2fc71
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31943299"
---
# <a name="neutral-resources-languages-for-localization"></a>Yerelleştirme İçin Bağımsız Kaynak Dilleri

<xref:System.Resources.NeutralResourcesLanguageAttribute> Sınıfı, ana derlemesinde bulunan kaynakların kültürünü belirtir. Bu öznitelik, bir performans geliştirmesi kullanılır böylece <xref:System.Resources.ResourceManager> nesne ana derlemesinde bulunan kaynaklar için arama yapma.

 Aşağıdaki kod Tarafsız kaynaklar dilinin nasıl ayarlanacağını gösterir. Kod derleme kod veya AssemblyInfo.vb ya da AssemblyInfo.cs dosyasında yerleştirilebilir.

```vb
' Set neutral resources language for assembly.
<Assembly: NeutralResourcesLanguageAttribute("en")>

```

```csharp
// Set neutral resources language for assembly.
[assembly: NeutralResourcesLanguageAttribute("en")]
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Resources.ResourceManager>
- [.NET Framework Tabanlı Uluslararası Uygulamalara Giriş](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)
- [Yerelleştirme için Kaynakların Hiyerarşik Organizasyonu](../ide/hierarchical-organization-of-resources-for-localization.md)
- [Uygulamaları Yerelleştirme](../ide/localizing-applications.md)
- [Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)