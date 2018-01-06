---
title: "Nasıl yapılır: uygulama bir Windows Communication Foundation sözleşmesi işlemi (eski) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d6aeb20e-fac8-4a9d-bd26-ae78bef96b41
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 8800055878c53adce195bbf7078da410c12128da
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-a-windows-communication-foundation-contract-operation-legacy"></a>Nasıl yapılır: uygulama bir Windows Communication Foundation sözleşmesi işlemi (eski)
Bu konuda nasıl uygulanacağını açıklar bir [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] sözleşme eski kullanarak işlemini [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] hedefleyen [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Sürükleme sonra bir **ReceiveActivity** araç etkinliğinden iş akışı tasarım yüzeyine ya da oluşturduğunuz yeni bir [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] sözleşme veya var olan bir sözleşmeyi alma ve işlemler uygulayın. Seçin ve/veya sizin oluşturup aracılığıyla işlemlerini [seçin işlem iletişim kutusu (eski)](../workflow-designer/choose-operation-dialog-box-legacy.md).  
  
### <a name="to-implement-a-wcf-contract-operation"></a>Bir WCF sözleşmesi işlemi uygulamak için  
  
1.  Çift **ReceiveActivity** etkinlik Tasarımcısı'nda veya yanındaki üç nokta düğmesini tıklatın **ServiceOperationInfo** özelliğinde **özellikleri** bölmesi.  
  
2.  Aşağıdakilerden birini yapın:  
  
    -   Tıklatın **ekleme Sözleşme** iletişim kutusunun sağ üst köşedeki. Bu yeni bir oluşturacak [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] sözleşme ve sizin için işlem.  
  
         veya  
  
    -   Tıklatın **alma** iletişim kutusunun sağ üst köşedeki. [Göz atın ve bir .NET türünü seç iletişim kutusu (eski)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) açar. Bir derlemeyi ya da istediğiniz sözleşme içeren projesi arayın. Sözleşme seçin ve tıklatın **Tamam**.  
  
     Bir sözleşme oluşturulan veya içeri sonra yeni işlemler için oluşturulan veya içeri aktarılan sözleşme ekleyebilirsiniz. Yeni işlem eklemek, sözleşmeyi seçin ve **ekleme işlemi** iletişim kutusunun sağ üst köşedeki. Ekleme işlemleri tamamladığınızda, 3. adıma geçin.  
  
3.  İle ilişkilendirmek istediğiniz işlemi seçin **ReceiveActivity** etkinlik. İşlem adı, parametreleri, özellikleri ve izin ayarlarını değiştirerek işlemi tanımını yönetebilirsiniz.  
  
     Adını değiştirmek için yeni adı girin **işlem adı** metin kutusu.  
  
     Tıklatın **parametreleri** işlem parametreleri erişmek için sekme. Ad, tür veya bir parametre yönünü değiştirmek yanı sıra ekleyebilir veya işlemi parametreleri silebilirsiniz.  
  
     Tıklatın **özellikleri** işlemi işlemi koruma düzeyi ve desteklenen ileti exchange işlevselliğini erişmek için sekme.  
  
     Tıklatın **izinleri** sekmesinde hangi gruplara işlemi uygulamak için izin verildiğini belirtmek için.  
  
4.  Tıklatın **Tamam** ve **ReceiveActivity** etkinlik uyguladığı işlemi için işlem adı görüntülenir.  
  
5.  Bulacağınızı içinde bu işlemi uygulanması için kullanılacak iş akışı etkinlikleri yerleştirin **ReceiveActivity** etkinlik.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem iletişim kutusu (eski) seçin](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [Nasıl yapılır: bir WCF sözleşmesi işlemi (eski) çağırma](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)