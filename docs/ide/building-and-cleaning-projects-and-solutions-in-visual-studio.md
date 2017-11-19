---
title: "Projeler ve çözümler Visual Studio'da oluşturma ve temizleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.BuildProjectPicker
- vs.batchbuild
helpviewer_keywords:
- Clean Solution command
- builds [Visual Studio], managing
- solution build configurations, starting
- Build Solution command
- project build configurations, starting
- build configurations, starting
- project build configurations, dependencies
- Rebuild Solution command
- solution build configurations, build order
- builds [Visual Studio], preparing
ms.assetid: 710891fd-379e-42c2-a84b-44a7af694ca0
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2e66af6d2d38685bdd905b7991c6e8f782e4f696
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="building-and-cleaning-projects-and-solutions-in-visual-studio"></a>Visual Studio'da Projeler ve Çözümler Oluşturma ve Temizleme
Bu konudaki yordamları kullanarak, derleme, yeniden oluşturmanız veya tüm veya bazı projeleri veya bir çözümde proje öğeleri temizleyin. Adım adım bir öğretici için bkz: [izlenecek yol: uygulama oluşturma](../ide/walkthrough-building-an-application.md).  
  
> [!NOTE]
> Visual Studio, sürümü kullanıcı Arabiriminde, bu konuda, etkin, ayarlarınıza bağlı olarak açıklanmaktadır gelen farklı olabilir. Ayarlarınızı, örneğin değiştirmek için **genel** veya **Visual C++** ayarları seçebilirsiniz **Araçları**, **içeri ve dışarı aktarma ayarları**ve ardından seçin **tüm ayarlara**.
  
### <a name="to-build-rebuild-or-clean-an-entire-solution"></a>Yapı, yeniden oluşturmak veya çözümün tamamında temizlemek için  
  
1.  İçinde **Çözüm Gezgini**, seçin veya çözümü açın.  
  
2.  Menü çubuğunda seçin **yapı**ve ardından aşağıdaki komutlardan birini seçin:  
  
    -   Seçin **yapı** veya **yapı çözümü** bu dosyaları ve en son derlemeden bu yana değişmiş olan bileşenleri proje yalnızca derlemek için.  
  
        > [!NOTE]
        >  **Yapı** komutu olur **Çözümü Derle** ne zaman bir çözüm birden çok proje içerir.  
  
    -   Seçin **çözümü yeniden derle** "Çözüm Temizle" ve sonra tüm proje dosyaları ve bileşenleri oluşturun.  
  
    -   Seçin **temiz çözüm** Ara ve çıktı dosyaları silmek için. Yalnızca proje ve bileşen dosyalarını ile sol Ara yeni örneklerini ve çıktı dosyalarını sonra oluşturulabilir.  
  
### <a name="to-build-or-rebuild-a-single-project"></a>Derleme veya tek bir projeyi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, seçin veya projeyi açın.  
  
2.  Menü çubuğunda seçin **yapı**ve ardından ya da **yapı***ProjectName* veya **yeniden***ProjectName*.  
  
    -   Seçin **yapı***ProjectName* olanlar en son derlemeden bu yana değişmiş olan bileşenleri proje yalnızca oluşturmak için.  
  
    -   Seçin **yeniden***ProjectName* "projeyi temizleyin" ve proje dosyalarını ve tüm proje bileşenleri oluşturmak için.  
  
### <a name="to-build-only-the-startup-project-and-its-dependencies"></a>Yalnızca başlangıç projesi ve onun bağımlılıklarını oluşturmak için  
  
1.  Menü çubuğunda seçin **Araçları**, **seçenekleri**.  
  
2.  İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler** düğümünü ve ardından **derleme ve çalıştırma** sayfası.  
  
     **Derleme ve çalıştırma, projeler ve çözümler, Seçenekler** iletişim kutusu açılır.  
  
3.  Seçin **yalnızca başlangıç projeleri ve bağımlılıkları çalıştırılmasında yapı** onay kutusu.  
  
     Bu onay kutusu seçili olduğunda, aşağıdaki adımlardan birini gerçekleştirdiğinizde yalnızca geçerli başlangıç projesi ve onun bağımlılıklarını oluşturulur:  
  
    -   Menü çubuğunda seçin **hata ayıklama**, **Başlat** (F5).  
  
    -   Menü çubuğunda seçin **yapı**, **yapı çözümü** (CTRL + SHIFT + B).  
  
    Bu onay kutusu temizlendiğinde, önceki komutlardan herhangi birini çalıştırdığınızda, tüm projeleri, bağımlılıklarını ve çözüm dosyalarını oluşturulmuştur. Varsayılan olarak, bu onay kutusu işaretli değildir.  
  
### <a name="to-build-only-the-selected-visual-c-project"></a>Yalnızca seçili Visual C++ projesi oluşturmak için  
  
1.  Seçin bir [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] proje ve ardından, menü çubuğunda, **yapı**, **yalnızca proje**ve aşağıdaki komutlardan birini:  
  
    -   **Yalnızca derleme** *ProjectName*  
  
    -   **Yalnızca yeniden** *ProjectName*  
  
    -   **Temizleme yalnızca** *ProjectName*  
  
    -   **Yalnızca bağlantı** *ProjectName*  
  
    Bu komutları yalnızca uygulama [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] oluşturma, yeniden oluşturma, temizleme veya herhangi bir proje bağımlılıkları veya çözüm dosyalarını bağlama olmadan seçtiğiniz proje. Sürümünüze bağlı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **yalnızca proje** alt başka komutlar içeriyor olabilir.  
  
### <a name="to-compile-multiple-c-project-items"></a>Birden çok C++ projesi derlemek için öğeleri  
  
1.  İçinde **Çözüm Gezgini**, sahip birden çok dosya derlenmiş eylemler olabilir seçin bu dosyalardan biri için kısayol menüsünü açın ve ardından **derleme**.  
  
    Dosyaları bağımlılıkları varsa, dosyaları bağımlılık sırayla derlenecek. Derlediğinizde kullanılamaz önceden derlenmiş üstbilgi dosyaları gerektiren derleme işlemi başarısız olur. Derleme işlemi geçerli etkin çözüm yapılandırması kullanır.  
  
### <a name="to-stop-a-build"></a>Bir yapı durdurmak için  
  
1.  Aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Menü çubuğunda seçin **yapı**, **iptal**.  
  
    -   Seçin Ctrl + Break anahtarları.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Nasıl yapılır: görüntüleme, kaydetme ve derleme günlüğü dosyalarını yapılandırma](../ide/how-to-view-save-and-configure-build-log-files.md)   
[Derleme günlüklerini alma](../msbuild/obtaining-build-logs-with-msbuild.md)   
[Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)   
[Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)   
[Hata ayıklama ve yayın proje yapılandırmaları](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e)   
[C/C++ oluşturma başvurusu](/cpp/build/reference/c-cpp-building-reference)   
[Devenv komut satırı anahtarları](../ide/reference/devenv-command-line-switches.md)   
[Çözümler ve projeler](../ide/solutions-and-projects-in-visual-studio.md)