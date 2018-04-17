---
title: Idiasession::symbolbyıd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b4cafc8bf83c9c5e3a61712b6a3791bc234102c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
Bir simge benzersiz tanımlayıcısıyla alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Benzersiz tanımlayıcı.  
  
 `ppSymbol`  
 [out] Döndürür bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) simgenin temsil eden nesnesi alınamadı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen tanımlayıcı tüm sembolleri benzersiz hale getirmek amacıyla DIA SDK'sı tarafından dahili olarak kullanılan benzersiz bir değerdir.  
  
 Bu yöntem, örneğin, başka bir simge türünü temsil eden simgeyi almak için kullanılabilir (örneğe bakın).  
  
## <a name="example"></a>Örnek  
 Bu örnek alır bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) temsil eden başka bir simge türü. Bu örnek nasıl kullanılacağını gösterir `symbolById` oturumunda yöntemi. Basit bir yaklaşım çağırmaktır [Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md) tür simgesi doğrudan alma yöntemi.  
  
```C++  
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)  
{  
    IDiaSymbol *pTypeSymbol = NULL;  
    if (pSymbol != NULL && pSession != NULL)  
    {  
        DWORD symbolTypeId;  
        pSymbol->get_typeId(&symbolTypeId);  
        pSession->symbolById(symbolTypeId, &pTypeSymbol);  
    }  
    return(pTypeSymbol);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)