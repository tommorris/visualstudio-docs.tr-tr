---
title: Yerelleştirme için bağımsız kaynak dilleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
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
ms.openlocfilehash: 0bbddac532d242ce42330c955a797603b2d7e4a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Resources.ResourceManager>   
 [.NET Framework tabanlı Uluslararası uygulamalara giriş](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [Yerelleştirme için kaynakların hiyerarşik organizasyonu](../ide/hierarchical-organization-of-resources-for-localization.md)   
 [Uygulamaları yerelleştirme](../ide/localizing-applications.md)   
 [Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)