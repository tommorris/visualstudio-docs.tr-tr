---
title: IDebugThread2::SetNextStatement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugThread2::SetNextStatement
helpviewer_keywords:
- IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e59d4087e44458ecd49efd5d7be9f45e68c6da2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
Geçerli yönerge işaretçisi verilen kodu bağlamına ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetNextStatement (   
   IDebugStackFrame2*  pStackFrame,  
   IDebugCodeContext2* pCodeContext  
);  
```  
  
```csharp  
int SetNextStatement (   
   IDebugStackFrame2  pStackFrame,  
   IDebugCodeContext2 pCodeContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStackFrame`  
 Gelecekte kullanılmak üzere ayrılmış; null bir değere ayarlayın.  
  
 `pCodeContext`  
 [in] Bir [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) çalıştırılmak üzere kod konumu açıklar nesne ve onun bağlamı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Diğer olası değerler aşağıdaki tabloda gösterilmektedir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|Sonraki deyim çerçeve yığında daha derin bir yığın çerçevesi olamaz.|  
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|Sonraki deyim yığındaki herhangi bir kareye ile ilişkili değil.|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|Bazı hata ayıklama altyapılarını özel durumdan sonra next deyimi ayarlanamıyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yönerge işaretçisi sonraki yönerge veya deyimi yürütmek için gösterir. Bu yöntem, bir kaynak kod satırı yeniden deneyin veya başka bir işlevde, örneğin devam etmek için yürütme zorlamak için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)