---
title: "Son durum etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: aa186893-8775-40dd-981f-8593ead831d0
caps.latest.revision: "5"
ms.author: sdanie
manager: erikre
ms.workload: multiple
ms.openlocfilehash: b7268da0f92a75d1e24b215dbfaf44d89210228f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="finalstate-activity-designer"></a>Son durum etkinlik Tasarımcısı
<xref:System.Activities.Core.Presentation.FinalState> Tasarımcısı oluşturmak için kullanılan bir <xref:System.Activities.Statements.State> durumu makine örneğini sonlandırır.  
  
## <a name="using-the-finalstate-activity-designer"></a>Son durum etkinlik Tasarımcısı'nı kullanarak  
 **Son durum** Tasarımcısı oluşturmak için kullanılan bir <xref:System.Activities.Statements.State> Durum makinesi sonlandırma durumunda olarak yapılandırılmış. A <xref:System.Activities.Statements.State> kullanılarak oluşturulan <xref:System.Activities.Core.Presentation.FinalState> etkinlik Tasarımcısı sahip kendi <xref:System.Activities.Statements.State.IsFinal%2A> özelliğini **true**, hiçbir <xref:System.Activities.Statements.State.Exit%2A> etkinliği ve ondan kaynaklanan hiçbir geçişler. Kullanılacak <xref:System.Activities.Core.Presentation.FinalState> etkinlik Tasarımcısı eklenecek bir <xref:System.Activities.Statements.State> Durum makinesi sonlandırma durumunda olarak önceden yapılandırılmış etkinlik sürükleyin **son durum** etkinlik Tasarımcısı'ndan **Durum makinesi**bölümünü **araç** ve iş akışı Tasarımcısı bırakın. <xref:System.Activities.Core.Presentation.FinalState> Etkinlik Tasarımcısı bırakılan üzerine bir <xref:System.Activities.Statements.StateMachine> ve geçişleri eklenen daha sonra; veya bir geçiş olarak oluşturulabilir <xref:System.Activities.Core.Presentation.FinalState> etkinlik Tasarımcısı bırakıldı. Geçişleri oluşturma hakkında daha fazla bilgi için bkz: [geçiş](../workflow-designer/transition-activity-designer.md).  
  
### <a name="state-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda durum etkinlik özellikleri  
 Aşağıdaki tabloda kullanılarak ayarlanabilir özellikleri gösterir <xref:System.Activities.Core.Presentation.FinalState> Tasarımcısı ve Tasarımcısı'nda nasıl kullanıldığını açıklar. Bu özelliklerden bazıları özellik kılavuzunda düzenlenebilir ve bazı Tasarımcı yüzeyine düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.State> etkinlik Tasarımcısı'nda başlığı. Varsayılan değer **durumu**. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir. <xref:System.Activities.Statements.State.DisplayName%2A> İş akışı Tasarımcısı'nı üstünde görüntülenen içerik haritası Gezinti kullanılır.<br /><br /> Ancak <xref:System.Activities.Statements.State.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.State.Entry%2A>|False|Bu durum için geçirildiğinde uygulanacak eylemi belirtir. Bu değer bir etkinlikten sürükleyerek ayarlanabilir **araç** ve üzerine bırakmadan <xref:System.Activities.Statements.State.Entry%2A> bölüm durumu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Durum makinesi](../workflow-designer/statemachine-activity-designer.md)   
 [Durumu](../workflow-designer/state-activity-designer.md)   
 [Geçiş](../workflow-designer/transition-activity-designer.md)