---
title: IDebugField::GetExtendedInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugField::GetExtendedInfo
helpviewer_keywords:
- IDebugField::GetExtendedInfo method
ms.assetid: 46c0dd4d-4fd5-4efd-a908-71e4248e8e8d
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c6b2aaa953e47366e7a99fb5a821f530d37ed66e
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="idebugfieldgetextendedinfo"></a>IDebugField::GetExtendedInfo
Bu yöntem, bir alan hakkında bilgi genişletilmiş.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetExtendedInfo(   
   REFGUID guidExtendedInfo,  
   BYTE**  prgBuffer,  
   DWORD*  pdwLen  
);  
```  
  
```csharp  
int GetExtendedInfo(  
   ref Guid guidExtendedInfo,   
   IntPtr[] prgBuffer,   
   ref uint pdwLen  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guidExtendedInfo`  
 [in] Döndürülecek bilgi seçer. Geçerli değerler şunlardır:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`guidConstantValue`|Bayt dizisi olarak değer.|  
|`guidConstantType`|Tür imzası türünde.|  
  
 `prgBuffer`  
 [out] Genişletilmiş bilgiler döndürür.  
  
 `pdwLen`  
 [içinde out] Genişletilmiş bilgiler boyutunu bayt cinsinden döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Şu anda, bu yöntem yalnızca türünü veya bir sabit değerini döndürür. Arayan döndürülen arabelleği serbest gerekir `prgBuffer` göre COM'ın çağırma `CoTaskMemFree` işlevi (C++) veya <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> (C#).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)