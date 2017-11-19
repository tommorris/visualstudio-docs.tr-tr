---
title: IDebugProcess2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::Attach
helpviewer_keywords: IDebugProcess2::Attach
ms.assetid: 40d78417-fde2-45c3-96c9-16e06bd9008d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 840f2dee6648a84b0f7c6259049dcc701b5aef82
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocess2attach"></a>IDebugProcess2::Attach
Oturum hata ayıklama Yöneticisi'ni (SDM) işleme ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   GUID*                 rgguidSpecificEngines,  
   DWORD                 celtSpecificEngines,  
   HRESULT*              rghrEngineAttach  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback,  
   Guid[]               rgguidSpecificEngines,  
   uint                 celtSpecificEngines,  
   int[]                rghrEngineAttach  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pCallback`  
 [in] Bir [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) hata ayıklama olay bildirimi için kullanılan nesne.  
  
 `rgguidSpecificEngines`  
 [in] Hata ayıklama motorları işlemde çalışan programlar hata ayıklama için kullanılacak GUID'lerini dizisi. Bu parametre bir null değeri olabilir. Açıklamalar için bkz.  
  
 `celtSpecificEngines`  
 [in] Hata ayıklama sayısı altyapıları `rgguidSpecificEngines` dizi ve boyutunu `rghrEngineAttach` dizi.  
  
 `rghrEngineAttach`  
 [içinde out] Hata ayıklama motoru tarafından döndürülen HRESULT kodlarını dizisi. Bu dizinin boyutu belirtilen `celtSpecificEngines` parametresi. Her kodu genellikle ya da. `S_OK` veya `S_ATTACH_DEFERRED`. İkincisi DE hiçbir program şu anda bağlı olduğu gösterir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Diğer olası değerler aşağıdaki tabloda gösterilmektedir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Belirtilen işlem için hata ayıklayıcı zaten eklenmiş.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Ekleme işlemi sırasında bir güvenlik ihlali oluştu.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Bir masaüstü işlemi için hata ayıklayıcı eklenemiyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir işlemine iliştirme iliştirir SDM belirtilen hata ayıklama motorları (DE) tarafından hata ayıklaması yapılabilir bu işlemde çalışan tüm programları `rgguidSpecificEngines` dizi. Ayarlama `rgguidSpecificEngines` parametre bir null değer veya dahil `GUID_NULL` işlemdeki tüm programlar iliştirmek için dizisindeki.  
  
 İşlem sırasında oluşan tüm hata ayıklama olaylar gönderilen verilen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) nesnesi. Bu `IDebugEventCallback2` nesnesi SDM bu yöntem çağırdığında sağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)