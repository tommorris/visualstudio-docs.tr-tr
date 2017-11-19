---
title: IDebugStackFrame3::InterceptCurrentException | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords: IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9631f2206705ef6daf36b355aa6cb1d5be6458d4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugstackframe3interceptcurrentexception"></a>IDebugStackFrame3::InterceptCurrentException
Geçerli özel durumun müdahale istediğinde hata ayıklayıcısını geçerli yığın çerçevesi tarafından çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT InterceptCurrentException(  
   INTERCEPT_EXCEPTION_ACTION dwFlags,  
   UINT64*                    pqwCookie  
);  
```  
  
```csharp  
int InterceptCurrentException(  
   uint dwFlags,   
   out  ulong pqwCookie  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 [in] Farklı eylemler belirtir. Şu anda yalnızca [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) değeri `IEA_INTERCEPT` desteklenir ve belirtilmesi gerekir.  
  
 `pqwCookie`  
 [out] Belirli bir özel durum tanımlayan benzersiz bir değerdir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde bir hata kodu döndürür.  
  
 En sık karşılaşılan hata döndürür verilmiştir.  
  
|Hata|Açıklama|  
|-----------|-----------------|  
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|Geçerli özel durumun müdahale edemez.|  
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|Geçerli yürütme çerçeve için bir işleyici henüz arandığını kurmadı.|  
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|Bu yöntem, bu çerçeve için desteklenmiyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir özel durum oluştuğunda, hata ayıklayıcı işlem işleme sırasında özel durum önemli noktaları çalışma zamanında denetiminden kazanır. Bu anahtar dakika sırasında hata ayıklayıcı geçerli yığın çerçevesini çerçeve özel müdahale isteyip istemediğini sorabilirsiniz. Bu yığın çerçevesi (örneğin, bir try/catch bloğu program kodundaki) bir özel durum işleyici olmasa bile bu şekilde, bir ilerlemesinden temelde üzerinde-çalışma sırasında özel durum işleyicisi yığın çerçevesi için istisnadır.  
  
 Hata ayıklayıcı özel durumu ele öğrenmek istediğinde geçerli yığın çerçevesini nesne üzerindeki bu yöntemi çağırır. Bu yöntem, tüm özel durum ayrıntıları işlemekten sorumludur. Varsa [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md) arabirimi uygulanmadı veya `InterceptStackException` yöntemi herhangi bir hata döndürür ve hata ayıklayıcısını özel normal şekilde işlemeye devam eder.  
  
> [!NOTE]
>  Özel durumlar ayıklanacak programın çalışma zamanı .NET altında çalışırken, yalnızca yönetilen kodda, diğer bir deyişle, geçirilebilir. Elbette, üçüncü taraf dil Implementers uygulayabilirsiniz `InterceptStackException` şekilde seçerseniz, kendi hata ayıklama altyapılarındaki.  
  
 Ele geçirilmesini tamamlandıktan sonra bir [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) verdi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)