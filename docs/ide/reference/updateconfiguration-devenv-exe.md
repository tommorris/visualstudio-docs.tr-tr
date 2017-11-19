---
title: -Updateconfiguration (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93efd5d0e0eb391a164f4997b7ddeedab09b4201
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="updateconfiguration-devenvexe"></a>/ Updateconfiguration (devenv.exe)
Bildirir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] birleştirmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sistem ve onay MEF paketleri önbelleğe herhangi bir değişiklik.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>Açıklamalar  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]VSIX paketi yüklediğinizde, bu komutu otomatik olarak çalıştırır. Çalışması gerektiğini `devenv.exe /updateconfiguration` dosyalarınızı düzeltme eki uygulama sonra böylece [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] MEF önbelleği güncelleştirir. Bu, düzeltme yeterli olup olmadığını değerlendirmek sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırı nedenleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] birleştirmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sistem ve onay MEF paketleri önbelleğe herhangi bir değişiklik.  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)