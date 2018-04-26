---
title: Python Git ile çalışma öğretici, adım 6 ile çalışma
description: 6. adımını çekirdek kılavuzun Visual Studio, Visual Studio'nun Git ilgili özellikleri kapsayan Python.
ms.date: 01/16/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: c428082a061224f5bb8f3703d6ab4bed2b33aa76
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-6-working-with-git"></a>6. adım: Git ile çalışma

**Önceki adımda: [paketlerinin yüklenmesi ve Python ortamınızı yönetme](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

Visual Studio, GitHub gibi hizmetler ve Visual Studio Team Services yerel Git depoları ve uzak depoları ile doğrudan tümleştirme sağlar. Depo kopyalama, değişiklikleri yaptıktan ve dalları yönetme tümleştirmesi içerir.

Bu makale, var olan bir proje için yerel bir Git deposu oluşturma ve kendiniz bazı Visual Studio'nun Git ile ilgili özellikler hakkında bilgi edinme temel bir genel bakış sağlar.

1. Visual Studio'da projeden gibi açık bir proje ile [önceki adımda](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md), çözüme sağ tıklayın ve seçin **kaynak denetimine Çözüm Ekle**. Visual Studio Proje kodunuzu içeren yerel bir Git deposu oluşturur.

1. Visual Studio Proje Git ile ilgili bir Git deposu denetimlerinde yönetilir algıladığında Visual Studio penceresinin alt sağ köşesindeki görüntülenir. Denetimlerini tamamlama, değişiklikleri, adını depo ve şube gösterir. Ek bilgi için denetimlerin üzerine gelin.

    ![Visual Studio penceresi Git denetiminde üzerinde hareket ederken ek bilgiler görüntülenir](media/working-with-git-01.png)

1. Yeni bir havuz oluşturduğunuzda ya da Git denetimleri birini seçin, Visual Studio açılır **Takım Gezgini** penceresi. (Dilediğiniz zaman penceresini açın **Görünüm > Takım Gezgini** menü komutu.) Açılan listeyi kullanarak arasında geçiş üç ana bölmeleri penceresine sahip **Takım Gezgini** üstbilgi. **Eşitleme** yayımlama işlemleri sağlayan bölmesi, aynı zamanda görünür itme denetim (yukarı ok simgesi) seçtiğinizde:

    ![Yerel deposu oluşturduktan sonra Visual Studio Takım Gezgini](media/working-with-git-02.png)

1. Seçin **değişiklikleri** (veya kalem simgesine Git denetimiyle) uygulanmayan değişiklikleri gözden geçirin ve bunları istediğiniz zaman kaydedilemedi.

    ![Uygulanmayan değişiklikleri gösteren Visual Studio Takım Gezgini](media/working-with-git-03.png)

    Bir dosyasına çift tıklayarak **değişiklikleri** bu dosya için bir fark görünümü açmak için listesi:

    ![Fark görünümü bir dosyada değişiklik yapmak için](media/working-with-git-05.png)

1. Seçin **dalları** (veya bir dal adı Git denetimiyle) dalları inceleyin ve birleştirme ve rebase işlemleri gerçekleştirmek için:

    ![Visual Studio'da dalları gösteren Takım Gezgini](media/working-with-git-04.png)

1. Havuz adı ("CosineWave" önceki görüntüde), Git denetimiyle seçme **Takım Gezgini** gösterir bir **Bağlan** ile kolayca geçirebilirsiniz başka bir depoya tamamen arabirimi.

1. Yerel deposu kullanırken, yapılan değişiklikleri doğrudan depoya gidin. Uzak bir depo bağlıysanız, aşağı açılan üstbilgisinde seçin **Takım Gezgini**, seçin **eşitleme** geçmek için **eşitleme** bölümünde ve birlikte çalışma çekme ve fetch komutları sunulan vardır.

## <a name="going-deeper"></a>Daha derin gitme

Uzak bir Git deposundan projesi oluşturma kısa için bkz [hızlı başlangıç: Visual Studio'da Python kodu bir depoyu kopyalayın](quickstart-03-python-in-visual-studio-project-from-repository.md).

Çekme istekleri, yeniden Temellendirme ve tek tek çekme değişiklikleri arasında dallar, kod gözden geçirme, birleştirme çakışmaları işleme dahil olmak üzere çok daha kapsamlı bir öğretici için bkz: [Git ve VSTS ile çalışmaya başlama](/vsts/git/gitquickstart?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json&view=vsts&tabs=visual-studio).

## <a name="tutorial-review"></a>Eğitmen gözden geçirme

Visual Studio'da Python üzerinde bu öğreticiyi tamamlamak tebrikler. Bu öğreticide, öğrendiğinize nasıl yapılır:

- Projeleri oluşturmak ve bir projenin içeriğini görüntüleyin.
- Kod Düzenleyicisi'ni kullanın ve bir proje çalıştırın.
- Yeni kod geliştirme ve kolayca kod düzenleyicisine kopyalayın etkileşimli penceresini kullanın.
- Visual Studio Hata Ayıklayıcısı'ndaki tamamlanmış bir programı çalıştırın.
- Paketleri yüklemek ve Python ortamları yönetme
- Bir Git deposu kodu ile çalışma

Buradan, kavramlar ve nasıl yapılır kılavuzları, aşağıdaki makaleler de dahil olmak üzere keşfedin:

- [Python için C++ uzantısı oluşturma](working-with-c-cpp-python-in-visual-studio.md)
- [Azure App Service’e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md)
- [Profil Oluşturma](profiling-python-code-in-visual-studio.md)
- [Birim testi](unit-testing-python-in-visual-studio.md)
