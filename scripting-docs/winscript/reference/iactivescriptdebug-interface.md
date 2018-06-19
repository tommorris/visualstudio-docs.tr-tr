---
title: Iactivescriptdebug arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptDebug interface
ms.assetid: e3e28cba-ee08-4a52-973a-b74be488c348
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a1e1d0c1cf51c63f1bb3fcd90ae72520da907e50
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793340"
---
# <a name="iactivescriptdebug-interface"></a>IActiveScriptDebug Arabirimi
Bu destek hata ayıklama komut dosyası motorları tarafından uygulanır. Genellikle, uygulayan bir nesne `IActiveScriptDebug` arabirim de uygulayan `IActiveScript` arabirimi. Bu durumda, çağrı `IActiveScript::QueryInterface` elde etmek için yöntemi `IActiveScriptDebug` arabirimi.  
  
 `IActiveScriptDebug` Arabirimi için yer sağlar:  
  
-   Belge yönetimini almak için akıllı ana bilgisayar'ı seçin.  
  
-   Birden çok komut dosyası motorları, hata ayıklama eşitlemek için hata ayıklama manager işlemi.  
  
 Kaynağından devralındı yöntemleri yanı sıra `IUnknown`, `IActiveScriptDebug` arabirimi aşağıdaki yöntemleri sunar.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)|Rastgele bir komut dosyası metin bloğunda metin özniteliklerini döndürür.|  
|[IActiveScriptDebug::GetScriptletTextAttributes](../../winscript/reference/iactivescriptdebug-getscriptlettextattributes.md)|Rastgele bir kod parçacığı metin özniteliklerini döndürür.|  
|[IActiveScriptDebug::EnumCodeContextsOfPosition](../../winscript/reference/iactivescriptdebug-enumcodecontextsofposition.md)|İçin temsilciler `IDebugDocumentContext::EnumCodeContexts`.|