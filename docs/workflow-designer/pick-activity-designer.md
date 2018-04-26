---
title: İş Akışı Tasarımcısı - çekme etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Pick.UI
ms.assetid: 642c0a47-1b47-45de-a19a-ca0606cedd7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f664ac3a22b91780d392e0fef3224cd80b1e7919
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="pick-activity-designer"></a>Etkinlik Tasarımcısı seçin

<xref:System.Activities.Statements.Pick> Olay tabanlı denetim akışı etkinliği sağlar. Etkinlik birçok dalı birini tetikleyici bir olaya yanıt olarak yürütür.

## <a name="the-pick-activity"></a>Çekme Etkinlik

A <xref:System.Activities.Statements.Pick> etkinlik içeren bir koleksiyonu <xref:System.Activities.Statements.PickBranch> nesneleri, bunlardan biri <xref:System.Activities.Statements.Pick> etkinlik tetikleyici olarak hizmet veren bazı gelen olayı nedeniyle yürütebilir. Bu şekilde, olay tabanlı denetim akışı modelleme Windows iş akışı Tasarımcısı sağlar. Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Trigger%2A> ve bir <xref:System.Activities.Statements.PickBranch.Action%2A>. Başında bir <xref:System.Activities.Statements.Pick> etkinliğin yürütme, tüm tetikleyici etkinliklerini <xref:System.Activities.Statements.PickBranch> öğeleri zamanlanır. İlk etkinlik tamamlandıktan sonra karşılık gelen eylem etkinlik zamanlanır ve diğer tüm tetikleyici etkinlikleri iptal edilir.

### <a name="how-to-use-the-pick-activity-designer"></a>Çekme Etkinlik Tasarımcısı kullanma

**Çekme** etkinlik Tasarımcısı bulunabilir **akış denetimi** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**iş akışı Tasarımcısı sekmesinde (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

**Çekme** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlik tasarımcıları normalde, örneğin içine yerleştirilen her yerde iş akışı Tasarımcısı yüzeyini açın bırakılan bir  **Sıra** etkinlik Tasarımcısı. İş Akışı Tasarımcısı'na bırakarak sonra oluşturduğu bir <xref:System.Activities.Statements.Pick> içeren varsayılan olarak iki boş etkinlik <xref:System.Activities.Statements.PickBranch> etkinlikleri ile öğeleri olarak Branch1 ve Branch2 adlarını görüntüler. Bu ilgili <xref:System.Activities.Statements.PickBranch.DisplayName%2A> özellik değerlerini düzenlenebilir **PickBranch** etkinlik Tasarımcısı üstbilgisi veya içinde **özellikleri** her dal için penceresi.

Eklemek için iki yolla <xref:System.Activities.Statements.PickBranch> etkinlikler koleksiyonu için bir <xref:System.Activities.Statements.Pick> nesne: sürükleme ve bırakma **PickBranch** gelen Tasarımcı **araç kutusu** veya bağlam menüsünden kullanarak içinde **çekme** tasarım yüzeyi. Ayrıntılar için bkz [PickBranch](../workflow-designer/pickbranch-activity-designer.md) konu. İçinde yalnızca öğesini bildirimi yerleştirilebilen bir **çekme** etkinlik Tasarımcısı bir **PickBranch** etkinlik Tasarımcısı.

### <a name="pick-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda etkinlik özellikleri seçin

Aşağıdaki tabloda <xref:System.Activities.Statements.Pick> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.Pick> etkinlik Tasarımcısı'nda başlığı. Çekme varsayılan değerdir. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|

## <a name="see-also"></a>Ayrıca bkz.

- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)
- [Pick Etkinliği](/dotnet/framework/windows-workflow-foundation/pick-activity)
- [Pick Etkinliği Kullanma](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)