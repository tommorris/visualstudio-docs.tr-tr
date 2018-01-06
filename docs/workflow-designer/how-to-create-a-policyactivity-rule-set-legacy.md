---
title: "Nasıl yapılır: bir PolicyActivity kural kümesi (eski) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- PolicyActivity activity, creating rule sets
- Rule Set Editor dialog box
- PolicyActivity activity, selecting rule sets
- Select Rule Set dialog box
- rule sets, creating for PolicyActivity
ms.assetid: f272489d-3342-4511-8b59-6a0fd7a42d70
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 1b57fe5f33bdbc4dfb7ab76856bdd80a3246ea9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-policyactivity-rule-set-legacy"></a>Nasıl yapılır: bir PolicyActivity kural kümesi (eski) oluşturma
Bu konu eski kullanılarak ayarlanan bir ilke etkinlik kuralının nasıl oluşturulacağını açıklar [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] hedefleyen [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Sürüklenen sonra bir **İlkesi** etkinlik öğesinden **araç** mevcut bir kuralı seçin veya yeni bir kural için kümesini oluşturmak isteyeceksiniz iş akışı tasarım yüzeyine [PolicyActivity ](http://go.microsoft.com/fwlink?LinkID=65019) etkinlik. Var olan bir kural kullanarak kümesi seçin [kural kümesi iletişim kutusunu (eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md) ve kullanarak kural kümeleri oluşturma [kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md).  
  
> [!NOTE]
>  Açabilirsiniz [kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) çift tarafından doğrudan iletişim kutusu bir [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) iş akışı tasarım yüzeyine etkinliğini.  
  
### <a name="to-select-or-create-a-rule-set-for-a-policyactivity-activity"></a>Seçin veya bir kural oluşturmak için bir PolicyActivity etkinliği için ayarlandı  
  
1.  Sağ [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)ve ardından **özellikleri** açmak için **özellikleri** penceresi.  
  
2.  Tıklatın **RuleSetReference** özelliği.  
  
3.  Aşağıdakilerden birini yapın:  
  
    -   Tıklatın **RuleSetReference** üç nokta **[...]** ve ardından var olan bir kural kümesi [kural kümesi iletişim kutusunu (eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md). Ardından 10. adıma gidin.  
  
         veya  
  
    -   Bir kural kümesi için bir ad yazın. Tıklatın **RuleSetReference** üç nokta **[...]** ve ardından **Düzenle** içinde [kural kümesi iletişim kutusunu (eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md).  
  
         veya  
  
    -   Bir kural kümesi için bir ad yazın. Genişletme **RuleSetReference** özelliği ve select üç nokta **[...]**  içinde **RuleSet tanımı** özelliği.  
  
         [Kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) açar.  
  
4.  İçinde [kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md), tıklatın **Kuralı Ekle** kuralı kümesine yeni bir kural eklemek için.  
  
5.  Girin **adı**, **öncelik**, ve **yeniden değerlendirme** özelliklerini veya varsayılan değerleri tutun.  
  
6.  İçin metin girin **koşul**.  
  
7.  İçin metin girin **sonra Eylemler** ve **başka eylemler**.  
  
8.  Tıklatın **Kuralı Ekle** yeniden başka bir kural eklemek için.  
  
9. İşiniz bittiğinde **Tamam**'a tıklayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)   
 [Select kural Ayarla iletişim kutusu (eski)](../workflow-designer/select-rule-set-dialog-box-legacy.md)   
 [Kural kümesi Düzenleyici iletişim kutusu (eski)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)   
 [İlke etkinlik kullanma](http://go.microsoft.com/fwlink?LinkID=65004)   
 [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)