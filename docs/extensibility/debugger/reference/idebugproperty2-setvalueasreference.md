---
title: IDebugProperty2::SetValueAsReference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2::SetValueAsReference
helpviewer_keywords: IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d27a087c67401e90e8a3f4629c27d1255d0ade75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
Bu özellik değerini verilen başvuru değerine ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rgpArgs`  
 [in] Yönetilen kod özellik ayarlayıcısı geçirilecek bağımsız değişkenleri bir dizi. Özellik ayarlayıcısı bağımsız değişken almaz veya bu [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) nesne böyle bir özellik ayarlayıcı için başvurmuyor `rgpArgs` boş bir değer olmalıdır. Bu parametre bir null değer genellikle olur.  
  
 `dwArgCount`  
 [in] İçinde bağımsız değişken sayısı `rgpArgs` dizi.  
  
 `pValue`  
 [in] Başvuru biçiminde bir [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) nesnesine bu özelliği ayarlamak için kullanılacak bir değer.  
  
 `dwTimeout`  
 [in] Ne kadar süre değerini milisaniye cinsinden ayarlamak için gerçekleştirin. Tipik bir değeridir `INFINITE`. Bu, tüm olası değerlendirme alabilir süreyi etkiler.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu, genellikle aşağıdakilerden biri:  
  
|Hata|Açıklama|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|Bir başvuru değeri ayarlanması desteklenmez.|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Bu özellik bir yönteme başvuran değeri ayarlanamaz.|  
|`E_SETVALUE_VALUE_IS_READONLY`|Değer salt okunur ve ayarlanamaz.|  
|`E_NOTIMPL`|Yöntem uygulanmadı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)