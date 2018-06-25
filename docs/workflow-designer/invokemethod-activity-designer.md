---
title: İş Akışı Tasarımcısı - InvokeMethod etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.InvokeMethod.UI
ms.assetid: 15e6efdc-52ca-46d8-9c5e-063f7c8265a6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 03c62abe30fe2ba3896885d1969a3ec2bc45cc86
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757772"
---
# <a name="invokemethod-activity-designer"></a>InvokeMethod Etkinlik Tasarımcısı

**InvokeMethod** Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.InvokeMethod> etkinlik.

## <a name="the-invokemethod-activity"></a>InvokeMethod etkinliği

<xref:System.Activities.Statements.InvokeMethod> Belirtilen nesne veya türü ortak bir yöntemi çağırır.

### <a name="use-the-invokemethod-activity-designer"></a>InvokeMethod etkinlik Tasarımcısı'nı kullanın

Erişim **InvokeMethod** etkinlik Tasarımcısı'nda **Temelleri** kategorisini **araç**. **InvokeMethod** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir burada ever, gibi olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.Activities.Statements.InvokeMethod> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> InvokeMethod biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **InvokeMethod** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-invokemethod-properties"></a>InvokeMethod özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.InvokeMethod> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.InvokeMethod> etkinlik. InvokeMethod varsayılan değerdir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil bir kullanmak en iyisidir.|
|<xref:System.Activities.Statements.InvokeMethod.MethodName%2A>|Doğru|Etkinlik yürüttüğünde çağrılacak yöntemin adı. Çağrılan yöntem olarak bildirilmelidir **ortak**. Bu özellik, Tasarımcı yüzeyine düzenlenebilir ve zorunludur.|
|<xref:System.Activities.Statements.InvokeMethod.Parameters%2A>|False|Çağrılan yöntemin parametre koleksiyonu. Parametreleri yöntemi imzada göründükleri aynı sırada koleksiyonuna eklenmesi gerekir. Görüntülenecek **parametreleri** iletişim ayarlayabilirsiniz bu özellik, üç nokta düğmesini tıklatın **parametreleri** ve özellik ızgarasının alanı. Tıklatın **bağımsız değişkeni oluşturma** parametreleri eklemek için düğmesi.|
|<xref:System.Activities.Statements.InvokeMethod.Result%2A>|False|Yöntem çağrısının dönüş değeri.|
|<xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>|Doğru|Zaman uyumsuz olarak çağrılan yöntemi olup olmadığını belirtir. Varsayılan değer **False**.|
|<xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>|False|Yöntem çağrısını içeren nesne. Bu özellik Tasarımcı yüzeyine düzenlenebilir.<br /><br /> Ya da <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> veya <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> ayarlanması gereklidir.|
|<xref:System.Activities.Statements.InvokeMethod.TargetType%2A>|False|Türü <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>. Bu özellik Tasarımcı yüzeyine düzenlenebilir. Çağrılan yöntemi statikse bu özellik yalnızca ayarlamanız gerekir.|

Parametreleri bir C# geçirmek için **çıkışı** parametresi (örneğin, `Method1(out myParam))`, kullanın **OutArgument** yerine **InOutArgument**

Bağımsız değişkenler olarak adlandırılan yöntemleriyle **TargetObject** veya **sonuç** kullanılarak çağrılamaz <xref:System.Activities.Statements.InvokeMethod> etkinlik. Bunun nedeni olan <xref:System.Activities.Statements.InvokeMethod> etkinlik kayıtlarını <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A>, <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> ve <xref:System.Activities.Statements.InvokeMethod.Result%2A> içinde <xref:System.Activities.Activity.CacheMetadata%2A>.

Parametrelerde kaydettirmek için algoritma <xref:System.Activities.Activity.CacheMetadata%2A> aşağıdaki listede gösterilir:

1.  Kayıt <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> bağımsız değişkeni.

2.  Kayıt <xref:System.Activities.Statements.InvokeMethod.Result%2A> bağımsız değişkeni.

3.  Yinelemek <xref:System.Activities.Statements.InvokeMethod.Parameters%2A> koleksiyonu ve her bağımsız kaydedin.

Sonuçta elde edilen özel durum türünde <xref:System.Activities.InvalidWorkflowException> aşağıdaki iletiyle: 'InvokeMethod': 'TargetObject' ada sahip bir değişken RuntimeArgument veya bir DelegateArgument zaten mevcut. Adları bir ortam kapsamı içinde benzersiz olmalıdır.

Bu kısıtlama geçerli değildir <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> ve <xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>. İş akışı değişkenleri olmadığınız ve bu nedenle kayıtlı olmayan <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A> koleksiyonu <xref:System.Activities.Statements.InvokeMethod> etkinliğinde <xref:System.Activities.Activity.CacheMetadata%2A> yöntemi.

## <a name="see-also"></a>Ayrıca bkz.

- [Temel Türler](../workflow-designer/primitives-activity-designers.md)
- [Ata](../workflow-designer/assign-activity-designer.md)
- [gecikme](../workflow-designer/delay-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)