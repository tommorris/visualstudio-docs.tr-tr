---
title: İş Akışı Tasarımcısı - PickBranch etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.PickBranch.UI
ms.assetid: f523ad47-bbc0-4cda-a35c-41e67c4ba081
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0c2a36392f3f83f533c2d072398800e105727b0
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755566"
---
# <a name="pickbranch-activity-designer"></a>PickBranch Etkinlik Tasarımcısı

<xref:System.Activities.Statements.PickBranch> İçinde yürütme olay tabanlı bir yol sağlayan bir <xref:System.Activities.Statements.Pick> gelen olayı tarafından tetiklenen etkinlik.

## <a name="pickbranch"></a>PickBranch

<xref:System.Activities.Statements.PickBranch> içinde kapsanan nesneleri <xref:System.Activities.Statements.Pick.Branches%2A> koleksiyonu bir <xref:System.Activities.Statements.Pick> etkinlik. Her <xref:System.Activities.Statements.PickBranch> bir dalındaki bulunan <xref:System.Activities.Statements.Pick> etkinliği ve tetikleyici olarak hizmet veren bazı gelen olayı nedeniyle çalıştırılabilir. Bu şekilde, olay tabanlı denetim akışı modelleme iş akışı Tasarımcısı sağlar. Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Trigger%2A> ve bir <xref:System.Activities.Statements.PickBranch.Action%2A>.

### <a name="how-to-use-the-pick-activity-designer"></a>Çekme Etkinlik Tasarımcısı kullanma

Erişim **PickBranch** içinde Tasarımcı **akış denetimi** kategorisini **araç**.

İki boş <xref:System.Activities.Statements.PickBranch> nesneleriyle adlarını görüntülemek **Branch1** ve **Branch2** öğeleri olarak varsayılan olarak oluşturulan bir <xref:System.Activities.Statements.Pick> etkinlik zaman **çekme** Etkinlik Tasarımcısı başlangıçta açın iş akışı Tasarımcısı bırakılır. Bu ilgili <xref:System.Activities.Statements.PickBranch.DisplayName%2A> özellik değerlerini düzenlenebilir **PickBranch** Tasarımcı üstbilgisi veya içinde **özellikleri** her dal için penceresi.

Eklemek için iki yolla <xref:System.Activities.Statements.PickBranch> koleksiyonunu nesnelere bir <xref:System.Activities.Statements.Pick> nesne: sürükleme ve bırakma **PickBranch** gelen Tasarımcı **araç kutusu**, veya bağlam menüsünden kullanarak içinde **çekme** tasarım yüzeyi:

- **PickBranch** Tasarımcısı oluşturur bir <xref:System.Activities.Statements.PickBranch> zaman onu sürüklenen gelen **araç** ve dalları birine bırakılan bir **çekme** etkinlik Tasarımcısı İş Akışı Tasarımcısı yüzeyini. Yeni <xref:System.Activities.Statements.PickBranch> nesneleri içine yerleştirilebilir <xref:System.Activities.Statements.Pick> sola veya sağa var olan Tasarımcı <xref:System.Activities.Statements.PickBranch> koleksiyonda zaten bulunan öğeleri. Sürüklendiğinde bir **PickBranch** üzerine Tasarımcı **çekme** fareyle, tasarımcı **çekme** Tasarımcısı yeri belirtmek için dikey bir gri mavi bant kullanır <xref:System.Activities.Statements.PickBranch> verilen fare yerleştirme için eklenir.

- Sağ **çekme** etkinlik Tasarımcısı (ancak değil iç **PickBranch** Tasarımcısı) bir bağlam menüsü almak ve seçmek için **dal oluşturma** yeni eklemek için <xref:System.Activities.Statements.PickBranch>. Dikkat yeni <xref:System.Activities.Statements.PickBranch> var olan sağa eklenen <xref:System.Activities.Statements.PickBranch> nesnelerini **çekme** Tasarımcısı.

**PickBranch** Tasarımcısı ortaya çıkarmak için Genişletilebilir **tetikleyici** ve **eylem** kutular veya kendi üstbilgileri sağ tarafındaki çift belirliyorsanız düzeltme işaretleri tıklayarak daraltılmış. Düzen <xref:System.Activities.Statements.PickBranch.Trigger%2A> ve <xref:System.Activities.Statements.PickBranch.Action%2A> her <xref:System.Activities.Statements.PickBranch> etkinliklerine bırakarak tarafından **tetikleyici** ve **eylem** kendi tasarımcıları kutuları.

<xref:System.Activities.Statements.PickBranch> Nesnelerini <xref:System.Activities.Statements.Pick.Branches%2A> koleksiyonu bir <xref:System.Activities.Statements.Pick> nesne, bunları içinde yeni bir konuma bırakarak kaldırılmasında **çekme** Tasarımcısı. **Çekme** Tasarımcısı yeri belirtmek için dikey bir gri mavi bant kullanır <xref:System.Activities.Statements.PickBranch> verilen fare yerleştirme için eklenir.

Silmek için iki yolla bir <xref:System.Activities.Statements.PickBranch>:

- Seçin **PickBranch** Tasarımcısı ve silin.
- Seçin **PickBranch** bağlam menüsü almak ve seçmek için tasarımcı, sağ **silmek**.

Seçtiğinizden emin olun **PickBranch** Tasarımcı içinde etkinliklerden birini seçerek olarak kendi **tetikleyici** veya **eylem** kutuları yanlışlıkla siler bu etkinlikler ve değil <xref:System.Activities.Statements.PickBranch> nesnesi.

### <a name="pickbranch-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda PickBranch özellikleri

Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.PickBranch> özellikleri ve iş akışı Tasarımcısı'nda kullanmayı açıklar.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.PickBranch.DisplayName%2A>|False|Başlığında görüntülenen kolay ad **PickBranch** Tasarımcısı. Dal varsayılan değerdir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.PickBranch.Trigger%2A>|Doğru|Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Trigger%2A> çağırabileceği eylem <xref:System.Activities.Statements.PickBranch.Action%2A>.|
|<xref:System.Activities.Statements.PickBranch.Action%2A>|False|Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Action%2A> tetiklenen ise gerçekleştirilir.|

## <a name="see-also"></a>Ayrıca bkz.

- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)
- [Pick Etkinliği](/dotnet/framework/windows-workflow-foundation/pick-activity)
- [Pick Etkinliği Kullanma](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)