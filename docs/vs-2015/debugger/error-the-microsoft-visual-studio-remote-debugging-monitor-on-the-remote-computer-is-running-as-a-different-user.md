---
title: 'Hata: Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayardaki farklı bir kullanıcı olarak çalışıyor | Microsoft Docs'
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
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
ms.assetid: e5b18734-2daf-4c58-b5de-24ae1295703e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5256feb22e09eb75fa8f4d5a50e8beafeec8f97d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697249"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Hata: Uzak bilgisayardaki Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisi farklı kullanıcı olarak çalışıyor.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayardaki farklı bir kullanıcı olarak çalışıyor](https://docs.microsoft.com/visualstudio/debugger/error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user).  
  
Uzaktan hata ayıklama yapmaya çalışırken, aşağıdaki hata iletisini alabilirsiniz:  
  
 Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayardaki farklı bir kullanıcı olarak çalışıyor.  
  
## <a name="cause"></a>Sebep  
 Bu ileti, kimlik doğrulaması yok modunda hata ayıklama ve msvsmon başlatan kullanıcının Visual Studio çalıştıran kullanıcının olmadığında oluşur.  
  
## <a name="solution"></a>Çözüm  
 Güvenli ve en iyi çözümü uzak bir hata ayıklama İzleyicisi (msvsmon.exe) Visual Studio aynı kullanıcı hesabı altında çalıştırmaktır. Bu işlemi yapamazsınız ile başka bir hesap altında uzaktan hata ayıklama İzleyicisi çalıştırabilirsiniz **tüm kullanıcıların hata ayıklamasına izin** seçeneği uzak hata ayıklama İzleyicisi'nde seçili **seçenekleri** iletişim kutusu.  
  
> [!CAUTION]
>  Diğer kullanıcıların bağlanma izni verme yanlışlıkla yanlış uzaktan hata ayıklama oturumu için bağlanma olanağı sağlar. Hata ayıklama **kimlik doğrulaması yok** modu hiçbir zaman güvendedir ve dikkatli kullanılmalıdır.  
  
 Daha fazla bilgi için [uzaktan hata ayıklama İzleyicisi'ni başlatmak](http://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)



