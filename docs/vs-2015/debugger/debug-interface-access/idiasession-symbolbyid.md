---
title: Idiasession::symbolbyıd | Microsoft Docs
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
helpviewer_keywords:
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4bf9dba9daea14ce98e5b5e4d0555b93fa56052
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633260"
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idiasession::symbolbyıd](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-symbolbyid).  
  
Bir sembol benzersiz kimliğine göre alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Benzersiz tanımlayıcısı.  
  
 `ppSymbol`  
 [out] Döndürür bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) sembol temsil eden bir nesne alındı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen tanımlayıcı, dahili olarak tüm sembolleri benzersiz olacak şekilde DIA SDK'sı tarafından kullanılan benzersiz bir değerdir.  
  
 Bu yöntem, örneğin, başka bir simge türünü gösteren simgenin almak için kullanılabilir (örneğe bakın).  
  
## <a name="example"></a>Örnek  
 Bu örnek alır bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) temsil eden başka bir simge türü. Bu örnek nasıl kullanılacağını gösterir `symbolById` oturumdaki yöntemi. Basit bir yaklaşım çağırmaktır [Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md) tür simgesi doğrudan almak için yöntemi.  
  
```cpp#  
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



