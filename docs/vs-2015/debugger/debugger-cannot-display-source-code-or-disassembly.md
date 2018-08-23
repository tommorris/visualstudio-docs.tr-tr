---
title: Hata ayıklayıcı kaynak kodu veya Ayrıştırılmış kod görüntüleyemiyor | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd21a38123894e7254bf4af6629528f8af4bf52d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685800"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>Hata Ayıklayıcı Kaynak Kodu veya Ayrıştırılmış Kodu Görüntüleyemez
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklayıcı olamaz görüntü kaynak kodu veya ayrıştırılmış kodu](https://docs.microsoft.com/visualstudio/debugger/debugger-cannot-display-source-code-or-disassembly).  
  
Bu hata görünür:  
  
 Hata ayıklayıcı kaynak kodu veya Ayrıştırılmış kod burada yürütme durduruldu şu anki konum için görüntülenemiyor.  
  
 Bu hata iletisi, bir dizi nedenden ötürü ortaya çıkabilir:  
  
-   Bir konum için kaynak kodu yok, ayrıştırılmış kodu desteklemiyor bir dil hata ayıklarken bir kesme noktasına ulaşırsınız. Açık **kesme noktaları** penceresinde kesme noktasını bulun ve silin.  
  
-   Betik hata ayıklaması yapıyorsanız programınızdaki iş parçacığı kopyalanırken bir kesme noktası isabet. Seçin **adım** veya **devam** gelen **hata ayıklama** hata ayıklama devam etmek için menü.  
  
-   Güvenlik konuları yığın, iş parçacığı, kaydı ve diğer bağlam bilgileriyle hata ayıklaması yaptığınız programı okunurken hata ayıklayıcı engellemiş olabilir. Bir Web uygulaması hata ayıklaması yapıyorsanız ve doğru sanal dizine erişim izni yoksa durum büyük olasılıkla budur. Sanal dizin için güvenlik anonim olarak ayarlayın ve yeniden deneyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Visual Studio'da hata ayıklama](../debugger/debugging-in-visual-studio.md)   
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)



