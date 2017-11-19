---
title: "Etkinlik Tasarımcısı çekme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Pick.UI
ms.assetid: 642c0a47-1b47-45de-a19a-ca0606cedd7a
caps.latest.revision: "9"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: aa06d4c63dbb18c080c8a6b8ffda01838607ba55
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="pick-activity-designer"></a>Etkinlik Tasarımcısı seçin
<xref:System.Activities.Statements.Pick> Olay tabanlı denetim akışı etkinliği sağlar. Etkinlik birçok dalı birini tetikleyici bir olaya yanıt olarak yürütür.  
  
## <a name="the-pick-activity"></a>Çekme Etkinlik  
 A <xref:System.Activities.Statements.Pick> etkinlik içeren bir koleksiyonu <xref:System.Activities.Statements.PickBranch> nesneleri, bunlardan biri <xref:System.Activities.Statements.Pick> etkinlik tetikleyici olarak hizmet veren bazı gelen olayı nedeniyle yürütebilir. Bu şekilde [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] olay tabanlı denetim akışı modelleme sağlar. Her <xref:System.Activities.Statements.PickBranch> içeren bir <xref:System.Activities.Statements.PickBranch.Trigger%2A> ve bir <xref:System.Activities.Statements.PickBranch.Action%2A>. Başında bir <xref:System.Activities.Statements.Pick> etkinliğin yürütme, tüm tetikleyici etkinliklerini <xref:System.Activities.Statements.PickBranch> öğeleri zamanlanır. İlk etkinlik tamamlandıktan sonra karşılık gelen eylem etkinlik zamanlanır ve diğer tüm tetikleyici etkinlikleri iptal edilir.  
  
### <a name="how-to-use-the-pick-activity-designer"></a>Çekme Etkinlik Tasarımcısı kullanma  
 **Çekme** etkinlik Tasarımcısı bulunabilir **akış denetimi** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **Çekme** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlik tasarımcıları normalde yerleştirilir, örneğin içine bir  **Sıra** etkinlik Tasarımcısı. İçine bırakmadan sonra [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], oluşturduğu bir <xref:System.Activities.Statements.Pick> içeren varsayılan olarak iki boş etkinlik <xref:System.Activities.Statements.PickBranch> etkinlikleri ile öğeleri olarak Branch1 ve Branch2 adlarını görüntüler. Bu ilgili <xref:System.Activities.Statements.PickBranch.DisplayName%2A> özellik değerlerini düzenlenebilir **PickBranch** etkinlik Tasarımcısı üstbilgisi veya içinde **özellikleri** her dal için penceresi.  
  
 Eklemek için iki yolla <xref:System.Activities.Statements.PickBranch> etkinlikler koleksiyonu için bir <xref:System.Activities.Statements.Pick> nesne: sürükleme ve bırakma **PickBranch** gelen Tasarımcı **araç kutusu** veya bağlam menüsünden kullanarak içinde **çekme** tasarım yüzeyi. Ayrıntılar için bkz [PickBranch](../workflow-designer/pickbranch-activity-designer.md) konu. İçinde yalnızca öğesini bildirimi yerleştirilebilen bir **çekme** etkinlik Tasarımcısı bir **PickBranch** etkinlik Tasarımcısı.  
  
### <a name="pick-activity-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda etkinlik özellikleri seçin  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Pick> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzu veya tasarımcı yüzeyine düzenlenebilir.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.Pick> etkinlik Tasarımcısı'nda başlığı. Çekme varsayılan değerdir. Değeri, özellik kılavuzu veya etkinlik Tasarımcısı başlığındaki doğrudan düzenlenebilir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim akışı](../workflow-designer/control-flow-activity-designers.md)   
 [Etkinlik seçin](/dotnet/framework/windows-workflow-foundation/pick-activity)   
 [Çekme etkinliğini kullanma](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)