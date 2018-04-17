---
title: 'Hata: Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayardaki farklı bir kullanıcı olarak çalışıyor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aefcb3f358d6dc22b7ea8bcca1c43e79cd9c4414
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Hata: Uzak bilgisayardaki Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisi farklı kullanıcı olarak çalışıyor.
Uzaktan hata ayıklama yapmaya çalışırken, aşağıdaki hata iletisini alabilirsiniz:  
  
 Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayardaki farklı bir kullanıcı olarak çalışıyor.  
  
## <a name="cause"></a>Sebep  
 Bu ileti doğrulaması yok modda hata ayıklama ve msvsmon başlatan kullanıcının Visual Studio çalıştıran kullanıcının olmadığında oluşur.  
  
## <a name="solution"></a>Çözüm  
 Güvenli ve en iyi uzaktan bir hata ayıklama İzleyicisi (msvsmon.exe) çalıştırmak için Visual Studio ile aynı kullanıcı hesabı altında çözümüdür. Yapamıyorsanız, sahip olan bir hesabın altında uzaktan hata ayıklama İzleyicisi çalıştırabilirsiniz **hata ayıklamak herhangi bir kullanıcının** seçeneği uzaktan hata ayıklama İzleyicisi'nde seçili **seçenekleri** iletişim kutusu.  
  
> [!CAUTION]
>  Diğer kullanıcıların bağlanma izni verme yanlışlıkla yanlış uzaktan hata ayıklama oturumu için bağlanma olasılığı sağlar. Hata ayıklamayı **doğrulaması yok** modu hiçbir zaman güvenli değildir ve dikkatli kullanılmalıdır.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)