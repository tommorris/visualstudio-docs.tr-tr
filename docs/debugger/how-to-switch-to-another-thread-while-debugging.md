---
title: "Nasıl yapılır: hata ayıklama sırasında geçiş yapmak için başka bir iş parçacığı | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0710bad95484ada62faa042edabf5b76ac459558
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-switch-to-another-thread-while-debugging-in-visual-studio"></a>Nasıl yapılır: Visual Studio'da hata ayıklarken başka bir iş parçacığı için geçiş
Çok iş parçacıklı uygulamada hata ayıklarken, başka bir iş parçacığı çalıştığınız iş parçacığı geçmek için birkaç yöntemden birini kullanabilirsiniz.

> [!NOTE]
> Hangi iş parçacığı yürütme sırasını denetlemek istiyorsanız, yapmanız [dondurma ve iş parçacıkları çözme](../debugger/get-started-debugging-multithreaded-apps.md).

Kod Düzenleyicisi'ni ve farklı birden çok iş parçacıklı hata ayıklama windows iş parçacıklarında incelediğinizde, sarı ok geçerli iş parçacığının gösterir. Süslü kuyruklu yeşil bir ok geçerli olmayan bir iş parçacığı geçerli hata ayıklayıcı bağlamını sahip olduğunu gösterir.
  
### <a name="to-switch-to-any-thread-that-appears"></a>Görüntülenen herhangi bir iş parçacığı için geçiş yapmak için 
  
-   İçinde **iş parçacığı** veya **paralel Gözcü** penceresinde, iş parçacığı çift tıklayın.  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>Bir iş parçacığı bir kaynak penceresinde geçmek için  
  
-   Sol cilt payı bir iş parçacığı işaret simgesini sağ tıklatın ![iş parçacığı işaret](../debugger/media/dbg-thread-marker.png "ThreadMarker"), işaret **geçiş**ve ardından geçiş yapmak istediğiniz o iş parçacığı adına tıklayın . Kısayol menüsü yalnızca bu belirli konumunda iş parçacığı gösterir.  
  
     Hiçbir iş parçacığı işaretçileri görünmüyorsa, sağ **iş parçacığı** penceresi doğrulayın **kaynak iş parçacıkları Göster** seçilir.  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>Hata ayıklama konumu araç çubuğunda bir iş parçacığı geçmek için  
  
1.  Üzerinde **hata ayıklama konumu** araç tıklatın **iş parçacığı** listesi.  
  
2.  Listede, geçiş yapmak istediğiniz iş parçacığı'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)
