---
title: IDebugSymbolProvider::GetAddressesFromPosition | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition method
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 129ed233361991f5e58a258c73838bc9739112de
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31118537"
---
# <a name="idebugsymbolprovidergetaddressesfromposition"></a>IDebugSymbolProvider::GetAddressesFromPosition
Bu yöntem, bir belgenin konumunu bir dizi halinde hata ayıklama adresleri eşler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAddressesFromPosition(   
   IDebugDocumentPosition2* pDocPos,  
   BOOL                     fStatmentOnly,  
   IEnumDebugAddresses**    ppEnumBegAddresses,  
   IEnumDebugAddresses**    ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromPosition(   
   IDebugDocumentPosition2  pDocPos,  
   bool                     fStatmentOnly,  
   out IEnumDebugAddresses  ppEnumBegAddresses,  
   out IEnumDebugAddresses  ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pDocPos`  
 [in] Belgenin konumu.  
  
 `fStatmentOnly`  
 [in] TRUE ise, tek bir deyimde hata ayıklama adreslere sınırlar.  
  
 `ppEnumBegAddresses`  
 [out] Bu deyimi veya satır ile ilişkili başlangıç hata ayıklama adresleri için bir numaralandırıcı döndürür.  
  
 `ppEnumEndAddresses`  
 [out] Döndürür bir [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) bu deyimi veya satır ile ilişkili bitiş hata ayıklama adresleri için Numaralandırıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir belge konumu genellikle kaynak satırları aralığını belirtir. Bu satırlar ile ilişkili hata ayıklama adresleri bitiş ve başlangıç bu yöntem sağlar. Bazı diller birden fazla satır ya da birden fazla deyim içeren satırları span deyimleri sağlar. Bu yöntem, tek bir deyimde hata ayıklama adreslere sınırlamak için bir bayrak sağlar.  
  
 Şablonları durumunda olduğu gibi birden fazla hata ayıklama adresine sahip tek bir deyimde mümkündür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)