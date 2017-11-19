---
title: -Log (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cf5ab0e1949716005d12d51d06b0d915344833aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
Tüm etkinliği, sorun giderme amacıyla günlük dosyasına kaydeder. Çağırdıktan sonra bu dosyayı görünür `devenv /log` en az bir kez. Varsayılan olarak, bu günlük dosyasıdır:  
  
 *% APPDATA %*\Microsoft\VisualStudio\\*sürüm*\ActivityLog.xml  
  
 Burada *sürüm* Visual Studio sürümü. Ancak, farklı bir yol ve dosya adını belirtebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /log Path\NameOfLogFile  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar, diğer tüm anahtarlardan sonra komut satırının en sonunda görünmelidir.  
  
 / Log anahtarı ile çağrılan Visual Studio tüm örnekleri için bir günlüğüne kaydedilir. Anahtar oluşturulmadan çağrılan Visual Studio Örnekleri oturum değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)