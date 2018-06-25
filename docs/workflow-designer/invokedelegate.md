---
title: İş Akışı Tasarımcısı - InvokeDelegate
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: e3d802000bede1a654b088fb80b134a36a0185be
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758533"
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate** Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.InvokeDelegate> etkinlik.

## <a name="the-invokedelegate-activity"></a>InvokeDelegate etkinliği

<xref:System.Activities.Statements.InvokeDelegate> Ortak temsilcisini çağırır.

### <a name="use-the-invokedelegate-activity-designer"></a>InvokeDelegate etkinlik Tasarımcısı'nı kullanın

Erişim **InvokeDelegate** etkinlik Tasarımcısı'nda **Temelleri** kategorisini **araç**. **InvokeDelegate** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir burada ever, gibi olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.Activities.Statements.InvokeDelegate> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> InvokeDelegate biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **InvokeDelegate** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-invokedelegate-properties"></a>InvokeDelegate özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.InvokeDelegate> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.InvokeDelegate> etkinlik. InvokeDelegate varsayılan değerdir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil bir kullanmak en iyisidir.|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|Doğru|Adını <xref:System.Activities.ActivityDelegate> etkinlik yürüttüğünde çağrılabilir. Bu özellik, Tasarımcı yüzeyine düzenlenebilir ve zorunludur.|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|Çağrılan temsilci bağımsız değişkeni koleksiyonu. Anahtarlar parametre nesneler üzerinde adlarıdır <xref:System.Activities.ActivityDelegate>, ve değerleri, ifadeler değerlendirilir ve karşılık gelen parametre nesnelere atanan bağımsız değişkenler. Görüntülenecek **DelegateArguments** iletişim ayarlayabilirsiniz bu özellik, üç nokta düğmesini tıklatın **DelegateArguments** ve özellik ızgarasının alanı. Tıklatın **bağımsız değişkeni oluşturma** bağımsız değişkenleri eklemek için alanı.|

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: İş Akışı Tasarımcısında etkinlik temsilcileri tanımlama ve kullanma](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)