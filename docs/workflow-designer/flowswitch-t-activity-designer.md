---
title: "FlowSwitch&lt;T&gt; etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Core.Presentation.FlowSwitchLink.UI
- System.Activities.Statements.FlowSwitch`1.UI
- System.Activities.Core.Presentation.FlowSwitchLink`1.UI
- System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 791067ff7e29a3eb63fd77e81a692f93edbda535
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="flowswitchlttgt-activity-designer"></a>FlowSwitch&lt;T&gt; etkinlik Tasarımcısı
<xref:System.Activities.Statements.FlowSwitch%601> Sağlayan dallanma ikiden fazla alternatif dalları gerekli olduğunda eşleştirme ölçütü temel alan denetim akışı için koşullu bir düğüm bir etkinliktir. Akış dallanma yalnızca iki yolu gerektiriyorsa, kullanın <xref:System.Activities.Statements.FlowDecision> etkinlik yerine.

## <a name="the-flowswitcht-activity"></a>FlowSwitch < T\> etkinliği
 <xref:System.Activities.Statements.FlowSwitch%601> Etkinlik içeren bir <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> türünde bir değer döndüren *T* (genel parametresi tarafından belirtilen) değerlendirildiğinde. Etkinlik kümesini de içeren <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>, bir dizi benzersiz bir eşleme Bu değerlendirme olası sonuçlarından belirtir <xref:System.Activities.Statements.FlowNode> nesneleri. <xref:System.Activities.Statements.FlowNode> Yürütülen türü, nesne sunucudur *T* değerlendirilen değeri ile eşleşen <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>. A <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> durum söz konusu içinde eşleşme elde edilir (isteğe bağlı) sağlanabilir.

### <a name="using-the-flowswitcht-activity-designer"></a>FlowSwitch kullanarak\<T > etkinlik Tasarımcısı
 **FlowSwitch\<T >** etkinlik Tasarımcısı bulunabilir **akış çizelgesi** kategorisini **araç**, hangi tıklayarakerişildiğinde**Araç** sol tarafındaki sekmesinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

 **FlowSwitch\<T >** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] içinde yüzey bir **akış** Etkinlik Tasarımcısı. Kullanım **türlerini Seç** türünü belirtmek için görüntüler penceresi (koduyla ilişkili <xref:System.Activities.Statements.FlowSwitch%601> genel parametresi tarafından) hesaplanması sonucunda elde edilen <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>. Bu yordam oluşturur bir <xref:System.Activities.Statements.FlowSwitch%601> etiketli etkinlik **anahtar** içinde <xref:System.Activities.Statements.Flowchart> etkinlik. <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> Yazılabilir **ifade** kutusunun **özellikleri** burada ipucu metnini bildiren "Girin VB ifade" tıklayarak penceresi.

 Fare üzerindeyken **FlowSwitch\<T >** bağlantı için kullanılan kare tanıtıcıları neden etkinlik Tasarımcısı <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> kendi kenarları görünmesi. Sürükleme sonra **FlowSwitch < T\>**  etkinlik Tasarımcısı ve diğer etkinlik tasarımcıları üzerine **akış çizelgesi**, <xref:System.Activities.Activity> bunlar temsil eden nesneler birbirine bağlı için hazır yürütme sırasını belirtmek için. Aşağıdakilerden birini oluşturmak için <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> ile ilişkili <xref:System.Activities.Statements.FlowSwitch%601>, çevre kare servis talebi tanıtıcıları birini tıklatın **FlowSwitch < T\>**  ve (fare düğmesini basılı tutarak) tanıtıcıları birine sürükleyin Fare kendi Tasarımcısı geldiğinde hedef etkinlik geçici benzer şekilde görüntülenir. Sürüm fare düğmesini ve bir ok **FlowSwitch < T\>**  bu durumda temsil eden hedef Designer'a görüntülenir. Varsayılan değer içinde düzenlenebilir ve bu durumda üzerindeki oku görüntüler için **durum** kutusunun **özellikleri** penceresi.

### <a name="the-flowswitcht-properties"></a>FlowSwitch < T\> özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.FlowSwitch%601> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|Doğru|Hangi belirlemek için değerlendirilen ifade belirtir <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> yürütme yolunda geçmek için.|
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|Benzersiz bir eşlemeyi hesaplanması sonucunda elde edilen olası sonuçlarından belirtir <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> bir dizi <xref:System.Activities.Statements.FlowNode> nesneleri.|
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|Doğru|Eşlemesi zaman değerlendirmesi <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> bulunan değerlerden biri eşleşmiyor <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> nesnesi.|

## <a name="see-also"></a>Ayrıca bkz.

- [Akış Çizelgesi](../workflow-designer/flowchart-activity-designers.md)
- [Akış Çizelgesi](../workflow-designer/flowchart-activity-designer.md)
- [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)