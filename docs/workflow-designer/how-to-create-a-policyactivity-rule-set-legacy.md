---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir PolicyActivity kural kümesi (eski) oluşturma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- PolicyActivity activity, creating rule sets
- Rule Set Editor dialog box
- PolicyActivity activity, selecting rule sets
- Select Rule Set dialog box
- rule sets, creating for PolicyActivity
ms.assetid: f272489d-3342-4511-8b59-6a0fd7a42d70
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 57142fc21bc9db03a338f20a27e20b8af51b48cd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975214"
---
# <a name="how-to-create-a-policyactivity-rule-set-legacy"></a>Nasıl yapılır: bir PolicyActivity kural kümesi (eski) oluşturma

Bu konuda hedefleyen bir ilke etkinlik kural eski Windows iş akışı Tasarımcısı'nı kullanarak kümesini oluşturmak .NET Framework sürüm 3.5 veya WinFX açıklar.

 Sürüklenen sonra bir **İlkesi** etkinlik öğesinden **araç** mevcut bir kuralı seçin veya yeni bir kural için kümesini oluşturmak isteyeceksiniz iş akışı tasarım yüzeyine [PolicyActivity ](http://go.microsoft.com/fwlink?LinkID=65019) etkinlik. Var olan bir kural kullanarak kümesi seçin [kural kümesi iletişim kutusunu (eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md) ve kullanarak kural kümeleri oluşturma [kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md).

> [!NOTE]
> Açabilirsiniz [kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) çift tarafından doğrudan iletişim kutusu bir [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) iş akışı tasarım yüzeyine etkinliğini.

## <a name="to-select-or-create-a-rule-set-for-a-policyactivity-activity"></a>Seçin veya bir kural oluşturmak için bir PolicyActivity etkinliği için ayarlandı

1.  Sağ [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)ve ardından **özellikleri** açmak için **özellikleri** penceresi.

2.  Tıklatın **RuleSetReference** özelliği.

3.  Aşağıdakilerden birini yapın:

    -   Tıklatın **RuleSetReference** üç nokta **[...]** ve ardından var olan bir kural kümesi [kural kümesi iletişim kutusunu (eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md). Ardından 10. adıma gidin.

         -veya-

    -   Bir kural kümesi için bir ad yazın. Tıklatın **RuleSetReference** üç nokta **[...]** ve ardından **Düzenle** içinde [kural kümesi iletişim kutusunu (eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md).

         -veya-

    -   Bir kural kümesi için bir ad yazın. Genişletme **RuleSetReference** özelliği ve select üç nokta **[...]**  içinde **RuleSet tanımı** özelliği.

         [Kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) açar.

4.  İçinde [kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md), tıklatın **Kuralı Ekle** kuralı kümesine yeni bir kural eklemek için.

5.  Girin **adı**, **öncelik**, ve **yeniden değerlendirme** özelliklerini veya varsayılan değerleri tutun.

6.  İçin metin girin **koşul**.

7.  İçin metin girin **sonra Eylemler** ve **başka eylemler**.

8.  Tıklatın **Kuralı Ekle** yeniden başka bir kural eklemek için.

9. İşiniz bittiğinde **Tamam**'a tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

- [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)
- [Kural Kümesi Seç İletişim Kutusu (Eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md)
- [Kural Kümesi Düzenleyicisi İletişim Kutusu (Eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)
- [İlke etkinlik kullanma](http://go.microsoft.com/fwlink?LinkID=65004)
- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)