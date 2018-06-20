---
title: Visual Studio'da bir birim testi projesi oluşturma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3dc86281542dbedd429fae5f9976219bfa623878
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36235056"
---
# <a name="create-a-unit-test-project"></a>Birim testi projesi oluşturma

Birim testleri test altındaki kod yapısına genellikle yansıtır. Örneğin, birim testi projesi ürün içinde her kod projesi için oluşturulmuş. Oluşturduğunuz test projesinin üretim kodu olarak aynı çözüme olabilir veya ayrı bir çözümde de olabilir. Test projeleri bir çözümde birden çok birim olabilir.

> [!NOTE]
> Yerel kod için birim konumunu sınar ve test proje yapısını bu konuda açıklanan yapısı farklı olabilir. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Birim testi projesi oluşturmak için:

1.  Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje** (klavye **Ctrl**+**Shift** + **N**).

2.  İçinde **yeni proje** iletişim kutusunda, genişletin **yüklü** düğümü, test projeniz için kullanın ve ardından istediğiniz dili seçin **Test**.

3.  Microsoft birim test çerçevelerini birini kullanmayı da tercih **birim testi projesi** proje şablonları listesinden. Aksi takdirde, kullanmak istediğiniz test çerçevesi biriminin proje şablonu seçin. Bizim örneğimizde, hesapları projeyi test etmek için proje adı **AccountsTests**.

4.  Birim testi projesi içinde test altındaki kodun bir başvuru ekleyin.  Aynı çözümde başvuru kod projesi oluşturmak nasıl şöyledir:

    1.  Projede seçin **Çözüm Gezgini**.

    2.  Üzerinde **proje** menüsünde seçin **Başvuru Ekle**.

    3.  İçinde **başvuru Yöneticisi** açık iletişim kutusunu **çözüm** düğümü seçin **projeleri**. Kod projesi adını denetleyin ve iletişim kutusunu kapatın.

5.  Başka bir konumda test etmek istediğiniz kod olup olmadığını [bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md) başvurular ekleme hakkında bilgi.

## <a name="next-steps"></a>Sonraki adımlar
 **Birim testleri yazma**

 Aşağıdaki bölümlerden birine bakın:

-   [Birim testi kodunuz](../test/unit-test-your-code.md)

-   [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)

-   [Birim testleri mstest'i framework kullanın](using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md)

 **Birim testleri**

- [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)