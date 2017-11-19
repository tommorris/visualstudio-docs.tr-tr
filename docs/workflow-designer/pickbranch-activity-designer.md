---
title: "PickBranch etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.PickBranch.UI
ms.assetid: f523ad47-bbc0-4cda-a35c-41e67c4ba081
caps.latest.revision: "10"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a77adbe5e2663ef11242d162b6ac718d88daea5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="pickbranch-activity-designer"></a>PickBranch etkinlik Tasarımcısı
<xref:System.Activities.Statements.PickBranch> İçinde yürütme olay tabanlı bir yol sağlayan bir <xref:System.Activities.Statements.Pick> gelen olayı tarafından tetiklenen etkinlik.  
  
## <a name="pickbranch"></a>PickBranch  
 <xref:System.Activities.Statements.PickBranch>içinde kapsanan nesneleri <xref:System.Activities.Statements.Pick.Branches%2A> koleksiyonu bir <xref:System.Activities.Statements.Pick> etkinlik. Her <xref:System.Activities.Statements.PickBranch> bir dalındaki bulunan <xref:System.Activities.Statements.Pick> etkinliği ve tetikleyici olarak hizmet veren bazı gelen olayı nedeniyle çalıştırılabilir. Bu şekilde [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] olay tabanlı denetim akışı modelleme sağlar. Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Trigger%2A> ve bir <xref:System.Activities.Statements.PickBranch.Action%2A>.  
  
### <a name="how-to-use-the-pick-activity-designer"></a>Çekme Etkinlik Tasarımcısı kullanma  
 **PickBranch** Tasarımcısı bulunabilir **akış denetimi** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç** sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X).  
  
 İki boş <xref:System.Activities.Statements.PickBranch> nesneleriyle adlarını görüntülemek **Branch1** ve **Branch2** öğeleri olarak varsayılan olarak oluşturulan bir <xref:System.Activities.Statements.Pick> etkinlik zaman **çekme** Etkinlik Tasarımcısı için bırakılan başlangıçta [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Bu ilgili <xref:System.Activities.Statements.PickBranch.DisplayName%2A> özellik değerlerini düzenlenebilir **PickBranch** Tasarımcı üstbilgisi veya içinde **özellikleri** her dal için penceresi.  
  
 Eklemek için iki yolla <xref:System.Activities.Statements.PickBranch> koleksiyonunu nesnelere bir <xref:System.Activities.Statements.Pick> nesne: sürükleme ve bırakma **PickBranch** gelen Tasarımcı **araç kutusu** veya bağlam menüsünden kullanarak içinde **çekme** tasarım yüzeyi:  
  
1.  **PickBranch** Tasarımcısı oluşturur bir <xref:System.Activities.Statements.PickBranch> zaman onu sürüklenen gelen **araç** ve dalları birine bırakılan bir **çekme** üzerindeetkinlikTasarımcısı[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini. Yeni <xref:System.Activities.Statements.PickBranch> nesneleri içine yerleştirilebilir <xref:System.Activities.Statements.Pick> sola veya sağa var olan Tasarımcı <xref:System.Activities.Statements.PickBranch> koleksiyonda zaten bulunan öğeleri. Sürüklendiğinde bir **PickBranch** üzerine Tasarımcı **çekme** fareyle, tasarımcı **çekme** Tasarımcısı yeri belirtmek için dikey bir gri mavi bant kullanır <xref:System.Activities.Statements.PickBranch> verilen fare yerleştirme için eklenir.  
  
2.  Sağ tıklayın **çekme** etkinlik Tasarımcısı (ancak değil iç **PickBranch** designer) bir bağlam menüsü almak ve seçmek için **oluşturma şube** yeni eklemek için <xref:System.Activities.Statements.PickBranch>. Dikkat yeni <xref:System.Activities.Statements.PickBranch> var olan sağa eklenen <xref:System.Activities.Statements.PickBranch> nesnelerini **çekme** Tasarımcısı.  
  
 **PickBranch** Tasarımcısı ortaya çıkarmak için Genişletilebilir **tetikleyici** ve **eylem** kutular veya kendi üstbilgileri sağ tarafındaki çift belirliyorsanız düzeltme işaretleri tıklayarak daraltılmış. Düzen <xref:System.Activities.Statements.PickBranch.Trigger%2A> ve <xref:System.Activities.Statements.PickBranch.Action%2A> her <xref:System.Activities.Statements.PickBranch> etkinliklerine bırakarak tarafından **tetikleyici** ve **eylem** kendi tasarımcıları kutuları.  
  
 <xref:System.Activities.Statements.PickBranch> Nesnelerini <xref:System.Activities.Statements.Pick.Branches%2A> koleksiyonu bir <xref:System.Activities.Statements.Pick> nesne, bunları içinde yeni bir konuma bırakarak kaldırılmasında **çekme** Tasarımcısı. **Çekme** Tasarımcısı yeri belirtmek için dikey bir gri mavi bant kullanır <xref:System.Activities.Statements.PickBranch> verilen fare yerleştirme için eklenir.  
  
 Silmek için iki yolla bir <xref:System.Activities.Statements.PickBranch>:  
  
1.  Seçin **PickBranch** Tasarımcısı ve silin.  
  
2.  Seçin **PickBranch** bağlam menüsü almak ve seçmek için tasarımcı, sağ **silmek**.  
  
 Seçtiğinizden emin olun **PickBranch** Tasarımcı içinde etkinliklerden birini seçerek olarak kendi **tetikleyici** veya **eylem** kutuları yanlışlıkla siler bu etkinlikler ve değil <xref:System.Activities.Statements.PickBranch> nesnesi.  
  
### <a name="pickbranch-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda PickBranch özellikleri  
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.PickBranch> özellikleri ve bunların kullanımını açıklar [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)].  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.PickBranch.DisplayName%2A>|False|Başlığında görüntülenen kolay ad **PickBranch** Tasarımcısı. Dal varsayılan değerdir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.PickBranch.Trigger%2A>|Doğru|Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Trigger%2A> çağırabileceği eylem <xref:System.Activities.Statements.PickBranch.Action%2A>.|  
|<xref:System.Activities.Statements.PickBranch.Action%2A>|False|Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Action%2A> tetiklenen ise gerçekleştirilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim akışı](../workflow-designer/control-flow-activity-designers.md)   
 [Etkinlik seçin](/dotnet/framework/windows-workflow-foundation/pick-activity)   
 [Çekme etkinliğini kullanma](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)