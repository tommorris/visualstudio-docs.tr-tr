---
title: T4 Çıkış yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03a14993-47ad-4f2e-8032-57db28d5842a
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e0eaa2d8e3fc257e14e04bad3cac706b8a3bc92a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693832"
---
# <a name="t4-output-directive"></a>T4 Çıkış Yönergesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [T4 çıkış yönergesi](https://docs.microsoft.com/visualstudio/modeling/t4-output-directive).  
  
İçinde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] metin şablonlarını `output` yönergesi, dosya adı uzantısı ve dönüştürülen dosyanın kodlamasını tanımlamak için kullanılır.  
  
 Örneğin, varsa, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] proje adlı şablon dosyası içerir **MyTemplate.tt** aşağıdaki yönerge içerir:  
  
 `<#@output extension=".cs"#>`  
  
 ardından [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] adlı bir dosya oluşturur **MyTemplate.cs**  
  
 `output` Çalışma zamanı (önceden işlenmiş) metin şablonunda yönergesi gerekli değildir. Bunun yerine, çağırarak uygulamanızı oluşturulan dizesi edinir `TextTransform()`. Daha fazla bilgi için [T4 metin şablonları ile çalışma süresi metni oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="using-the-output-directive"></a>Çıkış yönergesini kullanma  
  
```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 Olmalıdır en fazla bir `output` her metin şablonunda yönergesi.  
  
## <a name="extension-attribute"></a>Uzantı özniteliğine  
 Oluşturulan metin çıktı dosyasının dosya adı uzantısını belirtir.  
  
 Varsayılan değer **.cs**  
  
 Örnekler:  
 `<#@ output extension=".txt" #>`  
  
 `<#@ output extension=".htm" #>`  
  
 `<#@ output extension=".cs" #>`  
  
 `<#@ output extension=".vb" #>`  
  
 Kabul edilebilir değerler:  
 Tüm geçerli dosya adı uzantısı.  
  
## <a name="encoding-attribute"></a>kodlama özniteliği  
 Çıkış dosyası oluşturulurken kullanılacak kodlamayı belirtir. Örneğin:  
  
 `<#@ output encoding="utf-8"#>`  
  
 Metin şablonu dosyası tarafından kullanılan kodlama varsayılan değerdir.  
  
 Kabul edilebilir değerler:  
 `us-ascii`  
  
 `utf-16BE`  
  
 `utf-16`  
  
 `utf-8`  
  
 `utf-7`  
  
 `utf-32`  
  
 `0` (Sistem varsayılanı)  
  
 Genel olarak, Web adı dizesi veya herhangi biri tarafından döndürülen kodlamalarının kod sayfası numarası kullanabilirsiniz <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=fullName>.



