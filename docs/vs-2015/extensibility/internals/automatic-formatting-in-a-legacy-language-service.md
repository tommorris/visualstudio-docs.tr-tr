---
title: Eski dil hizmetinde otomatik biçimlendirme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 46e5f30d01a3063a3683aa3cae4ae1da3e0aa141
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692228"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Eski Dil Hizmetinde Otomatik Biçimlendirme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [eski dil hizmetinde otomatik biçimlendirme](https://docs.microsoft.com/visualstudio/extensibility/internals/automatic-formatting-in-a-legacy-language-service).  
  
Bir kullanıcı bir bilinen kod yapısı türüne başladığında otomatik biçimlendirme bir dil hizmeti otomatik olarak bir kod parçacığı ekler.  
  
## <a name="automatic-formatting-behavior"></a>Otomatik biçimlendirme davranışı  
 Örneğin, yazarken `if`dil hizmeti eşleşen küme ayraçlarını otomatik olarak ekler veya ENTER tuşuna basın, dil hizmeti noktasını yeni satırda uygun girinti düzeyine bağlı olarak zorlar önceki satırı yeni bir kapsam açılır.  
  
 Dil hizmeti geri kalanı için kullanılan komut filtresi, otomatik biçimlendirme için de kullanılabilir. Çağırarak eşleşen küme ayraçlarını vurgulayabilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski Dil Hizmeti Geliştirme](../../extensibility/internals/developing-a-legacy-language-service.md)

