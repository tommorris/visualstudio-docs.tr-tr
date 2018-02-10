---
title: "Visual Studio'da Python ile çalışma, adım 6'da, Git ile çalışma | Microsoft Docs"
description: "Visual Studio, Visual Studio'nun Git ilgili özellikleri kapsayan içinde Python ile çalışmak için adım 6 bir çekirdek Öğreticisi."
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: eb39d8807deb0c08b12b04128365c584d9bd8251
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="step-6-working-with-git"></a>6. adım: Git ile çalışma

**Önceki adımda: [paketlerinin yüklenmesi ve Python ortamınızı yönetme](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

Visual Studio, GitHub gibi hizmetler ve Visual Studio Team Services yerel Git depoları ve bulunan olanlar ile doğrudan tümleştirme sağlar. Depo kopyalama, değişiklikleri yaptıktan ve dalları yönetme tümleştirmesi içerir.

Bu konu, mevcut bir proje için yerel bir Git deposu oluşturuluyor açıklar. Uzak bir Git deposundan projesi oluşturma adımları için bkz: [hızlı başlangıç: Visual Studio'da Python kodu bir depoyu kopyalayın](quickstart-03-python-in-visual-studio-project-from-repository.md).

1. Visual Studio'da projeden gibi açık bir proje ile [önceki adımda](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md), çözüme sağ tıklayın ve seçin **kaynak denetimine Çözüm Ekle**. Visual Studio Proje kodunuzu içeren yerel bir Git deposu oluşturur ve Visual Studio penceresinin alt görüntüler Git ilgili denetimler de görünür. Denetimlerini tamamlama, değişiklikleri, adını depo ve şube gösterir. Ek bilgi için denetimlerin üzerine gelin.

  ![Visual Studio penceresi Git denetiminde üzerinde hareket ederken ek bilgiler görüntülenir](media/working-with-git-01.png)

1. **Takım Gezgini** penceresi de Havuz üstbilgisi seçerek çeşitli Git ile kullanılabilir seçenekleri görüntülenir. **Eşitleme** seçtiğinizde gösterildiği gibi bölmesinde **anında** üstbilgisi, uzak deponuza yayımlama seçeneklerini sağlar.

  ![Yerel deposu oluşturduktan sonra Visual Studio Takım Gezgini](media/working-with-git-02.png)

1. Seçin **değişiklikleri** uygulanmayan değişiklikleri gözden geçirin ve bunları istediğiniz zaman kaydedilemedi.

  ![Uygulanmayan değişiklikleri gösteren Visual Studio Takım Gezgini](media/working-with-git-03.png)

1. Seçin **dalları** dalları inceleyin ve birleştirme ve rebase işlemleri gerçekleştirmek için:

  ![Visual Studio'da dalları gösteren Takım Gezgini](media/working-with-git-04.png)

1. Yerel deposu kullanırken, yapılan değişiklikleri doğrudan depoya gidin. Uzak bir depo bağlıysanız, üstbilgi seçin, **eşitleme** geçmek için **eşitleme** bölümünde ve var. sunulan komutları ile çalışır.

## <a name="going-deeper"></a>Daha derin gitme

Git ile çalışma hakkında daha kapsamlı bir öğretici için bkz: [kodunuzu paylaşımı Visual Studio 2017 ve VSTS Git](/vsts/git/share-your-code-in-git-vs-2017)

## <a name="tutorial-review"></a>Eğitmen gözden geçirme

Visual Studio'da Python üzerinde bu öğreticiyi tamamlamak tebrikler. Bu öğreticide, öğrendiğinize nasıl yapılır:

- Projeleri oluşturmak ve bir projenin içeriğini görüntüleyin.
- Kod Düzenleyicisi'ni kullanın ve bir proje çalıştırın.
- Yeni kod geliştirme ve kolayca kod düzenleyicisine kopyalayın etkileşimli penceresini kullanın.
- Visual Studio Hata Ayıklayıcısı'ndaki tamamlanmış bir programı çalıştırın.
- Paketleri yüklemek ve Python ortamları yönetme
- Bir Git deposu kodu ile çalışma

Buradan, kavramlar ve nasıl yapılır kılavuzları, aşağıdakiler de dahil olmak üzere keşfedin:

- [Python için C++ uzantısı oluşturma](working-with-c-cpp-python-in-visual-studio.md)
- [Azure App Service’e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md)
- [Profil Oluşturma](profiling-python-code-in-visual-studio.md)
- [Birim testi](unit-testing-python-in-visual-studio.md)
