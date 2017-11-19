---
title: IDebugDefaultPort2::GetPortNotify | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDefaultPort2::GetPortNotify
helpviewer_keywords: IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 938cd3a2ab87d2145f9dca2b9d60591027650114
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
Bu yöntem alır bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) Bu bağlantı noktası için arabirim.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```csharp  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppPortNotify`  
 [out] Bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Normalde, `QueryInterface` yöntemi uygulama nesnesi üzerinde çağrılır [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) almak için arabirimi bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) arabirimi. Ancak, istenen arabirimi farklı bir nesne üzerinde uygulanan koşullar vardır. Bu yöntem, bu koşullar gizler ve döndürür `IDebugPortNotify2` en uygun nesnesindeki arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)