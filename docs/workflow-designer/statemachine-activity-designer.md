---
title: "Durum makinesi etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- StateMachine Designer
- System.Activities.Statements.StateMachine.UI
ms.assetid: 474d5fb3-1049-4b3f-bc6b-7524dbbe1672
caps.latest.revision: "5"
ms.author: sdanie
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 1800bfc9e60d52ea5c06bb94fdb765348a977681
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="statemachine-activity-designer"></a>Durum makinesi etkinlik Tasarımcısı
<xref:System.Activities.Statements.StateMachine> Etkinlik durumlar koleksiyonunu içerir ve tanıdık durumu makine kip kullanarak da iş akışları modeller.  
  
## <a name="using-the-statemachine-activity-designer"></a>Durum makinesi etkinlik Tasarımcısı'nı kullanarak  
 Eklemek için bir <xref:System.Activities.Statements.StateMachine> etkinlik, sürükle **Durum makinesi** etkinlik Tasarımcısı'ndan **Durum makinesi** bölümünü **araç** ve oturum bırakın [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] Yüzey. Bunun için bir alt durum eklemek için <xref:System.Activities.Statements.StateMachine> etkinlik, sürükle bir <xref:System.Activities.Statements.State> veya <xref:System.Activities.Core.Presentation.FinalState> gelen **araç** ve üzerine bırakın **Durum makinesi**.  
  
### <a name="statemachine-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda Durum makinesi etkinlik özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.StateMachine> Tasarımcısı'nda nasıl kullanıldığını açıklar ve iş akışı Tasarımcısı'nı kullanarak ayarlanabilir özellikleri. Bu özellikler ve özellik ızgarasının düzenlenebilir ve bazı Tasarımcı yüzeyine düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.StateMachine> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer **Durum makinesi**. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir. <xref:System.Activities.Activity.DisplayName%2A> İş akışı Tasarımcısı'nı üstünde görüntülenen içerik haritası Gezinti kullanılır.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)   
 [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)