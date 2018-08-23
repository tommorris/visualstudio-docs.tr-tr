---
title: IDebugDisassemblyStream2::GetCurrentLocation | Microsoft Docs
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
- IDebugDisassemblyStream2::GetCurrentLocation
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCurrentLocation
ms.assetid: 512302f1-12b1-4107-8a6e-c5bc878ce1c3
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 326d578b816b2e316bcb91a0fa16cf787f0a0316
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687141"
---
# <a name="idebugdisassemblystream2getcurrentlocation"></a>IDebugDisassemblyStream2::GetCurrentLocation
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugDisassemblyStream2::GetCurrentLocation](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation).  
  
Geçerli kod konumu temsil eden bir kod konum tanımlayıcısı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetCurrentLocation(   
   UINT64* puCodeLocationId  
);  
```  
  
```csharp  
int GetCurrentLocation(   
   out ulong puCodeLocationId  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `puCodeLocationId`  
 [out] Kod konumu tanımlayıcısını döndürür. İçin Açıklamalar bölümüne bakın [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) kod konum tanımlayıcısı bir açıklaması için yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kod konum tanımlayıcısı için bir kod bağlamı çağırarak dönüştürülebilir [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)

