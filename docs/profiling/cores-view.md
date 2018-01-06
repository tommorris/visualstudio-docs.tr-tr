---
title: "Çekirdek View | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.cores
helpviewer_keywords: Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6a2ce5cc9d80e7b96318d0e1fcf8aead09652b41
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="cores-view"></a>Çekirdekler Görünümü
Çekirdekler görünümü mantıksal işlemci çekirdeği için iş parçacığı nasıl eşlendi gösterir. Sunucu uygulamaları yazıyorsanız, bu görünüm iş parçacığı benzeşimini veya iş parçacığı havuzu yönetimi kullanarak Önbellek performansı en iyi hale getirmenize yardımcı olabilir. Ayrıca, durumları burada iş parçacığı benzeşimini kullanımını arası çekirdek geçiş sorun worsened incelemenize yardımcı olur. Çekirdekler görünümü bir grafik ve bir gösterge olmak üzere iki bölümden sahiptir.  
  
 Grafik mantıksal çekirdekler eksenindeki saat ve y ekseni üzerinde gösterir. Zaman içinde çekirdek arasında hareketini izleyebilmeniz için her iş parçacığı grafikte benzersiz bir renk vardır. Bu grafik iş parçacıklarında gösterge alanında seçerek filtreleyebilirsiniz.  
  
 Gösterge alan grafikte her renk için bir giriş var. Her giriş iş parçacığı renk ve adı, çapraz çekirdek bağlam geçişi sayısını, İçerik Geçişi toplam sayısı ve çekirdek arası İçerik Geçişi yüzdesini gösterir. Gösterge azalan içinde çapraz çekirdek bağlamı anahtarları sayısına göre sıralanır. Görüntülenen zaman aralığı içinde yürütülen iş parçacığı listeler.  Yakınlaştırma veya kaydırma liste güncelleştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md)   
 [Kullanım Görünümü](../profiling/utilization-view.md)   
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)