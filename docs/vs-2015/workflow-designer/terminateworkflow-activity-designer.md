---
title: TerminateWorkflow etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TerminateWorkflow.UI
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: a00677390967f0cc0cff8a04b33895d7c88588f6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692872"
---
# <a name="terminateworkflow-activity-designer"></a>TerminateWorkflow Etkinlik Tasarımcısı
**TerminateWorkflow** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.TerminateWorkflow> etkinlik.  
  
## <a name="the-terminateworkflow-activity"></a>TerminateWorkflow etkinlik  
 <xref:System.Activities.Statements.TerminateWorkflow> Etkinliğini bir iş akışı yürütülmesini sonlandırır.  
  
### <a name="using-the-terminateworkflow-activity-designer"></a>TerminateWorkflow etkinlik Tasarımcısı kullanma  
 **TerminateWorkflow** etkinlik Tasarımcısı bulunabilir **çalışma zamanı** kategorisi **araç kutusu**, hangi erişilen tıklayarak **araçkutusu** sekme (Alternatif olarak, seçin **araç kutusu** gelen **görünümü** menüsünden veya CTRL + ALT + X.)  
  
 **TerminateWorkflow** etkinlik Tasarımcısı, gelen sürüklenebilir **araç kutusu** ve oturum bırakılan [!INCLUDE[wfd2](../includes/wfd2-md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, örneğin olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu, oluşturur bir <xref:System.Activities.Statements.TerminateWorkflow> etkinliği ile bir varsayılan **DisplayName** TerminateWorkflow biri. <xref:System.Activities.Activity.DisplayName%2A> Üst bilgisinde düzenlenebilir **TerminateWorkflow** etkinlik Tasarımcısı veya **DisplayName** özellik kılavuzunda kutusu.  
  
### <a name="the-terminateworkflow-properties"></a>TerminateWorkflow özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.TerminateWorkflow> özellikleri Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzunda düzenlenebilir ve bunlardan bazıları üzerinde düzenlenebilir [!INCLUDE[wfd2](../includes/wfd2-md.md)] yüzeyi.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.TerminateWorkflow> etkinlik. TerminateWorkflow varsayılandır. Görünen ad kesinlikle gerekli olmamakla birlikte, bir görünen ad kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|İş akışı sonlandırıldığında oluşturulacak özel durum. Bu özellik, özellik kılavuzunda ayarlayın.|  
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|İş akışı neden sonlandırıldı açıklayan nedeni. Bu özellik, özellik kılavuzunda ayarlayın.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı](../workflow-designer/runtime-activity-designers.md)   
 [Kalıcı](../workflow-designer/persist-activity-designer.md)