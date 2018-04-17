---
title: -ResetSkipPkgs (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4ffc8ae23dd66cdf863b6bf193289df63b3fdb06
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)