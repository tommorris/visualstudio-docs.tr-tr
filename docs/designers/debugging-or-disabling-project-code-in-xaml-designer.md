---
title: "Hata ayıklama veya XAML Tasarımcısı'nda proje kodunu devre dışı bırakma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac600581-8fc8-49e3-abdf-1569a3483d74
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: bbfe3eb4f76d8237d6e1a1b7c26aa48b1f081f1e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-or-disabling-project-code-in-xaml-designer"></a>Hata ayıklama veya XAML Tasarımcısı'nda proje kodunu devre dışı bırakma
Çoğu durumda, İşlenmeyen özel durumlar XAML Tasarımcısı'nda özellikleri ya da farklı değerler döndürebilecek veya Tasarımcısı'nda, uygulamanızı çalıştırırken farklı şekillerde iş yöntemleri erişmeye proje kodu neden olabilir. Başka bir örneği Visual Studio Proje kodda hata ayıklama bu özel durumları çözümlemek ya da geçici olarak Tasarımcısı'nda proje kodunu devre dışı bırakarak engelleyin.  
  
 Proje kodunu içerir:  
  
-   Özel denetimler ve kullanıcı denetimleri  
  
-   Sınıf kitaplıkları  
  
-   Değer dönüştürücüler  
  
-   Tasarım zamanı veri proje koddan oluşturulan karşı bağlamaları  
  
 Visual Studio Proje kodunu devre dışı bırakıldığında, yer tutucular gösterir özellik adı verileri nerede artık kullanılamaz; bir bağlama için gibi veya artık çalışır durumda bir denetim için bir yer tutucu.  
  
 ![İşlenmeyen özel durum iletişim](../designers/media/xaml_unhandledexception.png "XAML_UnhandledException")  
  
#### <a name="to-determine-if-project-code-is-causing-an-exception"></a>Proje kodunu bir özel durum neden olup olmadığını belirlemek için  
  
1.  İşlenmeyen özel durum iletişim kutusunda seçin **Tasarımcısı'nı yeniden yüklemek için burayı tıklatın** bağlantı.  
  
2.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat** oluşturun ve uygulamayı çalıştırın.  
  
     Uygulama oluşturulur ve başarılı bir şekilde çalışır Tasarımcısı'nda çalışan, proje kodu tarafından tasarım zamanında özel durum neden olabilir.  
  
#### <a name="to-debug-project-code-running-in-the-designer"></a>Proje Tasarımcısı'nda çalışan kodu hata ayıklamak için  
  
1.  İşlenmeyen özel durum iletişim kutusunda seçin **çalışan proje kodunu devre dışı bırakın ve Tasarımcısı yeniden yüklemek için burayı tıklatın** bağlantı.  
  
2.  Windows Görev Yöneticisi'nde seçin **Görevi Sonlandır** düğmesi Visual Studio XAML Tasarımcısı'nın şu anda çalışan tüm örneklerini kapatın.  
  
     ![XAML Tasarımcısı Görev Yöneticisi durumlarda](../designers/media/xaml_taskmanager.png "XAML_TaskManager")  
  
3.  Visual Studio'da kod veya hata ayıklamak istediğiniz denetimi içeren XAML sayfası açın.  
  
4.  Visual Studio yeni bir örneğini açın ve ardından projenizi ikinci bir örneğini açın.  
  
5.  Proje kodunuzda bir kesme noktası ayarlayın.  
  
6.  Menü çubuğunda, Visual Studio, yeni bir örneğini seçin **hata ayıklama**, **ekleme işlemi için**.  
  
7.  İçinde **ekleme işlemi için** iletişim, **kullanılabilir işlemler** listesinde, seçin **XDesProc.exe**ve ardından **Attach** düğmesi.  
  
     ![XAML Tasarımcısı işlem](../designers/media/xaml_attach.png "XAML_Attach")  
  
     XAML Tasarımcısı'nda Visual Studio'nun ilk örneği işlemidir.  
  
8.  Menü çubuğunda Visual Studio'nun ilk örneği seçin **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
     Şimdi, koda Tasarımcısı'nda çalışan geçebilirsiniz.  
  
#### <a name="to-disable-project-code-in-the-designer"></a>Tasarımcıda proje kodunu devre dışı bırakmak için  
  
-   İşlenmeyen özel durum iletişim kutusunda seçin **çalışan proje kodunu devre dışı bırakın ve Tasarımcısı yeniden yüklemek için burayı tıklatın** bağlantı.  
  
-   Alternatif olarak, XAML Tasarımcısı'nda araç çubuğundaki seçin **proje kodunu devre dışı bırakma** düğmesi.  
  
     ![Proje kodunu devre dışı bırak düğmesi](../designers/media/xaml_disablecode.png "XAML_DisableCode")  
  
     Proje kodunu tekrar etkinleştirmeniz için düğmesini geçiş yapabilirsiniz.  
  
    > [!NOTE]
    >  ARM veya X64 hedefleyen projeler için işlemci, Visual Studio Proje kodunu Tasarımcısı'nda çalıştırılamaz böylece **proje kodunu devre dışı bırakma** Tasarımcısı'nda düğmesi devre dışı.  
  
-   Her iki seçenek yeniden yüklemek Tasarımcı neden olur ve ardından tüm ilişkili proje kodunu devre dışı bırakır.  
  
    > [!NOTE]
    >  Proje kodunu devre dışı bırakma tasarım zamanı veri kaybına yol açabilir. Tasarımcıda çalışan kodda hata ayıklamak için bir alternatiftir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio ve Visual Studio için Blend'de XAML tasarlama](../designers/designing-xaml-in-visual-studio.md)