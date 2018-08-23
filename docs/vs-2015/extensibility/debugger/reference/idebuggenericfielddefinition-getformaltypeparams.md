---
title: IDebugGenericFieldDefinition::GetFormalTypeParams | Microsoft Docs
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
- GetFormalTypeParams
- IDebugGenericFieldDefinition::GetFormalTypeParams
ms.assetid: cadbd6a1-bc7c-4aff-8777-5396b7a23c3e
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c3eb40b1b24ca70e0ce1f44490c80231827b5fe1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632347"
---
# <a name="idebuggenericfielddefinitiongetformaltypeparams"></a>IDebugGenericFieldDefinition::GetFormalTypeParams
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugGenericFieldDefinition::GetFormalTypeParams](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebuggenericfielddefinition-getformaltypeparams).  
  
Parametre sayısı belirtilen tür parametreleri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetFormalTypeParams(  
   ULONG32                   cParams,  
   IDebugGenericParamField** ppParams,  
   ULONG32*                  pcParams  
);  
```  
  
```csharp  
int GetFormalTypeParams(  
   uint                          cParams,  
   out IDebugGenericParamField[] ppParams,  
   ref uint                      pcParams  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cParams`  
 [in] Parametre sayısı.  
  
 `ppParams`  
 [out] Tür parametreleri dizisi.  
  
 `pcParams`  
 [out içinde] Parametre sayısı `ppParams` dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Tür parametreleri sırayla soldan sağa döndür. Örneğin, sözlük\<K, V > IDebugFormalGenericParameters {K, V} döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)

