---
title: -SafeMode (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c8748a6dadaee41a5e615742715a92240b74ab8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
Başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] güvenli modda, yalnızca varsayılan ortamı ve Hizmetleri Yükleniyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar tüm üçüncü taraf VSPackages ne zaman yüklenmesini engeller [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] başlar, bu nedenle kararlı yürütme sağlama.  
  
## <a name="description"></a>Açıklama  
 Aşağıdaki örnek başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] güvenli modda.  
  
## <a name="code"></a>Kod  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)