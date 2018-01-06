---
title: "Visual Studio'da çok iş parçacıklı uygulamalarda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 09/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.gputthreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], high-performance computing
- debugging [Visual Studio], multithreaded
- multithreaded debugging
- high-performance debugging
ms.assetid: 9d175bc2-1d95-4c47-9bc3-9755af968a9c
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8b32134abff19965edac150ac5f69db25640ee08
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="debug-multithreaded-applications-in-visual-studio"></a>Visual Studio'da Çok İş Parçacıklı Uygulamalarda Hata Ayıklama
Bir iş parçacığı, işletim sistemi işlemci zamanı tarafından ayrılan yönergeler dizisidir. İşletim sisteminde çalışan her işlem en az bir iş parçacığından oluşur. Birden çok iş parçacığı bulunan işlemlerin çok iş parçacıklı denir.  
  
Birden çok işlemci, çok çekirdekli işlemciler veya hiper iş parçacığı işlemler bilgisayarlarla aynı anda birden çok iş parçacığı çalıştırabilirsiniz. Birden çok iş parçacığı paralel işleme büyük ölçüde program performansı iyileştirebilir ancak birden çok iş parçacığı izlemek için gereken oluşturduğundan, ayrıca hata ayıklama daha zor hale getirebilir.  
  
Buna ek olarak, çoklu iş parçacığı kullanımı olası hatalar yeni bazı türleri sunar. Genellikle, örneğin, aynı kaynağa erişmek iki veya daha fazla iş parçacığı vardır, ancak aynı anda yalnızca bir iş parçacığı güvenli bir şekilde kaynağa erişebilir. Karşılıklı dışlama çeşit yalnızca bir iş parçacığı aynı anda kaynağa eriştiği emin olmak gereklidir. Karşılıklı dışlama yanlış gerçekleştirilirse oluşturabilirsiniz bir *kilitlenme* koşulu hiçbir iş parçacığı burada yürütebilir. Kilitlenmeler hata ayıklamak için özellikle sabit bir sorun olabilir.

Visual Studio hata ayıklama birden çok iş parçacıklı uygulamaları kullanmak için farklı araçlar sağlar.

- İş parçacığı için iş parçacıklarında hata ayıklama için kullanılan birincil araçlardır **iş parçacığı** penceresinde, iş parçacığı işaretçileri kaynak Windows **Paralel Yığınlar** penceresinde **paralel Gözcü** penceresinde ve **hata ayıklama konumu** araç. Hakkında bilgi edinmek için **iş parçacığı** penceresi ve **hata ayıklama konumu** araç bkz [izlenecek yol: iş parçacıkları penceresini kullanarak hata ayıklama](../debugger/how-to-use-the-threads-window.md). Nasıl kullanılacağını öğrenmek için **Paralel Yığınlar** ve **paralel Gözcü** windows için bkz: [birden çok iş parçacıklı uygulamada hata ayıklama başlamak](../debugger/get-started-debugging-multithreaded-apps.md). Her iki konular iş parçacığı işaretçileri kullanmayı gösterir.
  
- Kullanan kodu için [görev paralel kitaplığı (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl) veya [eşzamanlılık çalışma zamanı](/cpp/parallel/concrt/concurrency-runtime/), hata ayıklama için başlıca araçlar **Paralel Yığınlar** penceresinde, **Paralel Gözcü** penceresinde ve **görevleri** penceresi ( **görevleri** penceresi de JavaScript destekler). Başlamak için bkz: [izlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md) ve [izlenecek yol: C++ AMP uygulamasında hata ayıklama](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application). 

- GPU iş parçacıklarında hata ayıklama için birincil araçtır **GPU iş parçacıkları** penceresi. Bkz: [nasıl yapılır: GPU iş parçacıkları penceresini kullanma](../debugger/how-to-use-the-gpu-threads-window.md).  

- İşlemleri için kullanılan birincil araçlardır **ekleme işlemi için** iletişim kutusu, **işlemleri** penceresinde ve **hata ayıklama konumu** araç.  
  
Visual Studio de güçlü kesme noktaları ve tracepoints, birden çok iş parçacıklı uygulamalarda hata ayıklama, çok kullanışlı olabilir sağlar. Kesme noktaları üzerinde tek tek iş parçacığı yerleştirmek için kesme noktası koşulları ve filtreleri kullanabilirsiniz. Bkz: [kesme noktalarını kullanma](../debugger/using-breakpoints.md). 
  
Bir kullanıcı arabirimine sahiptir çok iş parçacıklı uygulamada hata ayıklama özellikle zor olabilir. Bu durumda, ikinci bir bilgisayara uygulaması çalıştıran ve uzaktan hata ayıklama kullanan düşünebilirsiniz. Bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
## <a name="in-this-section"></a>Bu Bölümde
 [Çok iş parçacıklı uygulamada hata ayıklama başlamak](../debugger/get-started-debugging-multithreaded-apps.md).  
 Kılavuzlu Tur özelliklerle özelliklerinde indirimlere hata ayıklama iş parçacığı **Paralel Yığınlar** penceresi ve **paralel Gözcü** penceresi.

 [İş parçacıklarında ve işlemlerde hata ayıklama araçları](../debugger/debug-threads-and-processes.md)  
 İş parçacıklarında ve işlemlerde hata ayıklama araçları'nın özelliklerini listeler.  
  
 [Birden çok işlem hata ayıklama](../debugger/debug-multiple-processes.md)  
 Hata ayıklama birden çok işlemleri açıklanmaktadır.

 [İzlenecek yol: iş parçacıkları penceresini kullanarak hata ayıklama](../debugger/how-to-use-the-threads-window.md).  
 Nasıl kullanılacağını gösterir izlenecek **iş parçacığı** penceresi ve **hata ayıklama konumu** araç. 

 [İzlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Nasıl kullanılacağını gösterir izlenecek **Paralel Yığınlar** ve **görevleri** windows.  
  
 [Nasıl yapılır: hata ayıklarken başka bir iş parçacığı için geçiş](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
 Başka bir iş parçacığı için hata ayıklama bağlamı değiştirmek için üç yol.  
  
 [Nasıl yapılır: bayrak ve iş parçacıklarını bayrakla](../debugger/how-to-flag-and-unflag-threads.md)  
 Hata ayıklama çalışırken özel dikkat vermek istediğiniz işareti veya bayrak iş parçacıkları.    
  
 [Nasıl yapılır: yüksek performanslı kümede hata ayıklama](../debugger/how-to-debug-on-a-high-performance-cluster.md)  
 Yüksek performanslı kümede çalışan bir uygulamada hata ayıklama teknikleri.  

 [Yerel kod iş parçacıklarında hata ayıklama ipuçları](../debugger/tips-for-debugging-threads-in-native-code.md)  
 Yerel iş parçacıklarında hata ayıklama için yararlı olabilecek basit teknikler. 

 [Nasıl yapılır: yerel kodda iş parçacığı adı ayarlama](../debugger/how-to-set-a-thread-name-in-native-code.md)  
 İş parçacığı gördüğünüz bir ad verin **iş parçacığı** penceresi.  
  
 [Nasıl yapılır: yönetilen kodda iş parçacığı adı ayarlama](../debugger/how-to-set-a-thread-name-in-managed-code.md)  
 İş parçacığı gördüğünüz bir ad verin **iş parçacığı** penceresi. 
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kesme noktalarını kullanma](../debugger/using-breakpoints.md)

 - Tek bir iş parçacığı hata ayıklamak istediğiniz kesme noktası koşullar veya filtreleri kullanın.  
  
 - Tracepoints programınızı sonu olmadan yürütülmesini izlemek için etkinleştirin. Kilitlenmeler gibi sorunlara kavramlarını için yararlı olabilir.  
  
 [İş parçacığı oluşturma](/dotnet/standard/threading/index)  
 Kavramlar iş parçacığı oluşturma [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] programlama, örnek kod dahil.  
  
 [Bileşenleri çoklu iş parçacığı kullanımı](http://msdn.microsoft.com/Library/2fc31e68-fb71-4544-b654-0ce720478779)  
 Nasıl kullanılacağını içinde çoklu iş parçacığı kullanımı [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] bileşenleri.  
  
 [Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](/cpp/parallel/multithreading/multithreading-support-for-older-code-visual-cpp)  
 MFC kullanma C++ programcıları için iş parçacığı, kavramlar ve örnek kod.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş parçacıklarında ve işlemlerde hata ayıklama](../debugger/debug-threads-and-processes.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)