---
title: İş Akışı Tasarımcısı - InitializeCorrelation etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.InitializeCorrelation.UI
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b210b5e0d3d0f3638e78331d9db093f7e86079e
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117179"
---
# <a name="initializecorrelation-activity-designer"></a>InitializeCorrelation Etkinlik Tasarımcısı

**InitializeCorrelation** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.InitializeCorrelation> etkinlik. <xref:System.ServiceModel.Activities.InitializeCorrelation> Etkinlik ileti gönderirken ya da bunları alırken önce arasında bir ilişki kurar.

## <a name="the-initializecorrelation-activity"></a>InitializeCorrelation etkinliği

Bir <xref:System.ServiceModel.Activities.InitializeCorrelation> etkinlik bağıntıları gönderme veya bir ileti alma olmadan başlatmak için kullanılır. Genellikle bağıntı gönderirken ya da bir mesaj alarak başlatılır. Bir ileti gönderilen veya alınan önce bağıntı kurulmalıdır kullanırsanız <xref:System.ServiceModel.Activities.InitializeCorrelation> bağıntı başlatılamadı.

### <a name="using-the-initializecorrelation-activity-designer"></a>InitializeCorrelation etkinlik Tasarımcısı'nı kullanarak

Erişim **InitializeCorrelation** etkinlik Tasarımcısı'nda **ileti** kategorisini **araç**.

**InitializeCorrelation** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve iş akışı Tasarımcısı yüzeyini açın. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.ServiceModel.Activities.InitializeCorrelation> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> InitializeCorrelation biri. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **InitializeCorrelation** etkinlik Tasarımcısı veya **DisplayName** kutusunun **özellikleri** penceresi.

<xref:System.ServiceModel.Activities.CorrelationHandle> Olabilir belirtir **bağıntı** alanındaki **özellikleri** penceresinde **InitializeCorrelation** etkinlik Tasarımcı yüzeyine.

Görüntülenecek **başlatma bağıntı** bağıntı tanıtıcısı, başlatmak için kullanılan anahtar-değer çiftleri seçin ve üç nokta düğmesini yanındaki belirtebileceğiniz iletişim kutusu **CorrelationData** alanındaki **özellikleri** penceresi. Veya "Görünümü..." İpucu metnini seçin **InitializeCorrelation** etkinlik Tasarımcı yüzeyine. Bu iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz: [türü koleksiyon Düzenleyicisi iletişim kutusu](../workflow-designer/type-collection-editor-dialog-box.md) makalesi.

### <a name="the-initializecorrelation-properties"></a>InitializeCorrelation özellikleri

Aşağıdaki tabloda <xref:System.ServiceModel.Activities.InitializeCorrelation> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri düzenlenebilecek **özellikleri** penceresi veya iş akışı Tasarımcısı yüzeyinde.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.ServiceModel.Activities.InitializeCorrelation> etkinlik. InitializeCorrelation varsayılan değerdir.<br /><br /> Ancak kolay için varsayılan olmayan bir değer kullanımını <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değildir önerilir.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|<xref:System.ServiceModel.Activities.CorrelationHandle> Bağıntı iş akışı etkinlikleri ilişkilendirmek için kullanılır.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|İletileri iş akışı örneği ile ilişkilendirir bağıntı veri sözlüğü.<br /><br /> Kullanım **başlatma bağıntı** yapılandırmak için iletişim kutusunu <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>. Kullanımı hakkında daha fazla bilgi için bu iletişim kutusunu bkz [türü koleksiyon Düzenleyicisi iletişim kutusu](../workflow-designer/type-collection-editor-dialog-box.md) makalesi.|

## <a name="see-also"></a>Ayrıca bkz.

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [Alma](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Gönder](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)