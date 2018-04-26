---
title: 'Nasıl yapılır: oluşturun ve proje bağımlılıkları kaldırın'
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ProjectDependenciesDlg
helpviewer_keywords:
- vs.build.projectdependencies
- project dependencies
- builds [Visual Studio], setting up
- project build configurations, dependencies
- dependencies, project
- projects [Visual Studio], dependencies
ms.assetid: e2a0a8ff-dae7-40a8-b774-b88aa5235183
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b0948dab860431d9693e67489d958f00743fa17
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Nasıl yapılır: oluşturun ve proje bağımlılıkları kaldırın

Birden çok proje içeren bir çözüm oluştururken, önce belirli projeler derlemek için diğer projeler tarafından kullanılan kodu oluşturmak için gerekli olabilir. Bir proje başka bir project tarafından oluşturulan yürütülebilir kod kullanır, kod oluşturur proje kodunu tüketen projenin proje bağımlılık olarak adlandırılır. İçinde bu tür bağımlılık ilişkiler tanımlanabilir **proje bağımlılıkları** iletişim kutusu.

## <a name="to-assign-dependencies-to-projects"></a>Bağımlılıklar projelerine atamak için

1.  İçinde **Çözüm Gezgini**, bir proje seçin.

2.  Üzerinde **proje** menüsünde seçin **proje bağımlılıkları**.

     **Proje bağımlılıkları** iletişim kutusu açılır.

    > [!NOTE]
    > **Proje bağımlılıkları** seçenektir yalnızca bir çözümde birden çok proje ile kullanılabilir.

3.  Üzerinde **bağımlılıkları** sekmesinde, bir projeden seçin **proje** açılır menü.

4.  İçinde **bağlıdır** alanında, bu proje yapmadan önce oluşturmalısınız başka bir projeye ait onay kutusunu seçin.

 Proje bağımlılıkları oluşturmadan önce çözümünüzün birden fazla projenin oluşmalıdır.

## <a name="to-remove-dependencies-from-projects"></a>Proje bağımlılıkları kaldırmak için

1.  İçinde **Çözüm Gezgini**, bir proje seçin.

2.  Üzerinde **proje** menüsünde seçin **proje bağımlılıkları**.

     **Proje bağımlılıkları** iletişim kutusu açılır.

    > [!NOTE]
    > **Proje bağımlılıkları** seçenektir yalnızca bir çözümde birden çok proje ile kullanılabilir.

3.  Üzerinde **bağımlılıkları** sekmesinde, bir projeden seçin **proje** açılır menü.

4.  İçinde **bağlıdır** alan, artık bu proje bağımlılıkları olmayan diğer projeler yanındaki onay kutularını temizleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme ve projeler ve çözümler Visual Studio'da Temizle](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)
- [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)
- [Proje ve çözüm özelliklerini yönetme](managing-project-and-solution-properties.md)