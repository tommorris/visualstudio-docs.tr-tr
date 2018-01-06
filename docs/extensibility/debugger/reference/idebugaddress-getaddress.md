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
ms.workload: vssdk
ms.openlocfilehash: 3fdaf96f0026a6ef89bf9eb234c97ee7bdff700a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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