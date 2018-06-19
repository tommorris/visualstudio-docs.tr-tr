---
title: IDebugCustomAttribute::GetAttributeBytes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttribute::GetAttributeBytes
helpviewer_keywords:
- IDebugCustomAttribute::GetAttributeBytes
ms.assetid: cf34583b-6530-4dcc-89f8-eb27e4e8d594
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 949bc7b8722e11be0a69800f890b509399169688
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107013"
---
# <a name="idebugcustomattributegetattributebytes"></a>IDebugCustomAttribute::GetAttributeBytes
Bir BLOB bayt öznitelik bilgileri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAttributeBytes(   
   BYTE*  ppBlob,  
   DWORD* pdwLen  
);  
```  
  
```csharp  
int GetAttributeBytes(  
   ref byte[] ppBlob,   
   ref uint   pdwLen  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppBlob`  
 [içinde out] Oturum özniteliği bayt doldurulmuş bir dizi.  
  
 `pdwLen`  
 [içinde out] Döndürmek için bayt sayısını belirtir `ppBlob` dizi ve gerçekte diziye yazılan bayt sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayarlama `ppBlob` parametre sayısını döndürmek için bir null değere öznitelikleri kullanılabilir bayt sayısı. Ardından bir dizi ayırın ve bu dizide için geçirin `ppBlob` parametresi.  
  
 Öznitelik bayt özel özniteliğinin ham verileri temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)