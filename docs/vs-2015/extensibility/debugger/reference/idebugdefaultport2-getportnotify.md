---
title: IDebugDefaultPort2::GetPortNotify | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0a0cd508f0eab1d4ffc0feea32de128c411bef6c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694803"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugDefaultPort2::GetPortNotify](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdefaultport2-getportnotify).  
  
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
 [out] Bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Normalde, `QueryInterface` yöntemi, uygulama nesnesi üzerinde çağrıldığında [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) arabirimi almak için bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) arabirimi. Ancak, istendiği arayüz farklı bir nesne üzerinde uygulanmadı koşullar vardır. Bu yöntem bu koşullarda gizler ve döndürür `IDebugPortNotify2` en uygun nesnesinden arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)

