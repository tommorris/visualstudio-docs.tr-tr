---
title: "Hata ayıklayıcıda GPU iş parçacıkları görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.gputthreads
- vs.debug.gputhreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, GPU threads window
ms.assetid: c647c502-a9f0-48e0-a430-976744a5fa51
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b4782a1650034424d2616e47f46e07cec4d01ae5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-gpu-threads-window"></a>Nasıl Yapılır: GPU İş Parçacıkları Penceresini Kullanma
GPU iş parçacıkları penceresinde inceleyin ve uygulamada hata ayıklama yaptığınız GPU üzerinde çalışan iş parçacıkları ile iş. GPU üzerinde çalışan uygulamalar hakkında daha fazla bilgi için bkz: [C++ AMP'ye genel bakış](/cpp/parallel/amp/cpp-amp-overview).  
  
 GPU iş parçacıkları penceresi, her satır sütunların tümünün aynı değerlere sahip GPU iş parçacıkları kümesi temsil eden bir tablo içeriyor. Sıralama, yeniden sıralamak, kaldırmak ve sütunları olan öğeleri grubu. Bayrak, bayrakla dondurmak, (askıya alma) ve GPU iş parçacıkları penceresi (devam) parçacıklarından çözme. GPU iş parçacıkları penceresinde aşağıdaki sütunlar görüntülenir:  
  
-   Özel dikkat edilmesi gereken istediğiniz bir iş parçacığı işaretleyebilirsiniz bayrağı sütun.  
  
-   Sarı bir ok geçerli iş parçacığının gösterir geçerli iş parçacığı sütununun.  
  
-   **İş parçacığı sayısı** aynı konumda iş parçacığı sayısını görüntüler sütun.  
  
-   **Satır** her grup iş parçacığı bulunduğu kod satırını görüntüler sütun.  
  
-   **Adresi** her grup iş parçacığı bulunduğu yönerge adresi görüntüler sütun. Varsayılan olarak, bu sütun gizlenir.  
  
-   **Konumu** kaynak kodunu konumdadır sütun.  
  
-   **Durum** sütununda, iş parçacığının etkin, engellenmiş, başlatılmamış veya tam olup olmadığını gösterir.  
  
-   **Döşeme** iş parçacıklarının döşeme dizini satırda gösterir sütun.  
  
 Tablo üstbilgisinin kutucuğu ve iş parçacığı görüntülenmesini gösterir.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-display-the-gpu-threads-window"></a>GPU iş parçacıkları penceresini görüntülemek için  
  
1.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** projenin penceresine altında **yapılandırma özellikleri**, seçin **hata ayıklama**.  
  
3.  İçinde **başlatmak için hata ayıklayıcı** listesinde **yerel Windows hata ayıklayıcı**. İçinde **hata ayıklayıcı türü** listesinde **yalnızca GPU**. Bu hata ayıklayıcı kesme noktalarında GPU üzerinde çalışan bir kod bozan seçmeniz gerekir.  
  
4.  Seçin **Tamam** düğmesi.  
  
5.  GPU kodunda kesme noktası ayarlayın.  
  
6.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**. Uygulamayı kesme ulaşmak için bekleyin.  
  
7.  Menü çubuğu birini **hata ayıklama**, **Windows**, **GPU iş parçacıkları**.  
  
### <a name="to-switch-to-a-different-thread"></a>Farklı bir iş parçacığı için geçiş yapmak için  
  
-   Sütun çift tıklayın. (Klavye: satırı seçin ve Enter'i seçin.)  
  
### <a name="to-display-a-particular-tile-and-thread"></a>Belirli kutucuğu ve iş parçacığı görüntülemek için  
  
1.  Seçin **iş parçacığı değiştirici genişletin** GPU iş parçacıkları penceresi düğmesini.  
  
2.  Metin kutularına kutucuğu ve iş parçacığı değerler girin.  
  
3.  Üzerinde oku olan düğmesini seçin.  
  
### <a name="to-display-or-hide-a-column"></a>Görüntülemek veya bir sütun gizlemek için  
  
-   GPU iş parçacıkları penceresi için kısayol menüsünü açın, seçin **sütunları**ve ardından görüntülemek veya gizlemek istediğiniz sütun seçin.  
  
### <a name="to-sort-by-a-column"></a>Bir sütuna göre sıralamak için  
  
-   Sütun başlığı seçin.  
  
### <a name="to-group-threads"></a>Grup iş parçacığı  
  
-   GPU iş parçacıkları penceresi için kısayol menüsünü açın, seçin **Group By**ve ardından görüntülenen sütun adlarından birini seçin. Seçin **hiçbiri** iş parçacıklarının çözmek için.  
  
### <a name="to-freeze-or-thaw-a-row-of-threads"></a>Freeze veya iş parçacıkları sırasının çözme  
  
-   Satır için kısayol menüsünü açın ve seçin **Dondur** veya **çözme**.  
  
### <a name="to-flag-or-unflag-a-row-of-threads"></a>Bayrak veya iş parçacıkları sırasının bayrakla  
  
-   İş parçacığı için bayrağı sütunu seçin veya iş parçacığı için kısayol menüsünü açın ve seçin **bayrağı** veya **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Yalnızca görüntülemek için iş parçacıklarını bayrakla  
  
-   GPU iş parçacıkları penceresinde bayrak düğmesini seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Nasıl yapılır: paralel İzleme penceresini kullanma](../debugger/how-to-use-the-parallel-watch-window.md)   
 [İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)