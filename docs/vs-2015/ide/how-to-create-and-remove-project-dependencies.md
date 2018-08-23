---
title: 'Nasıl yapılır: Proje bağımlılıklarını oluşturma ve kaldırma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3626cc4c13600b0a6f20cc40713bd77f4527a3ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690981"
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Nasıl Yapılır: Proje Bağımlılıklarını Oluşturma ve Kaldırma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: Proje bağımlılıklarını oluşturma kaldırıp](https://docs.microsoft.com/visualstudio/ide/how-to-create-and-remove-project-dependencies).  
  
Birden çok proje içeren bir çözüm derlerken, belirli projeleri ilk oluşturulacak, diğer projeleri tarafından kullanılan kodu oluşturmak için gerekli olabilir. Bir proje başka bir proje tarafından oluşturulan yürütülebilir kodu kullanırken, kodu oluşturan proje kodu kullanan projenin proje bağımlılık olarak adlandırılır. Bu bağımlılık ilişkiler tanımlanabilir **proje bağımlılıkları** iletişim kutusu.  
  
### <a name="to-assign-dependencies-to-projects"></a>Bağımlılıkları projelerine atamak için  
  
1.  Çözüm Gezgini'nde bir proje seçin.  
  
2.  Üzerinde **proje** menüsünde seçin **proje bağımlılıkları**.  
  
     **Proje bağımlılıkları** iletişim kutusu açılır.  
  
    > [!NOTE]
    >  **Proje bağımlılıkları** seçeneği, yalnızca kullanılabilir birden fazla proje içeren bir çözümde.  
  
3.  Üzerinde **bağımlılıkları** sekmesinde, bir proje seçin **proje** açılan menüsü.  
  
4.  İçinde **bağlıdır** alanında, bu proje önce oluşturmanız gerekir, başka bir projeye ait onay kutusunu seçin.  
  
 Proje bağımlılıkları oluşturmadan önce çözümünüzü birden fazla proje oluşmalıdır.  
  
### <a name="to-remove-dependencies-from-projects"></a>Proje bağımlılıkları kaldırmak için  
  
1.  Çözüm Gezgini'nde bir proje seçin.  
  
2.  Üzerinde **proje** menüsünde seçin **proje bağımlılıkları**.  
  
     **Proje bağımlılıkları** iletişim kutusu açılır.  
  
    > [!NOTE]
    >  **Proje bağımlılıkları** seçeneği, yalnızca kullanılabilir birden fazla proje içeren bir çözümde.  
  
3.  Üzerinde **bağımlılıkları** sekmesinde, bir proje seçin **proje** açılan menüsü.  
  
4.  İçinde **bağlıdır** alan, bu projenin bağımlılıklarıdır artık herhangi bir projeyi yanındaki onay kutularını temizleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Projeleri ve Visual Studio çözümleri oluşturma ve temizleme](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)   
 [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)   
 [NIB nasıl yapılır: Proje özelliklerini ve yapılandırma ayarlarını değiştirme](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)



