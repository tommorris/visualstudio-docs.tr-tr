---
title: 'Nasıl yapılır: yangın Düzenleyicisi odağı kaybettiğinde olayları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbdcf30443bc548fd8d182db301cbc7119d8ceae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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