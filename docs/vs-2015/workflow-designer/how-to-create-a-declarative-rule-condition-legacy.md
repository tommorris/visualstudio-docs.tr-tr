---
title: 'Nasıl yapılır: bildirime dayanan Kural koşulu (eski) oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- declarative rule conditions
- condition statements, declarative rule conditions
- Rule Condition Editor dialog box
ms.assetid: 804b6129-c433-408f-a424-46987967730c
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 59eebe93b5c11fa1b02dc9ae481d0658010e961b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692040"
---
# <a name="how-to-create-a-declarative-rule-condition-legacy"></a>Nasıl yapılır: bildirime dayanan Kural koşulu (eski) oluşturma
Bu konu, bir kural koşulu kullanılarak bildirmek açıklar [!INCLUDE[wfd1](../includes/wfd1-md.md)] hedefleyen [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] veya [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Bir koşul deyimi değerlendiren **True** veya **False**. Bildirime dayanan Kural koşulu kullanılarak oluşturulan bir koşul deyimdir [Kural Koşulu Düzenleyicisi iletişim kutusu (eski)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md) ve sahip iş akışı XML olarak depolanır. İş akışı durumunu ve birden fazla doğrulamaları birleştiren bir Boolean Cebir karşılaştırma doğrulamaları içerebilir.  
  
 Bildirime dayanan kural koşulları aşağıdaki Windows Workflow Foundation out-of-box etkinliklerini kullanılır:  
  
-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)  
  
-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)  
  
-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)  
  
-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)  
  
-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)  
  
### <a name="to-create-a-declarative-rule-condition-using-the-rule-condition-editor"></a>Kural Koşulu Düzenleyicisi'ni kullanarak bir bildirime dayanan Kural koşulu oluşturma  
  
1.  Etkinliğin içinde **özellikleri** penceresinde tıklayın **koşul** özelliği veya **UntilCondition** etkinliğe bağlı bir özellik.  
  
2.  Seçin **bildirim temelli bir kural koşulu** özelliği için listeden.  
  
3.  Genişletin **koşul** veya **UntilCondition** özelliği.  
  
4.  Tıklayın **ConditionName** özelliği.  
  
5.  Tıklayın **ConditionName** üç nokta **[...]**  açmak için **koşulu seçin** iletişim kutusu.  
  
6.  Tıklayın **yeni koşul** açmak için **Kural Koşulu Düzenleyicisi** iletişim kutusu.  
  
7.  Koşul ifadesi türü **koşul** metin kutusu.  
  
     Koşul ifadeleri oluşturma hakkında daha fazla bilgi için bkz: [Kural Koşulu Düzenleyicisi iletişim kutusu (eski)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md).  
  
8.  Koşul ifadesi oluşturmayı tamamladığınızda, tıklayın **Tamam** iletişim kutusunu kapatmak ve Kural koşulu ile atanan bir ad oluşturun.  
  
     **Koşulu seçin** iletişim kutusu açılır.  
  
     Nasıl kullanılacağı hakkında daha fazla bilgi için **koşulu seçin** iletişim kutusu, bakın [seçin koşul iletişim kutusu (eski)](../workflow-designer/select-condition-dialog-box-legacy.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski iş akışı etkinlikleri](../workflow-designer/legacy-workflow-activities.md)   
 [ConditionedActivityGroup kullanma](http://go.microsoft.com/fwlink?LinkID=65066)   
 [Öğeye etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65075)   
 [Çoğaltıcı etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65080)   
 [While kullanarak etkinlik](http://go.microsoft.com/fwlink?LinkID=65091)   
 [Kural Koşulu Düzenleyicisi iletişim kutusu (eski)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)   
 [Koşul seç iletişim kutusu (eski)](../workflow-designer/select-condition-dialog-box-legacy.md)   
 [İş akışlarında koşullar kullanma](http://go.microsoft.com/fwlink?LinkID=65009)