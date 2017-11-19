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
ms.openlocfilehash: 1f9811440146e1d758158a64fd227ba0a2c2e1e4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>.NET derleme Platformu (&quot;Roslyn&quot;) genişletilebilirliği
.NET derleme Platformu ("Roslyn"), çekirdek görev C# ve Visual Basic derleyicileri açma ve araçlar sağlayan ve programlar hakkında zengin bilgi derleyicileri paylaşmak için geliştiricilere sahiptir. Kod çözümleme araçları kod kalitesini geliştirme ve uygulama yapı içinde oluşturucuları yardımcı kod. Araçlar akıllı aldıkça, çok daha da fazla yalnızca derleyicileri sahip derin kod bilgi erişim. Donuk çevirmenler (kaynak kodu ve nesne kodu) yerine Roslyn derleyicileri araç ve uygulama kodu ilgili görevler için kullanabileceğiniz bir API sunar.  
  
 En iyi Roslyn derleyicileri, kendi API, örnekler ve izlenecek yollar ve bu API'leri üstünde oluşturulmuş gerçek araçları tam olarak tüm açık kaynakta olduğunu parçasıdır [github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn). Lütfen daha fazla bilgi edinin ve Roslyn ile çalışmaya başlama OSS sitesine gidin. Roslyn API'lerinden yararlanan bir aracı Oluşturucu olarak başlamak için bağlantıları yanı sıra, en son C# ve son kullanıcı olarak kullanabileceğiniz VB özellikleri almak için bağlantıları bulabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Roslyn çözümleyiciler ile çalışmaya başlama](../extensibility/getting-started-with-roslyn-analyzers.md)