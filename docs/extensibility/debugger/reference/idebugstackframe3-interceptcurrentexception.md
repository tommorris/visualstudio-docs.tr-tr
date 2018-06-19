---
title: IDebugStackFrame3::InterceptCurrentException | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords:
- IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d46ae2f3ae0c63c798fc42b93d50e5aee398ccf5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120929"
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