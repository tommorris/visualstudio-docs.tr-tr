---
title: IDebugCoreServer3::EnableAutoAttach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bf32eb5d8771f95ec155a93d1fe1e770e0cc2d52
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108501"
---
# <a name="idebugcoreserver3enableautoattach"></a>IDebugCoreServer3::EnableAutoAttach
Otomatik ekleme için belirtilen hata ayıklama altyapısı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnableAutoAttach(  
   GUID*     rgguidSpecificEngines,  
   DWORD     celtSpecificEngines,  
   LPCOLESTR pszStartPageUrl,  
   BSTR*     pbstrSessionId  
);  
```  
  
```csharp  
int EnableAutoAttach(  
   Guid[]     rgguidSpecificEngines,  
   uint       celtSpecificEngines,  
   string     pszStartPageUrl,  
   out string pbstrSessionId  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rgguidSpecificEngines`  
 [in] Otomatik ekleme olarak işaretlemek için her hata ayıklama altyapısı GUID'lerini dizisi.  
  
 `celtSpecificEngines`  
 [in] Belirtilen altyapısı sayısı `rgguidSpecificEngines`.  
  
 `pszStartPageUrl`  
 [in] Otomatik ekleme yapılırken kullanılacak başlangıç URL'si.  
  
 `pbstrSessionID`  
 [out] Otomatik bağlı oturum kimliği.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde hata kodunu döndürür. Bir hata kodu `E_AUTO_ATTACH_NOT_REGISTERED`, belirten auto-attach sınıf üreticisi kaydedilmedi.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen URL ile ilişkili bir program başlatıldığında, belirtilen hata ayıklama motorları otomatik olarak başlatıldığını bağlı ve.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)