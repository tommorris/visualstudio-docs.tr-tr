---
title: IDebugFunctionObject2::CreateStringObjectWithLength | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CreateStringObjectWithLength
- IDebugFunctionObject2::CreateStringObjectWithLength
ms.assetid: 1f43ec66-1615-4a4c-8b9d-e933f549f96d
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 20fd1000170a662baa5770ae396da98d48e813c7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628987"
---
# <a name="idebugfunctionobject2createstringobjectwithlength"></a>IDebugFunctionObject2::CreateStringObjectWithLength
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugFunctionObject2::CreateStringObjectWithLength](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject2-createstringobjectwithlength).  
  
Belirtilen uzunlukta bir dize nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT CreateStringObjectWithLength (  
   LPCOLESTR      pcstrString,  
   UINT           uiLength,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateStringObjectWithLength (  
   string           pcstrString,  
   uint             uiLength,  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pcstrString`  
 [in] Dize nesnesi için dize değeri.  
  
 `uiLength`  
 [in] Dize bayt cinsinden uzunluğu.  
  
 `ppObject`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) yeni oluşturulan bir dize nesnesini temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)

