---
title: IDebugProcess3::Continue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::Continue
helpviewer_keywords:
- IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38bb11237d5016e3747c5a615e61144511c17fad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocess3continue"></a>IDebugProcess3::Continue
Bu işlem durdurulmuş bir durumdan çalışmaya devam eder. Herhangi bir önceki yürütme durumu (örneğin, bir adım) korunur, ve yeniden yürütme işlemi başlatır.  
  
> [!NOTE]
>  Bu yöntem yerine kullanılmalıdır [devam](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Continue(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pThread`  
 [in] Bir [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) ettirilecek iş parçacığı temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde, hata kodunu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bu işleme kaç işlemleri ayıklanacak veya hangi işlem durdurma olay oluşturulan bağımsız olarak çağrılır. Uygulama, önceki yürütme durumu (örneğin, bir adım) korumak ve hiçbir zaman önceki yürütülmesinin tamamlamadan önce durmuş gibi sorgulamanıza yürütme devam gerekir. Diğer bir deyişle, bir iş parçacığında bu işlemi adım üzerinde işlem yapılması ve başka bir işlem durdurulduğundan durduruldu ve ardından `Continue` çağrıldı, belirtilen iş parçacığı, özgün adım üzerinden işlemi tamamlanmalıdır.  
  
 **Uyarı** bir durdurma veya bir anında (zaman uyumlu) olayın göndermeyin [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) bu çağrıyı; işlenirken hata ayıklayıcı aksi kilitlenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)