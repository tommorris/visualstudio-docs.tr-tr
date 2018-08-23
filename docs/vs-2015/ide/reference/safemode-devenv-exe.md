---
title: -Güvenli modda (devenv.exe) | Microsoft Docs
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
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 308dd7e81a35604bcd0f6f5eba517b850ace17ad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690367"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [- SafeMode (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/safemode-devenv-exe).  
  
  
Başlar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] güvenli modda, yalnızca varsayılan ortama ve Hizmetleri Yükleniyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar, ne zaman yüklenmesini tüm üçüncü taraf VSPackages engeller [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] böylece kararlı yürütme sağlamaya başlar.  
  
## <a name="description"></a>Açıklama  
 Aşağıdaki örnek başlatır [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] güvenli modda.  
  
## <a name="code"></a>Kod  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)



