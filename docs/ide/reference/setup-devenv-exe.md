---
title: -Setup (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e63b69c9d97edf5049dfb6e55b8f9d5010984d4d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
Zorlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] menüleri ve araç çubukları komutu gruplarından tüm kullanılabilir VSPackages açıklayan kaynak meta veriler birleştirmek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /setup  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar hiçbir bağımsız değişkenleri alır. `devenv /setup` Komutu genellikle yükleme işleminin son adımı verilir. Kullanımı `/setup` anahtar başlamıyor [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Çalıştırmalısınız `devenv` kullanmak için yönetici olarak [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) ve [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) anahtarları.  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir sürümü yüklemesinde son adımı gösterir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackages içerir.  
  
```  
devenv /setup  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)