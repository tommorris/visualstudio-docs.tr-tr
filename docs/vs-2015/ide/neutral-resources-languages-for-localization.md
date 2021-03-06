---
title: Yerelleştirme için bağımsız kaynak dilleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a9470718743e506a7a8cd5ad03d9b6f69b1d5477
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631858"
---
# <a name="neutral-resources-languages-for-localization"></a>Yerelleştirme İçin Bağımsız Kaynak Dilleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:System.Resources.NeutralResourcesLanguageAttribute> Sınıfı ana derlemede bulunan kaynakların kültürü belirtir. Bu öznitelik bir performans geliştirmesi kullanılır. böylece <xref:System.Resources.ResourceManager> nesne ana derlemede bulunan kaynaklar için arama yapmaz.  
  
 Aşağıdaki kod bağımsız kaynaklar dilinin nasıl ayarlanacağını gösterir. Kod, derleme betiğindeki veya AssemblyInfo.vb veya AssemblyInfo.cs dosyasında yerleştirilebilir.  
  
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

