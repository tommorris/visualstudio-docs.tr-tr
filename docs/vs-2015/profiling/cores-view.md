---
title: Çekirdek görünümü | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bce1c1ca458b8d06af89c669a76a2a93371fad5a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684240"
---
# <a name="cores-view"></a>Çekirdekler Görünümü
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [çekirdekler görünümü](https://docs.microsoft.com/visualstudio/profiling/cores-view).  
  
Çekirdekler görünümü mantıksal işlemci çekirdeği için iş parçacığı nasıl eşlendi gösterir. Bu görünüm sunucu uygulamaları yazıyorsanız, iş parçacığı benzeşimini veya iş parçacığı havuzu Yönetimi'ni kullanarak önbellek performansını iyileştirmenize yardımcı olabilir. Da burada iş parçacığı benzeşimini kullanımını çekirdek arası geçiş sorununu worsened durumlarda incelemenize yardımcı olabilir. Çekirdekler görünümü, grafik ve bir gösterge olmak üzere iki bölümden sahiptir.  
  
 Graf y ekseni ve x eksenindeki zaman mantıksal çekirdek gösterir. Graftaki her iş parçacığı benzersiz bir renk sahiptir; böylece zamanla Çekirdekte hareketini izleyebilirsiniz. İş parçacıkları Bu grafikte gösterge alanında seçerek filtreleyebilirsiniz.  
  
 Açıklama alanına grafikte her renk girişi var. Her giriş, iş parçacığı rengi ve adı, çapraz-çekirdek bağlam anahtarları sayısı, toplam bağlam anahtarları sayısı ve çekirdekleri çaprazlayan bağlam anahtarlarının yüzdesi gösterilmektedir. Gösterge, azalan olarak çekirdekler arası bağlam anahtarları sayısına göre sıralanır. Görüntülenen zaman aralığı içinde yürütülen iş parçacıkları listeler.  Yakınlaştırma veya kaydırma listesi güncelleştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md)   
 [Kullanım Görünümü](../profiling/utilization-view.md)   
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)



