---
title: IDebugSymbolProvider::GetAddressesFromContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 3d8776ee9e00aebbe3c33021c160c8f7f3677743
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
Bu yöntem bir belge bağlamı hata ayıklama adresleri bir diziye eşler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAddressesFromContext(   
   IDebugDocumentContext2* pDocContext,  
   BOOL                    fStatmentOnly,  
   IEnumDebugAddresses**   ppEnumBegAddresses,  
   IEnumDebugAddresses**   ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromContext(  
   IDebugDocumentContext2  pDocContext,  
   bool                    fStatmentOnly,  
   out IEnumDebugAddresses ppEnumBegAddresses,  
   out IEnumDebugAddresses ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pDocContext`  
 [in] Belge bağlamı.  
  
 `fStatmentOnly`  
 [in] TRUE ise, tek bir deyimde hata ayıklama adreslere sınırlar.  
  
 `ppEnumBegAddresses`  
 [out] Bu deyimi veya satır ile ilişkili başlangıç hata ayıklama adresleri için bir numaralandırıcı döndürür.  
  
 `ppEnumEndAddresses`  
 [out] Döndürür bir [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) bu deyimi veya satır ile ilişkili bitiş hata ayıklama adresleri için Numaralandırıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir belge bağlamı genellikle kaynak satırları aralığını belirtir. Bu satırlar ile ilişkili hata ayıklama adresleri bitiş ve başlangıç bu yöntem sağlar. Bazı diller birden fazla satır ya da birden fazla deyim içeren satırları span deyimleri sağlar. Bu yöntem, tek bir deyimde hata ayıklama adreslere sınırlamak için bir bayrak sağlar.  
  
 Şablonları durumunda olduğu gibi birden fazla hata ayıklama adresine sahip tek bir deyimde mümkündür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)