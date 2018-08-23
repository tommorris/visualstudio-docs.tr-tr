---
title: IDebugPointerObject::Dereference | Microsoft Docs
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
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dd1c0652a8c1b165ae37756238c5615c4572c886
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697466"
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugPointerObject::Dereference](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpointerobject-dereference).  
  
Belirtilen nesnenin alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwIndex`  
 [in] İşaret nesne başlangıcı basit bayt uzaklığı.  
  
 `ppObject`  
 [out] Döndürür bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) nesnesini temsil eden işaret yanı sıra uzaklığı, varsa nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür. Bu nesne başka bir nesneye işaret etmiyorsa E_FAIL döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 İşaret edilen nesnenin, basit bir tür veya bir sınıf veya yapı gibi daha karmaşık bir tür olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)

