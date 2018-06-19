---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir Windows Communication Foundation sözleşmesi işlemi (eski) çağırma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: a9058345-708f-4fcf-8739-2a43e5285b7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b39d2132b29ec1f8fbfd8339bdb8f81e6f752a0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974724"
---
# <a name="how-to-invoke-a-windows-communication-foundation-contract-operation-legacy"></a>Nasıl yapılır: bir Windows Communication Foundation sözleşmesi işlemi (eski) çağırma

Bu konuda hedefleyen eski Windows iş akışı Tasarımcısı'nı kullanarak bir Windows Communication Foundation (WCF) sözleşme işlemini çağırmak .NET Framework sürüm 3.5 veya WinFX açıklar.

Sürükleme sonra bir **SendActivity** araç etkinliğinden iş akışı tasarım yüzeyi için var olan bir sözleşmeyi içeri aktarın. Hangi işlemi, çağrılan belirlemek **SendActivity** etkinlik. Sözleşme ve işlemlerini aracılığıyla seçin [seçin işlem iletişim kutusu (eski)](../workflow-designer/choose-operation-dialog-box-legacy.md).

Hizmetiniz ile bir yapılandırma dosyası kullanıyorsanız, ayrıca, belirtmek ihtiyacınız bir <xref:System.Workflow.Activities.ChannelToken>. <xref:System.Workflow.Activities.ChannelToken> Gönder etkinliği iş akışı hizmetine bağlanmak için kullanılacak olduğuna uç nokta yapılandırması tanımlar.

## <a name="to-invoke-a-wcf-contract-operation-from-a-sendactivity-activity"></a>Bir WCF sözleşmesi işlemi SendActivity etkinliğinden çağırmak için

1.  Çift **SendActivity** etkinlik Tasarımcısı'nda veya yanındaki üç nokta düğmesini tıklatın **ServiceOperationInfo** özelliğinde **özellikleri** bölmesi.

2.  Zaman **seçin işlemi** iletişim kutusunu açar, tıklatın **alma** iletişim kutusunun sağ üst köşedeki.

     [Göz atın ve bir .NET türünü seç iletişim kutusu (eski)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) açar.

3.  Bir derlemeyi ya da istediğiniz sözleşme içeren projesi arayın.

4.  Sözleşme seçin ve tıklatın **Tamam**.

5.  Altında **kullanılabilir işlemleri**, önce çağırma istediğiniz işlemi seçin **Tamam**.

## <a name="to-specify-a-channel-token"></a>Bir kanal belirteci belirtmek için

1.  Seçin <xref:System.Workflow.Activities.SendActivity> etkinlik Tasarımcısı'nda.

2.  İçinde **özellikleri** bölmesinde için bir ad belirtin <xref:System.Workflow.Activities.ChannelToken>. Bu ad, kanal belirteci benzersiz şekilde tanımlar.

3.  Kanal belirteci düğümünü genişletin ve bulacağınızı kullanmak için istemci uç noktası için bir ad belirtin <xref:System.Workflow.Activities.ChannelToken.EndpointName%2A> alan. Yapılandırma dosyası aynı adlı uç nokta yapılandırması kanalı yapılandırmak için kullanılır.

4.  Uç nokta yapılandırması zaten yoksa, yapılandırma dosyanızda oluşturun. İstemci yapılandırma hakkında daha fazla bilgi için bkz: [WCF istemcisi genel bakış](/dotnet/framework/wcf/wcf-client-overview).

## <a name="see-also"></a>Ayrıca bkz.

- [İşlem Seç İletişim Kutusu (Eski)](../workflow-designer/choose-operation-dialog-box-legacy.md)
- [Nasıl yapılır: uygulama bir WCF sözleşmesi işlemi (eski)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)
- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)