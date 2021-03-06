---
title: IDebugProgram2::GetProcess | Microsoft Docs
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
- IDebugProgram2::GetProcess
helpviewer_keywords:
- IDebugProgram2::GetProcess
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d5e40776af6011d612d4af79eca70928b6c39edb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692989"
---
# <a name="idebugprogram2getprocess"></a>IDebugProgram2::GetProcess
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgram2::GetProcess](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-getprocess).  
  
Bu programı çalıştırmayı işlem alın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetProcess(  
   IDebugProcess2** ppProcess  
);  
```  
  
```csharp  
int GetProcess(  
   out IDebugProcess2 ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppProcess`  
 [out] Döndürür [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) işlemi temsil eden arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı (DE) uygulayan sürece [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md) arabirimi, bu yöntemin DE'ın kullanımı döndürmelidir her zaman `E_NOTIMPL` bir DE buna ve bu nedenle çalıştırdığı işlemi yapamazsınız belirleyemediğinden Bu yöntemin bir uygulaması, karşılar.  
  
 Uygulama `IDebugEngineLaunch2` arabirimi anlamına gelir; işlem oluşturma DE bilmeniz gerekir bu nedenle DE'ın uygulaması [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimi içinde çalıştığı hangi işlemin bilmeniz mümkün.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)

