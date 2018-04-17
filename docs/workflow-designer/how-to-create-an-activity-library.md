---
title: 'Nasıl yapılır: bir etkinlik kitaplığı oluşturma | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: faa7c593d27474c0980e7c7df7bf932bd2d5431d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-an-activity-library"></a>Nasıl yapılır: bir etkinlik kitaplığı oluşturma
Özel etkinlikler belirli İş süreçlerinizi bir iş akışında model oluşturmak için kullanılır. Etkinlik kitaplığı şablonunda [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] görsel olarak Windows iş akışı Tasarımcısı'nı kullanarak bu tür özel etkinlikler oluşturmanıza olanak sağlaması için sağlanan.

### <a name="to-create-a-workflow-activity-library"></a>Bir iş akışı etkinlik kitaplığı oluşturmak için

1.  Başlat [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje...** .

     **Yeni proje** iletişim kutusu açılır.

3.  İçinde **proje türleri** bölmesinde, **iş akışı** da **Visual C#** projeleri veya **Visual Basic** gruplandırmaları bağlı olarak, dil tercihi.

4.  İçinde **şablonları** bölmesinde, **etkinlik Kitaplığı**.

5.  İçinde **adı** kutusuna tanınmasını kolaylaştırmak için projeniz için açıklayıcı bir ad yazın.

6.  İçinde **konumu** kutusuna istediğiniz projeyi kaydedin veya dizinde **Gözat** gitmek için.

7.  İçinde **çözüm** kutusunda, çözümünüz için açıklayıcı bir ad yazın ve ardından **Tamam**.

    > [!NOTE]
    > Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözümde açmak [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, ardından **Yeni proje...** açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.

8.  Proje şablonu XAML içinde bir etkinlik tanımı oluşturur. Windows iş akışı Tasarımcısı açar ve özel etkinliklerinizi tuvale görüntüler.

9. Bir etkinlikten sürükleyin **araç** özel etkinlik eklemek için tasarım yüzeyine.

    > [!CAUTION]
    > Yalnızca bir alt etkinlik özel etkinliklerinizi gövdesinde izin verilir; Ancak, bu alt etkinlik bileşik bir etkinlik gibi olabilir bir <xref:System.Activities.Statements.Sequence> etkinlik veya <xref:System.Activities.Statements.Flowchart> etkinlik.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Etkinlik Oluşturma](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)