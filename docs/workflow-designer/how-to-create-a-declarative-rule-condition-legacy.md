---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bildirim temelli Kural koşulu (eski) oluşturma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- declarative rule conditions
- condition statements, declarative rule conditions
- Rule Condition Editor dialog box
ms.assetid: 804b6129-c433-408f-a424-46987967730c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 43b359040256788db240274f43f706b41f01d021
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977949"
---
# <a name="how-to-create-a-declarative-rule-condition-legacy"></a>Nasıl yapılır: bildirim temelli Kural koşulu (eski) oluşturma

Bu konu, .NET Framework sürüm 3.5 ya da WinFX hedefleyen eski Windows iş akışı Tasarımcısı'nı kullanarak bir kural koşulu bildirmek açıklar.

Bir koşul deyimi değerlendiren **True** veya **False**. Bir bildirim temelli Kural koşulu kullanılarak oluşturulan bir koşul deyimi olan [Kural Koşulu Düzenleyicisi iletişim kutusu (eski)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md) ve iş akışı ile XML olarak depolanır. İş akışı durumu ve birden çok koşulları birleştirir Boolean cebiri karşılaştırmak koşulları içerebilir.

Bildirim temelli kural koşulları, aşağıdaki Windows Workflow Foundation out-of-box etkinlikler kullanılır:

-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)

-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

## <a name="to-create-a-declarative-rule-condition-using-the-rule-condition-editor"></a>Kural Koşulu Düzenleyicisi'ni kullanarak bir bildirim temelli Kural koşulu oluşturmak için

1.  Etkinliğin içinde **özellikleri** penceresinde tıklatın **koşul** özelliği veya **UntilCondition** etkinliğe bağlı olarak özellik.

2.  Seçin **bildirim temelli Kural koşulu** özelliği için listeden.

3.  Genişletme **koşulu** veya **UntilCondition** özelliği.

4.  Tıklatın **ConditionName** özelliği.

5.  Tıklatın **ConditionName** üç nokta **[...]**  açmak için **seçin koşulu** iletişim kutusu.

6.  Tıklatın **yeni koşul** açmak için **Kural Koşulu Düzenleyicisi** iletişim kutusu.

7.  Koşul ifadesi yazın **koşulu** metin kutusu.

     Koşul ifadeleri oluşturma hakkında daha fazla bilgi için bkz: [Kural Koşulu Düzenleyicisi iletişim kutusu (eski)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md).

8.  Koşul ifadesi oluşturmayı tamamladığınızda tıklatın **Tamam** iletişim kutusunu kapatmak ve atanmış bir ad ile Kural koşulu oluşturmak için.

     **Seçin koşulu** iletişim kutusu açılır.

     Nasıl kullanılacağı hakkında bilgi için **seçin koşulu** iletişim kutusu, bkz: [koşulu iletişim kutusunu (eski)](../workflow-designer/select-condition-dialog-box-legacy.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)
- [ConditionedActivityGroup kullanma](http://go.microsoft.com/fwlink?LinkID=65066)
- [Öğeye etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65075)
- [Çoğaltıcı etkinliğini kullanma](http://go.microsoft.com/fwlink?LinkID=65080)
- [While kullanarak etkinliği](http://go.microsoft.com/fwlink?LinkID=65091)
- [Kural Koşulu Düzenleyicisi İletişim Kutusu (Eski)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)
- [Koşul Seç İletişim Kutusu (Eski)](../workflow-designer/select-condition-dialog-box-legacy.md)
- [İş akışlarında koşullar kullanma](http://go.microsoft.com/fwlink?LinkID=65009)