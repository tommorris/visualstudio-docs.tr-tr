---
title: "Visual Studio'da C++ kullanmaya Başlarken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 99c73344-86ba-4b08-9e15-f6111cc04185
caps.latest.revision: "18"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 48f2bb4e61ca6a4f9a9464a6b67a3218b418c8ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-with-c-in-visual-studio"></a>Visual Studio'da C++ Kullanmaya Başlarken
Bu kılavuzu izleyerek, araçları ve Visual Studio ile uygulamaları geliştirirken kullanabileceğiniz iletişim kutuları çoğu öğrenmeniz. Bir basit "Hello, World" oluşturacaksınız-stil uygulaması sırasında tümleşik geliştirme ortamı (IDE) çalışma hakkında daha fazla bilgi edinin.  
  
 Bu konu aşağıdaki bölümleri içermektedir:  
  
 [Visual Studio'da oturum açın](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_Configure)  
  
 [Basit bir uygulama oluşturma](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_CreateApp)  
  
 [Uygulama kodu ekleme](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_AddCode)  
  
 [Hata ayıklama ve uygulamayı test etme](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_DebugTest)  
  
 [Uygulama sürümü oluşturma](../ide/getting-started-with-cpp-in-visual-studio.md#BKMK_BuildRelease)  
  
##  <a name="BKMK_Configure"></a>Visual Studio'da oturum açın  
 Visual Studio ilk kez başlattığınızda, Canlı veya Outlook gibi bir Microsoft hesabı kullanarak oturum olanağı verilir. Oturum açma ayarlarınızı tüm cihazlar arasında eşitlenmesine izin verir. Daha fazla bilgi için bkz: [Visual Studio'da oturum açma](../ide/signing-in-to-visual-studio.md)  
  
 Şekil 1: Visual Studio IDE  
  
 ![Visual C# 43; &#43;IDE; uygulanan ayarları](../ide/media/c--ide_defaultenvironmentlayout.png "C ++ IDE_DefaultEnvironmentLayout")  
  
 Visual Studio açtıktan sonra IDE üç temel bölümlerini görebilirsiniz: aracı windows, menüleri ve araç çubukları ve ana penceresi alanı. Araç pencereleri yerleşik ve uygulama penceresinin sol tarafında üzerinde ile **hızlı başlatma**, menü çubuğundaki ve standart araç çubuğu üstünde. Uygulama penceresi merkezi içerir **başlangıç sayfası**. Bir çözüm ya da projeyi açtığınızda, düzenleyiciler ve tasarımcıları bu alanında görünür. Bir uygulama geliştirirken, çoğu zaman, merkezi bu alandaki harcamanız.  
  
##  <a name="BKMK_CreateApp"></a>Basit bir uygulama oluşturma  
 Visual Studio'da bir uygulama oluşturduğunuzda, bir proje ve çözüm ilk oluşturun. Bu örnekte, bir Windows konsol uygulaması oluşturacaksınız.  
  
#### <a name="to-create-a-console-app"></a>Bir konsol uygulaması oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
     ![Menü çubuğunda, dosya, yeni seçin, proje](../ide/media/exploreide-filenewproject.png "ExploreIDE FileNewProject")  
  
2.  İçinde **Visual C++** kategorisi seçin **Win32 konsol uygulaması** şablonu ve ardından ad proje `GreetingsConsoleApp`.  
  
     ![Win32 konsol uygulaması şablonu](../ide/media/c--ide_newprojectdlg.png "C ++ IDE_NewProjectDlg")  
     İletişim kutusu, yüklemiş olduğunuz bağlı olarak farklı seçenekler olabilir. Visual C++ proje şablonları görmüyorsanız yükleyicinin geri dönün ve C++ iş yükü yüklemeniz gerekir.
  
3.  Win32 Uygulama Sihirbazı'nı belirdiğinde seçin **son** düğmesi.  
  
     ![Win32 Konsol Uygulama Sihirbazı'nı](../ide/media/c--ide_win32consoleappwizard.png "C ++ IDE_Win32ConsoleAppWizard")  
  
 GreetingsConsoleApp proje ve çözüm, bir Win32 konsol uygulaması için temel dosyalarla oluşturulur ve otomatik olarak yüklenen **Çözüm Gezgini**. Kod Düzenleyicisi'nde GreetingsConsoleApp.cpp dosya açılır. Aşağıdaki öğeler görünür **Çözüm Gezgini**:  
  
 Şekil 4: Proje öğeleri  
  
 ![Çözüm Gezgini'ndeki çözüme dosyaları](../ide/media/c--ide_solutioncontents.png "C ++ IDE_SolutionContents")  
  
##  <a name="BKMK_AddCode"></a>Uygulama kodu ekleme  
 Ardından, konsol penceresinde "Hello" sözcüğünü görüntülemek için kod ekleyeceksiniz.  
  
#### <a name="to-display-hello-in-the-console-window"></a>"Hello" Konsol penceresinde görüntülemek için  
  
1.  GreetingsConsoleApp.cpp dosyasında satırdan önce boş bir satır girin `return 0;` ve ardından aşağıdaki kodu girin:  
  
    ```  
    cout << "Hello\n";  
    ```  
  
     Kırmızı kırık çizgi altında görünür `cout`. Üzerine bir hata iletisi görüntülenir.  
  
     ![Cout hata metni](../ide/media/c--ide_couterror.png "C ++ IDE_CoutError")  
  
     Hata iletisi de görünür **hata listesi** penceresi. Pencerenin seçerek görüntüleyebilirsiniz **Görünüm**, **hata listesi** menü çubuğunda.  
  
     [cout](/cpp/standard-library/iostream) dahil \<iostream > Üstbilgi dosyası.  
  
2.  İostream üstbilgisi eklemek için sonra aşağıdaki kodu girin `#include "stdafx.h"`:  
  
    ```  
    #include <iostream>  
    using namespace std;  
    ```  
  
     Girdiğiniz karakterler için öneri sağlama kodu girdiğiniz gibi görünen bir kutu büyük olasılıkla fark. Bu kutu sınıfta veya arabirimde üye ve parametre bilgileri listeleyen dahil olmak üzere kodlama istemleri sağlayan C++ IntelliSense bir parçasıdır. Kodu önceden tanımlanmış taşlarıdır kod parçacıkları de kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak IntelliSense](../ide/using-intellisense.md) ve [kod parçacıkları](../ide/code-snippets.md).  
  
     Altında kırmızı kırık çizgi `cout` hata düzelttiğinizde kaybolur.  
  
3.  Değişiklikleri dosyaya kaydedin.  
  
     ![Cout hata düzeltmeleri kod](../ide/media/c--ide_coutfix.png "C ++ IDE_CoutFix")  
  
##  <a name="BKMK_DebugTest"></a>Hata ayıklama ve uygulamayı test etme  
 "Hello" sözcüğü konsol penceresinde görünür olup olmadığını görmek için GreetingsConsoleApp ayıklayabilirsiniz.  
  
#### <a name="to-debug-the-application"></a>Uygulama hata ayıklamak için  
  
-   Hata ayıklayıcı başlatın.  
  
     ![Hata ayıklama menüsündeki komutu hata ayıklamayı Başlat](../ide/media/exploreide-startdebugging.png "ExploreIDE StartDebugging")  
  
     Hata ayıklayıcı başlar ve kodu çalıştırır. Konsol penceresi (bir komut istemi gibi görünüyor ayrı bir pencerede) birkaç saniye görünür ancak hata ayıklayıcı çalışmayı durdurduğunda hızlı bir şekilde kapatır. Metin görmek için program yürütme durdurmak için kesme noktası ayarlamanız gerekir.  
  
#### <a name="to-add-a-breakpoint"></a>Bir kesme noktası eklemek için  
  
1.  Menü çubuğundan satırında bir kesme noktası ekleme `return 0;`. Ayrıca, bir kesme noktası ayarlamak için sol kenar boşluğunda tıklatabilirsiniz.  
  
     ![Hata Ayıklama menüsünde kesme komutu geçiş](../ide/media/exploreide-togglebreakpoint.png "ExploreIDE ToggleBreakpoint")  
  
     Düzenleyici penceresinin en sol kenar boşluğunda, kod satırının yanında kırmızı bir daire görünür.  
  
2.  Hata ayıklamayı başlatmak için F5 tuşuna seçin.  
  
     Hata ayıklayıcıyı başlatır, ve word gösteren bir konsol penceresi görünür **Hello**.  
  
     ![Windows Komut İstemi penceresindeki metin Hello](../ide/media/c--ide_hellocommandwindow.png "C ++ IDE_HelloCommandWindow")  
  
3.  SHIFT + hata ayıklamayı durdurmak için F5 tuşuna basın.  
  
 Daha fazla bilgi için bkz: [konsol projeleri](../debugger/debugging-preparation-console-projects.md).  
  
##  <a name="BKMK_BuildRelease"></a>Uygulama sürümü oluşturma  
 Her şeyi çalıştığını doğruladıktan, uygulamanın yayın derlemesi hazırlayabilirsiniz.  
  
#### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Çözüm dosyalarını temizlemek ve yayın sürümünü oluşturmak için  
  
1.  Menü çubuğundan ara dosyaları ve önceki yapıları sırasında oluşturulan çıktı dosyalarını silin.  
  
     ![Yapı menüsünde çözümü Temizle komutunu](../ide/media/exploreide-cleansolution.png "ExploreIDE CleanSolution")  
  
2.  GreetingsConsoleApp yapı yapılandırmasını değiştirme **hata ayıklama** için **sürüm**.  
  
     ![Uygulama sürümü yapı](../ide/media/c--ide_changingbuildtorelease.png "C ++ IDE_ChangingBuildtoRelease")  
  
3.  Çözümü oluşturun.  
  
     ![Build menüsünden yapı çözümü komutu](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")  
  
 Tebrikler, bu izlenecek yolu tamamladınız! Daha fazla örnek keşfetmek, bkz: [Visual Studio örnekleri](../ide/visual-studio-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanma](/cpp/ide/using-the-visual-studio-ide-for-cpp-desktop-development)   
 [İzlenecek yol: Visual C# veya Visual Basic ile basit uygulama oluşturma](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)   
 [Visual Studio için üretkenlik ipuçları](../ide/productivity-tips-for-visual-studio.md)   
 [Visual Studio Örnekleri](../ide/visual-studio-samples.md)   
 [Visual Studio ile Geliştirmeye Başlarken](../ide/get-started-developing-with-visual-studio.md)