---
title: IDiaSession::findAcceleratorInlineesByName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e203e5c2-6563-43fa-be56-3063955043ab
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc2b6c7a221cf495ecbc9c981b1a62eef40d0a24
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindacceleratorinlineesbyname"></a>IDiaSession::findAcceleratorInlineesByName
Belirtilen satır içi işlev adına karşılık gelen satır içi çerçeveler simgelerini numaralandırması döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findAcceleratorInlineeLinesByName (   
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `name`  
 [in] Aranacak inlinee işlev adı.  
  
 `option`  
 [in] Satır içi arama çerçeveler yapılırken kullanılacak adı arama seçeneklerini karşılık `name`. Daha fazla bilgi için bkz: [NameSearchOptions numaralandırması](../../debugger/debug-interface-access/namesearchoptions.md).  
  
 `ppResult`  
 [out] Bir işaretçi bir `IDiaEnumSymbols` sonucu ile başlatılmış arabirim işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca Hızlandırıcı saplama işlevler içinde inlinees arar. Yerel C++ yordamı kayıtları yoksayar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)