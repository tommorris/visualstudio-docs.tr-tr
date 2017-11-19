---
title: IDebugAddress::GetAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAddress::GetAddress
helpviewer_keywords: IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3ed14b69dbc116514b191aadf58d209b4d39e458
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
Bir nesne ve kendi kapsamı veya kapsayıcı içinde konumuna açıklayan bir yapı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAddress (  
   DEBUG_ADDRESS * pAddress  
);  
```  
  
```csharp  
int GetAddress(  
   DEBUG_ADDRESS[] pAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pAddress`  
 [içinde out] A [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) bu yöntem tarafından doldurulur yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) yapısı oturum uygun bilgileri doldurur bu yönteme geçirilir. Bu bilgilerin nasıl yorumlanacağını döndürülen bilgi ve sembol işleyici türüne bağlıdır. Bkz: [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) daha fazla ayrıntı için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)