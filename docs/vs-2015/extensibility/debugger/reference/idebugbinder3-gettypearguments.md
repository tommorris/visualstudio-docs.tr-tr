---
title: IDebugBinder3::GetTypeArguments | Microsoft Docs
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
- IDebugBinder3::GetTypeArguments
helpviewer_keywords:
- IDebugBinder3::GetTypeArguments method
ms.assetid: fa0c37a7-327f-463e-9a9d-bb3f534584cb
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b82c5befe302c88e9f687bd2e6be7195dc4757cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692780"
---
# <a name="idebugbinder3gettypearguments"></a>IDebugBinder3::GetTypeArguments
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugBinder3::GetTypeArguments](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder3-gettypearguments).

Bu yöntem, bu nesneyle ilişkili bağımsız değişken türlerinin bir listesini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetTypeArguments(
   UINT          skip,
   UINT          count,
   IDebugField** ppFields,
   UINT*         pFetched
);
```

```csharp
int GetTypeArguments(
   uint          skip,
   uint          count,
   IDebugField[] ppFields,
   out uint      pFetched
);
```

#### <a name="parameters"></a>Parametreler

 `skip`

 [in] Bağımsız değişken türleri almadan önce atlamak için alanların sayısı.

 `count`

 [in] Döndürülecek bağımsız değişken alan sayısı (Ayrıca boyutunu belirtir `ppFields` dizisi).

 `ppFields`

 [out içinde] Bu yöntemin geri doldurulur alanları dizisi.

 `pFetched`

 [out] Bağımsız değişken türü alan sayısı gerçekte (isteğe bağlı) döndürdü.

## <a name="return-value"></a>Dönüş Değeri
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.

## <a name="remarks"></a>Açıklamalar
 Bağımsız değişken türlerinin sayısı ile önceden alınabilir [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md).

## <a name="see-also"></a>Ayrıca Bkz.

- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)