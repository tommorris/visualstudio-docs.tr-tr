---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir iş akışı projesine yeni öğe ekleme'
ms.date: 06/25/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3f1202c87986eab6af899a3d4c3b7a5f62e5af6
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757685"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Nasıl yapılır: bir iş akışı projesine yeni öğe ekleme

Bir iş akışı projesi oluşturduktan sonra iş akışı etkinlikleri, tasarımcıları ve tanıdık diğer Visual Studio öğeleri projenize ekleyebilirsiniz.

Aşağıdaki tabloda, bir iş akışı projesine eklemek Windows Workflow Foundation (WF) öğeleri listeler:

|Ad|Açıklama|
|----------|-----------------|
|Etkinlik|Diğer etkinliklerini gibi bir etkinlik. Bu öğeyi seçerek ekler aynı XAML dosyası projeye seçerken elde edebilirsiniz gibi **etkinlik Kitaplığı** için yeni bir proje şablonu. Hakkında daha fazla bilgi için bu yordamı, bkz: [nasıl yapılır: bir etkinlik kitaplığı oluşturma](../workflow-designer/how-to-create-an-activity-library.md).|
|Etkinlik Tasarımcısı|Bir etkinliğin tasarım zamanı deneyimini özelleştirmek için bir tasarımcı. Bu öğeyi seçerek ekler aynı dosyaları projeye seçerken elde edebilirsiniz gibi **etkinlik Tasarımcısı Kitaplığı** için yeni bir proje şablonu. Hakkında daha fazla bilgi için bu yordamı, bkz: [nasıl yapılır: bir etkinlik Tasarımcısı kitaplığı oluşturma](../workflow-designer/how-to-create-an-activity-designer-library.md).|
|Kod etkinliği|Kod içinde yazılmış yürütme mantığı ile etkinlik. Kaynak kodu dosyasının geçersiz kılma ile <xref:System.Activities.CodeActivity.Execute%2A> yöntemi zaten oluşturulur sizin için.|
|WCF iş akışı hizmeti|A [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] iş akışı etkinlikleri kullanılarak oluşturulan hizmet. Bu öğeyi seçerek ekler aynı dosyaları projeye seçerken elde edebilirsiniz gibi **WCF iş akışı hizmeti uygulaması** için yeni bir proje şablonu. Bu yordam hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir WCF iş akışı hizmeti uygulaması oluştur](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|

## <a name="to-add-a-new-item-to-a-workflow-project"></a>Bir iş akışı projesine yeni öğe eklemek için

1. Üzerinde **proje** menüsünde, select **Yeni Öğe Ekle**.

   **Yeni Öğe Ekle** iletişim kutusu açılır.

1. Sol bölmede seçin **iş akışı** kategori ve iş akışı öğesi şablonu seçin.

   > [!NOTE]
   > Görmüyorsanız, **iş akışı** kategori, ilk yükleme **Windows Workflow Foundation** Visual Studio 2017'in bileşeni. Ayrıntılı yönergeler için bkz: [Windows Workflow Foundation yüklemek](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation).

1. Öğesi için bir ad girin **adı** iletişim kutusunun altındaki kutusunu.

1. Seçin **Ekle** projeye öğe eklemek için.

## <a name="see-also"></a>Ayrıca bkz.

- [Bir iş akışı projesi oluşturma](../workflow-designer/creating-a-workflow-project.md)