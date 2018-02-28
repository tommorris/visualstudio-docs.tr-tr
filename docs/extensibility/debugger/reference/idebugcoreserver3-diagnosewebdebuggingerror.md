---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4b93a82bfd79abe6400e8e1bb213b00154fbbf16
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
Bir auto-attach neden belirleme girişimi başarısız oldu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszUrl`  
 [in] Şu anda kullanılmıyor; her zaman null bir değere ayarlamanız gerekir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Diğer tipik dönüş kodları şunlardır:  
  
|Kod|Açıklama|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Hata ayıklamayı başlatmak uzak sunucu neden başarısız belirleyemiyor.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Büyük olasılıkla yetersiz izinler nedeniyle uzak sunucuda hata ayıklaması yapılamıyor veya DEBUG fiilini etkin olmadığından.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Web sunucusu kilitli ve hata ayıklamayı etkinleştirmek için gerekli olan DEBUG fiilini engelliyor.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)