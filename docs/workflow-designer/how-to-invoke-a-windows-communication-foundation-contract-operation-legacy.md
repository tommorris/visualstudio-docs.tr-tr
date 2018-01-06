---
title: "Nasıl yapılır: bir Windows Communication Foundation sözleşmesi işlemi (eski) çağırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a9058345-708f-4fcf-8739-2a43e5285b7a
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: fdc27d34efef818dae30d1f54f5f3a67e7408d7d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-invoke-a-windows-communication-foundation-contract-operation-legacy"></a>Nasıl yapılır: bir Windows Communication Foundation sözleşmesi işlemi (eski) çağırma
Bu konu, çağrılacak açıklar bir [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] sözleşme eski kullanarak işlemini [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] hedefleyen [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Sürükleme sonra bir **SendActivity** etkinlik araç kutusu'ndan iş akışı tasarım yüzeyine, var olan bir sözleşmeyi içeri aktarabilir ve hangi işlemi değerinden çağrılacak belirlemek **SendActivity** Etkinlik. Sizin ve işlemlerini aracılığıyla seçin [seçin işlem iletişim kutusu (eski)](../workflow-designer/choose-operation-dialog-box-legacy.md).  
  
 Ayrıca, hizmetiniz ile bir yapılandırma dosyası kullanıyorsanız, belirtmeniz gerekecektir bir <xref:System.Workflow.Activities.ChannelToken>. <xref:System.Workflow.Activities.ChannelToken> Gönder etkinliği iş akışı hizmetine bağlanmak için kullanılacak olduğuna uç nokta yapılandırması tanımlar.  
  
### <a name="to-invoke-a-wcf-contract-operation-from-a-sendactivity-activity"></a>Bir WCF sözleşmesi işlemi SendActivity etkinliğinden çağırmak için  
  
1.  Çift **SendActivity** etkinlik Tasarımcısı'nda veya yanındaki üç nokta düğmesini tıklatın **ServiceOperationInfo** özelliğinde **özellikleri** bölmesi.  
  
2.  Zaman **seçin işlemi** iletişim kutusunu açar, tıklatın **alma** iletişim kutusunun sağ üst köşedeki.  
  
     [Göz atın ve bir .NET türünü seç iletişim kutusu (eski)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) açar.  
  
3.  Bir derlemeyi ya da istediğiniz sözleşme içeren projesi arayın.  
  
4.  Sözleşme seçin ve tıklatın **Tamam**.  
  
5.  Altında **kullanılabilir işlemleri**, önce çağırma istediğiniz işlemi seçin **Tamam**.  
  
### <a name="to-specify-a-channel-token"></a>Bir kanal belirteci belirtmek için  
  
1.  Seçin <xref:System.Workflow.Activities.SendActivity> etkinlik Tasarımcısı'nda.  
  
2.  İçinde **özellikleri** bölmesinde için bir ad belirtin <xref:System.Workflow.Activities.ChannelToken>. Bu ad, kanal belirteci benzersiz şekilde tanımlar.  
  
3.  Kanal belirteci düğümünü genişletin ve bulacağınızı kullanmak için istemci uç noktası için bir ad belirtin <xref:System.Workflow.Activities.ChannelToken.EndpointName%2A> alan. Yapılandırma dosyası aynı adlı uç nokta yapılandırması kanalı yapılandırmak için kullanılır.  
  
4.  Uç nokta yapılandırması zaten yoksa, yapılandırma dosyanızda oluşturun. İstemci yapılandırma hakkında daha fazla bilgi için bkz: [WCF istemcisi genel bakış](/dotnet/framework/wcf/wcf-client-overview).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem iletişim kutusu (eski) seçin](../workflow-designer/choose-operation-dialog-box-legacy.md)   
 [Nasıl yapılır: uygulama bir WCF sözleşmesi işlemi (eski)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)   
 [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)