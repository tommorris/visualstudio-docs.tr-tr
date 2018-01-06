---
title: ".NET derleme Platformu (&quot;Roslyn&quot;) genişletilebilirlik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 564201b3-1e18-4b88-b615-42c2f57f3fe8
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b292593c6a6c426bb184acd67a920b5e76e3a51f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>.NET derleme Platformu (&quot;Roslyn&quot;) genişletilebilirliği
.NET derleme Platformu ("Roslyn"), çekirdek görev C# ve Visual Basic derleyicileri açma ve araçlar sağlayan ve programlar hakkında zengin bilgi derleyicileri paylaşmak için geliştiricilere sahiptir. Kod çözümleme araçları kod kalitesini geliştirme ve uygulama yapı içinde oluşturucuları yardımcı kod. Araçlar akıllı aldıkça, çok daha da fazla yalnızca derleyicileri sahip derin kod bilgi erişim. Donuk çevirmenler (kaynak kodu ve nesne kodu) yerine Roslyn derleyicileri araç ve uygulama kodu ilgili görevler için kullanabileceğiniz bir API sunar.  
  
 En iyi Roslyn derleyicileri, kendi API, örnekler ve izlenecek yollar ve bu API'leri üstünde oluşturulmuş gerçek araçları tam olarak tüm açık kaynakta olduğunu parçasıdır [github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn). Lütfen daha fazla bilgi edinin ve Roslyn ile çalışmaya başlama OSS sitesine gidin. Roslyn API'lerinden yararlanan bir aracı Oluşturucu olarak başlamak için bağlantıları yanı sıra, en son C# ve son kullanıcı olarak kullanabileceğiniz VB özellikleri almak için bağlantıları bulabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Roslyn Çözümleyicileriyle Çalışmaya Başlama](../extensibility/getting-started-with-roslyn-analyzers.md)