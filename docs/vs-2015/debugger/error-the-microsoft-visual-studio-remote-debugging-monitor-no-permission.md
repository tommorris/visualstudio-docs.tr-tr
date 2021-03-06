---
title: 'Hata: Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayarda bu bilgisayara bağlanma izni yok | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.access_denied_oncallback
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
- remote debugging, Windows version error
ms.assetid: ba08a59b-6dbc-4bbc-9c52-379d3bf5241f
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a62f20afc5ba57da64205491a3c5dfeabd75daf
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43231272"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>Hata: Uzak bilgisayardaki Microsoft Visual Studio Uzaktan Hata Ayıklama İzleyicisinin bu bilgisayara bağlanma izni yok.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: Microsoft Visual Studio uzaktan hata ayıklama İzleyicisi uzak bilgisayarda bu bilgisayara bağlanma izni yok](https://docs.microsoft.com/visualstudio/debugger/error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer).  
  
Visual Studio uzaktan hata ayıklama İzleyicisi (msvsmon) çalıştırmayı denediği kullanıcının yerel bilgisayarda bir hesabı yoksa, bu hata oluşur.  
  
### <a name="to-fix-this-problem"></a>Bu sorunu gidermek için  
  
-   Visual Studio hata ayıklayıcısı ana bilgisayar aynı adı ve parola msvsmon uzak bilgisayarda çalışan kullanıcı hesabı için bir kullanıcı hesabı eklemek,  
  
     \- veya -  
  
-   Msvsmon yerel bilgisayara çağırma izni olan bir kullanıcı olarak çalıştırın. Başka bir deyişle, kullanıcının bir etki alanı kullanıcısı ve msvsmon bilgisayarda yönetici olması gerekir. Msvsmon iki yoldan biriyle çalıştırmak için kullanıcı hesabı belirtebilirsiniz:  
  
    -   Msvsmon simgesini sağ tıklatın ve seçin **Çalıştır** kısayol menüsünden  
  
     \- veya -  
  
    -   Komut isteminde çalıştırın `runas.exe`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan etki alanları arasında hata ayıklama](http://msdn.microsoft.com/library/8e697ce1-55e8-4ab0-a05f-f87225e2f29b)   
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan Hata Ayıklama](../debugger/remote-debugging.md)



