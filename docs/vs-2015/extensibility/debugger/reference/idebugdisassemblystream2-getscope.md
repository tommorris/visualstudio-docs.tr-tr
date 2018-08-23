---
title: IDebugDisassemblyStream2::GetScope | Microsoft Docs
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
- IDebugDisassemblyStream2::GetScope
helpviewer_keywords:
- IDebugDisassemblyStream2::GetScope
ms.assetid: 71c6e632-642a-42d8-a995-77e4ac190a5b
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e201bcc4e6de8b39ce8e72c7648045eeb7b9ec72
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627734"
---
# <a name="idebugdisassemblystream2getscope"></a>IDebugDisassemblyStream2::GetScope
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugDisassemblyStream2::GetScope](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdisassemblystream2-getscope).  
  
Ayrıştırılmış kod akışın kapsamını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetScope(   
   DISASSEMBLY_STREAM_SCOPE* pdwScope  
);  
```  
  
```csharp  
int GetScope(   
   out enum_ DISASSEMBLY_STREAM_SCOPE pdwScope  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pdwScope`  
 [out] Bir değer döndürür [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) bu ayrıştırılmış kodu akışın kapsamını tanımlayan sabit listesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir ayrıştırma kapsamını bir işlev veya tüm modül, örneğin olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)

