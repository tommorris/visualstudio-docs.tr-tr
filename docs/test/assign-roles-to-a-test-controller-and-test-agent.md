---
title: Visual Studio'da Otomatikleştirilmiş Testler için Test Denetleyicisine ve Test Aracısına Roller Atama
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- testing, walkthroughs, test controller and test agents
- test agent, walkthrough
- walkthroughs [Visual Studio ALM] testing
- test controller, walkthrough
- walkthroughs, test controller and test agents
ms.assetid: 57ed43ae-4e67-4139-8aec-3e9fceb0a745
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: f939947c4b96584439d85c33c234dc769531888d
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36280617"
---
# <a name="assign-roles-to-a-test-controller-and-test-agent"></a>Bir test denetleyicisi ve test aracısına roller atama

Bu kılavuz, oluşturmak ve Visual Studio kullanarak birden fazla makine arasında sınamayı dağıtmak için bir test denetleyicisi ve test aracısı kullanan bir test ayarı yapılandırmak gösterilmiştir. Ayrıca, bu kılavuzda tanılama ve veri bağdaştırıcıları için test ayarı eklemek gösterilmiştir.

Bu kılavuzda, aşağıdaki görevleri tamamlar:

-   Bir test ayarı oluşturun.

-   Test denetleyicisi ve test aracıları için rolleri atayın.

-   Tanılama ve veri bağdaştırıcısı test ayarınız atayın.

## <a name="prerequisites"></a>Önkoşullar

-   Birim testleri veya test ayarı ile kodlanmış UI testi oluşturun.

-   Test denetleyicisi ve test aracıları yükleyin. Bir test denetleyicisi ve test aracıları hakkında daha fazla bilgi için bkz: [yükleme ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

## <a name="to-create-and-configure-a-test-setting"></a>Oluşturma ve test ayarı yapılandırmak için

1.  İçinde **Çözüm Gezgini**, sağ **çözüm öğeleri** işaret **Ekle**ve ardından **yeni öğe**.

     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.

2.  İçinde **yüklü şablonlar** bölmesinde seçin **Test ayarlarını**.

3.  İçinde **adı** kutusuna **TestSettingDistributedTestWalkthrough**.

4.  Seçin **eklemek**.

     Yeni test *TestSettingDistributedTestWalkthrough.testsettings* dosya görünür **Çözüm Gezgini**altında **çözüm öğeleri** klasör.

     **Test ayarlarını** iletişim kutusu görüntülenir. **Genel** sayfa seçilidir.

     Şimdi, düzenleme ve test ayarları değerlerini kaydedin.

    > [!NOTE]
    > Oluşturduğunuz her test ayarları için bir seçenek olarak listeleniyor **Etkin Test ayarlarını seçin** ve **Test Ayarlarını Düzenle** seçeneklerinden **Test** menüsü.

5.  Altında **adı**, test ayarları için bir ad yazın.

6.  Altında **açıklama**, türü **Dağıtılmış test ayarları**.

7.  Bırakın **adlandırma şeması varsayılan** seçili.

## <a name="to-assign-roles-to-a-test-controller-and-test-agents"></a>Test denetleyicisi ve test aracıları için rolleri atamak için

1.  Seçin **rolleri**.

     **Rolleri** sayfası görüntülenir.

2.  Testinizi uzaktan çalıştırmak için kullandığınız **Test yürütme yöntemi** aşağı açılan liste ve select **uzaktan yürütme**.

3.  İçinde **denetleyicisi** aşağı açılan listesinde, bilgisayar adını yazın [için test denetleyicisi](../test/lab-management/install-configure-test-agents.md).

    > [!NOTE]
    > Denetleyici eklediğiniz ilk kez kullanıyorsanız aşağı açılan listesinde hiçbir denetleyicisi vardır. Liste diğer test ayarlarında belirttiğiniz önceki denetleyiciler tarafından doldurulur.

4.  Altında **rolleri**, seçin **Ekle**.

5.  Vurgulanan satırda altında **adı** sütununa, **Dağıtılmış test**.

## <a name="to-assign-a-diagnostic-and-data-adapter-to-your-test-setting"></a>Tanılama ve veri bağdaştırıcısı test ayarınız atamak için

1.  Seçin **veri ve tanılama**.

     **Veri ve tanılama** sayfası görüntülenir.

2.  Altında **rol**, doğrulayın **Dağıtılmış test** rolü seçilir.

3.  Altında **veri ve tanılama select rol için**seçin **IntelliTrace** ve **sistem bilgisi** bağdaştırıcıları.

     Bu bağdaştırıcılar ve bir test ayarında kullanabileceğiniz diğer bağdaştırıcılar hakkında daha fazla bilgi için bkz: [yapılandırma birim testleri](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).

4.  Seçin **ana**.

5.  (İsteğe bağlı) Makinenizde Microsoft Windows'un 64 bit sürümünde çalışıyorsa ve kullanarak test derlenmiş **herhangi bir CPU** yapılandırması, kullanımı **32 bit veya 64 bit işlem testi çalıştırma** aşağı açılan liste ve seçin **64-bit makine üzerinde 64-bit işlemde testler**.

    > [!TIP]
    > Maksimum esneklik için test projelerinizi derleme **herhangi bir CPU** yapılandırma. Ardından, 32 bit ve 64-bit aracısında çalıştırabilirsiniz. Test projeleriyle derleme avantajlı yoktur **64-bit** yapılandırma.

6.  Yeni test ayarlarını kaydetmek üzere seçim yapın **Uygula**.

7.  Seçin **Kapat**.

8.  Test menüsünde seçin **Etkin Test ayarlarını seçin** ve ardından **TestSettingDistributedTestWalkthrough.testsettings**.

9. Testinizi her zamanki gibi çalıştırın.

     Birim testleri ve kodlanmış UI testlerini test denetleyicisi işlediğinde, test denetleyicisi testleri 100 gruplara böler ve bunları bir test aracısı makineye gönderir. Örneğin, 250 birim testleri varsa ve üç test aracıları, ilk 100 birim testleri için Aracı1 gönderilir, sonraki 100 birim testleri için Aracı2 gönderilir ve kalan 50 birim testleri için Aracı3 gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)