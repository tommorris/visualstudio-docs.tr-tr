---
title: 'Nasıl yapılır: derleme aynı anda birden çok yapılandırmaları'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3772e194f801735edf4c857b605b3abb6c22144b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>Nasıl yapılır: derleme aynı anda birden çok yapılandırmaları

Kullanarak birden çok projelerle veya hatta tüm yapı yapılandırmalarına aynı anda birçok türleri oluşturabilirsiniz **Toplu derleme** iletişim kutusu. Ancak, aynı anda birden çok derleme yapılandırmaları projelerinde aşağıdaki türlerini oluşturulamıyor:

1.  [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar JavaScript kullanan Windows için oluşturulmuştur.

2.  Tüm Visual Basic projeleri.

 Derleme yapılandırmaları hakkında daha fazla bilgi için bkz: [anlayın yapı yapılandırmaları](../ide/understanding-build-configurations.md).

## <a name="to-build-a-project-in-multiple-build-configurations"></a>Birden çok derleme yapılandırmaları bir proje oluşturmak için

1.  Menü çubuğunda seçin **yapı** > **Toplu derleme**.

2.  İçinde **yapı** onay kutularını bir projeyi oluşturmak istediğiniz yapılandırmaları için sütun seçin.

    > [!TIP]
    > Düzenlemek veya bir yapı yapılandırması için bir çözüm oluşturmak için Seç **yapı** > **Configuration Manager** açmak için menü çubuğunda **Configuration Manager** iletişim kutusu. Bir çözüm için bir yapı yapılandırma düzenledikten sonra Seç **yeniden** düğmesini **Toplu derleme** derleme Çözümdeki projeler için yapılandırmaları tüm güncelleştirmek için iletişim kutusu.

3.  Seçin **yapı** veya **yeniden** belirttiğiniz yapılandırmalarla Projeyi derlemek için düğmeler.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: oluşturma ve düzenleme yapılandırmaları](../ide/how-to-create-and-edit-configurations.md)
- [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)
- [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)