---
title: Dia2dump örneği | Microsoft Docs
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
- C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 410d4e8cf2a63c7d01058e501391f02543b1eee7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690983"
---
# <a name="dia2dump-sample"></a>Dia2dump Örneği
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Dia2dump örneği](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/dia2dump-sample).  
  
Dia2dump örneği, Visual Studio ile yüklenir ve Dia2dump.cpp kaynak dosyası içerir. Derlenmiş yürütülebilir dosya, komut satırından çalıştırır ve tüm program veritabanı (.pdb) dosyasının içeriği görüntüler.  
  
### <a name="to-install-the-sample"></a>Örneği yüklemek için  
  
1.  Sisteminizin Visual Studio Kurulumu başlangıç sayfasında açıklanan tüm Kurulum gereksinimlerini karşıladığını doğrulayın.  
  
2.  Visual Studio yükleyin ve dahil edilen örnekleri tüm Kurulum ve yükleme yönergelerini izleyin.  
  
#### <a name="to-build-the-sample"></a>Örneği oluşturmak için  
  
1.  Dia2dump.sln dosyasını Visual Studio'da açın. (Gerekirse, Visual Studio ilk Dia2dump proje yükseltmenize yardımcı olur.)  
  
2.  Projenin özellik sayfalarındaki içinde **C/C++** &#124; **genel** &#124; **ek içerik dizinleri** özelliği belirtin `..\DIA SDK\include` dizin. Bu, derleyicinin dia2.h dosya bulabilirsiniz garanti eder.  
  
3.  Üzerinde **derleme** menüsünde tıklatın **çözümü yeniden derle**.  
  
4.  Visual Studio’yu kapatın.  
  
#### <a name="to-run-the-sample"></a>Örnek çalıştırmak için  
  
1.  Bir komut istemi açın ve aşağıdaki komutu yazın:  
  
    ```  
    dia2dump filename  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dia2dump.cpp kaynak dosyası](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [Nasıl yapılır: başarısız Visual Studio Proje yükseltmelerinde sorun giderme](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)



