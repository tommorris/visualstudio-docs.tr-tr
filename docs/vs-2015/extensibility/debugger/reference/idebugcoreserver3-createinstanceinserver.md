---
title: IDebugCoreServer3::CreateInstanceInServer | Microsoft Docs
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
- IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords:
- IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8536fe85e58d3c43784d52b85d50015225068141
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693471"
---
# <a name="idebugcoreserver3createinstanceinserver"></a>IDebugCoreServer3::CreateInstanceInServer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugCoreServer3::CreateInstanceInServer](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver).  
  
Sunucuda bir hata ayıklama altyapısı örneğini oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT CreateInstanceInServer(  
   LPCWSTR  szDll,  
   WORD     wLangId,  
   REFCLSID clsidObject,  
   REFIID   riid,  
   void**   ppvObject  
);  
```  
  
```csharp  
int CreateInstanceInServer(  
   string     szDll,   
   ushort     wLangID,   
   ref Guid   clsidObject,   
   ref Guid   riid,   
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szDll`  
 [in] Belirtilen CLSID uygulayan dll yolu `clsidObject` parametresi. Bu ise `NULL`, ardından COM's `CoCreateInstance` işlevi çağrılır.  
  
 `wLangId`  
 [in] Yerel hata ayıklama altyapısı. Bu 0 olabilir [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md) yöntemi çağırılmalıdır.  
  
 `clsidObject`  
 [in] Oluşturmak için CLSID hata ayıklama altyapısı.  
  
 `riid`  
 [in] Sınıf nesneyi almak için belirli arabirimi arabirim kimliği.  
  
 `ppvObject`  
 [out] `IUnknown` arabiriminden oluşturulan nesne. Cast veya istenen arabirim için bu nesnesi hazırlanamadı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)

