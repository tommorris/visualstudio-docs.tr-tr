---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir iş akışına açıklamaları ekleme'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.Annotations.Annotation.UI
- Annotation
ms.assetid: 9aa0e8d6-8129-4438-8389-d460611581a7
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d740614ed94d0fd91ba9f3e73a083791b9112919
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752033"
---
# <a name="how-to-add-comments-to-a-workflow-in-the-workflow-designer"></a>Nasıl yapılır: bir iş akışı iş akışı Tasarımcısı'nda açıklamaları ekleme

Daha büyük ve daha karmaşık iş akışları oluşturma kolaylaştırmak için .NET Framework 4.5 öğesi Tasarımcısı'nda aşağıdaki türlerini ek açıklamaları eklemek Geliştirici sağlar:

-   <xref:System.Activities.Activity>

-   <xref:System.Activities.Statements.State>

-   <xref:System.Activities.Statements.Transition>

-   Türetilmiş sınıflar <xref:System.Activities.Statements.FlowNode>

-   <xref:System.Activities.Variable>

-   <xref:System.Activities.Argument>

> [!IMPORTANT]
> Ek açıklamanın içeriğini iş akışı ile ilişkilendirilmiş XAML dosyasına düz metin olarak kaydedilir ve potansiyel olarak başkaları tarafından okunabilen. Önemli bilgileri bir ek açıklamanın içine girerken dikkatli olun.

## <a name="adding-an-annotation-to-an-activity-in-the-designer"></a>Bir etkinlik Tasarımcısı'nda bir ek açıklama ekleme

1. İş Akışı Tasarımcısı'nda bir öğe seçin ve tasarımcı iş akışındaki sağ tıklayın **ek açıklamaları**, **ek açıklama eklemek**.

1. Ek açıklamanın metin sağlanan alana ekleyin.

   Öğe bir ek açıklama simgesi gösterir. Ek açıklama simgenin üzerine gelerek veya onları ek açıklamanın metin görüntüler.

## <a name="displaying-an-annotation-in-an-activitys-designer"></a>Ek açıklamanın bir etkinliğin tasarımcıda görüntüleme

1.  Bir ek açıklamanın dışında etkinliği görüntüleme sahip bir etkinlik Tasarımcısı ile tıklatın **PIN** ek açıklama donatıcı simgesi.

   Ek açıklamanın etkinliğin Tasarımcısı'nda görüntülenir. Aşağıdaki ekran görüntüsünde, ek açıklama "İş akışındaki başlangıç etkinliği" etkinliğin Tasarımcısı'nda görüntülenir.

   ![Etkinlik Tasarımcısı'nda gösterilen ek açıklaması](../workflow-designer/media/annotationindesigner.png)

1. Etkinliğin Tasarımcısı dışında ek açıklama görüntülemek için etkinliğin Tasarımcısı'nda ek açıklama alanı üzerine getirin ve tıklatın **telefondaki** simgesi

   ![Bir etkinliğin designe dışında görüntülenen ek açıklaması](../workflow-designer/media/annotationoutsidedesigner.png)

## <a name="showing-or-hiding-all-annotations"></a>Gösterme veya gizleme tüm ek açıklamaları

1. Ek açıklamanın sahip bir etkinliği sağ tıklatın. Seçin **ek açıklamaları**, **tüm ek açıklamaları Göster**.

   Tüm ek açıklamaları etkinlik tasarımcıları görüntülenir.

1. Etkinliğin tasarımcıları dışında tüm ek açıklamaları görüntülemek için etkinliği sağ tıklatın ve **ek açıklamaları**, **tüm ek açıklamaları Gizle**.

## <a name="editing-or-deleting-an-annotation-for-an-activity"></a>Düzenleme veya açıklamanın bir etkinliğin silme

1. Ek açıklamanın sahip bir etkinliğini sağ tıklatın.

1. Seçin **ek açıklamaları**, **ek açıklamayı Düzenle** veya **açıklamayı Sil**.

   Ek açıklamanın düzenlenmek üzere açıldıktan veya silinmiş.

1. Tüm ek açıklamaları aynı anda silmek için iş akışı Tasarımcısı ve select sağ **ek açıklama**, **tüm ek açıklamaları silmek**.

## <a name="adding-editing-and-deleting-an-annotation-for-a-variable-or-argument"></a>Ekleme, düzenleme ve bir değişkeni veya bağımsız değişkeni için ek açıklamanın silme

1. Bir değişken veya değişken sağ tıklatın ve ek açıklama eklemek seçin.

1. Ek Açıklama metnini girin. Değişken veya bağımsız bir ek açıklama simgesi görüntüler.

1. Bir değişken veya açıklamanın sahip bağımsız değişken sağ tıklayın. Ek Açıklama Düzenle.

   Ek açıklamanın düzenleme için açıldı.

1. Bir değişken veya açıklamanın sahip bağımsız değişken sağ tıklayın. Delete ek açıklama seçin.

   Ek açıklamanın silinir.