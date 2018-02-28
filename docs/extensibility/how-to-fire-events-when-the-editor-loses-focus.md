---
title: "Nasıl yapılır: yangın Düzenleyicisi odağı kaybettiğinde olayları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bb20adf3950e87c37e2ca64bcd78913839f89d01
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>Nasıl yapılır: yangın Düzenleyicisi odağı kaybettiğinde olayları
Bazen bir düzenleyici pencere çerçevesi odağı kaybettiğinde öğrenmek gereklidir. Örneğin, Kod Düzenleyicisi artık üzerinde odaklanmıştır sonra bir kod penceresinden ayıklamak gerekebilir. Aşağıdaki yordam odağı kaybeden Düzenleyicisi bildirim almak için izlemeniz gereken adımları sağlar.  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>Olaya yanıt olarak odağı kaybeden bir düzenleyici tetiklenecek  
  
1.  İzleme seçimi olayları elde ederek bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> nesnesinin <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A> ve bunu sağlamak, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents> nesnesi.  
  
3.  Aramanız için de <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>, Ara `elementid==SEID_WindowFrame`.  
  
4.  Test `varValueNew` parametresi iki şey için:  
  
    1.  Aradığınız pencere çerçevesi.  
  
    2.  Hangi programınız Bu pencere çerçevesi seçimi kaybederse noktası.