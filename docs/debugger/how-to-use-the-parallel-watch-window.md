---
title: Paralel iş parçacıklarında değişkenleri bir izleme ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 04/25/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.parallelwatch
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel watch window
ms.assetid: 28004d9b-420c-48f7-b80e-ab1519802558
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7909553271e138ab3bddaa1f4d509a4f4b0b293d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="set-a-watch-on-variables-in-parallel-threads-in-visual-studio"></a>Visual Studio'da paralel iş parçacıklarında değişkenleri bir izleme ayarlama
Paralel Gözcü penceresi içinde aynı anda tek bir ifade birden çok iş parçacığı üzerinde tutan değerleri görüntüleyebilirsiniz. Her satır bir uygulamada çalıştırılan bir iş parçacığını temsil eder, ancak bir iş parçacığı içinde birden çok satır temsil edilebilir. Daha açık belirtmek gerekirse, her satır, işlev imzası geçerli yığın çerçevesinde işlevi eşleşen bir işlev çağrısını temsil eder. Sıralama, yeniden sıralamak, kaldırmak ve sütunları öğeleri grubu. Bayrak, bayrakla dondurmak, (askıya) ve (devam) iş parçacıklarının çözme. Aşağıdaki sütunlar görüntülenir **paralel Gözcü** penceresi:  
  
-   Özel dikkat edilmesi gereken istediğiniz bir iş parçacığı işaretleyebilirsiniz bayrağı sütun.  
  
-   Sarı bir ok geçerli iş parçacığının gösterir geçerli iş parçacığı sütununun (yeşil bir ok süslü kuyruklu geçerli olmayan bir iş parçacığı geçerli hata ayıklayıcı bağlamını sahip olduğunu gösterir).  
  
-   Makine, işlem, kutucuğu, görev ve iş parçacığı görüntüleyebilirsiniz yapılandırılabilir bir sütun.  
  
    > [!TIP]
    >  Değiştirilen görev bilgileri **paralel Gözcü** penceresinde, ilk açmanız **görev** penceresi.  
  
-   Boş *Gözcü Ekle* sütunları, hangi girebilirsiniz izlemek için ifadeler.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-display-the-parallel-watch-window"></a>Paralel İzleme penceresini görüntülemek için  
  
1.  Kodda bir kesme noktası ayarlayın.  
  
2.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**. Uygulamayı kesme ulaşmak için bekleyin.  
  
3.  Menü çubuğunda seçin **hata ayıklama**, **Windows**, **paralel Gözcü**ve ardından Gözcü penceresi seçin. Dörde kadar windows açabilirsiniz.  
  
### <a name="to-add-a-watch-expression"></a>Gözcü ifadesi eklemek için  
  
-   Boş birini *Gözcü Ekle* sütunları ve Gözcü ifadesi girin.  
  
### <a name="to-flag-or-unflag-a-thread"></a>Bayrak veya bir iş parçacığı bayrakla  
  
-   Satır bayrağı sütunu seçin (ilk sütun) veya iş parçacığı için kısayol menüsünü açın ve seçin **bayrağı** veya **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Yalnızca görüntülemek için iş parçacıklarını bayrakla  
  
-   Seçin **Göster'i yalnızca işaretlenen** sol üst köşesindeki düğmesini **paralel Gözcü** penceresi.  
  
### <a name="to-switch-to-another-thread"></a>Başka bir iş parçacığı için geçiş yapmak için  
  
-   Geçerli iş parçacığı sütun çift tıklayın (ikinci sütun). (Klavye: satırı seçin ve Enter tuşuna basın.)  
  
### <a name="to-sort-a-column"></a>Bir sütunu sıralamak için  
  
-   Sütun başlığı seçin.  
  
### <a name="to-group-threads"></a>Grup iş parçacığı  
  
-   Paralel Gözcü penceresi için kısayol menüsünü açın, seçin **Group By**ve ardından uygun alt menü öğesini seçin.  
  
### <a name="to-freeze-or-thaw-threads"></a>Freeze veya iş parçacığı çözme  
  
-   Satır için kısayol menüsünü açın ve seçin **Dondur** veya **çözme**.  
  
### <a name="to-export-the-data-in-the-parallel-watch-window"></a>Paralel Gözcü penceresi verileri dışarı aktarmak için  
  
-   Seçin **Excel'de Aç** düğmesine tıklayın ve ardından **Excel'de Aç** veya **CSV'ye aktar**.  
  
### <a name="to-filter-by-a-boolean-expression"></a>Boole ifadesine göre filtre uygulamak için  
  
-   Boole ifadesinde girin **Boole ifadesine göre filtrele** kutusu. Hata ayıklayıcı her iş parçacığı içeriği için ifadeyi hesaplar. Yalnızca değerin olduğu satırları `true` görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Nasıl yapılır: GPU iş parçacıkları penceresini kullanma](../debugger/how-to-use-the-gpu-threads-window.md)   
 [İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)