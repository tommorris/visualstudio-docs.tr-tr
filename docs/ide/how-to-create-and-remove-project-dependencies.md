---
title: "Nasıl yapılır: oluşturma ve kaldırma proje bağımlılıkları | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ProjectDependenciesDlg
helpviewer_keywords:
- vs.build.projectdependencies
- project dependencies
- builds [Visual Studio], setting up
- project build configurations, dependencies
- dependencies, project
- projects [Visual Studio], dependencies
ms.assetid: e2a0a8ff-dae7-40a8-b774-b88aa5235183
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9762bf8905ad162bd6059fae9ed1b7be06ca7919
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Proje ve çözüm özelliklerini yönetme](managing-project-and-solution-properties.md)

