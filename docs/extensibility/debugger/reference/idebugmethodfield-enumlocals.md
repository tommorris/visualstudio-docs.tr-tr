---
title: IDebugMethodField::EnumLocals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumLocals
helpviewer_keywords:
- IDebugMethodField::EnumLocals method
ms.assetid: b0456a6d-2b96-49e2-a871-516571b4f6a5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8379407a275fa4b89b4107037b2a39691d062dd9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31118177"
---
# <a name="idebugmethodfieldenumlocals"></a>IDebugMethodField::EnumLocals
Seçili yerel değişkenler yöntemi için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pAddress`  
 [in] Bir [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) bağlamı veya kapsam Yereller alınacağı seçer hata ayıklama adresini temsil eden nesne.  
  
 `ppLocals`  
 [out] Döndüren bir [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) hiçbir yerel öğeler varsa, boş bir değer döndürür; Yereller listesini temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK döndürür veya hiçbir Yereller varsa S_FALSE döndürür. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca belirli hata ayıklama adresini içeren bloğu içinde tanımlanan değişkenler numaralandırılır. Derleyici tarafından üretilen tüm yerel öğeler de dahil olmak üzere tüm Yereller gerekirse, çağrı [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md) yöntemi.  
  
 Bir yöntemi, birden çok kapsam bağlamları veya blokları içerebilir. Örneğin, aşağıdaki contrived yöntemi üç kapsamları, iki iç blokları ve yöntem gövdesi içerir.  
  
```csharp  
public void func(int index)  
{  
    // Method body scope  
    int a = 0;  
    if (index == 1)  
    {  
        // Inner scope 1  
        int temp1 = a;  
    }  
    else  
    {  
        // Inner scope 2  
        int temp2 = a;  
    }  
}  
```  
  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) nesne temsil `func` yöntemin kendisi. Çağırma `EnumLocals` yöntemi ile bir [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) kümesine `Inner Scope 1` adresini döndürür bir numaralandırma içeren `temp1` örneğin değişken.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)