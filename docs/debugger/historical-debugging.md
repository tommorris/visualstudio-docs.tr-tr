---
title: Geçmiş hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a75dfc04bd5ce3b1e61cc2c8e8fe293c13560cf9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="historical-debugging"></a>Geçmiş hata ayıklama
Geçmiş hata ayıklama IntelliTrace tarafından toplanan bilgiler bağımlı hata ayıklama bir moddur. Geriye doğru taşıyın ve uygulamanızı yürütme iletmek ve durumunu incelemek sağlar.  
  
 Visual Studio Enterprise edition (ancak değil Professional veya topluluk sürümleri), IntelliTrace kullanabilirsiniz.  
  
## <a name="why-use-historical-debugging"></a>Geçmiş hata ayıklama neden kullanılır?  
 Hataları bulmak için kesme noktalarını ayarlama yerine hit-or-miss affair olabilir. Kodunuzda yakın bir yerde olması için hata şüpheleniyorsanız burada bir kesme noktası belirleyerek, sonra hata ayıklayıcı ve, kesme noktası isabet ve burada yürütme keser yer hatanın kaynağını ortaya çıkarabilir alır soluk uygulamayı çalıştırın. Aksi durumda, kodda başka bir yere kesme noktası ayarlama deneyin ve sorun bulana kadar test adımları tekrar tekrar yürütme hata ayıklayıcı yeniden zorunda kalırsınız.  
  
 ![kesme noktası ayarlama](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 IntelliTrace ve geçmiş hata ayıklama kullanın geçici uygulamanızda dolaşıma girer ve kesme noktalarını ayarlayın, hata ayıklama yeniden başlatmak zorunda kalmadan durumuna (çağrı yığını ve yerel değişkenler) inceleyin ve test adımları yineleyin. Bu, çok kaydetmeniz süresini, özellikle zaman hatayı bulunan yürütmek için uzun süren derin bir test senaryosunda.  
  
## <a name="how-do-i-start-using-historical-debugging"></a>Geçmiş hata ayıklama kullanarak nasıl başlamanız gerekir?  
 IntelliTrace varsayılan olarak açıktır. Yapmanız gereken tek şey hangi olayları ve işlev çağrıları ilginizi çeken ve anlık görüntüler, tam uygulama durumunun görüntülemek isteyip istemediğinizi karar verin. Aramak istediğiniz tanımlama hakkında daha fazla bilgi için bkz: [IntelliTrace özellikleri](../debugger/intellitrace-features.md).  

 - Geçmiş hata ayıklama ile anlık görüntüleri görüntülemek için bkz: [IntelliTrace adım geri kullanarak anlık görüntüleri görüntüleme](../debugger/how-to-use-intellitrace-step-back.md)
 - Değişkenleri inceleyin ve kod gidin öğrenmek için bkz: [geçmiş hata ayıklama ile uygulamanızı inceleyin.](../debugger/historical-debugging-inspect-app.md)
 - IntelliTrace olayları ile hata ayıklama hakkında daha fazla bilgi için bkz: [izlenecek yol: IntelliTrace'i kullanarak](../debugger/walkthrough-using-intellitrace.md).