---
title: StateMachine etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- StateMachine Designer
- System.Activities.Statements.StateMachine.UI
ms.assetid: 474d5fb3-1049-4b3f-bc6b-7524dbbe1672
caps.latest.revision: 5
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1f768142ce3cf71b254e6740a87895f5626372fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630660"
---
# <a name="statemachine-activity-designer"></a>StateMachine Etkinlik Tasarımcısı
<xref:System.Activities.Statements.StateMachine> Etkinliği durumları koleksiyonunu içeren ve tanıdık durum makine paradigma kullanarak iş akışları modeller.  
  
## <a name="using-the-statemachine-activity-designer"></a>StateMachine etkinlik Tasarımcısı kullanma  
 Eklemek için bir <xref:System.Activities.Statements.StateMachine> etkinliğini sürükleyip **StateMachine** etkinlik Tasarımcısı'ndan **Durum makinesi** bölümünü **araç kutusu** oturum bırakın [!INCLUDE[wfd1](../includes/wfd1-md.md)] Surface. Bunun için bir alt durum eklemek için <xref:System.Activities.Statements.StateMachine> etkinliğini sürükleyip bir <xref:System.Activities.Statements.State> veya <xref:System.Activities.Core.Presentation.FinalState> gelen **araç kutusu** üzerine bırakın **StateMachine**.  
  
### <a name="statemachine-activity-properties-in-the-workflow-designer"></a>Durum makinesi iş akışı tasarımcısında etkinlik özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.StateMachine> iş akışı Tasarımcısı'nı kullanarak ayarlanabilir ve Tasarımcısı'nda nasıl kullanıldığını açıklar. Bu özellikler, özellik kılavuzunda düzenlenebilir ve bazı Tasarımcı yüzeyinde düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.StateMachine> üst bilgisindeki etkinlik Tasarımcısı. Varsayılan değer **StateMachine**. Değer özellik kılavuzunda veya etkinlik Tasarımcısı başlığındaki doğrudan düzenleyebilirsiniz. <xref:System.Activities.Activity.DisplayName%2A> İş akışı Tasarımcısı üst kısmında görüntülenen içerik haritalı gezinme kullanılır.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kati şekilde gerekli değil kullanmak için en iyi bir uygulamadır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)   
 [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)