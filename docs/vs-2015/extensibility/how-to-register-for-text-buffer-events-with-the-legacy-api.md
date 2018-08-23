---
title: "Nasıl yapılır: metin arabelleği olayları eski API'si ile kaydolma | Microsoft Docs"
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
- editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b98c6a084e8d77b9c85d56da95ec9abdcd469192
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689300"
---
# <a name="how-to-register-for-text-buffer-events-with-the-legacy-api"></a>Nasıl yapılır: metin arabelleği olayları eski API'si ile kaydolma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: metin arabelleği olayları eski API'si ile kaydolma](https://docs.microsoft.com/visualstudio/extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api).  
  
Metin arabelleği eski API'si aracılığıyla erişiyorsanız aşağıdaki yordamda gösterildiği gibi metin arabelleği olayları kaydolmalıdır.  
  
### <a name="to-advise-text-buffer-events"></a>Metin arabelleği olayları bildirmek için  
  
1.  Arabirimlerde birine bir işaretçiden <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>, çağrı `QueryInterface` işaretçisi için <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A> yöntemi ve kaydetmek istediğiniz olayların arabirimi kimliği geçirin.  
  
     Örneğin, kaydolmak istiyorsanız <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>, ardından bir arabirim kimliği, IID_IVsTextLinesEvents geçirin.  
  
     Metin arabelleği için bir işaretçi döndürür <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> uygun bir bağlantı noktası nesne için arabirim.  
  
3.  Bu işaretçinin kullanarak, çağrı <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A> yöntemi, bir işaretçiyi istediğiniz kaydetmek örneğin olaylar arabirimi uygulamanıza geçirmeden `IVsTextLinesEvents` arabirimi.  
  
     Ardından çağırarak olayları dinleyecek şekilde kullanabileceğiniz bir tanımlama bilgisi ortam döndürür <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A> yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin arabelleği olayları eski API](../extensibility/text-buffer-events-in-the-legacy-api.md)

