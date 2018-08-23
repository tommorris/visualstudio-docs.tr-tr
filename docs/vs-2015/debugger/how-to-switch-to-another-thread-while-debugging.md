---
title: 'Nasıl yapılır: hata ayıklarken başka bir iş parçacığına geçiş | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c682ddff5fd4dc44fe79fa81c1615362f8121e5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690962"
---
# <a name="how-to-switch-to-another-thread-while-debugging"></a>Nasıl Yapılır: Hata Ayıklarken Başka Bir İş Parçacığına Değiştirme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: başka bir iş parçacığı sırasında hata ayıklama için geçiş](https://docs.microsoft.com/visualstudio/debugger/how-to-switch-to-another-thread-while-debugging).  
  
Çok iş parçacıklı uygulamada hata ayıklaması yaparken, başka bir iş parçacığına çalıştığınız iş parçacığı bağlamdan geçiş yapmak için birkaç yöntemden birini kullanabilirsiniz.  
  
### <a name="to-switch-to-any-thread-that-appears-in-the-threads-window"></a>İş parçacıkları penceresinde görüntülenen herhangi bir iş parçacığına geçiş yapmak için  
  
-   İş parçacığını çift tıklayın.  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>Bir kaynak penceresinde bir iş parçacığına geçiş yapmak için  
  
-   Sol kanaldaki iş parçacığı göstergesi sağ tıklayın, fareyle **geçin**ve sonra geçiş yapmak istediğiniz o iş parçacığı adına tıklayın. Yalnızca bu belirli bir konumdaki iş parçacıkları kısayol menüsünü gösterir.  
  
     Hiçbir göstergeleri görünmüyorsa, sağ **iş parçacıkları** penceresi doğrulayın **kaynak iş parçacıklarını Göster** seçilir.  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>Hata ayıklama konumu araç çubuğunda bir iş parçacığına geçiş yapmak için  
  
1.  Üzerinde **hata ayıklama konumu** araç çubuğunda tıklatın **iş parçacığı** kutusu.  
  
2.  Listede, geçiş yapmak istediğiniz iş parçacığı tıklayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)



