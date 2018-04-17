---
title: IDebugDisassemblyStream2::Seek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::Seek
helpviewer_keywords:
- IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 55a8c2c205627130e8dd6dd28f288b2d3dee9d2e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
Ayrıştırılmış akış yönergeler belirtilen konuma göre verilen sayıda okuma imleci taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```csharp  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwSeekStart`  
 [in] Arasında bir değer [SEEK_START](../../../extensibility/debugger/reference/seek-start.md) arama işlemine başlamak için göreli konumunu belirten numaralandırma.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) göreli arama işlemi olan kod bağlamına temsil eden nesne. Bu parametre yalnızca kullanılır `dwSeekStart`  =  `SEEK_START_CODECONTEXT`; Aksi takdirde, bu parametre yoksayılır ve boş bir değer olabilir.  
  
 `uCodeLocationId`  
 [in] Arama işlemi göreli olarak kod konumu tanımlayıcı. Bu parametre, kullanılan `dwSeekStart`  =  `SEEK_START_CODELOCID`; Aksi takdirde, bu parametre yoksayılır ve 0 olarak ayarlayın. Açıklamalar bölümüne bakın [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) yöntemi bir kod konumu tanımlayıcı açıklaması.  
  
 `iInstructions`  
 [in] Belirtilen konuma göre taşımak için yönergeler sayısı `dwSeekStart`. Bu değer, geriye doğru taşımak için negatif olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` arama konumundan kullanılabilir yönergeleri listesi dışında bir nokta ise. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Arama listesi başlamadan önce bir konuma olduysa, okuma konumu listedeki ilk yönergesi için ayarlanır. Bkz: listenin sonunda bir konuma olduysa, okuma konumu son yönerge listede ayarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)