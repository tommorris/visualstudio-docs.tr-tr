---
title: "FlowDecision etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.FlowDecision.UI
ms.assetid: 4a49edc3-3662-4b7b-812e-0a5ba00d6c94
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 3e3fd48f33e5499f7a67aed02c7b732ebe6b3b7b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="flowdecision-activity-designer"></a>FlowDecision etkinlik Tasarımcısı
<xref:System.Activities.Statements.FlowDecision> Sağlayan bir dal için denetim akışı iki alternatifleri olup belirtilen bir koşul yerine getirildiği dayalı birine koşullu bir düğüm düğümdür. Akış ikiden fazla dalları gerektiriyorsa, kullanın <xref:System.Activities.Statements.FlowSwitch%601> yerine.  
  
## <a name="the-flowdecision-node"></a>FlowDecision düğümü  
 Kullanım <xref:System.Activities.Statements.FlowDecision> zaman akış dallandırılmış iki yolu. A <xref:System.Activities.Statements.FlowDecision> düğüm bir <xref:System.Activities.Statements.FlowDecision.Condition%2A> ve <xref:System.Activities.Statements.FlowNode> her iki olası sonucunu ile ilişkilendirilmiş: <xref:System.Activities.Statements.FlowDecision.True%2A> veya <xref:System.Activities.Statements.FlowDecision.False%2A>. <xref:System.Activities.Statements.FlowDecision.Condition%2A> Değerlendirilir ve değerin Bu değerlendirme sonraki belirler <xref:System.Activities.Statements.FlowNode> içinde işlenmek üzere <xref:System.Activities.Statements.Flowchart>.  
  
### <a name="using-the-flowdecision-designer"></a>FlowDecision Tasarımcısı'nı kullanarak  
 **FlowDecision** Tasarımcısı bulunabilir **akış çizelgesi** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç** sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **FlowDecision** Tasarımcısı'ndan sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] içinde yüzey bir **akış çizelgesi** etkinlik Tasarımcısı. Bu oluşturur bir <xref:System.Activities.Statements.FlowDecision> etiketli **karar** içinde <xref:System.Activities.Statements.Flowchart> etkinlik. Fare Tasarımcı üzerine ve **True** ve **False** iki dalı için kare işleyicilerin görünür.  
  
 Sürükleme sonra **FlowDecision** Tasarımcısı ve diğer tasarımcılar üzerine **akış çizelgesi**, düğümleri bağlı birlikte yürütme sırasını belirtmek için. Bir kaynak düğüm arasında bir bağlantı oluşturmak için (de dahil olmak üzere **True** ve **False** , dallandırır **FlowDecision**) ve hedef düğüm, kaynak düğüm designer üzerinden fare ve bunu her bir tarafta kare tanıtıcıları görünür. Kare tanıtıcıları birini tıklatın ve üzerine fare yükleyen hedef düğüm geçici benzer şekilde görünen tanıtıcıları birine fare düğmesini basılı tutarak sürükleyin. Fare düğmesini bırakın ve bir bağlantı arasındaki bir ok olarak kaynağı Tasarımcısı'ndan hedef Designer'a temsil edilen bu iki düğüm oluşturulur.  
  
 Durumları ifade <xref:System.Activities.Statements.FlowDecision.Condition%2A> yazılabilir **koşulu** kutusunun **özellikleri** burada ipucu metnini bildiren "Girin VB ifade" tıklayarak penceresi.  
  
### <a name="the-flowdecision-properties"></a>FlowDecision özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.FlowDecision> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.FlowDecision.Condition%2A>|Doğru|Hangi yolu belirler koşul akış denetimi alır.|  
|<xref:System.Activities.Statements.FlowDecision.True%2A>|False|Varsa akış denetimi tarafından alınan yolu <xref:System.Activities.Statements.FlowDecision.Condition%2A> memnun kalır.|  
|<xref:System.Activities.Statements.FlowDecision.False%2A>|False|Varsa akış denetimi tarafından alınan yolu <xref:System.Activities.Statements.FlowDecision.Condition%2A> memnun değil.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış Çizelgesi](../workflow-designer/flowchart-activity-designers.md)   
 [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)   
 [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)