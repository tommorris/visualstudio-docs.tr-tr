---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: bir etkinlik Tasarımcısı kitaplığı oluşturma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d05ddb48e88627f4b7ab4112c164b5129ddba910
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974597"
---
# <a name="how-to-create-an-activity-designer-library"></a>Nasıl yapılır: bir etkinlik Tasarımcısı kitaplığı oluşturma
Özel Etkinlik tasarımcıları, standart veya özel bir aktivite için kullanıcı arabirimi oluşturmak üzere izin verir. Kullanıcı arabirimi karmaşıklığını denetlemek ve bir etkinliğin birden fazla etkinlik Tasarımcısı oluşturma olanağı vardır. Bu senaryo için birden çok İzleyici uyarlanmış tasarımcıları oluşturmanıza olanak sağlar.

## <a name="to-create-an-activity-designer-library"></a>Bir etkinlik Tasarımcısı kitaplığı oluşturmak için

1.  Visual Studio 2010'u başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje** açmak için **yeni proje** iletişim kutusu.

3.  İçinde **proje türleri** bölmesinde, **iş akışı** da **Visual C#** veya **Visual Basic** gruplandırmaları bağlı olarak, tercih edilen dili.

4.  İçinde **şablonları** bölmesinde, **etkinlik Tasarımcısı Kitaplığı**.

5.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.

6.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.

7.  İçinde **çözüm** kutusunda, çözümünüz için açıklayıcı bir ad yazın ve ardından **Tamam**.

    > [!NOTE]
    > Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözüm Visual Studio 2010'da açın, çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, sonra **Yeni proje** açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.

8.  Proje şablonu bir etkinlik Tasarımcısı tanımı XAML ve kaynak kodu arka plan kodu uygulama dosyasında oluşturur. Windows iş akışı Tasarımcısı açılır ve tuvale, etkinlik Tasarımcısı için görüntüler.

9. Sürükleme Windows Presentation Foundation (WPF) denetimleri **araç** özel etkinlik Tasarımcısı'nda kullanmak için tasarım yüzeyine.  Özel Etkinlik Tasarımcısı uygulamak nasıl bir örnek için bkz: [nasıl yapılır: özel bir etkinlik Tasarımcısı oluşturma](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer).

    > [!WARNING]
    > Özel Etkinlik tasarımcıları, varsayılan .NET Framework 4activities ettirilmesi de özel etkinlikler için kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

- [İş Akışı Projesi Oluşturma](../workflow-designer/creating-a-workflow-project.md)