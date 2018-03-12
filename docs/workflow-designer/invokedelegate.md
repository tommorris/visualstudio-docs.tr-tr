---
title: InvokeDelegate | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 717e9bec58c1eed248c868144ad72aae55948636
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="invokedelegate"></a>InvokeDelegate
**InvokeDelegate** Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.InvokeDelegate> etkinlik.

## <a name="the-invokedelegate-activity"></a>InvokeDelegate etkinliği
 <xref:System.Activities.Statements.InvokeDelegate> Ortak temsilcisini çağırır.

### <a name="using-the-invokedelegate-activity-designer"></a>InvokeDelegate etkinlik Tasarımcısı'nı kullanarak
 **InvokeDelegate** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisini **araç**, hangi tıklayarak erişildiğinde **araçkutusu** sekmesini [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CRTL + ALT + X.)

 **InvokeDelegate** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey burada herhangi bir zamanda etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.InvokeDelegate> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> InvokeDelegate biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **InvokeDelegate** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-invokedelegate-properties"></a>InvokeDelegate özellikleri
 Aşağıdaki tabloda <xref:System.Activities.Statements.InvokeDelegate> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bazı üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]Tasarımcı yüzeyine.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.InvokeDelegate> etkinlik. InvokeDelegate varsayılan değerdir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|Doğru|Adını <xref:System.Activities.ActivityDelegate> etkinlik yürüttüğünde çağrılabilir. Bu özellik Tasarımcı yüzeyine düzenlenebilir. Bu zorunlu bir özelliktir.|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|Çağrılan temsilci bağımsız değişkeni koleksiyonu. Anahtarlar parametre nesneler üzerinde adlarıdır <xref:System.Activities.ActivityDelegate> ve değerleri, ifadeler değerlendirilir ve karşılık gelen parametre nesnelere atanan bağımsız değişkenler. Özellik kılavuzunda üç nokta düğmesini **DelegateArguments** alanını görüntüler **DelegateArguments** iletişim, bu özelliği ayarlamak olanak tanır. Tıklatın **bağımsız değişkeni oluşturma** bağımsız değişkenleri eklemek için alanı.|

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: İş Akışı Tasarımcısında etkinlik temsilcileri tanımlama ve kullanma](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)