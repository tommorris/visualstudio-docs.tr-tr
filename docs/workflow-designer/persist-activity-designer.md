---
title: İş Akışı Tasarımcısı - kalıcı etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04c7989f5cc37ec295f9fa778f2120dd372fd99a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="persist-activity-designer"></a>Etkinlik Tasarımcısı Sürdür

**Devam ettir** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Persist> etkinlik.

## <a name="the-persist-activity"></a>Etkinlik Sürdür

<xref:System.Activities.Statements.Persist> Etkinliğini bir iş akışı Mümkünse, diske kaydeder. <xref:System.Activities.Statements.Persist> Etkinlik yürütülemez olarak, örneğin, kalıcı olmayan bölgedeki içinde bir <xref:System.Activities.Statements.TransactionScope> etkinlik. Kullanırsanız, bir <xref:System.Activities.Statements.Persist> etkinlik kalıcı olmayan kapsamında özel durum çalışma zamanında.

### <a name="using-the-persist-activity-designer"></a>Kullanarak etkinlik Tasarımcısı Sürdür

**Devam ettir** etkinlik Tasarımcısı bulunabilir **çalışma zamanı** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç** sekme (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)

**Devam ettir** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle yerleştirilir olduğunda, örneğin olarak içinde açın iş akışı Tasarımcısı yüzeyini bırakılan bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Persist> varsayılan etkinlik **DisplayName** kalan. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **devam ettir** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.

### <a name="the-persist-properties"></a>Özellikler Sürdür

Aşağıdaki tabloda <xref:System.Activities.Statements.Persist> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bazı iş akışı Tasarımcısı yüzeyine düzenlenebilir.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Persist> etkinlik. Kalan varsayılandır. Görünen ad kesinlikle gerekli olmamakla birlikte, bir görünen ad kullanmak için en iyi bir uygulamadır.|

## <a name="see-also"></a>Ayrıca bkz.

- [Çalışma Zamanı](../workflow-designer/runtime-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)