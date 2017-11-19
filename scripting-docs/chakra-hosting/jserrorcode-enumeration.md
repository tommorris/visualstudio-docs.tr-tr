---
title: "JsErrorCode numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsErrorCode
helpviewer_keywords: JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b09babd38505c5619f414d2e349cd52b3596ceac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jserrorcode-enumeration"></a>JsErrorCode Numaralandırması
Chakra barındırma API'sinden bir hata kodu döndürüldü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum JsErrorCode : unsigned int;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|Bağlam zaten bir hata ayıklama durumunda olduğundan bir hata ayıklama durumuna sokulamaz.|  
|`JsErrorAlreadyProfilingContext`|Bağlam zaten profil oluşturduğundan profil oluşturmaya başlayamaz.|  
|`JsErrorArgumentNotObject`|Nesne değerleri üzerinde çalışan bir barındırma API'si, nesne olmayan bir değer ile çağrılmış.|  
|`JsErrorBadSerializedScript`|Hatalı olarak seri hale getirilmiş bir betik kullanılmış veya seri hale getirilmiş betik Chakra alt yapısının farklı bir sürümü ile seri hale getirilmiş.|  
|`JsErrorCannotDisableExecution`|Çalışma zamanı güvenilir kod kesintisini desteklemez.|  
|`JsErrorCannotSerializeDebugScript`|Betikler hata ayıklama bağlamlarında seri hale getirilemez.|  
|`JsErrorCategoryEngine`|Altyapıda oluşan hatalarla ilgili hata kategorisi.|  
|`JsErrorCategoryFatal`|Ciddi olan ve altyapı hatasını belirten hatalarla ilgili hata kategorisi.|  
|`JsErrorCategoryScript`|Bir betikteki hatalarla ilgili hata kategorisi.|  
|`JsErrorCategoryUsage`|API'nin yanlış kullanımı ile ilgili hata kategorisi.|  
|`JsErrorFatal`|Altyapıda önemli bir hata oluştu.|  
|`JsErrorHeapEnumInProgress`|Bir yığın numaralandırma şu anda betik bağlamında çalışma halinde.|  
|`JsErrorIdleNotEnabled`|Konak boşta işlemi etkinleştirmediğinde boşta bildirimi verildi.|  
|`JsErrorInDisabledState`|Çalışma zamanı devre dışı durumda.|  
|`JsErrorInExceptionState`|Altyapı bir özel durumda ve özel durum temizlenene kadar hiçbir API çağrılamaz.|  
|`JsErrorInObjectBeforeCollectCallback`|Toplama geri çağırma önce nesnedeki işlemi desteklenmiyor.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
|`JsErrorInProfileCallback`|Bir betik içeriği, profil geri çağırmasının ortasında.|  
|`JsErrorInThreadServiceCallback`|Bir iş parçacığı hizmeti geri araması şu anda çalışma halinde.|  
|`JsErrorInvalidArgument`|Bir barındırma API'si için bir bağımsız değişken geçersiz.|  
|`JsErrorNoCurrentContext`|Barındırma API'si geçerli bir bağlamı gerektirir; ancak geçerli bağlam yok.|  
|`JsErrorNotImplemented`|Barındırma API'si henüz uygulanmadı.|  
|`JsErrorNullArgument`|Bir barındırma API için bir bağımsız değişken, null olmasına izin verilmeyen bir bağlamda null'du.|  
|`JsErrorObjectNotInspectable`|Nesne için sarmalanmamış olamaz `IInspectable` işaretçi.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
|`JsErrorOutOfMemory`|Chakra altyapısının belleği doldu.|  
|`JsErrorPropertyNotSymbol`|Sembol özellik kimlikleri üzerinde çalışır, ancak bir sembol olmayan özellik kimliği ile çağrıldı barındırma bir API. Tarafından döndürülen hata kodu `JsGetSymbolFromPropertyId` simgesi olmayan özellik kimliği ile işlevi çağrıldıysa.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
|`JsErrorPropertyNotString`|Dize özelliği kimlikleri üzerinde çalışır, ancak bir dize olmayan özellik kimliği ile çağrıldı barındırma bir API. Varolan tarafından döndürülen hata kodu `JsGetPropertyNamefromId` dize olmayan özellik kimliği ile işlevi çağrıldıysa.<br /><br /> Bu numaralandırma değeri yalnızca kenar modunda desteklenir.|  
|`JsErrorRuntimeInUse`|Hala kullanımda olan bir çalışma zamanı atılamaz.|  
|`JsErrorScriptCompile`|JavaScript derlenemedi.|  
|`JsErrorScriptEvalDisabled`|Bir betik, `eval` veya `function` kullanmayı denediğiniz için sonlandırıldı ve değerlendirme devre dışı bırakıldı.|  
|`JsErrorScriptException`|Bir betik çalıştırılırken bir JavaScript özel durumu oluştu.|  
|`JsErrorScriptTerminated`|Bir betik, çalışma zamanı askıya alınması isteğiyle sonlandırıldı.|  
|`JsErrorWrongRuntime`|Bir barındırma API farklı JavaScript çalışma zamanında oluşturulan nesne ile çağrıldı.|  
|`JsErrorWrongThread`|Bir barındırma API'si yanlış iş parçacığında çağrıldı.|  
|`JsNoError`|Başarı hata kodu.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)