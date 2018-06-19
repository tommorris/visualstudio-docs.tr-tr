---
title: İş Akışı Tasarımcısı - CorrelatesOn tanımı iletişim kutusu
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 490740f8f2682ad6b82bc60edb5d24e6d410b192
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970304"
---
# <a name="correlateson-definition-dialog-box"></a>CorrelatesOn tanımı iletişim kutusu

**CorrelatesOn** iletişim kutusu Windows iş akışı Tasarımcısı'nda düzenlemek için kullanılan <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> özelliği bir <xref:System.ServiceModel.Activities.Receive> etkinlik. Daha fazla bilgi için bkz: [alma](../workflow-designer/receive-activity-designer.md) konu.

Geçişi arasındaki bağıntı <xref:System.ServiceModel.Activities.Receive> etkinlikleri nasıl farklı hizmet işlemleri bağlanmak birbirleri ile bir iş akışında belirtir.

Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **CorrelatesOn** iletişim kutusu.

|Arabirim Öğesi|Açıklama|
|----------------|-----------------|
|**CorrelatesWith**|<xref:System.ServiceModel.Activities.CorrelationHandle> Uygun iş akışı örneğine ileti yönlendirmek için kullanılır.|
|**XPath sorguları**|Gelen iletilere bağıntı veri ayıklamak için kullanılan sorgu içeren bir anahtar/değer çifti. Bu karşılık gelen <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> özelliği. XPath sorguları bulunan bir <xref:System.ServiceModel.MessageQuerySet> nesnesi.|

## <a name="to-launch-the-correlateson-dialog-box"></a>CorrelatesOn iletişim kutusunu başlatmak için

**Alma** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir her yerde iş akışı Tasarımcısı yüzeyini açın. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> alma. Seçin **alma** etkinlik Tasarımcısı ve üç nokta düğmesini (toplama) metnini yanındaki tıklatın **CorrelatesOn** özellik için özellik kılavuzunda **CorrelatesOn tanımı**  iletişim kutusu görünür.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.ServiceModel.Activities.Receive>
- [CorrelationInitializer Ekle İletişim Kutusu](../workflow-designer/add-correlationinitializers-dialog-box.md)
- [Bağıntı iletişim kutusu ekleme](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)
- [Bağıntıyı Başlat İletişim Kutusu](../workflow-designer/initialize-correlation-dialog-box.md)