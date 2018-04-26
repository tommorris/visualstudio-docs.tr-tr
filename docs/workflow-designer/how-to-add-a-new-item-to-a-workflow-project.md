---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir iş akışı projesine yeni öğe ekleme'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0aa2be7fd8ecccbd8de0aa54c2693dd6b02c7e10
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Nasıl yapılır: bir iş akışı projesine yeni öğe ekleme

Projenize bir iş akışı projesi oluşturduktan sonra iş akışı etkinlikleri, tasarımcıları ve tanıdık diğer Visual Studio öğeleri ekleyebilirsiniz.

Aşağıdaki tabloda, bir iş akışı projesine eklemek Windows Workflow Foundation (WF) öğeleri listeler.

|Ad|Açıklama|
|----------|-----------------|
|Etkinlik|Diğer etkinliklerini gibi bir etkinlik. Bu öğeyi seçerek ekler aynı XAML dosyası projeye seçerken elde edebilirsiniz gibi **etkinlik Kitaplığı** için yeni bir proje şablonu. Hakkında daha fazla bilgi için bu yordamı, bkz: [nasıl yapılır: bir etkinlik kitaplığı oluşturma](../workflow-designer/how-to-create-an-activity-library.md).|
|Etkinlik Tasarımcısı|Bir etkinliğin tasarım zamanı deneyimini özelleştirmek için bir tasarımcı. Bu öğeyi seçerek ekler aynı dosyaları projeye seçerken elde edebilirsiniz gibi **etkinlik Tasarımcısı Kitaplığı** için yeni bir proje şablonu. Hakkında daha fazla bilgi için bu yordamı, bkz: [nasıl yapılır: bir etkinlik Tasarımcısı kitaplığı oluşturma](../workflow-designer/how-to-create-an-activity-designer-library.md).|
|Kod etkinliği|Kod içinde yazılmış yürütme mantığı ile etkinlik. Kaynak kodu dosyasının geçersiz kılma ile <xref:System.Activities.CodeActivity.Execute%2A> yöntemi zaten oluşturulur sizin için.|
|WCF iş akışı hizmeti|A [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] iş akışı etkinlikleri kullanılarak oluşturulan hizmet. Bu öğeyi seçerek ekler aynı dosyaları projeye seçerken elde edebilirsiniz gibi **WCF iş akışı hizmeti uygulaması** için yeni bir proje şablonu. Bu yordam hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir WCF iş akışı hizmeti uygulaması oluştur](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|

## <a name="to-add-a-new-item-to-a-workflow-project"></a>Bir iş akışı projesine yeni öğe eklemek için

1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle...** .

     **Yeni Öğe Ekle** iletişim kutusu açılır.

2.  İçinde **yüklü şablonlar** bölmesinde, **iş akışı** grubu.

3.  Dört öğelerden birini seçin. Önceki tabloda kullanılabilir seçenekler listeler.

4.  Öğe için uygun bir ad yazın **adı** iletişim kutusunun altındaki kutusunu.

5.  Tıklatın **Ekle** geçerli iş akışı projeye öğe eklemek için.

## <a name="see-also"></a>Ayrıca bkz.

- [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)