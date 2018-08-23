---
title: IDebugProviderProgramNode2::UnmarshalDebuggeeInterface | Microsoft Docs
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
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
helpviewer_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
ms.assetid: 2e4653c5-10f1-493c-9973-f31d266c5d48
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 917fe90fe8d751586989f89b9b94ec235bb86baa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693771"
---
# <a name="idebugproviderprogramnode2unmarshaldebuggeeinterface"></a>IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProviderProgramNode2::UnmarshalDebuggeeInterface](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface).  
  
Belirtilen bir arabirim işlem sınırları alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT UnmarshalDebuggeeInterface(  
   REFIID riid,  
   void** ppvObject  
);  
```  
  
```csharp  
int UnmarshalDebuggeeInterface(  
   ref Guid   riid,  
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 [in] Elde etmek için GUID arabirimi.  
  
 `ppvObject`  
 [out] İstenen arabirimini uygulayan bir nesne döndürür. [C++] Bu doğrudan istenen arabirim türüne çevirebilirsiniz. [C#] kullanımı <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> istendiği arayüz almak için yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, hata ayıklama altyapısı çalışırken kullanılır [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] işlem alanına ve hata ayıklanan programa kendi işlem alanında çalışıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)

