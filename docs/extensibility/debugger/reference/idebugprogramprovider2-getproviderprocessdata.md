---
title: IDebugProgramProvider2::GetProviderProcessData | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramProvider2::GetProviderProcessData
helpviewer_keywords:
- IDebugProgramProvider2::GetProviderProcessData
ms.assetid: 90cf7b7f-53d2-487e-b793-94501a6e24dd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 77a6da58083feb8699c6db24207c265bf50c0f0e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramprovider2getproviderprocessdata"></a>IDebugProgramProvider2::GetProviderProcessData
Belirtilen bir işlemden çalışan programların listesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetProviderProcessData(  
   PROVIDER_FLAGS         Flags,  
   IDebugDefaultPort2*    pPort,  
   AD_PROCESS_ID          processId,  
   CONST_GUID_ARRAY       EngineFilter,  
   PROVIDER_PROCESS_DATA* pProcess  
);  
```  
  
```csharp  
int GetProviderProcessData(  
   enum_PROVIDER_FLAGS     Flags,  
   IDebugDefaultPort2      pPort,  
   AD_PROCESS_ID           ProcessId,  
   CONST_GUID_ARRAY        EngineFilter,  
   PROVIDER_PROCESS_DATA[] pProcess  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Flags`  
 [in] Bayraklarını bileşimini [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) numaralandırması. Aşağıdaki bayraklar bu çağrı için tipik şunlardır:  
  
|Bayrağı|Açıklama|  
|----------|-----------------|  
|`PFLAG_REMOTE_PORT`|Çağıran uzak makinede çalışıyor.|  
|`PFLAG_DEBUGGEE`|Arayan şu anda hata ayıklaması (dizimi hakkında ek bilgi her düğüm için döndürülecek).|  
|`PFLAG_ATTACHED_TO_DEBUGGEE`|Arayan bağlı, ancak hata ayıklayıcı tarafından başlatılan değil.|  
|`PFLAG_GET_PROGRAM_NODES`|Çağıran program düğümler listesi için döndürülmesini istiyor.|  
  
 `pPort`  
 [in] Arama işlemi bağlantı noktası çalışıyor.  
  
 `processId`  
 [in] Bir [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) programı içeren işlem Kimliğini söz konusu bulunduran yapısı.  
  
 `EngineFilter`  
 [in] GUID'ler dizisi (bunlar hiçbir motorları belirtilmezse, tüm programlar döndürülür sağlanan motorları desteği ne üzerinde; tabanlı gerçekten getirilen programlar filtrelemek için kullanılacak) Bu işlemde hata ayıklamak için atanan hata ayıklama altyapıları için.  
  
 `pProcess`  
 [out] A [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md) istenen bilgileri girilir yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, normalde bu işlemde çalışan programların listesini almak için bir işlem tarafından çağrılır. Döndürülen bilgilerin listesidir [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) nesneleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)   
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)   
 [CONST_GUID_ARRAY](../../../extensibility/debugger/reference/const-guid-array.md)   
 [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)   
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)