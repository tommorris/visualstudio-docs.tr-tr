---
title: IDebugModOpt::GetModOpts | Microsoft Docs
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
- IDebugModOpt::GetModOpts
- GetModOpts
ms.assetid: cb513fa9-d521-4a65-b968-f55f53a368df
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 344a2640cf550d9e2025c6ccb9aec28a0eb98895
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634114"
---
# <a name="idebugmodoptgetmodopts"></a>IDebugModOpt::GetModOpts
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugModOpt::GetModOpts](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmodopt-getmodopts).  
  
İsteğe bağlı değiştiricilere listesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetModOpts(  
   ULONG  celt,  
   BSTR*  rgelt,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetModOpts(  
   uint         celt,  
   out string[] rgelt,  
   ref uint     pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Döndürülecek öğe sayısı.  
  
 `rgelt`  
 [out] Seçenekleri içeren bir dizi döndürür.  
  
 `pceltFetched`  
 [out içinde] Döndürülen öğe sayısını `rgelt` dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)

