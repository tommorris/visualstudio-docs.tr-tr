---
title: "Nasıl yapılır: bir etkinlik Tasarımcısı kitaplığı oluşturma | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0f257aabb4b1c2c1b1dce05e34273dc303a8f7da
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-an-activity-designer-library"></a>Nasıl yapılır: bir etkinlik Tasarımcısı kitaplığı oluşturma
Özel Etkinlik tasarımcıları, standart veya özel bir aktivite için kullanıcı arabirimi oluşturmak üzere izin verir. Kullanıcı arabirimi karmaşıklığını denetlemek ve bir etkinliğin birden fazla etkinlik Tasarımcısı oluşturma olanağı vardır. Bu senaryo için birden çok İzleyici uyarlanmış tasarımcıları oluşturmanıza olanak sağlar.

### <a name="to-create-an-activity-designer-library"></a>Bir etkinlik Tasarımcısı kitaplığı oluşturmak için

1.  Başlat [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje...**  açmak için **yeni proje** iletişim kutusu.

3.  İçinde **proje türleri** bölmesinde, **iş akışı** da **Visual C#** veya **Visual Basic** gruplandırmaları bağlı olarak, tercih edilen dili.

4.  İçinde **şablonları** bölmesinde, **etkinlik Tasarımcısı Kitaplığı**.

5.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

6.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

7.  İçinde **çözüm** kutusunda, çözümünüz için açıklayıcı bir ad yazın ve ardından **Tamam**.

    > [!NOTE]
    > Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözümde açmak [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, sonra **Yeni proje...**  açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.

8.  Proje şablonu bir etkinlik Tasarımcısı tanımı XAML ve kaynak kodu arka plan kodu uygulama dosyasında oluşturur. Windows iş akışı Tasarımcısı açılır ve tuvale, etkinlik Tasarımcısı için görüntüler.

9. Sürükleme [!INCLUDE[avalon1](../workflow-designer/includes/avalon1_md.md)] gelen denetimleri **araç** özel etkinlik Tasarımcısı'nda kullanmak için tasarım yüzeyine.  Özel Etkinlik Tasarımcısı uygulamak nasıl bir örnek için bkz: [nasıl yapılır: özel bir etkinlik Tasarımcısı oluşturma](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer).

    > [!WARNING]
    > Özel Etkinlik tasarımcıları, varsayılan ettirilmesi de özel etkinlikler için kullanılabilir [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)]etkinlikler.

## <a name="see-also"></a>Ayrıca bkz.

- [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)