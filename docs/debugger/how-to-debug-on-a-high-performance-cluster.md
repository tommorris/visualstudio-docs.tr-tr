---
title: 'Nasıl yapılır: yüksek performanslı kümede hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- cluster debugging
- high-perfomance debugging
ms.assetid: a2f0eb07-840e-4f95-a1b1-9509217e5b8f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d90037fbf147dd0234ee356f217ab97e5af87a01
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-on-a-high-performance-cluster"></a>Nasıl Yapılır: Yüksek Performanslı Kümede Hata Ayıklama
Bir çoklu işlem programı yüksek performanslı kümede hata ayıklama uzak bir bilgisayarda sıradan bir program hata ayıklama gibi değildir. Ancak, bazı ek noktalar vardır. Genel Uzaktan Kurulum gereksinimleri için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
 Yüksek performanslı kümede hata ayıklarken, tüm kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] windows ve uzaktan hata ayıklama için kullanılabilir teknikleri hata ayıklama. Ancak, uzaktan hata ayıklama yaptığınız çünkü dış konsol penceresi kullanılabilir değil.  
  
 **İş parçacığı** penceresi ve **işlemleri** penceresi paralel uygulamalarında hata ayıklama için özellikle yararlıdır. Bu windows kullanımı hakkında ipuçları için bkz: [nasıl yapılır: işlemler penceresini kullanma](http://msdn.microsoft.com/en-us/0207ce2f-8ceb-4fe7-b2b5-4dd35b035ed7) ve [izlenecek yol: iş parçacıkları penceresini kullanarak hata ayıklama](../debugger/how-to-use-the-threads-window.md).  
  
 Aşağıdaki yordamlar, yüksek performanslı kümede hata ayıklama için özellikle yararlı olan bazı teknikleri gösterir.  
  
 Paralel uygulamada hata ayıklama işlemi yaparken, belirli iş parçacığı, işlem veya bilgisayarda bir kesme noktası ayarlamak isteyebilirsiniz. Bu, normal bir kesme noktası oluşturma ve sonra bir kesme noktası filtre ekleyerek yapabilirsiniz.  
  
### <a name="to-open-the-breakpoint-filter-dialog-box"></a>Kesme noktası filtre iletişim kutusunu açmak için  
  
1.  Bir kaynak penceresinde kesme karakteri sağ **ayrıştırılmış** penceresinde, **çağrı yığını** penceresinde, veya **kesme noktaları** penceresi.  
  
2.  Kısayol menüsünde **filtre**. Bu seçenek en üstünde düzeyi veya alt altında görünebilir **kesme noktaları**.  
  
### <a name="to-set-a-breakpoint-on-a-specific-computer"></a>Belirli bir bilgisayarda bir kesme noktası ayarlama  
  
1.  Bilgisayar adından alma **işlemleri** penceresi.  
  
2.  Bir kesme noktası seçin ve açın **kesme noktası filtre** önceki yordamda açıklandığı gibi iletişim kutusu.  
  
3.  İçinde **kesme noktası filtre** iletişim kutusuna:  
  
     MachineName =*yourmachinename*  
  
     Daha karmaşık bir filtre oluşturmak için yan tümceleri kullanılarak birleştirebilirsiniz `&`, AND işleci `||`, OR işleci `!`, NOT işleci ve parantez.  
  
4.  **Tamam**'ı tıklatın.  
  
### <a name="to-set-a-breakpoint-on-a-specific-process"></a>Belirli bir işlemde bir kesme noktası ayarlamak için  
  
1.  İşlem adı veya kimliği numarasından işlem **işlemleri** penceresi.  
  
2.  Bir kesme noktası seçin ve açın **kesme noktası filtre** ilk yordam olduğu gibi iletişim kutusu.  
  
3.  İçinde **kesme noktası filtre** iletişim kutusuna:  
  
     `ProcessName =`  *yourprocessname*  
  
     —veya—  
  
     `ProcessID =` *yourprocessIDnumber*  
  
     Daha karmaşık bir filtre oluşturmak için yan tümceleri kullanılarak birleştirebilirsiniz `&`, AND işleci `||`, OR işleci `!`, NOT işleci ve parantez.  
  
4.  **Tamam**'ı tıklatın.  
  
### <a name="to-set-a-breakpoint-on-a-specific-thread"></a>Belirli bir iş parçacığı üzerinde bir kesme noktası ayarlamak için  
  
1.  İş parçacığı adı elde etmek veya kimliği numaralı iş parçacığı **iş parçacığı** penceresi.  
  
2.  Bir kesme noktası seçin ve açın **kesme noktası filtre** ilk yordamda açıklanan iletişim kutusu.  
  
3.  İçinde **kesme noktası filtre** iletişim kutusuna:  
  
     `ThreadName =` *yourthreadname*  
  
     —veya—  
  
     `ThreadID =` *yourthreadIDnumber*  
  
     Daha karmaşık bir filtre oluşturmak için yan tümceleri kullanılarak birleştirebilirsiniz `&`, AND işleci `||`, OR işleci `!`, NOT işleci ve parantez.  
  
4.  **Tamam**'ı tıklatın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek adlı bir bilgisayarda bir kesme noktası için bir filtre oluşturulacağını gösterir `marvin` ve adlı bir iş parçacığı `fourier1`.  
  
```  
(MachineName = marvin) & (ThreadName = fourier1)  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)   
 [Nasıl yapılır: işlemler penceresini kullanma](http://msdn.microsoft.com/en-us/0207ce2f-8ceb-4fe7-b2b5-4dd35b035ed7)   
 [Hata ayıklama birden çok iş parçacıklı uygulamaları kullanmaya başlama](../debugger/get-started-debugging-multithreaded-apps.md)   
 [İş parçacıklarında ve işlemlerde](http://msdn.microsoft.com/en-us/73d87480-9af3-4d1b-baf5-397d5d876ae6)   
 [Kesme noktalarını kullanma](../debugger/using-breakpoints.md)