---
title: Oluşturma ve Visual Studio UWP uygulamaları için birim testleri çalıştırma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, creating
- unit tests
- unit tests, UWP apps
- unit tests, running
ms.author: gewarren
manager: douge
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: cf27c036f68eb4d2847c1070282c7949f59d2454
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751721"
---
# <a name="walkthrough-create-and-run-unit-tests-for-uwp-apps"></a>İzlenecek yol: Oluşturma ve UWP uygulamaları için birim testleri çalıştırma

Visual Studio birim testi Evrensel Windows Platformu (UWP) uygulamaları için destek içerir. Visual C#, Visual Basic ve Visual C++ için birim testi projesi şablonları içerir.

> [!TIP]
> UWP uygulamaları geliştirme hakkında daha fazla bilgi için bkz: [UWP uygulamaları ile çalışmaya başlama](/windows/uwp/get-started/).

Aşağıdaki yordamlar oluşturmak, çalıştırmak ve bir UWP uygulaması için birim testleri hata ayıklamak için adımları açıklar.

## <a name="create-a-unit-test-project-for-a-uwp-app"></a>Bir UWP uygulaması için bir birim testi projesi oluşturma

1.  Gelen **dosya** menüsünde seçin **yeni proje**.

     Yeni Proje iletişim kutusu görüntüler.

2.  Şablonlar'ın altında birim testleri oluşturma ve ardından Kitaplık ilişkili Windows Evrensel birim test etmek istediğiniz programlama dili seçin. Örneğin, tercih **Visual C#** , ardından **Windows Evrensel**ve ardından **birim testi kitaplığı (Evrensel Windows)**.

3.  (İsteğe bağlı) İçinde **adı** metin kutusuna, proje için kullanmak istediğiniz adı girin.

4.  (İsteğe bağlı) İçine girerek projeyi oluşturmak istediğiniz yolun değiştirme **konumu** metin kutusuna, veya seçerek **Gözat** düğmesi.

5.  (İsteğe bağlı) İçinde **çözüm** adı metin kutusuna, çözümünüz için kullanmak istediğiniz bu adı girin.

6.  Bırakın **çözüm için dizin oluştur** seçeneği seçili ve seçin **Tamam** düğmesi.

     ![Özel birim testi kitaplığı](../test/media/unit_test_win8_1.png)

     Çözüm Gezgini UWP birim testi projesi ile doldurulur ve UnitTest1 başlıklı varsayılan birim testi kod düzenleyicisinde görüntüler.

     ![Yeni özel birim testi projesi](../test/media/unit_test_win8_unittestexplorer_newprojectcreated.png)

## <a name="edit-the-unit-test-projects-uwp-application-manifest-file"></a>Birim test projesinin UWP uygulama bildirim dosyasının Düzenle

1.  Çözüm Gezgini'nde sağ *Package.appxmanifest* dosya ve seçin **açık**.

     Bildirim Tasarımcısı düzenlemek için görüntüler.

2.  Bildirim Tasarımcısı'nda seçin **yetenekleri** sekmesi.

3.  Listesinde altında **özellikleri**, birim testi ve kodu gereken özellikleri işaretleyin sağlamak için sınama onun. Örneğin, seçin **Internet** ihtiyaçlarını birim testi ve kodu test onay kutusunu Internet'e erişmek için özelliği olması gerekir.

    > [!NOTE]
    > Seçtiğiniz özellikleri yalnızca birim testi düzgün çalışması gerekli özellikleri eklemeniz gerekir.

     ![Birim testi bildirimi](../test/media/unit_test_win8_.png)

## <a name="code-the-unit-test-for-a-uwp-app"></a>Bir UWP uygulaması için birim testini kodlama

Kod Düzenleyicisi'nde, birim testi düzenleyebilir ve ekleme onaylar ve test için gerekli mantığı.

## <a name="run-unit-tests"></a>Birim testleri çalıştırma

### <a name="to-build-the-solution-and-run-the-unit-test-using-test-explorer"></a>Çözümü derlemek ve Test Gezgini'ni kullanarak birim testi çalıştırma

1.  Üzerinde **Test** menüsünde seçin **Windows**ve ardından **Test Gezgini**.

     Explorer görüntüler listelenmesini testinizi sınayın.

2.  Gelen **yapı** menüsünde seçin **yapı çözümü**.

     Birim testi artık listelenir.

    > [!NOTE]
    > Birim testleri Test Gezgini listesini güncelleştirmek için çözüm oluşturmanız gerekir.

3.  Test Gezgini içinde oluşturduğunuz birim testi seçin.

    > [!TIP]
    > Test Gezgini sağlar kaynak kodunu bağlantı yanına **kaynak:**.

4.  Seçin **çalıştırması**.

     ![Birim testi Explorer &#45; birim testi çalıştırma](../test/media/unit_test_win8_unittestexplorer_contextmenurun.png)

    > [!TIP]
    > Explorer'da listelenen bir veya daha fazla birim testleri seçebilir ve ardından sağ tıklatın ve seçin **seçili Testleri Çalıştır**.
    >
    > Ayrıca, seçebileceğiniz **seçili Testlerde Hata Ayıkla**, **açık Test**ve **özellikleri** seçeneği.
    >
    > ![Birim testi Explorer &#45; UNI test bağlam menüsü](../test/media/unit_test_win8_unittestexplorer_contextmenu.png)

    Test çalışmasını birim. Tamamlandıktan sonra Test Gezgini geçen süre test durumu görüntüler ve kaynak için bir bağlantı sağlar.

    ![Birim testi Explorer &#45; testi tamamlandı](../test/media/unit_test_win8_unittestexplorer_done.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio ile UWP uygulamalarını test etme](../test/testing-store-apps-with-visual-studio.md)
- [Derleme ve test bir UWP uygulaması](/vsts/build-release/apps/windows/universal?tabs=vsts)
