---
title: -Log (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8fa0fa90e904d4fb7f3e6820ce997a6a93e738f9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)