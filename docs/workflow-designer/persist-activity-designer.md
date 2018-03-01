---
title: "Etkinlik Tasarımcısı kalıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 3bd0ef80e5255a828ad31ebfa2398ff6f8b1a1e8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="persist-activity-designer"></a>Etkinlik Tasarımcısı Sürdür
**Devam ettir** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Persist> etkinlik.  
  
## <a name="the-persist-activity"></a>Etkinlik Sürdür  
 <xref:System.Activities.Statements.Persist> Etkinliğini bir iş akışı Mümkünse, diske kaydeder. <xref:System.Activities.Statements.Persist> Etkinlik yürütülemez olarak, örneğin, kalıcı olmayan bölgedeki içinde bir <xref:System.Activities.Statements.TransactionScope> etkinlik. Kullanırsanız, bir <xref:System.Activities.Statements.Persist> etkinlik kalıcı olmayan kapsamında özel durum çalışma zamanında.  
  
### <a name="using-the-persist-activity-designer"></a>Kullanarak etkinlik Tasarımcısı Sürdür  
 **Devam ettir** etkinlik Tasarımcısı bulunabilir **çalışma zamanı** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç** sekme (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 **Devam ettir** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Persist> varsayılan etkinlik **DisplayName** kalan. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **devam ettir** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
### <a name="the-persist-properties"></a>Özellikler Sürdür  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Persist> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzunda düzenlenebilir ve bunların bazıları üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Persist> etkinlik. Kalan varsayılandır. Görünen ad kesinlikle gerekli olmamakla birlikte, bir görünen ad kullanmak için en iyi bir uygulamadır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma zamanı](../workflow-designer/runtime-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)