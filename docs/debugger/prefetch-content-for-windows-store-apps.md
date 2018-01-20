---
title: "UWP uygulamalarında prefetched içeriği kullanarak hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 6a0555e2a3ea600a1f5b11eaf95a48f4cfd7df3e
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="debug-uwp-apps-using-prefetched-content-in-visual-studio"></a>UWP uygulamaları prefetched içerik Visual Studio kullanarak hata ayıklama
  
 UWP uygulamanızı daha iyi yanıt vermesi için uygulamanın web sayfaları veya görüntüleri gibi bazı web içeriği önceden yüklemek için Windows isteyebilir [WinINet](http://msdn.microsoft.com/library/0a06f2af-957a-4dff-a8cc-187370181b5c) önbelleği. Bu işlev, prefetching adı verilir. Başlatmada kullanılan içerik için özellikle etkili olur, ancak diğer sık kullanılan içerik çok hazırlık. Yöntemlerinin [Windows.Networking.BackgroundTransfer.ContentPrefetcher](/uwp/api/Windows.Networking.BackgroundTransfer.ContentPrefetcher) sınıfı dağıtılacak istediğiniz içerik URI'ler olanak sağlar. Bkz: Windows SDK [içerik hazırlık örnek](http://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309) uygulamanıza ContentPrefetcher işlevselliği ekleme örnekleri için.  
  
 Windows, zaman ve prefetching gerçekleşmesi gerektiğini belirlemek için buluşsal yöntemler ve hangi kaynaklara indirilir kullanır. Buluşsal hesabı sistem ağ ve güç koşulları, kullanıcı uygulama kullanım geçmişi ve önceki hazırlık denemeleri sonuçlarını alın. Visual Studio'da kullandığınız **tetikleyici Windows mağazası uygulama hazırlık** ContentPrefetcher buluşsal yöntemler yoksaymak ve tüm belirtilen web içeriği önceden yüklemek için Windows zorlamak için komutu. Bu, uygulamanın davranışı veya içeriği (yüklenen veya yüklü değil) bilinen bir durumda hazırlık performansı test etmek istediğiniz durumlarda yararlı olabilir.  
  
## <a name="to-force-preloading-of-contentprefetcher-specified-resources"></a>Belirtilen kaynaklar önceden ContentPrefetcher yüklenmesini zorlamak için  
 Bu yordam, zaten ContentPrefetcher işlevselliği ayarlayın ve uygulama projenizde önceden yüklemek için içerik URI'ler belirtilen olduğunu varsayar. Belirtilen kaynaklar yeni veya değiştirilmiş bir önceden içerik yüklenmesini zorlamak için seçmeden önce uygulamayı durdurmak ve başlatmak sahip **tetikleyici Windows mağazası uygulama hazırlık** komutu. İlk URI'ler kaydetmek için uygulamayı çalıştırın. **Windows mağazası uygulama hazırlık tetiklemek** komutu sonra içerik indirmek ve önbelleğine eklemek için ContentPrefetcher zorlar. Uygulama sonraki çalıştırmalarında içeriği önceden yüklü olmadığını varsayabilirsiniz.  
  
1.  Önceden getirme içerik URI'ler uygulamayla kaydetmek için uygulamayı başlatın. Üzerinde **hata ayıklama** menüsünde seçin **hata ayıklamayı Başlat** (klavye kısayolu: F5).  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **durdurma hata ayıklama** (klavye kısayolu: Shift + F5).  
  
3.  Üzerinde **hata ayıklama** menüsünde seçin **diğer hata ayıklama hedeflerini** ve ardından **tetikleyici Windows mağazası uygulama hazırlık**.  
  
 Şimdi hata ayıklama, test veya prefetched web kaynaklar ile uygulamanızı analiz edin.  
  
> [!NOTE]
>  Her ekleyin veya belirtilen web içeriğini değiştirme adımları yineleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Blog postası: Hazırlık Windows mağazası uygulamaları için Visual Studio 2013 güncelleştirme 2'deki tetikleme](http://blogs.msdn.com/b/visualstudioalm/archive/2014/02/06/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2.aspx)