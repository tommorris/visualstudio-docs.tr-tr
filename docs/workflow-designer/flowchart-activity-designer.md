---
title: "Akış Çizelgesi etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: d8bcdcc42ada14f808c165e9e06b269817f79575
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="flowchart-activity-designer"></a>Akış Çizelgesi etkinlik Tasarımcısı
<xref:System.Activities.Statements.Flowchart> Etkinlik tanımlayan ve karmaşık akış denetimleri yönetmek iş akışları oluşturmak için kullanılır. A <xref:System.Activities.Statements.Flowchart> kodda veya kullanarak yazılabilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Bu konuda belgeleri [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] karşılaşırsınız. [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] İş akışı etkinlik Tasarımcısı doğal bir biçimde Geliştiriciler iş akışları yazabilirsiniz sağlar.  
  
## <a name="the-flowchart-activity"></a>Akış etkinliği  
 <xref:System.Activities.Statements.Flowchart> Benzersiz bir belirtir <xref:System.Activities.Statements.Flowchart.StartNode%2A> kullanır ve iş akışı başlatıldığında bir ağ bağlantılı yürütülen <xref:System.Activities.Statements.Flowchart.Nodes%2A> rasgele döngüler veya akışını iş akışı içinde başka bir yerde için verilen herhangi bir zamanda yönlendir.  
  
### <a name="using-the-flowchart-activity-designer"></a>Akış Çizelgesi etkinlik Tasarımcısı'nı kullanarak  
 **Akış çizelgesi** etkinlik Tasarımcısı bulunabilir **akış çizelgesi** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **Akış çizelgesi** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlik tasarımcıları normalde yerleştirilir, bir kök etkinlik veya alt olarak başka bir denetim akışı etkinliği. Varsa **akış çizelgesi** etkinlik Tasarımcısı boş bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey, oluşturduğu bir <xref:System.Activities.Statements.Flowchart> sunan varsayılan kendisini yürütme başlatır başlangıç düğümü olduğu bir genişletilmiş görünümünde etkinlik Yeşil Top temsil. Varsa **akış çizelgesi** etkinlik Tasarımcısı başka bir denetim akışı etkinliği bırakılan, çift tıklatarak genişletilebilir bir simge durumuna küçültülmüş görünümünde kendisi sunar **akış çizelgesi** etkinlik Tasarımcısı. Herhangi bir etkinlik **araç** doğrudan üzerine sürüklediğiniz **akış çizelgesi** diğer denetim akışı etkinlikleri de dahil olmak üzere etkinlik Tasarımcısı.  
  
 Çeşitli etkinlik tasarımcıları üzerine sürükleyerek sonra [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] tuvale, <xref:System.Activities.Activity> bunlar temsil eden nesneler bağlantılı olması birlikte yürütme sırasını belirtmek için. Fare kare tanıtıcıları ve kaynak etkinliği tasarımcısına üzerine bir kaynak ve hedef etkinliğiyle arasında bir bağlantı oluşturmak için bunu her bir tarafta görünür. Kare tanıtıcıları birine tıklayın ve fareyle üzerine getirildiğinde, hedef etkinlik geçici benzer şekilde görünür tanıtıcıları birine fare düğmesini basılı tutarak sürükleyin. Fare düğmesini bırakın ve bir ok olarak kaynağı Tasarımcısı'ndan hedef Designer'a temsil edilen bu iki etkinlik arasında bir bağlantı oluşturulur.  
  
### <a name="flowchart-activity-properties"></a>Akış Çizelgesi etkinlik özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Flowchart> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Etkinlik Tasarımcısı görünen adını başlığı belirtir. Akış Çizelgesi varsayılan değerdir. Değer içinde düzenlenebilir **özellikleri** penceresi veya doğrudan başlığındaki etkinlik Tasarımcısı.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|False|Bu içinde kapsamındaki değişkenlerinin koleksiyonunu <xref:System.Activities.Statements.Flowchart> durumu onun alt etkinlikler arasında paylaşmak için.|  
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|False|<xref:System.Activities.Statements.FlowNode> Diğer bir deyişle yürütülmesi <xref:System.Activities.Statements.Flowchart> başlatır.|  
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|False|Koleksiyonunu içerir <xref:System.Activities.Statements.FlowNode> nesnelerini <xref:System.Activities.Statements.Flowchart>.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış Çizelgesi](../workflow-designer/flowchart-activity-designers.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)   
 [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)