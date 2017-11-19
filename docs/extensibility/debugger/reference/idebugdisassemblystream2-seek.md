---
title: IDebugDisassemblyStream2::Seek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDisassemblyStream2::Seek
helpviewer_keywords: IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 61ef1e649a80fcda5ec3ce4be6c74b154c17f9a4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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