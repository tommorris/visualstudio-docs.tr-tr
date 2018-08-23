---
title: IDebugCustomAttribute::GetAttributeBytes | Microsoft Docs
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
- IDebugCustomAttribute::GetAttributeBytes
helpviewer_keywords:
- IDebugCustomAttribute::GetAttributeBytes
ms.assetid: cf34583b-6530-4dcc-89f8-eb27e4e8d594
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 574deb12fd774d989f2868dd1300c6a641849015
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690598"
---
# <a name="idebugcustomattributegetattributebytes"></a>IDebugCustomAttribute::GetAttributeBytes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugCustomAttribute::GetAttributeBytes](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcustomattribute-getattributebytes).  
  
Bir blobu bayt olarak öznitelik bilgileri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [out içinde] Öznitelik bayt ile doldurulmuş bir dizi.  
  
 `pdwLen`  
 [out içinde] Bayt olarak döndürülecek en fazla sayısını belirtir `ppBlob` dizisi ve diziye gerçekte yazılan bayt sayısını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Ayarlama `ppBlob` kullanılabilir bayt sayısını döndürmek için bir null değer parametresi öznitelikleri. Ardından bir dizi ayırmak ve geçirmek için bu dizide `ppBlob` parametresi.  
  
 Öznitelik bayt özel özniteliğinin ham verileri temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)

