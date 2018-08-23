---
title: IDiaSymbol::findSymbolsForAcceleratorPointerTag | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: fb66852c-c5f7-4140-b9fe-20cb4e51a9fe
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a09f4ca4d4aa65c54f04e086e9fcd4ac66355ff2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697099"
---
# <a name="idiasymbolfindsymbolsforacceleratorpointertag"></a>IDiaSymbol::findSymbolsForAcceleratorPointerTag
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDiaSymbol::findSymbolsForAcceleratorPointerTag](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-findsymbolsforacceleratorpointertag).  
  
Hızlandırıcı işaretçi etiket sayısı, bir C++ AMP saplama işlevde döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT findSymbolsForAccleratorPointerTag (   
   DWORD             tagValue,  
   IDiaEnumSymbols** ppResult);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `tagValue`  
 [in] İşaretçi etiket değeri için pointee sembol kayıtların bulunduğu.  
  
 `ppResult`  
 [out] Bir işaretçi bir `IDiaEnumSymbols` arabirim işaretçisini, bir sonuç ile başlatılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde döndürür `S_FALSE` veya bir hata kodu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)



