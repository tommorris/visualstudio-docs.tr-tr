---
title: 'Nasıl yapılır: metin arabelleği olayları eski API ile kaydetme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b708507096e7035039e54af7505c8f5f939b5724
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127249"
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