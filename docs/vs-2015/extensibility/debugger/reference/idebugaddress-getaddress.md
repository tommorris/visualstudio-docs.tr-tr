---
title: IDebugAddress::GetAddress | Microsoft Docs
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
- IDebugAddress::GetAddress
helpviewer_keywords:
- IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e4a469ba1e6f85a1ac83ba06efa45ba2b6c4fcbc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695142"
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugAddress::GetAddress](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugaddress-getaddress).  
  
Bir nesne ve onun kapsamındaki veya kapsayıcı konumunu tanımlayan bir yapıyı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetAddress (  
   DEBUG_ADDRESS * pAddress  
);  
```  
  
```csharp  
int GetAddress(  
   DEBUG_ADDRESS[] pAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pAddress`  
 [out içinde] A [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) bu yöntem tarafından girilir yapısının.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) yapısı, ilgili bilgileri ile oturum kaplayacak şekilde bu yönteme geçirilir. Bu bilgileri nasıl yorumlanacağını döndürülen bilgileri ve sembol işleyici türüne bağlıdır. Bkz: [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) daha fazla ayrıntı için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)

