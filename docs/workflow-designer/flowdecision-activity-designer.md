---
title: İş Akışı Tasarımcısı - FlowDecision etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.FlowDecision.UI
ms.assetid: 4a49edc3-3662-4b7b-812e-0a5ba00d6c94
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 033eeff34c095b4598a02a386794379d06086450
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31978141"
---
# <a name="flowdecision-activity-designer"></a>FlowDecision etkinlik Tasarımcısı

<xref:System.Activities.Statements.FlowDecision> Sağlayan bir dal için denetim akışı iki alternatifleri olup belirtilen bir koşul yerine getirildiği dayalı birine koşullu bir düğüm düğümdür. Akış ikiden fazla dalları gerektiriyorsa, kullanın <xref:System.Activities.Statements.FlowSwitch%601> yerine.

## <a name="the-flowdecision-node"></a>FlowDecision düğümü

Kullanım <xref:System.Activities.Statements.FlowDecision> zaman akış dallandırılmış iki yolu. A <xref:System.Activities.Statements.FlowDecision> düğüm bir <xref:System.Activities.Statements.FlowDecision.Condition%2A> ve <xref:System.Activities.Statements.FlowNode> her iki olası sonucunu ile ilişkilendirilmiş: <xref:System.Activities.Statements.FlowDecision.True%2A> veya <xref:System.Activities.Statements.FlowDecision.False%2A>. <xref:System.Activities.Statements.FlowDecision.Condition%2A> Değerlendirilir ve değerin Bu değerlendirme sonraki belirler <xref:System.Activities.Statements.FlowNode> içinde işlenmek üzere <xref:System.Activities.Statements.Flowchart>.

### <a name="using-the-flowdecision-designer"></a>FlowDecision Tasarımcısı'nı kullanarak
 **FlowDecision** Tasarımcısı bulunabilir **akış çizelgesi** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç** İş Akışı Tasarımcısı sekmesinde (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **FlowDecision** Tasarımcısı'ndan sürüklenebilir **araç** ve iş akışı Tasarımcısı yüzeyini içinde açın bırakılan bir **akış çizelgesi** etkinlik Tasarımcısı. Bu oluşturur bir <xref:System.Activities.Statements.FlowDecision> etiketli **karar** içinde <xref:System.Activities.Statements.Flowchart> etkinlik. Fare Tasarımcı üzerine ve **True** ve **False** iki dalı için kare işleyicilerin görünür.

 Sürükleme sonra **FlowDecision** Tasarımcısı ve diğer tasarımcılar üzerine **akış çizelgesi**, düğümleri bağlı birlikte yürütme sırasını belirtmek için. Bir kaynak düğüm arasında bir bağlantı oluşturmak için (de dahil olmak üzere **True** ve **False** , dallandırır **FlowDecision**) ve hedef düğüm, kaynak düğüm designer üzerinden fare ve bunu her bir tarafta kare tanıtıcıları görünür. Kare tanıtıcıları birini tıklatın ve üzerine fare yükleyen hedef düğüm geçici benzer şekilde görünen tanıtıcıları birine fare düğmesini basılı tutarak sürükleyin. Fare düğmesini bırakın ve bir bağlantı arasındaki bir ok olarak kaynağı Tasarımcısı'ndan hedef Designer'a temsil edilen bu iki düğüm oluşturulur.

 Durumları ifade <xref:System.Activities.Statements.FlowDecision.Condition%2A> yazılabilir **koşulu** kutusunun **özellikleri** burada ipucu metnini bildiren "Girin VB ifade" tıklayarak penceresi.

### <a name="the-flowdecision-properties"></a>FlowDecision özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.FlowDecision> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.FlowDecision.Condition%2A>|Doğru|Hangi yolu belirler koşul akış denetimi alır.|
|<xref:System.Activities.Statements.FlowDecision.True%2A>|False|Varsa akış denetimi tarafından alınan yolu <xref:System.Activities.Statements.FlowDecision.Condition%2A> memnun kalır.|
|<xref:System.Activities.Statements.FlowDecision.False%2A>|False|Varsa akış denetimi tarafından alınan yolu <xref:System.Activities.Statements.FlowDecision.Condition%2A> memnun değil.|

## <a name="see-also"></a>Ayrıca bkz.

- [Akış Çizelgesi](../workflow-designer/flowchart-activity-designers.md)
- [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)
- [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)