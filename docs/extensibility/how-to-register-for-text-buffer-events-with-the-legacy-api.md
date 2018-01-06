---
title: "Nasıl yapılır: metin arabelleği olayları eski API ile kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 94f2e781c316f3891fdef0c324d54fa2f9742222
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-for-text-buffer-events-with-the-legacy-api"></a>Nasıl yapılır: metin arabelleği olayları eski API ile kaydetme
Eski API kullanarak metin arabelleği erişiyorsanız, aşağıdaki yordamda gösterildiği gibi metin arabelleği olayları için kaydetmelisiniz.  
  
### <a name="to-advise-text-buffer-events"></a>Metin arabelleği olaylarını bildirmek için  
  
1.  Arabirimlerde biri için bir işaretçi gelen <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>, çağrı `QueryInterface` gösteren bir işaretçi için <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A> yöntemi ve kaydetmek istediğiniz olayların arabirimi Kimliğini geçirin.  
  
     Kaydetmek istiyorsanız, örneğin, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>, daha sonra bir arabirim kimliği, IID_IVsTextLinesEvents geçirin.  
  
     Bir işaretçi metin arabelleğini döndürür <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> uygun bir bağlantı noktası nesnesi için arabirim.  
  
3.  Bu işaretçinin kullanarak, çağrı <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A> istediğiniz kaydetmek, örneğin, olayları arabirimi uygulamanız için bir işaretçi geçirerek yöntemini `IVsTextLinesEvents` arabirimi.  
  
     Ortam çağırarak olaylarını dinleyecek şekilde sonra kullanabileceğiniz bir tanımlama bilgisi döndürür <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A> yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski API metin arabelleği olayları](../extensibility/text-buffer-events-in-the-legacy-api.md)