---
title: "Kural Koşulu Düzenleyicisi iletişim kutusu (eski) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI
helpviewer_keywords: Rule Condition dialog box
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: a4f38bed7fc164fd5283b98afe780bc81a6a7265
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="rule-condition-editor-dialog-box-legacy"></a>Kural Koşulu Düzenleyicisi iletişim kutusu (eski)
Bu konuda açıklanmaktadır kullanma **Kural Koşulu Düzenleyicisi** eski iletişim kutusunda [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Eski kullanmak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] ya da hedeflemek gerektiğinde [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Oluşturma ve bildirim temelli kural koşulları kullanarak değiştirme **Kural Koşulu Düzenleyicisi** iletişim kutusu. Bu kural koşulları, aşağıdaki Windows Workflow Foundation out-of-box etkinliklerin özellikleri olarak sunulur:  
  
-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)  
  
-   [Öğeye](http://go.microsoft.com/fwlink?LinkID=65034)  
  
-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)  
  
-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)  
  
-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)  
  
 Size erişim **Kural Koşulu Düzenleyicisi** iletişim kutusunu kullanarak [koşulu iletişim kutusunu (eski)](../workflow-designer/select-condition-dialog-box-legacy.md).  
  
 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **Kural Koşulu Düzenleyicisi** iletişim kutusu.  
  
|Arabirim Öğesi|Açıklama|  
|----------------|-----------------|  
|**Koşul:**|Kural koşulu için ifade girin.|  
|**TAMAM**|Kural koşulu kaydetmek için tıklatın.|  
  
## <a name="entering-condition-expressions"></a>Koşul ifadeleri girme  
 Koşul ifadeleri metin olarak girilir. Yazabilirsiniz **bu.** düzenleyicisine alanları, özellikleri ve yöntemleri iş akışı içinde kullanılan başvurmak için IntelliSense benzeri menüsünü kullanarak. Veya doğrudan bir iş akışı üye adı yazın. AND, OR gibi koşul mantıksal işleçler ekleyebilirsiniz ve değil. Koşulları de ekleyebilirsiniz. Bir koşul, ikili işleç ve iki işlenen ' dir. Desteklenen ikili işleçler  **==** ,  **>** ,  **\<** ,  **>=** , ve  **<=** . Desteklenen işlenenler sabit değer, aritmetik işlevi ve kapsamlı Genel Üyeler ' dir.  
  
 Karşılaştırma için türünü belirtebilirsiniz ve'karşılaştırabilirsiniz **null** ya da boş bir dize. Örneğin, bir karmaşık tür içeren bir değişken iç içe geçmiş çağrıları üyelerine yapabileceğiniz `this.Address.State == "WA"`.  
  
 Kural Koşulu Düzenleyicisi aşağıdaki işleçleri destekler:  
  
-   İlişkisel işleçleri: ==, =,! =  
  
-   Karşılaştırma işleçleri: <, \<=, >, > =  
  
-   Aritmetik işleçler: +, -, *, /, MOD  
  
-   Mantıksal işleçler: ve, & &, OR, &#124; &#124; değil,!  
  
-   Bit düzeyinde işleçler: &, &#124;  
  
 İfade İşleç önceliği C# işleci öncelik kuralları izler.  
  
 Kural Koşulu Düzenleyicisi aşağıdaki sayısal ifadeler destekler:  
  
 this.i == 1 D (çözümler 1.0 için)  
  
 this.i 1E1 == (10.0 için çözümler)  
  
 this.i == 1 M (çözümler bir uzun olarak)  
  
 this.i == 1 M (çözümler bir ondalık olarak)  
  
 this.i 1F == (tek bir çözümler)  
  
 this.i 1U == (imzalanmamış int çözümler)  
  
 Koşullar hakkında daha fazla bilgi için bkz: [kullanan koşulları iş akışlarında](http://go.microsoft.com/fwlink?LinkID=65009).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)   
 [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)   
 [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)   
 [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)   
 [Koşul iletişim kutusu (eski) seçin](../workflow-designer/select-condition-dialog-box-legacy.md)   
 [İş akışlarında koşullar kullanma](http://go.microsoft.com/fwlink?LinkID=65009)   
 [Windows Workflow Foundation Kullanıcı Arabirimi Yardımı için Eski Tasarımcı](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)