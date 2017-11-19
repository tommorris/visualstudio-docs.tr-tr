---
title: IDiaSession::findAcceleratorInlineesByName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e203e5c2-6563-43fa-be56-3063955043ab
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25aceb146aac7d23647172e53989d30bd9d72a08
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)