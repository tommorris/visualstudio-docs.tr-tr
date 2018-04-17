---
title: İstemci tarafı komut dosyası hata ayıklama | Microsoft Docs
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
- debugging [Visual Studio], client-side scripts
- client-side scripts, debugging
ms.assetid: bb668527-2288-47bd-a6c8-cecbad76dde2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6db58ee98ffded99ac9eeaa790f9f255842b5905
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="client-side-script-debugging"></a>İstemci Tarafı Betikte Hata Ayıklama
Visual Studio hata ayıklayıcısı bulma ve istemci tarafı betikler ASP.NET sayfalarında hataları düzeltmek için kapsamlı bir hata ayıklama ortamı sağlar.  
  
## <a name="opening-script-documents"></a>Komut dosyası belgeleri açma  
Sunucu tarafı ve istemci tarafı komut dosyası belgelerde listesini görebilirsiniz **Çözüm Gezgini** görüntülemek için. Herhangi bir komut dosyası belgeden açabilirsiniz **Çözüm Gezgini**. Daha fazla bilgi için bkz: [nasıl yapılır: komut dosyası belgeleri görüntüleme](../debugger/how-to-view-script-documents.md).  
  
## <a name="breakpoint-mapping"></a>Kesme noktası eşleme  
 Visual Studio'da doğrudan sunucu tarafı kodu hata ayıklama olamaz, ancak bir sunucu tarafı dosyasında bir kesme noktası ayarlayabilirsiniz. Visual Studio otomatik olarak istemci tarafı dosyasında karşılık gelen bir konuma kesme eşler ve istemci tarafı kodda eşlenen bir kesme noktası oluşturur.  
  
## <a name="manually-or-automatically-attaching-to-script"></a>El ile veya otomatik olarak betiğe ekleme  
 Komut dosyasında hata ayıklama başlamaya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], hata ayıklamak istediğiniz komut dosyası hata ayıklayıcısı eklemeniz gerekir. El ile veya otomatik olarak bu durum oluşabilir.  
  
 Kullanarak el ile ekleyebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı arabirimi eklemek istediğiniz çalışan bir komut dosyası işlemi seçin. Daha fazla bilgi için bkz: [nasıl yapılır: betiğe ekleme](../debugger/how-to-attach-to-script.md).  
  
 Aşağıdakilerden biri oluştuğunda hata ayıklayıcı komut dosyası için otomatik olarak ekler:  
  
-   Komut dosyasında ayarlanan bir kesme noktası isabet.  
  
-   VBScript isabet `Stop` deyimi veya JScript `debugger` betik kodunuzu deyiminde.  
  
-   Tarayıcı veya sunucu bir söz dizimi karşılaşırsa veya komut dosyanıza çalıştırma hatası. Bu durumda, bir iletişim kutusu görünür ve hata ayıklama başlamak için seçeneğiniz vardır.  
  
 Komut dosyasına el ile taktığınızda, komut dosyası işlemi şekilde durdurulamaz kadar çalışmaya devam eder. Bunu seçerek durdurmak **bölün** üzerinde **hata ayıklama** menüsü.  
  
 Hata ayıklayıcı otomatik olarak ekler, komut dosyası yürütme satırında durdurulamaz burada kesme noktası `Stop` deyimi veya `debugger` deyimi veya hata oluştu, veya Internet Explorer'da hata ayıklamayı başlatmak için seçtiğiniz burada noktada.  
  
 Bu noktada, hata ayıklama başlamak için normal hata ayıklayıcı tesis kullanabilirsiniz. Örneğin, kullanabileceğiniz **adım** kodunuzu satır yürütmek devam etmek için komutları. Kullanabileceğiniz **çağrı yığını** penceresini görüntülemek ve denetlemek için komut dosyası akış. Değişken pencerelerini kullanabilirsiniz veya **hemen** değişkenleri ve özelliklerini görüntülemek veya değiştirmek için penceresi.  
  
## <a name="enhanced-error-messages-for-script-debugging"></a>Komut dosyası hata ayıklama için Gelişmiş hata iletileri  
 Visual Studio Gelişmiş hata iletileri sorunlarını hata ayıklama genel komut dosyası için sağlar. Internet Explorer'ı el ile ekleme sürece bu iletileri görüntülenmez. Internet Explorer otomatik olarak açıldığında bir hata koşulu karşılaşırsanız, hata iletileri görebilmeniz için el ile eklemeyi deneyin.  
  
## <a name="debugging-ajax-script-applications"></a>AJAX komut dosyası uygulamalarında hata ayıklama  
 AJAX etkinleştirilmiş Web uygulamaları bir kod yoğun olarak kullanılır ve özel hata ayıklama zorluklar teşkil. AJAX hata ayıklama teknikleri hakkında daha fazla bilgi için bkz:  
  
 [Hata ayıklama ve Ajax uygulamaları genel bakış izleme](http://msdn.microsoft.com/Library/92684ea0-7bb4-4a34-9203-3aa6394ce375).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET ve AJAX uygulamalarında hata ayıklama](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Betik hata ayıklamasında sınırlamalar](../debugger/limitations-on-script-debugging.md)   
 [Değişken pencereler](../debugger/debugger-windows.md)   
 [Komut penceresi](../ide/reference/immediate-window.md)   
 [Hata ayıklama ve izlemeye Ajax uygulamaları genel bakış](http://msdn.microsoft.com/Library/92684ea0-7bb4-4a34-9203-3aa6394ce375)
