---
title: IDebugProgram2::Execute | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Execute
helpviewer_keywords:
- IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f7f4e26a5c892e1c796a2b6e2f9371898db21f68
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115417"
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
Bu program durdurulmuş bir durumdan çalışmaya devam eder. Herhangi bir önceki yürütme durumu (örneğin, bir adım) temizlenmiş, ve programı yeniden yürütme.  
  
> [!NOTE]
>  Bu yöntem kullanım dışıdır. Kullanım [yürütme](../../../extensibility/debugger/reference/idebugprocess3-execute.md) yöntemi yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Execute(  
   void  
);  
```  
  
```csharp  
int Execute();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı bazı diğer programın iş parçacığı durdurulmuş durumda gelen yürütme başlatıldığında, bu programı, bu yöntem çağrılır. Kullanıcı seçtiğinde bu yöntem olarak da adlandırılır **Başlat** komutunu **hata ayıklama** IDE menüde. Bu yöntemin kullanımı çağırmak kadar kolaydır [Sürdür](../../../extensibility/debugger/reference/idebugthread2-resume.md) programda geçerli iş parçacığının yöntemi.  
  
> [!WARNING]
>  Bir durdurma veya bir anında (zaman uyumlu) olayın göndermeyin [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) bu çağrıyı; işlenirken hata ayıklayıcı aksi kilitlenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Devam et](../../../extensibility/debugger/reference/idebugthread2-resume.md)