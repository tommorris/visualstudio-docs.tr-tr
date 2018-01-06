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
ms.workload: multiple
ms.openlocfilehash: fb84c4bab7ce9480deefbb88ac02289415f33d5d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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