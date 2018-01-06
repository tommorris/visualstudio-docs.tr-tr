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
ms.workload: vssdk
ms.openlocfilehash: 43d9c59beaddfc6992e7b9e16e0e778be2a6d30f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Otomatik bir eski dil hizmetinde biçimlendirme
Bir kullanıcı bir bilinen kod yapı türüne başladığında otomatik biçimlendirme dil hizmeti otomatik olarak bir kod parçacığını ekler.  
  
## <a name="automatic-formatting-behavior"></a>Otomatik biçimlendirme davranışı  
 Örneğin, yazarken `if`, eşleşen küme parantezleri dil hizmeti otomatik olarak ekler veya ENTER tuşuna basın, dil hizmeti ekleme noktasını yeni satırda için kullanılıp bağlı olarak uygun girinti düzeyini zorlar önceki satırı yeni bir kapsam açılır.  
  
 Dil hizmeti geri kalanı için kullanılan komut filtresi, otomatik biçimlendirme için de kullanılabilir. Eşleşen küme parantezleri çağırarak de baloncuklarını vurgulayabilir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski Dil Hizmeti Geliştirme](../../extensibility/internals/developing-a-legacy-language-service.md)