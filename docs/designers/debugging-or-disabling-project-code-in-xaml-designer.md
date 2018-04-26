---
title: Hata ayıklama veya XAML Tasarımcısı'nda proje kodunu devre dışı bırakma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: ac600581-8fc8-49e3-abdf-1569a3483d74
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 9d77aa1d776352edd3a030507bc25086cad47d58
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="debug-or-disable-project-code-in-xaml-designer"></a>Hata ayıklama veya XAML Tasarımcısı'nda proje kodunu devre dışı bırakma

Çoğu durumda, İşlenmeyen özel durumlar XAML Tasarımcısı'nda özellikleri veya farklı değerler döndürebilecek veya farklı bir şekilde uygulamanızı Tasarımcısı'nda çalıştırıldığında iş yöntemlerini erişmeye proje kodu neden olabilir. Başka bir örneği Visual Studio Proje kodda hata ayıklama bu özel durumları çözümlemek ya da özel durumlar Tasarımcısı'nda proje kodunu devre dışı bırakarak geçici olarak engellemek.

Proje kodunu içerir:

-   Özel denetimler ve kullanıcı denetimleri

-   Sınıf kitaplıkları

-   Değer dönüştürücüler

-   Tasarım zamanı veri proje koddan oluşturulan karşı bağlamaları

Visual Studio Proje kodunu devre dışı bırakıldığında, yer tutucular gösterir. Örneğin, Visual Studio veri artık kullanılabilir olduğu bir bağlama ya da artık çalışır durumda bir denetim için bir yer tutucu özellik adını gösterir.

![İşlenmeyen özel durum iletişim](../designers/media/xaml_unhandledexception.png)

## <a name="to-determine-if-project-code-is-causing-an-exception"></a>Proje kodunu bir özel durum neden olup olmadığını belirlemek için

1.  İşlenmeyen özel durum iletişim kutusunda seçin **Tasarımcısı'nı yeniden yüklemek için burayı tıklatın** bağlantı.

2.  Menü çubuğunda seçin **hata ayıklama** > **hata ayıklamayı Başlat** oluşturun ve uygulamayı çalıştırın.

     Uygulama oluşturulur ve başarılı bir şekilde çalışır Tasarımcısı'nda çalışan, proje kodu tarafından tasarım zamanında özel durum neden olabilir.

## <a name="to-debug-project-code-running-in-the-designer"></a>Proje Tasarımcısı'nda çalışan kodu hata ayıklamak için

1.  İşlenmeyen özel durum iletişim kutusunda seçin **çalışan proje kodunu devre dışı bırakın ve Tasarımcısı yeniden yüklemek için burayı tıklatın** bağlantı.

2.  Windows Görev Yöneticisi'nde seçin **Görevi Sonlandır** düğmesi Visual Studio XAML Tasarımcısı'nın şu anda çalışan tüm örneklerini kapatın.

     ![XAML Tasarımcısı örnekleri Görev Yöneticisi](../designers/media/xaml_taskmanager.png)

3.  Visual Studio'da kod veya hata ayıklamak istediğiniz denetimi içeren XAML sayfası açın.

4.  Visual Studio yeni bir örneğini açın ve ardından projenizi ikinci bir örneğini açın.

5.  Proje kodunuzda bir kesme noktası ayarlayın.

6.  Menü çubuğunda, Visual Studio, yeni bir örneğini seçin **hata ayıklama** > **ekleme işlemi için**.

7.  İçinde **ekleme işlemi için** iletişim, **kullanılabilir işlemler** listesinde, seçin **XDesProc.exe**ve ardından **Attach** düğmesi.

     ![XAML Tasarımcısı işlemi](../designers/media/xaml_attach.png)

     XAML Tasarımcısı'nda Visual Studio'nun ilk örneği işlemidir.

8.  Menü çubuğunda Visual Studio'nun ilk örneği seçin **hata ayıklama** > **hata ayıklamayı Başlat**.

     Şimdi, koda Tasarımcısı'nda çalışan geçebilirsiniz.

## <a name="to-disable-project-code-in-the-designer"></a>Tasarımcıda proje kodunu devre dışı bırakmak için

-   İşlenmeyen özel durum iletişim kutusunda seçin **çalışan proje kodunu devre dışı bırakın ve Tasarımcısı yeniden yüklemek için burayı tıklatın** bağlantı.

-   Alternatif olarak, XAML Tasarımcısı'nda araç çubuğundaki seçin **proje kodunu devre dışı bırakma** düğmesi.

     ![Proje kodunu devre dışı bırak düğmesi](../designers/media/xaml_disablecode.png)

     Proje kodunu tekrar etkinleştirmeniz için düğmesini geçiş yapabilirsiniz.

    > [!NOTE]
    > ARM veya X64 hedefleyen projeler için işlemci, Visual Studio Proje kodunu Tasarımcısı'nda çalıştırılamaz böylece **proje kodunu devre dışı bırakma** Tasarımcısı'nda düğmesi devre dışı.

-   Her iki seçenek yeniden yüklemek Tasarımcı neden olur ve ardından tüm ilişkili proje kodunu devre dışı bırakır.

    > [!NOTE]
    > Proje kodunu devre dışı bırakma tasarım zamanı veri kaybına yol açabilir. Tasarımcıda çalışan kodda hata ayıklamak için bir alternatiftir.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio ve Visual Studio için Blend'de XAML tasarım](../designers/designing-xaml-in-visual-studio.md)