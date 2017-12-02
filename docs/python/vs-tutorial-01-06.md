---
title: "Visual Studio'da Python ile çalışma, 6. adım | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 8356a9d4ab470b67a6e495d753fa498237e530f4
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-working-with-git"></a>6. adım: Git ile çalışma

**Önceki adımda: [paketlerinin yüklenmesi ve Python ortamınızı yönetme](vs-tutorial-01-05.md)**

Visual Studio, GitHub gibi hizmetler ve Visual Studio Team Services yerel Git depoları ve bulunan olanlar ile doğrudan tümleştirme sağlar. Depo kopyalama, değişiklikleri yaptıktan ve dalları yönetme tümleştirmesi içerir.

Bu konu, mevcut bir proje için yerel bir Git deposu oluşturuluyor açıklar. Uzak bir Git deposundan projesi oluşturma adımları için bkz: [hızlı başlangıç: Visual Studio'da Python kodu bir depoyu kopyalayın](quickstart-03-project-from-repository.md).

1. Visual Studio'da projeden gibi açık bir proje ile [önceki adımda](vs-tutorial-01-05.md), çözüme sağ tıklayın ve seçin **kaynak denetimine Çözüm Ekle**. Visual Studio Proje kodunuzu içeren yerel bir Git deposu oluşturur ve Visual Studio penceresinin alt görüntüler Git ilgili denetimler de görünür. Denetimlerini tamamlama, değişiklikleri, adını depo ve şube gösterir. Ek bilgi için denetimlerin üzerine gelin.

  ![Visual Studio penceresi Git denetiminde üzerinde hareket ederken ek bilgiler görüntülenir](media/working-with-git-01.png)

1. **Takım Gezgini** penceresi de Havuz üstbilgisi seçerek çeşitli Git ile kullanılabilir seçenekleri görüntülenir. **Eşitleme** bölmesinde gösterildiği gibi uzak deponuza yayımlama seçeneklerini sağlar.

  ![Yerel deposu oluşturduktan sonra Visual Studio Takım Gezgini](media/working-with-git-02.png)

1. Seçin **değişiklikleri** uygulanmayan değişiklikleri gözden geçirin ve bunları istediğiniz zaman kaydedilemedi.

  ![Uygulanmayan değişiklikleri gösteren Visual Studio Takım Gezgini](media/working-with-git-03.png)

1. Seçin **dalları** dalları inceleyin ve birleştirme ve rebase işlemleri gerçekleştirmek için:

  ![Visual Studio'da dalları gösteren Takım Gezgini](media/working-with-git-04.png)

1. Yerel deposu kullanırken, yapılan değişiklikleri doğrudan depoya gidin. Uzak bir depo bağlıysanız seçin **eşitleme** yerel yürütmelerini gönderdiğiniz için.

## <a name="going-deeper"></a>Daha derin gitme

Git ile çalışma hakkında daha kapsamlı bir öğretici için bkz: [kodunuzu paylaşımı Visual Studio 2017 ve VSTS Git](https://docs.microsoft.com/vsts/git/share-your-code-in-git-vs-2017)


## <a name="tutorial-review"></a>Eğitmen gözden geçirme

Visual Studio'da Python üzerinde bu öğreticiyi tamamlamak tebrikler. Bu öğreticide, öğrendiğinize nasıl yapılır:

- Projeleri oluşturmak ve bir projenin içeriğini görüntüleyin.
- Kod Düzenleyicisi'ni kullanın ve bir proje çalıştırın.
- Yeni kod geliştirme ve kolayca kod düzenleyicisine kopyalayın etkileşimli penceresini kullanın.
- Visual Studio Hata Ayıklayıcısı'ndaki tamamlanmış bir programı çalıştırın.
- Paketleri yüklemek ve Python ortamları yönetme
- Bir Git deposu kodu ile çalışma

Buradan, kavramlar ve nasıl yapılır kılavuzları, aşağıdakiler de dahil olmak üzere keşfedin:

- [Python için C++ uzantısı oluşturma](cpp-and-python.md)
- [Azure uygulama hizmeti yayımlama](publishing-to-azure.md)
- [Profil oluşturma](profiling.md)
- [Birim Testi](unit-testing.md)
