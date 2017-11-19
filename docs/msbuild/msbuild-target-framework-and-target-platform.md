---
title: "MSBuild hedef çerçevesi ve hedef platformu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df6517c5-edd6-4cc4-97ad-b3cdfc78e799
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: cdfbe126e8a647cda4c8e29e50591a1aa229df80
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-target-framework-and-target-platform"></a>MSBuild Hedef Çerçevesi ve Hedef Platformu
Bir proje üzerinde çalışmak için yerleşik bir *hedef framework*, belirli bir .NET Framework sürümü olduğu ve *hedef platformu*, belirli yazılım mimarisi olduğu.  Örneğin, bir uygulamayı .NET Framework 2.0 802 x 86 işlemci ailesi ("x86") ile uyumlu bir 32 bit platformda çalışacak şekilde hedefleyebilirsiniz. Hedef Çerçeve ve hedef platformu bileşimi olarak bilinen *hedef bağlamı*.  
  
## <a name="target-framework-and-profile"></a>Hedef Framework ve profil  
 Bir hedef framework belirli sürümüdür [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] projeniz üzerinde çalışmak üzere yapılandırıldığı. Derleyici özellikleri ve framework'ün bu sürüme özel derleme başvurularını sağladığından hedef çerçevesi belirtimi gereklidir.  
  
 Şu anda, .NET Framework'ün aşağıdaki sürümler kullanılabilir:  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] (Visual Studio 2005'te yer alan) 2.0  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 3.0 (dahil [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)])  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 3.5 (dahil [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)])  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4 (Visual Studio 2010'da dahil)  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.5 (dahil [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)])  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.5.1 (dahil [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)])  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.5.2  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.6 (dahil [!INCLUDE[vs_dev14](../misc/includes/vs_dev14_md.md)])  
  
 .NET Framework sürümleri her başvurmak kullanılabilir hale derlemeler listesinde birbirinden farklı. Örneğin, Windows Presentation Foundation (WPF) uygulamaları projeniz .NET Framework sürüm 3.0 hedefliyor sürece veya üstü oluşturamaz.  
  
 Hedef Framework'ü belirtilen `TargetFrameworkVersion` proje dosyası bir özellik. Visual Studio tümleşik geliştirme ortamı (IDE) proje özellik sayfalarını kullanarak bir proje hedef çerçevesi değiştirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md). Kullanılabilir değerler için `TargetFrameworkVersion` olan `v2.0`, `v3.0`, `v3.5`, `v4.0`, `v4.5`, `v4.5.1`, `v4.5.2`, ve `v4.6`.  
  
```xml  
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>  
```  
  
 A *hedef profil* bir hedef Framework'ü bir alt kümesidir. Örneğin, .NET Framework 4 istemci profili MSBuild derlemelerine başvurular içermez.  
  
 Hedef profil belirtilen `TargetFrameworkProfile` bir proje dosyası bir özellik. Hedef profil hedef framework denetim IDE içinde proje özellik sayfalarını kullanarak değiştirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
```xml  
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>  
<TargetFrameworkProfile>Client</TargetFrameworkProfile>  
```  
  
## <a name="target-platform"></a>Hedef platformu  
 A *platform* donanım ve belirli çalışma zamanı ortamı tanımlar yazılım birleşimidir. Örneğin,  
  
-   `x86`bir Intel 80 x 86 işlemci veya eşdeğer üzerinde çalışan 32 bit Windows işletim sistemi belirler.  
  
-   `Xbox`Microsoft Xbox 360 platform belirler.  
  
 A *hedef platformu* projenizi çalıştırmak için yerleşik belirli platformudur. Hedef platform belirtilen `Platform` proje dosyasında özellik oluşturun. Proje özellik sayfalarını kullanarak hedef platformu değiştirebilir veya **Configuration Manager** IDE içinde.  
  
```xml  
<PropertyGroup>  
   <Platform>x86</Platform>  
</PropertyGroup>  
  
```  
  
 A *hedef Yapılandırması* hedef platformu alt kümesidir. Örneğin, `x86``Debug` yapılandırma çoğu kod iyileştirmeler içermez. Hedef yapılandırmasında belirtilen `Configuration` proje dosyasında özellik oluşturun. Proje özellik sayfalarını kullanarak hedef yapılandırmasını değiştirebilirsiniz veya **Configuration Manager**.  
  
```xml  
<PropertyGroup>  
   <Platform>x86</Platform>  
   <Configuration>Debug</Configuration>  
<PropertyGroup>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md)