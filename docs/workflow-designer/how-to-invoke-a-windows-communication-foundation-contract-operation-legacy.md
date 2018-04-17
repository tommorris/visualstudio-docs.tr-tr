---
title: 'Nasıl yapılır: bir Windows Communication Foundation sözleşmesi işlemi (eski) çağırma | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: a9058345-708f-4fcf-8739-2a43e5285b7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c97b62f7ddfbe46ac5ede4aefba53e50020f3b65
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-invoke-a-windows-communication-foundation-contract-operation-legacy"></a>Nasıl yapılır: bir Windows Communication Foundation sözleşmesi işlemi (eski) çağırma
Bu konu, çağrılacak açıklar bir [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] sözleşme hedefler eski Windows iş akışı Tasarımcısı kullanarak işlemini [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

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

## <a name="see-also"></a>Ayrıca bkz.

- [İşlem Seç İletişim Kutusu (Eski)](../workflow-designer/choose-operation-dialog-box-legacy.md)
- [Nasıl yapılır: uygulama bir WCF sözleşmesi işlemi (eski)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)
- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)