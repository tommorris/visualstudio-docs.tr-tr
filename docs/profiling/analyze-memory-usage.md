---
title: "Visual Studio'da bellek kullanımını çözümleme | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: aac1c901f98d63b8cf77b41a165548cccede4f21
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="analyze-memory-usage"></a>Bellek kullanımını çözümleme
Hata ayıklayıcı tümleşik kullanmak **bellek kullanımı** bellek sızıntıları ve verimli bellek kullanımı bulmak için tanı aracı. Uygulamanız bir veya daha fazla bellek kullanımı araç sağlar *anlık görüntüleri* , yönetilen ve yerel bellek yığını. .NET, yerel ya da karma mod (.NET ve yerel) uygulamaları anlık görüntüleri toplayabilirsiniz.  
  
-   Nesne türlerinin bellek kullanımı üzerindeki göreli etkisini anlamak ve uygulamanızda belleği verimsiz kullanan kodu bulmak için tek bir anlık görüntüyü anailz edebilirsiniz.  
  
-   Zaman içinde artırmak bellek kullanımını neden (fark) iki anlık görüntüleri uygulama kodunuzda alanlar bulmak için de karşılaştırabilirsiniz.  

Ayrıntılı yönergeler için bkz: [bellek kullanımını çözümleme](../profiling/memory-usage.md) Öğreticisi. Hata ayıklayıcı eklemeden bellek kullanımı çözümlemek için bkz: [bellek kullanımını hata ayıklayıcı olmadan](memory-usage-without-debugging2.md).
  
## <a name="blogs-and-videos"></a>Bloglar ve videolar  

|         |         |
|---------|---------|
|  ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin")  |    [Bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171) bellek kullanımı ve Visual Studio 2017 CPU kullanımı analiz etme gösterir tanılama araçlarını kullanma. |

 [Hata ayıklama sırasında CPU ve bellek çözümleme](https://blogs.msdn.microsoft.com/visualstudio/2016/02/15/analyze-cpu-memory-while-debugging/)  
  
 [Visual C++ Blog: Visual C++ 2015'te bellek profili oluşturma](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)  

## <a name="see-also"></a>Ayrıca Bkz.
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)