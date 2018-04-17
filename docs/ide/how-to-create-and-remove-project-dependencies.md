---
title: 'Nasıl yapılır: oluşturma ve kaldırma proje bağımlılıkları | Microsoft Docs'
ms.custom: ''
ms.date: 06/21/2017
ms.technology:
- vs-ide-general
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
ms.openlocfilehash: 9798df83536634797a101e09ca1638d6fa22e1f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Nasıl Yapılır: Proje Bağımlılıklarını Oluşturma ve Kaldırma
Birden çok proje içeren bir çözüm oluştururken, önce belirli projeler derlemek için diğer projeler tarafından kullanılan kodu oluşturmak için gerekli olabilir. Bir proje başka bir project tarafından oluşturulan yürütülebilir kod kullanır, kod oluşturur proje kodunu tüketen projenin proje bağımlılık olarak adlandırılır. İçinde bu tür bağımlılık ilişkiler tanımlanabilir **proje bağımlılıkları** iletişim kutusu.  

### <a name="to-assign-dependencies-to-projects"></a>Bağımlılıklar projelerine atamak için  

1.  Çözüm Gezgini'nde proje seçin.  

2.  Üzerinde **proje** menüsünde seçin **proje bağımlılıkları**.  

     **Proje bağımlılıkları** iletişim kutusu açılır.  

    > [!NOTE]
    >  **Proje bağımlılıkları** seçenektir yalnızca bir çözümde birden çok proje ile kullanılabilir.  

3.  Üzerinde **bağımlılıkları** sekmesinde, bir projeden seçin **proje** açılır menü.  

4.  İçinde **bağlıdır** alanında, bu proje yapmadan önce oluşturmalısınız başka bir projeye ait onay kutusunu seçin.  

 Proje bağımlılıkları oluşturmadan önce çözümünüzün birden fazla projenin oluşmalıdır.  

### <a name="to-remove-dependencies-from-projects"></a>Proje bağımlılıkları kaldırmak için  

1.  Çözüm Gezgini'nde proje seçin.  

2.  Üzerinde **proje** menüsünde seçin **proje bağımlılıkları**.  

     **Proje bağımlılıkları** iletişim kutusu açılır.  

    > [!NOTE]
    >  **Proje bağımlılıkları** seçenektir yalnızca bir çözümde birden çok proje ile kullanılabilir.  

3.  Üzerinde **bağımlılıkları** sekmesinde, bir projeden seçin **proje** açılır menü.  

4.  İçinde **bağlıdır** alan, artık bu proje bağımlılıkları olmayan diğer projeler yanındaki onay kutularını temizleyin.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Projeler ve çözümler Visual Studio'da oluşturma ve temizleme](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)   
 [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)   
 [Proje ve Çözüm Özelliklerini Yönetme](managing-project-and-solution-properties.md)

