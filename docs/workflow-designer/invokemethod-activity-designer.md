---
title: "InvokeMethod etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.InvokeMethod.UI
ms.assetid: 15e6efdc-52ca-46d8-9c5e-063f7c8265a6
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 1fe242e3e4fd2a885373d776f79f50071fa83c1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="invokemethod-activity-designer"></a>InvokeMethod etkinlik Tasarımcısı
**InvokeMethod** Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.InvokeMethod> etkinlik.  
  
## <a name="the-invokemethod-activity"></a>InvokeMethod etkinliği  
 <xref:System.Activities.Statements.InvokeMethod> Belirtilen nesne veya türü ortak bir yöntemi çağırır.  
  
### <a name="using-the-invokemethod-activity-designer"></a>InvokeMethod etkinlik Tasarımcısı'nı kullanarak  
 **InvokeMethod** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisini **araç**, hangi tıklayarak erişildiğinde **araçkutusu** sekmesini [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CRTL + ALT + X.)  
  
 **InvokeMethod** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey burada herhangi bir zamanda etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.InvokeMethod> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> InvokeMethod biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **InvokeMethod** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
### <a name="the-invokemethod-properties"></a>InvokeMethod özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.InvokeMethod> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bazı üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]Tasarımcı yüzeyine.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.InvokeMethod> etkinlik. InvokeMethod varsayılan değerdir.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.InvokeMethod.MethodName%2A>|Doğru|Etkinlik yürüttüğünde çağrılacak yöntemin adı. Çağrılan yöntem olarak bildirilmelidir **ortak**. Bu özellik Tasarımcı yüzeyine düzenlenebilir. Bu zorunlu bir özelliktir.|  
|<xref:System.Activities.Statements.InvokeMethod.Parameters%2A>|False|Çağrılan yöntemin parametre koleksiyonu. Parametreleri yöntemi imzada göründükleri aynı sırada koleksiyonuna eklenmesi gerekir. Özellik kılavuzunda üç nokta düğmesini **parametreleri** alanını gösterir **parametreleri** iletişim, bu özelliği ayarlamak olanak tanır. Tıklatın **bağımsız değişkeni oluşturma** parametreleri eklemek için düğmesi.|  
|<xref:System.Activities.Statements.InvokeMethod.Result%2A>|False|Yöntem çağrısının dönüş değeri.|  
|<xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>|Doğru|Zaman uyumsuz olarak çağrılan yöntemi olup olmadığını belirtir. Varsayılan değer **False**.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>|False|Yöntem çağrısını içeren nesne. Bu özellik Tasarımcı yüzeyine düzenlenebilir.<br /><br /> Ya da <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> veya <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> ayarlanması gereklidir.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetType%2A>|False|Türü <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>. Bu özellik Tasarımcı yüzeyine düzenlenebilir. Çağrılan yöntemi statikse bu özellik yalnızca ayarlamanız gerekir.|  
  
 Parametreleri bir C# geçirmek için **çıkışı** parametresi (örneğin, `Method1(out myParam)),` kullanması gereken **OutArgument** yerine **InOutArgument**  
  
 Bağımsız değişkenler olarak adlandırılan yöntemleriyle **TargetObject** veya **sonuç** kullanılarak çağrılamaz <xref:System.Activities.Statements.InvokeMethod> etkinlik. Bunun nedeni olan <xref:System.Activities.Statements.InvokeMethod> etkinlik kayıtlarını <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A>, <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> ve <xref:System.Activities.Statements.InvokeMethod.Result%2A> içinde <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
 Parametrelerde kaydettirmek için algoritma <xref:System.Activities.Activity.CacheMetadata%2A> aşağıdaki listede gösterilir:  
  
1.  Kayıt <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> bağımsız değişkeni.  
  
2.  Kayıt <xref:System.Activities.Statements.InvokeMethod.Result%2A> bağımsız değişkeni.  
  
3.  Yinelemek <xref:System.Activities.Statements.InvokeMethod.Parameters%2A> koleksiyonu ve her bağımsız kaydedin.  
  
 Sonuçta elde edilen özel durum türünde <xref:System.Activities.InvalidWorkflowException> aşağıdaki iletiyle: 'InvokeMethod': 'TargetObject' ada sahip bir değişken RuntimeArgument veya bir DelegateArgument zaten mevcut. Adları bir ortam kapsamı içinde benzersiz olmalıdır.  
  
 Bu kısıtlama geçerli değildir <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> ve <xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A> çünkü bunlar iş akışı bağımsız değişkenleri ve bu nedenle, kayıtlı olmayan <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A> koleksiyonu <xref:System.Activities.Statements.InvokeMethod> etkinliğinde <xref:System.Activities.Activity.CacheMetadata%2A> yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temelleri](../workflow-designer/primitives-activity-designers.md)   
 [Ata](../workflow-designer/assign-activity-designer.md)   
 [Gecikme](../workflow-designer/delay-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)