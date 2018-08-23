---
title: -(Devenv.exe) çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- /run Devenv
- run Devenv switch
- applications [Visual Studio], running
- /r Devenv switch
- Devenv, /run switch
- r Devenv switch (/r)
ms.assetid: b1f22f9d-39a5-4918-8a2a-4b5c1e872665
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 98ec2d8be12b8d0dbf9f3283b31c62d90d55e7b4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695980"
---
# <a name="run-devenvexe"></a>/Run (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [-çalıştırın (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/run-devenv-exe).  
  
  
Derler ve belirtilen proje veya çözüm çalıştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv {/run|/r} {SolutionName|ProjectName}  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Gerekli. Bir çözüm dosyası adını ve tam yolu.  
  
 `ProjectName`  
 Gerekli. Bir proje dosyasının adını ve tam yolu.  
  
## <a name="remarks"></a>Açıklamalar  
 Derler ve belirtilen proje veya çözümü etkin çözüm yapılandırması için belirtilen ayarlara göre çalıştırır. Bu anahtar tümleşik geliştirme ortamı (IDE) başlatır ve sonra proje etkin bırakan veya çözüm çalıştırma tamamlandı.  
  
-   Çift tırnak içine boşluk dizeleri alın.  
  
-   Hataları dahil olmak üzere Özet bilgileri görüntülenebilir **komut** penceresinde veya belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek çözüm çalıştırılır `MySolution` kullanarak etkin dağıtım yapılandırması.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Runexit (devenv.exe)](../../ide/reference/runexit-devenv-exe.md)   
 [/ Derleme (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ (Devenv.exe out)](../../ide/reference/out-devenv-exe.md)



