---
title: IDebugEngine2::DestroyProgram | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::DestroyProgram
helpviewer_keywords:
- IDebugEngine2::DestroyProgram
ms.assetid: 0c9e2698-c70f-4770-a7bb-39650e9c3a1f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8e85eb457a16de03fa989d86109a8705c3b36174
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31105872"
---
# <a name="idebugengine2destroyprogram"></a>IDebugEngine2::DestroyProgram
Belirtilen program beklenmedik şekilde sona erdi ve DE program için tüm başvuruları temizlemek bir hata ayıklama altyapısı (DE) olduğunu bildirir ve olay gönderme bir program yok.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DestroyProgram(   
   IDebugProgram2* pProgram  
);  
```  
  
```cpp  
int DestroyProgram(   
   IDebugProgram2 pProgram  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pProgram`  
 [in] Bir [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) beklenmedik şekilde sonlandırıldı programı temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırıldıktan sonra DE sonradan gönderir bir [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) olay oturumu hata ayıklama Yöneticisi'ni (SDM) dön.  
  
 Bu yöntem uygulanmadı (döndürür `E_NOTIMPL`) DE ayıklanacak program aynı işlemde çalıştırıyorsa. Bu yöntem yalnızca DE SDM aynı süreci çalışıyorsa uygulanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)