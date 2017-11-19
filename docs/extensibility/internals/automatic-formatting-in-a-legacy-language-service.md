---
title: "Eski dil hizmetinde otomatik biçimlendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f09ab8a948011cdc53516ec21f0d213852166956
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Otomatik bir eski dil hizmetinde biçimlendirme
Bir kullanıcı bir bilinen kod yapı türüne başladığında otomatik biçimlendirme dil hizmeti otomatik olarak bir kod parçacığını ekler.  
  
## <a name="automatic-formatting-behavior"></a>Otomatik biçimlendirme davranışı  
 Örneğin, yazarken `if`, eşleşen küme parantezleri dil hizmeti otomatik olarak ekler veya ENTER tuşuna basın, dil hizmeti ekleme noktasını yeni satırda için kullanılıp bağlı olarak uygun girinti düzeyini zorlar önceki satırı yeni bir kapsam açılır.  
  
 Dil hizmeti geri kalanı için kullanılan komut filtresi, otomatik biçimlendirme için de kullanılabilir. Eşleşen küme parantezleri çağırarak de baloncuklarını vurgulayabilir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti geliştirme](../../extensibility/internals/developing-a-legacy-language-service.md)