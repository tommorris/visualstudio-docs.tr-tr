---
title: "Dia2dump örneği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a3166065680c193875c451626846a090e50cbc1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="dia2dump-sample"></a>Dia2dump Örneği
Dia2dump örneği ile Visual Studio yüklenmiş ve Dia2dump.cpp kaynak dosyası içerir. Derlenmiş yürütülebilir komut satırından çalıştırır ve bir bütün program veritabanı (.pdb) dosyasının içeriğini görüntüler.  
  
### <a name="to-install-the-sample"></a>Örneği yüklemek için  
  
1.  Sisteminizi Visual Studio Kurulumu başlangıç sayfasında açıklanan tüm Kurulum gereksinimlerini karşıladığını doğrulayın.  
  
2.  Visual Studio yükleyin ve ekteki örnekleri için tüm Kurulum ve yükleme yönergelerini izleyin.  
  
#### <a name="to-build-the-sample"></a>Örneği oluşturmak için  
  
1.  Dia2dump.sln dosyasını Visual Studio'da açın. (Gerekirse, Visual Studio ilk Dia2dump proje yükseltmenize yardımcı olur.)  
  
2.  Proje özellik sayfalarındaki içinde **C/C++** &#124; **Genel** &#124; **Ek içeren dizinler** özelliği belirtin `..\DIA SDK\include` dizin. Başka bir garanti derleyici dia2.h dosyasını bulabilirsiniz.  
  
3.  Üzerinde **yapı** menüsünde tıklatın **çözümü yeniden derle**.  
  
4.  Visual Studio’yu kapatın.  
  
#### <a name="to-run-the-sample"></a>Örnek çalıştırmak için  
  
1.  Bir komut istemi açın ve aşağıdaki komutu yazın:  
  
    ```  
    dia2dump filename  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dia2dump.cpp kaynak dosyası](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [Bağlantı noktası, geçirme ve Visual Studio projelerini yükseltme](../../porting/port-migrate-and-upgrade-visual-studio-projects.md)