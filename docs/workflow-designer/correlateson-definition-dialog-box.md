---
title: "CorrelatesOn tanımı iletişim kutusunu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: babe684c0fd4eeec1a00e4f44868bfc0a67e5f9d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="correlateson-definition-dialog-box"></a>CorrelatesOn tanımı iletişim kutusu
**CorrelatesOn** iletişim kutusu kullanılıyor [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] düzenlemek için <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> özelliği bir <xref:System.ServiceModel.Activities.Receive> etkinlik. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][alma](../workflow-designer/receive-activity-designer.md) konu.  
  
 Geçişi arasındaki bağıntı <xref:System.ServiceModel.Activities.Receive> etkinlikleri nasıl farklı hizmet işlemleri bağlanmak birbirleri ile bir iş akışında belirtir.  
  
 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **CorrelatesOn** iletişim kutusu.  
  
|Arabirim Öğesi|Açıklama|  
|----------------|-----------------|  
|**CorrelatesWith**|<xref:System.ServiceModel.Activities.CorrelationHandle> Uygun iş akışı örneğine ileti yönlendirmek için kullanılır.|  
|**XPath sorguları**|Gelen iletilere bağıntı veri ayıklamak için kullanılan sorgu içeren bir anahtar/değer çifti. Bu karşılık gelen <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> özelliği. XPath sorguları bulunan bir <xref:System.ServiceModel.MessageQuerySet> nesnesi.|  
  
## <a name="to-launch-the-correlateson-dialog-box"></a>CorrelatesOn iletişim kutusunu başlatmak için  
 **Alma** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir. Bu oluşturur bir <xref:System.ServiceModel.Activities.Receive> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> alma. Seçin **alma** etkinlik Tasarımcısı ve üç nokta düğmesini (toplama) metnini yanındaki tıklatın **CorrelatesOn** özellik için özellik kılavuzunda **CorrelatesOn tanımı**  iletişim kutusu görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Activities.Receive>   
 [Ekle CorrelationInitializers iletişim kutusu](../workflow-designer/add-correlationinitializers-dialog-box.md)   
 [Bağıntı iletişim kutusu ekleme](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)   
 [Bağıntı iletişim kutusu başlatılamadı](../workflow-designer/initialize-correlation-dialog-box.md)