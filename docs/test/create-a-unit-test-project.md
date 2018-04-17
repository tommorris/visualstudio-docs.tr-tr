---
title: Visual Studio'da bir birim testi projesi oluşturma | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 998b936f33047d6132889a949a6ecd56f5a40911
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-unit-test-project"></a>Birim testi projesi oluşturma

Birim testleri test altındaki kod yapısına genellikle yansıtır. Örneğin, birim testi projesi ürün içinde her kod projesi için oluşturulmuş. Oluşturduğunuz test projesinin üretim kodu olarak aynı çözüme olabilir veya ayrı bir çözümde de olabilir. Test projeleri bir çözümde birden çok birim olabilir.

> [!NOTE]
>  Yerel kod için birim konumunu sınar ve test proje yapısını bu konuda açıklanan yapısı farklı olabilir. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Birim testi projesi oluşturmak için:

1.  Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje** (klavye Ctrl + Shift + N).

2.  Yeni Proje iletişim kutusuna genişletin **yüklü** düğümü, test projeniz için kullanın ve ardından istediğiniz dili seçin **Test**.

3.  Microsoft birim test çerçevelerini birini kullanmayı da tercih **birim testi projesi** proje şablonları listesinden. Aksi takdirde, kullanmak istediğiniz test çerçevesi biriminin proje şablonu seçin. Bizim örneğimizde, hesapları projeyi test etmek için AccountsTests proje adı.

4.  Birim testi projesi içinde test altındaki kodun bir başvuru ekleyin.  Aynı çözümde başvuru kod projesi oluşturmak nasıl şöyledir:

    1.  Çözüm Gezgini'nde proje seçin.

    2.  Üzerinde **proje** menüsünde seçin **Başvuru Ekle...** .

    3.  Başvuru Yöneticisi iletişim kutusunu açmak **çözüm** düğümü seçin **projeleri**. Kod projesi adını denetleyin ve iletişim kutusunu kapatın.

5.  Başka bir konumda test etmek istediğiniz kod olup olmadığını [bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md) başvurular ekleme hakkında bilgi.

## <a name="next-steps"></a>Sonraki adımlar
 **Birim testleri yazma**

 Aşağıdaki bölümlerden birine bakın:

-   [Yönetilen Kod için Microsoft Birim Testi Çerçevesi ile .NET Framework için Birim Testleri Yazma](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)

-   [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)

 **Birim testleri**

- [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)