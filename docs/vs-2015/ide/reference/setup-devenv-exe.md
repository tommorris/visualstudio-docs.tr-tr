---
title: -Setup (devenv.exe) | Microsoft Docs
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
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75b7fb7d812135014a8b868ef7590c99e83c15b5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686385"
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [-Kurulum (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/setup-devenv-exe).  
  
  
Zorlar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] menüleri, araç çubukları ve komut gruplarından tüm kullanılabilir VSPackages tanımlayan kaynak meta verileri birleştirmek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /setup  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar hiçbir bağımsız değişkeni alır. `devenv /setup` Komut genellikle yükleme işleminin son adımı verilir. Kullanım `/setup` anahtar başlamıyor [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 Çalıştırmalısınız `devenv` kullanabilmek için yönetici olarak [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) ve [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) anahtarlar.  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir sürümünü yükleme işleminin son adımında gösterir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSPackage içeren.  
  
```  
devenv /setup  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)



