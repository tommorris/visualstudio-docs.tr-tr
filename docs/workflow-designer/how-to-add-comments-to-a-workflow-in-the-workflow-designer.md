---
title: "Nasıl yapılır: bir iş akışı iş akışı Tasarımcısı'nda açıklamaları ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.Annotations.Annotation.UI
- Annotation
ms.assetid: 9aa0e8d6-8129-4438-8389-d460611581a7
caps.latest.revision: "7"
ms.author: sdanie
manager: erikre
ms.openlocfilehash: 22a96549b70ebf1627b8a94a7c8cd5e2d5835194
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-add-comments-to-a-workflow-in-the-workflow-designer"></a>Nasıl yapılır: bir iş akışı iş akışı Tasarımcısı'nda açıklamaları ekleme
Daha büyük ve daha karmaşık iş akışları oluşturma kolaylaştırmak için [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)] öğesi Tasarımcısı'nda aşağıdaki türlerini ek açıklamaları eklemek Geliştirici sağlar:  
  
-   <xref:System.Activities.Activity>  
  
-   <xref:System.Activities.Statements.State>  
  
-   <xref:System.Activities.Statements.Transition>  
  
-   Türetilmiş sınıflar<xref:System.Activities.Statements.FlowNode>  
  
-   <xref:System.Activities.Variable>  
  
-   <xref:System.Activities.Argument>  
  
> [!IMPORTANT]
>  Ek açıklamanın içeriğini iş akışı ile ilişkilendirilmiş XAML dosyasına düz metin olarak kaydedilir ve potansiyel olarak başkaları tarafından okunabilen. Önemli bilgileri bir ek açıklamanın içine girerken dikkatli olun.  
  
### <a name="adding-an-annotation-to-an-activity-in-the-designer"></a>Bir etkinlik Tasarımcısı'nda bir ek açıklama ekleme  
  
1.  İş Akışı Tasarımcısı'nda bir öğe seçin ve tasarımcı iş akışındaki sağ tıklayın **ek açıklamaları**, **ek açıklama eklemek**.  
  
2.  Ek açıklamanın metin sağlanan alana ekleyin.  
  
3.  Öğe bir ek açıklama simgesini gösterir. Ek açıklama simgenin üzerine gelerek veya onları ek açıklamanın metin görüntüler.  
  
     ![Sıralı etkinlik ek açıklama gösteren](../debugger/debug-interface-access/annotation.md "ek açıklaması")  
  
### <a name="displaying-an-annotation-in-an-activitys-designer"></a>Ek açıklamanın bir etkinliğin tasarımcıda görüntüleme  
  
1.  Bir ek açıklamanın dışında etkinliği görüntüleme sahip bir etkinlik Tasarımcısı ile tıklatın **PIN** ek açıklama donatıcı simgesi.  
  
2.  Ek açıklamanın etkinliğin Tasarımcısı'nda görüntülenir. Aşağıdaki ekran görüntüsünde, ek açıklama "İş akışındaki başlangıç etkinliği" etkinliğin Tasarımcısı'nda görüntülenir.  
  
     ![Etkinlik Tasarımcısı'nda gösterilen ek açıklama](../workflow-designer/media/annotationindesigner.png "AnnotationInDesigner")  
  
3.  Etkinliğin Tasarımcısı dışında ek açıklama görüntülemek için etkinliğin Tasarımcısı'nda ek açıklama alanı üzerine getirin ve tıklatın **telefondaki** simgesi  
  
     ![Ek açıklama dışında bir etkinliğin designe görüntülenen](../workflow-designer/media/annotationoutsidedesigner.png "AnnotationOutsideDesigner")  
  
### <a name="showing-or-hiding-all-annotations"></a>Gösterme veya gizleme tüm ek açıklamaları  
  
1.  Ek açıklamanın sahip bir etkinliği sağ tıklatın. Seçin **ek açıklamaları**, **tüm ek açıklamaları Göster**.  
  
2.  Tüm ek açıklamaları etkinlik tasarımcıları görüntülenir.  
  
3.  Etkinliğin tasarımcıları dışında tüm ek açıklamaları görüntülemek için etkinliği sağ tıklatın ve **ek açıklamaları**, **tüm ek açıklamaları Gizle**.  
  
### <a name="editing-or-deleting-an-annotation-for-an-activity"></a>Düzenleme veya açıklamanın bir etkinliğin silme  
  
1.  Ek açıklamanın sahip bir etkinliğini sağ tıklatın.  
  
2.  Seçin **ek açıklamaları**, **ek açıklamayı Düzenle** veya **açıklamayı Sil**.  
  
3.  Ek açıklamanın düzenlenmek üzere açıldıktan veya silinmiş.  
  
4.  Tüm ek açıklamaları aynı anda silmek için iş akışı Tasarımcısı ve select sağ **ek açıklama**, **tüm ek açıklamaları silmek**.  
  
### <a name="adding-editing-and-deleting-an-annotation-for-a-variable-or-argument"></a>Ekleme, düzenleme ve bir değişkeni veya bağımsız değişkeni için ek açıklamanın silme  
  
1.  Bir değişken veya değişken sağ tıklatın ve ek açıklama eklemek seçin.  
  
2.  Ek Açıklama metnini girin. Değişken veya bağımsız bir ek açıklama simgesi görüntüler.  
  
3.  Bir değişken veya açıklamanın sahip bağımsız değişken sağ tıklayın. Ek Açıklama Düzenle.  
  
4.  Ek açıklamanın düzenleme için açılacak.  
  
5.  Bir değişken veya açıklamanın sahip bağımsız değişken sağ tıklayın. Delete ek açıklama seçin.  
  
6.  Ek açıklamanın silinir.