---
title: -Log (devenv.exe) | Microsoft Docs
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
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bfd6d9ac2493e4caca95538140fb9af78db8e074
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675220"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [-Log (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/log-devenv-exe).  
  
  
Tüm etkinliği, sorun giderme amacıyla günlük dosyasına kaydeder. Bu dosya çağırdıktan sonra görünür `devenv /log` en az bir kez. Varsayılan olarak, bu günlük dosyasıdır:  
  
 *% APPDATA %* \Microsoft\VisualStudio\\*sürüm*\ActivityLog.xml  
  
 Burada *sürüm* Visual Studio sürümüdür. Ancak, farklı bir yol ve dosya adı belirtebilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /log Path\NameOfLogFile  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar, diğer tüm anahtarlardan sonra komut satırının en sonunda görünmelidir.  
  
 Günlük, / log anahtarı ile çağrılan Visual Studio'nun tüm örnekleri için yazılır. Anahtar olmadan çağrılan Visual Studio örneklerini oturumu değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)



