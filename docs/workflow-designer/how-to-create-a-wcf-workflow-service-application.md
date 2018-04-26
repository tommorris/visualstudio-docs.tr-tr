---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir WCF iş akışı hizmeti uygulaması oluştur'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93fb69862c228a3b6e61467facba188dd20c67c7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>Nasıl yapılır: bir WCF iş akışı hizmeti uygulaması oluştur

Windows Communication Foundation (WCF) iş akışı hizmeti iletileri işlem sınırlarındaki istemciler ve kendilerini arasında iletmek dağıtılmış iletişim hizmetleri uygulamalardır. Hizmet tarafı hizmet sözleşmesini uygulama bildirimli olarak iş akışı etkinlikleri .NET Framework 4'te .NET Framework 3.5 eski iş akışı hizmetlerine benzer bir şekilde yapılır.

## <a name="to-create-a-wcf-workflow-service-application"></a>Bir WCF iş akışı hizmeti uygulaması oluşturmak için

1.  Visual Studio 2010'u başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu açılır.

3.  İçinde **yüklü şablonlar** bölmesinde, **WCF** veya **iş akışı** da **Visual C#** veya **Visual Basic** seçim dilinin bağlı olarak gruplandırmaları.

4.  Orta bölmede seçin **WCF iş akışı hizmeti uygulaması**.

5.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

6.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

7.  İçinde **çözüm** kutusunda, yeni bir çözüm oluşturmak ve ardından seçin **Tamam**.

    > [!NOTE]
    > Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözüm Visual Studio 2010'da açın, çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, ardından  **Yeni proje** açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.

8.  Proje şablonu bir hizmet tanımı XAML olarak oluşturur. Windows iş akışı Tasarımcısı ile Tasarım görünümüne açılır bir <xref:System.Activities.Statements.Sequence> içeren bir dizi etkinlik <xref:System.ServiceModel.Activities.Receive> ve <xref:System.ServiceModel.Activities.SendReply> etkinlikler.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Etkinlik Oluşturma](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)