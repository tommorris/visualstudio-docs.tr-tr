---
title: IDebugProviderProgramNode2::UnmarshalDebuggeeInterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
helpviewer_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
ms.assetid: 2e4653c5-10f1-493c-9973-f31d266c5d48
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b9ebadbc35ee8752e9f3b985a99155444caff5f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31119756"
---
# <a name="idebugproviderprogramnode2unmarshaldebuggeeinterface"></a>IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
Belirtilen bir arabirim işlem sınırlarında alır.  
  
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
 [in] Almak için GUID arabirimi.  
  
 `ppvObject`  
 [out] İstenen arabirimini uygulayan nesne döndürür. [C++] Bu doğrudan istenen arabirim türü çevirebilirsiniz. [C#] kullanım <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> istenen arabirimi alma yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı çalışırken bu yöntem kullanılır [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] işlem alanı ve ayıklanacak program kendi işlem alanında çalışıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)