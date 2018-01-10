---
title: "İzlenecek yol: Oluşturma ve çalıştırma UWP uygulamaları için birim testleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests
- unit tests, UWP apps
- unit tests, running
ms.author: gewarren
manager: ghogen
ms.workload: uwp
author: gewarren
ms.openlocfilehash: 82ba9f9419964d9c626a81f78cf7f8ccace57320
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="walkthrough-creating-and-running-unit-tests-for-uwp-apps"></a>UWP uygulamalar için birim testleri izlenecek yol: Oluşturma ve çalıştırma
Visual Studio birim testi yönetilen için destek içerir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamaları ve Visual C#, Visual Basic ve Visual C++ için birim testi kitaplık şablonları içerir.  
  
> [!TIP]
>  Geliştirme hakkında daha fazla bilgi için [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamaları bkz [UWP uygulamaları ile çalışmaya başlama](http://go.microsoft.com/fwlink/?LinkID=241410).  
  
 Visual Studio işlevselliğini test etme aşağıdaki birim sağlar:  
  
-   [Birim testi projelerini oluşturma](#CreateAndRunUnitTestWin8Tailored_Create)  
  
-   [Birim testi projesi bildirimini Düzenle](#CreateAndRunUnitTestWin8Tailored_Manifest)  
  
-   [Birim testini kodlama](#CreateAndRunUnitTestWin8Tailored_Code)  
  
-   [Birim testleri çalıştırma](#CreateAndRunUnitTestWin8Tailored_Run)  
  
 Aşağıdaki yordamlar oluşturmak, çalıştırmak ve yönetilen Windows 8 için birim testleri hata ayıklamak için adımları açıklar [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulama.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Create"></a>Birim testi projelerini oluşturma  
  
#### <a name="to-create-a-unit-test-project-for-a-uwp-app"></a>Bir UWP uygulaması için birim testi projesi oluşturmak için  
  
1.  Gelen **dosya** menüsünde seçin **yeni proje**.  
  
     Yeni Proje iletişim kutusu görüntüler.  
  
2.  Şablonlar'ın altında istediğiniz birim testi oluşturma ve ardından ilişkili programlama dili seçin [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] birim testi kitaplığı. Örneğin, tercih **Visual C#** , ardından **Windows Evrensel**ve ardından **birim testi kitaplığı (Evrensel Windows)**.  
  
    > [!NOTE]
    >  Visual Studio, Visual C#, Visual Basic ve Visual C++ için birim testi kitaplık şablonları içerir.  
  
3.  (İsteğe bağlı) İçinde **adı** metin kutusuna, kullanmak istediğiniz adı girin [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]birim testi projesi.  
  
4.  (İsteğe bağlı) İçine girerek projeyi oluşturmak istediğiniz yolun değiştirme **konumu** metin kutusuna, veya seçme **Gözat** düğmesi.  
  
5.  (İsteğe bağlı) İçinde **çözüm** adı metin kutusuna, çözümünüz için kullanmak istediğiniz bu adı girin.  
  
6.  Bırakın **çözüm için dizin oluştur** seçeneği seçili ve seçin **Tamam** düğmesi.  
  
     ![Birim testi kitaplığı uyarlanmış](../test/media/unit_test_win8_1.png "Unit_Test_Win8_1")  
  
     Çözüm Gezgini doldurulur yeni ile [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]birim testi projesi ve kod düzenleyicisinde UnitTest1 başlıklı varsayılan birim testi görüntüler.  
  
     ![Yeni özel birim testi projesi](../test/media/unit_test_win8_unittestexplorer_newprojectcreated.png "Unit_Test_Win8_UnitTestExplorer_NewProjectCreated")  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Manifest"></a>Birim testi projesi bildirimini Düzenle  
 Uygulamayı çalıştırmak için gerekli özellikler sağlamak birim testi projesi için bildirim düzenlemek gerekli olabilir.  
  
#### <a name="to-edit-the-unit-test-projects-uwp-application-manifest-file"></a>Birim test projesinin UWP uygulama bildirim dosyasının düzenlemek için  
  
1.  Çözüm Gezgini'nde, yeni [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] birim testi projesi Package.appxmanifest dosyasını sağ tıklatın ve seçin **açık**.  
  
     Bildirim Tasarımcısı düzenlemek için görüntüler.  
  
2.  Bildirim Tasarımcısı'nda seçin **yetenekleri** sekmesi.  
  
3.  Listesinde altında **özellikleri**, birim testi ve kodu gereken özellikleri işaretleyin sağlamak için sınama onun. Örneğin, seçin **Internet** ihtiyaçlarını birim testi ve kodu test onay kutusunu Internet'e erişmek için özelliği olması gerekir.  
  
    > [!NOTE]
    >  Seçtiğiniz özellikler için gerekli olan özellikleri yalnızca içermelidir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] düzgün çalışması için birim testi. Özellikleri olmayan yetenekleri eklemek hiçbir zaman olmalıdır parçası [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulama olan test ve genellikle için belirtilen yeteneklerinin bir alt kümesini olması gerekir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]test altındaki uygulama.  
  
     Bildirim Tasarımcısı hakkında daha fazla bilgi için bkz: [bildirim Tasarımcısını kullanarak bir Windows 8.1 uygulama paketini yapılandırma](http://msdn.microsoft.com/Library/24c58b7f-9c6d-41c3-b385-c1e8497d5b2d).  
  
     ![Birim testi bildirimi](../test/media/unit_test_win8_.png "Unit_Test_Win8_")  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Code"></a>Birim testini kodlama  
  
#### <a name="to-code-the-unit-test-for-a-uwp-app"></a>Kod bir UWP uygulaması için birim testi  
  
1.  Kod Düzenleyicisi'nde, birim testi düzenleyebilir ve ekleme onaylar ve test için gerekli mantığı.  
  
     Daha fazla bilgi için bkz [onay sınıfları kullanma](http://go.microsoft.com/fwlink/?LinkID=224991) MSDN Kitaplığı'nda.  
  
##  <a name="CreateAndRunUnitTestWin8Tailored_Run"></a>Birim testleri çalıştırma  
  
#### <a name="to-build-the-solution-and-run-the-unit-test-using-test-explorer"></a>Çözümü derlemek ve Test Gezgini'ni kullanarak birim testi çalıştırma  
  
1.  Üzerinde **Test** menüsünde seçin **Windows**ve ardından **Test Gezgini**.  
  
     Explorer görüntüler listelenmesini testinizi sınayın.  
  
2.  Gelen **yapı** menüsünde seçin **yapı çözümü**.  
  
     Birim testi artık listelenir.  
  
    > [!NOTE]
    >  Birim testleri Test Gezgini listesini güncelleştirmek için çözüm oluşturmanız gerekir.  
  
    > [!WARNING]
    >  Visual Studio bilinen sorun: test projesinin derlenmesi önce Test Gezgini açmanız gerekir.  
  
3.  Test Gezgini içinde oluşturduğunuz birim testi seçin.  
  
    > [!TIP]
    >  Test Gezgini sağlar kaynak kodunu bağlantı yanına **kaynak:**.  
  
4.  Seçin **çalıştırması**.  
  
     ![Birim Test Gezgini &#45; Birim testi çalıştırma](../test/media/unit_test_win8_unittestexplorer_contextmenurun.png "Unit_Test_Win8_UnitTestExplorer_ContextMenuRun")  
  
    > [!TIP]
    >  Explorer'da listelenen bir veya daha fazla birim testleri seçebilir ve ardından sağ tıklatın ve seçin **seçili Testleri Çalıştır**.  
    >   
    >  Ayrıca, seçebileceğiniz **seçili Testlerde Hata Ayıkla**, **açık Test**ve **özellikleri** seçeneği.  
    >   
    >  ![Birim Test Gezgini &#45; UNI test bağlam menüsü](../test/media/unit_test_win8_unittestexplorer_contextmenu.png "Unit_Test_Win8_UnitTestExplorer_ContextMenu")  
  
     Test çalışmasını birim. Tamamlandıktan sonra Test Gezgini geçen süre test durumu görüntüler ve kaynak için bir bağlantı sağlar.  
  
     ![Birim Test Gezgini &#45; Testi tamamlandı](../test/media/unit_test_win8_unittestexplorer_done.png "Unit_Test_Win8_UnitTestExplorer_Done")  
  
## <a name="external-resources"></a>Dış Kaynaklar  
  
### <a name="videos"></a>Videolar  
 [Kanal 9: Birim XAML kullanarak oluşturulan, UWP uygulamaları testi](http://go.microsoft.com/fwlink/?LinkId=226285)  
  
### <a name="forums"></a>Forumlar  
 [Visual Studio birim testi](http://go.microsoft.com/fwlink/?LinkId=224477)  
  
### <a name="msdn-library"></a>MSDN Kitaplığı  
 [MSDN Kitaplığı - oluşturma ve var olan kodu (Visual Studio 2010) için birim testleri çalıştırma](http://go.microsoft.com/fwlink/?LinkID=223683)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio ile UWP uygulamaları test etme](../test/testing-store-apps-with-visual-studio.md)   
 [Derleme ve Team Foundation Build kullanarak bir UWP uygulaması test](http://msdn.microsoft.com/Library/d0ca17bb-deae-4f3d-a18d-1a99bebceaa9)
