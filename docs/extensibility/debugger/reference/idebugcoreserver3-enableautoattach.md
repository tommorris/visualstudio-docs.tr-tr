---
title: IDebugCoreServer3::EnableAutoAttach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords: IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 23c7faed077b8af442d81593808f9360995ba246
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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