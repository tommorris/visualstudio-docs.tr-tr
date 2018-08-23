---
title: Bir birim testi projesi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a608bfba-1a43-4a60-b73a-1fe53ef58098
caps.latest.revision: 10
ms.author: gewarren
manager: douge
ms.openlocfilehash: eb9c64fca2bcd4086073fc349d2c81fa2a62be31
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691754"
---
# <a name="create-a-unit-test-project"></a>Birim testi projesi oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [birim testi projesi oluşturma](https://docs.microsoft.com/visualstudio/test/create-a-unit-test-project).  
  
Birim testleri, test altındaki kod yapısına genellikle yansıtır. Örneğin, her kod projesini ürün için birim testi projesi oluşturulması. Ayrı bir çözümde de olabilir veya üretim kodu aynı çözümde test projesini olabilir. Test projeleri bir çözümde birden çok birim olabilir.  
  
> [!NOTE]
>  Yerel kod için birim konumunu testleri ve test Proje yapısı bu konuda açıklanan yapısı farklı olabilir. Daha fazla bilgi için [mevcut C++ uygulamalarına birim testleri ekleme](../test/unit-testing-existing-cpp-applications-with-test-explorer.md).  
  
## <a name="to-create-a-unit-test-project"></a>Birim testi projesi oluşturmak için:  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni** seçip **proje** (klavye Ctrl + Shift + N).  
  
2.  Yeni Proje iletişim kutusunda Genişlet **yüklü** düğümü, test projeniz için kullanın ve ardından istediğiniz dili seçin **Test**.  
  
3.  Microsoft birim testi çerçevelerini birini kullanmak üzere, **Birim Test projesi** proje şablonları listesinden. Aksi takdirde, kullanmak istediğiniz test çerçevesi biriminin proje şablonu seçin. Bizim örneğimizde, hesapları proje test etmek için AccountsTests proje adı.  
  
4.  Birim test projenizde, test edilen kod bir başvuru ekleyin.  Aynı çözümdeki bir kod projesine başvuru oluşturmak nasıl aşağıda verilmiştir:  
  
    1.  Çözüm Gezgini'nde projeyi seçin.  
  
    2.  Üzerinde **proje** menüsünde seçin **Başvuru Ekle...** .  
  
    3.  Başvuru Yöneticisi iletişim kutusunda açın **çözüm** düğüm ve **projeleri**. Kod projesi adını denetleyin ve iletişim kutusunu kapatın.  
  
5.  Test etmek istediğiniz kod başka bir konumda olup olmadığını, [bir projedeki başvuruları yönetme](../ide/managing-references-in-a-project.md) başvurular ekleme hakkında daha fazla bilgi için.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 **Birim testleri yazma**  
  
 Aşağıdaki bölümlerden birine bakın:  
  
-   [Yönetilen Kod için Microsoft Birim Testi Çerçevesi ile .NET Framework için Birim Testleri Yazma](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)  
  
-   [C++ için Microsoft birim testi çerçevesi ile C/C++ için birim testleri yazma](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)  
  
 **Birim testlerini çalıştırma**  
  
 [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)



