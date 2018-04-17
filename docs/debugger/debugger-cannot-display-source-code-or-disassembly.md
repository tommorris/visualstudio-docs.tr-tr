---
title: Hata ayıklayıcı kaynak kodu veya ayrıştırılmış kodu görüntüleyemez | Microsoft Docs
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
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee5fe6c07eb9f6f5fbcbca70b58c60a996b5b297
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>Hata Ayıklayıcı Kaynak Kodu veya Ayrıştırılmış Kodu Görüntüleyemez
Bu hata görünür:  
  
 Hata ayıklayıcı kaynak kodu veya burada yürütme durduruldu geçerli konum için ayrıştırılmış kodu görüntüleyemez.  
  
 Bu hata iletisi, birçok nedenden dolayı ortaya çıkabilir:  
  
-   Kendisi için kaynak kodu yok, ayrıştırılmış desteklemeyen bir dil hata ayıklama sırasında bir konumda bir kesme noktası isabet. Açık **kesme noktaları** penceresinde kesme bulun ve silin.  
  
-   Komut dosyasında hata ayıklama, programınıza hiçbir iş parçacığı sırada bir kesme noktası isabet. Seçin **adım** veya **devam** gelen **hata ayıklama** hata ayıklama sürdürmek için menüsü.  
  
-   Güvenlik konuları yığını, iş parçacığı, kaydetme ve diğer bilgileri ayıkladığınız programdan okunurken hata ayıklayıcı engellemiş olabilir. Bir Web uygulamasında hata ayıklama ve sanal dizine erişmek için doğru iznin yoksa durum büyük olasılıkla budur. Sanal dizin için güvenlik anonim ayarlayın ve tekrar deneyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da hata ayıklamayı](../debugger/index.md) [özelliği turu hata ayıklayıcı](../debugger/debugger-feature-tour.md)   
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)