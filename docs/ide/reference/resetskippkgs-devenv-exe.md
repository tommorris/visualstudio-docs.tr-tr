---
title: -ResetSkipPkgs (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1d9e639379ca16e6544cac1368cd4012c981bd24
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="resetskippkgs-devenvexe"></a>/ResetSkipPkgs (devenv.exe)
Yükleme için VSPackages sorun VSPackages yüklenmesini önlemek amacıyla isteyen kullanıcılar tarafından eklenen atlamak için tüm seçenekleri temizler ve ardından başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /ResetSkipPkgs  
```  
  
## <a name="remarks"></a>Açıklamalar  
 SkipLoading etiketi varlığını bir VSPackage yüklenmesini devre dışı bırakır; Etiket temizleme VSPackage yüklenmesini yeniden etkinleştirir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tüm SkipLoading etiketleri temizler.  
  
```  
Devenv.exe /ResetSkipPkgs  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)