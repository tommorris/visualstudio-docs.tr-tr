---
title: IDebugMethodField::EnumParameters | Microsoft Docs
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
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 51e51a3c8dffebb90b36f60df6859d1cfdf4db6f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689640"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugMethodField::EnumParameters](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmethodfield-enumparameters).  
  
Yöntem parametreleri için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppParams`  
 [out] Döndürür bir [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) yöntem için parametrelerin listesini temsil eden nesne; hiç parametre varsa, aksi durumda null değeri döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür veya parametresiz varsa S_FALSE döndürür. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Her öğe bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) farklı parametre türleri temsil eden nesne. Çağrı [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) tam olarak hangi tür parametresi bir nesneyi temsil belirlemek için her bir nesne üzerindeki yöntemi.  
  
 Bir parametre hem değişken adını ve türünü içerir. İlk parametre olarak sınıf yöntemi genellikle "Bu" işaretçisidir.  
  
 Yalnızca bir parametre türleri gereklidir, çağrı [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)

