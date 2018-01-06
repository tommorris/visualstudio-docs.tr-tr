---
title: -LCID (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /LCID switch
- locale IDs
- /l Devenv switch
- LCID devenv switch
- /lcid Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bdc04655ccfc8ca5f6c1e45e4378f15221b99f4c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)
Metin, para birimi ve tümleşik geliştirme ortamı (IDE) içinde diğer değerler için kullanılan varsayılan dili ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv {/LCID|/l} LocaleID  
```  
  
## <a name="arguments"></a>Arguments  
 `LocaleID`  
 Gerekli. Dilin LCID (yerel ayar kimliği) belirtin.  
  
## <a name="remarks"></a>Açıklamalar  
 IDE yükler ve ortamı için varsayılan doğal dili ayarlar. Bu değişiklik oturumlar arasında kalıcı ve yansıtılan **uluslararası ayarları** bölmesinde **ortam** içinde seçenekleri **seçenekleri** IDE iletişim kutusunda.  
  
 Belirtilen dil kullanıcının sisteminde kullanılabilir durumda değilse, / lcid anahtar göz ardı edilir.  
  
 Tarafından desteklenen dilleri LCID'ler aşağıdaki tabloda listelenmektedir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
|Dil|LCID|  
|--------------|----------|  
|ve|2052|  
|seçenekleri yerine|1028|  
|İngilizce|1033|  
|Fransızca|1036|  
|Almanca|1031|  
|İtalyanca|1040|  
|Japonca|1041|  
|Kore Dili|1042|  
|İspanyolca|3082|  
  
## <a name="example"></a>Örnek  
 Bu örnek IDE İngilizce kaynaklarını dizeleri ile yükler.  
  
```  
devenv /LCID 1033  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [Uluslararası ayarlar, ortam, Seçenekler iletişim kutusu](../../ide/reference/international-settings-environment-options-dialog-box.md)   
 [Pencere düzenlerini özelleştirme](../../ide/customizing-window-layouts-in-visual-studio.md)