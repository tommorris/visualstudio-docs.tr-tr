---
title: "Nasıl yapılır: bir iş akışı projesine yeni öğe eklemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
caps.latest.revision: "14"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: e2031f084b11f9879fd94f5d2e454e0966ed3787
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Nasıl yapılır: bir iş akışı projesine yeni öğe ekleme
Bir iş akışı projesi oluşturduktan sonra iş akışı etkinlikleri, tasarımcıları ve diğer tanıdık ekleyebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] öğelerini projenize.  
  
 Aşağıdaki tabloda [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] bir iş akışı projesine eklemek öğeleri.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|Etkinlik|Diğer etkinliklerini gibi bir etkinlik. Bu öğeyi seçerek ekler aynı XAML dosyası projeye seçerken elde edebilirsiniz gibi **etkinlik Kitaplığı** için yeni bir proje şablonu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu yordamı, bkz: [nasıl yapılır: bir etkinlik kitaplığı oluşturma](../workflow-designer/how-to-create-an-activity-library.md).|  
|Etkinlik Tasarımcısı|Bir etkinliğin tasarım zamanı deneyimini özelleştirmek için bir tasarımcı. Bu öğeyi seçerek ekler aynı dosyaları projeye seçerken elde edebilirsiniz gibi **etkinlik Tasarımcısı Kitaplığı** için yeni bir proje şablonu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu yordamı, bkz: [nasıl yapılır: bir etkinlik Tasarımcısı kitaplığı oluşturma](../workflow-designer/how-to-create-an-activity-designer-library.md).|  
|Kod etkinliği|Kod içinde yazılmış yürütme mantığı ile etkinlik. Kaynak kodu dosyasının geçersiz kılma ile <xref:System.Activities.CodeActivity.Execute%2A> yöntemi zaten oluşturulur sizin için.|  
|WCF iş akışı hizmeti|A [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] iş akışı etkinlikleri kullanılarak oluşturulan hizmet. Bu öğeyi seçerek ekler aynı dosyaları projeye seçerken elde edebilirsiniz gibi **WCF iş akışı hizmeti uygulaması** için yeni bir proje şablonu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Bu yordamı, bkz: [nasıl yapılır: bir WCF iş akışı hizmeti uygulaması oluştur](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|  
  
### <a name="to-add-a-new-item-to-a-workflow-project"></a>Bir iş akışı projesine yeni öğe eklemek için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle...** .  
  
     **Yeni Öğe Ekle** iletişim kutusu açılır.  
  
2.  İçinde **yüklü şablonlar** bölmesinde, **iş akışı** grubu.  
  
3.  Dört öğelerden birini seçin. Önceki tabloda kullanılabilir seçenekler listeler.  
  
4.  Öğe için uygun bir ad yazın **adı** iletişim kutusunun altındaki kutusunu.  
  
5.  Tıklatın **Ekle** geçerli iş akışı projeye öğe eklemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)