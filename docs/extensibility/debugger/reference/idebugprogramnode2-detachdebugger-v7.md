---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3a79c073048fe30a4abed069487ad09943253475
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7

> [!Note]
> KULLANIM DIŞI. KULLANMAYIN.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT DetachDebugger_V7 (
   void 
);
```

```csharp
int DetachDebugger_V7 ();
```

## <a name="return-value"></a>Dönüş Değeri

Bir uygulama her zaman döndürmelidir `E_NOTIMPL`.

## <a name="remarks"></a>Açıklamalar

> [!WARNING]
> Visual Studio 2005 ' ten itibaren bu yöntem artık kullanılmıyor ve her zaman döndürmelidir `E_NOTIMPL`.

Hata ayıklayıcı beklenmedik bir şekilde sonlandırıldığında bu yöntem çağrılır. Bu yöntem çağrıldığında, kullanıcı ondan ayrılmış gibi sorgulamanıza DE programı devam. Daha fazla hata ayıklama olay gönderilmelidir. Program, başka bir hata ayıklayıcı örneğinden takılabilir olduğu bir durumda olması gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)