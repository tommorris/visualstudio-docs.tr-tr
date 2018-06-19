---
title: İş Akışı Tasarımcısı - geçiş etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Transition.UI
ms.assetid: f6e8b5cc-7fb8-4699-9703-f3c9fc7cc316
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0f63369c67470378856133b912e6da48f924bb45
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977503"
---
# <a name="transition-activity-designer"></a>Geçiş etkinlik Tasarımcısı

A <xref:System.Activities.Statements.Transition> iki durumları arasında geçiş temsil eder.

## <a name="using-the-transition-activity-designer"></a>Geçiş etkinliği Tasarımcısı'nı kullanarak

Geçiş etkinlik Tasarımcısı iki durumlu arasında bir geçiş yapılandırmanıza olanak sağlar.

### <a name="transition-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda geçiş özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.Transition> Tasarımcısı'nda nasıl kullanıldığını açıklar ve iş akışı Tasarımcısı'nı kullanarak ayarlanabilir özellikleri.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.Transition.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.Transition> etkinlik Tasarımcısı. Varsayılan değer **T1**. Değeri, özellik Kılavuzu, genişletilmiş geçiş Tasarımcısı üstbilgisinin ve eylem bölümü genişletilmiş geçiş Tasarımcısı'nda başlığı düzenlenebilir. <xref:System.Activities.Activity.DisplayName%2A> İş akışı Tasarımcısı'nı üstünde görüntülenen içerik haritası Gezinti kullanılır.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.Transition.Condition%2A>|False|Varsa, değerlendirilmelidir bir ifade belirtir **True** denetim hedef duruma geçmeden önce. Bu durum, özellik kılavuzunda ve genişletilmiş geçiş Tasarımcısı'nda düzenlenebilir. Paylaşılan bir geçiş aşamasında birden çok koşul geçiş Tasarımcısı'nda görünme sırasını değerlendirilir. **Not:** unutmayın <xref:System.Activities.Statements.Transition.Condition%2A> bir geçişin değerlendiren **False** (veya bir paylaşılan tetikleyici geçiş koşulların tümü için değerlendirin **False**), geçiş gerçekleşmez ve durumundan tüm geçişler için tüm Tetikleyicileri zamanlanacak. Bu öğreticide, bu durum koşulları yapılandırılmış yol nedeniyle meydana olamaz (tahmin doğru veya yanlış olmasına için belirli eylemler uyguluyoruz).|
|**Kaynak**|Doğru|Bu geçiş kaynaklandığı durumu gösterir. Kaynak durumu adını tıklatarak designer görünüm bu durumu için genişletilmiş görünümünü geçer. Bu değer, geçiş oluşturulur ve değiştirilemez olduğunda ayarlanır.|
|<xref:System.Activities.Statements.Transition.Trigger%2A>|False|Geçişi, tamamlama başlatan etkinlik belirtir. Bu etkinlik ayarlamak için bir etkinlikten sürükleyin **araç** ve üzerine bırakın **tetikleyici** geçişi bölümü.|
|<xref:System.Activities.Statements.Transition.Action%2A>|False|Tetikleyici etkinlik tamamlandığında çalıştırılan etkinlik belirtir ve <xref:System.Activities.Statements.Transition.Condition%2A>, varsa, değerlendiren **doğru**. Bu etkinlik sonra hedef duruma geçerek sonra yürütülür <xref:System.Activities.Statements.State.Exit%2A> kaynak durumu için etkinlik varsa, gerçekleştirilir. Geçiş Tasarımcısı genişletildiğinde, bu değer bir etkinlikten sürükleyerek ayarlanabilir **araç** ve üzerine bırakmadan **eylem** geçişi bölümü. Tek bir geçiş için birden fazla eylem olabilir. Tek tek eylemleri genişletilmiş ve sözleşme yapılan ve yukarı tıklayarak ya da aşağı olduğunda geçiş birden çok Eylemler eylemini görüntülenen ok sıralanabilir.|
|**Hedef**|Doğru|Geçiş tamamlandıktan sonra Durum makinesi için geçiş durumu gösterir. Bu karşılık <xref:System.Activities.Statements.Transition.To%2A> nesne modelinde geçişin özelliği. Hedef durumu adını tıklatarak designer görünüm bu durumu için genişletilmiş görünümünü geçer. Bu değer, geçiş oluşturulduğunda ve Tasarımcısı'nda hedef durumu geçişi bağlandığı oku sürükleyerek değiştirilebilir ayarlanır.|

### <a name="creating-transitions"></a>Geçişler oluşturma

Geçişler, bir satır bir durumdan diğerine sürükleme ya da durum başka bir duruma sürüklendiğinde görüntülenen üçgenler üzerine bir durumda bırakarak oluşturulur. Sürükleyerek bir geçiş oluşturmak için fareyi kaynak durumu kenarına getirin ve bir satır kaynak durumundan hedef duruma sürükleyin. Bir geçiş tarafından bırakma oluşturmak için hedef durumu sürükleyin ve kaynak durumu getirin ve onu görünen dört üçgenler birini üzerine kaynak durumu bırakın. Hedef durumu gelen sürüklenen ya da yeni bir durum olabilir **araç**, veya mevcut bir durumu sürüklendiğinde iş akışı Tasarımcısı'ndan.

> [!NOTE]
> İş Akışı Tasarımcısı'nı kullanarak oluşturulan kadar 76 geçişleri Durum makinesi tek bir durumda olabilir. Tasarımcı dışında oluşturulan iş akışı için bir durum için geçişleri sınırını yalnızca sistem kaynaklarının yetersizliği sınırlıdır.

Paylaşılan tetikleyici geçişleri aynı tetikleyici olay paylaşan geçişleri kümesidir. Paylaşılan bir tetikleyici yaygın bir tetikleyici olayı paylaşmak için birden çok geçişleri yapılandırılmış ifadelerin göre bir hedef duruma koşullu progression sağlar. Bir geçiş için ek eylemler ekleyin ve paylaşılan bir geçiş oluşturmak için istenen geçiş başlangıcını gösterir daireye tıklayın ve belirtilen istenen duruma sürükleyin. Yeni geçiş aynı tetikleyici ilk geçiş olarak paylaşır, ancak benzersiz bir koşul veya eylem sahip olur. Paylaşılan geçişleri de oluşturulabilir gelen geçiş Tasarımcısı'nda tıklayarak **paylaşılan tetikleyici geçiş Ekle** geçiş Tasarımcısı'nı ve ardından istenen hedef durumundan seçerek altındaki  **Bağlanmak için kullanılabilir durumları** açılır.

## <a name="see-also"></a>Ayrıca bkz.

- [Durum makinesi](../workflow-designer/statemachine-activity-designer.md)
- [Son durum](../workflow-designer/finalstate-activity-designer.md)
- [Durumu](../workflow-designer/state-activity-designer.md)