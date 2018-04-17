---
title: FRAMEINFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- FRAMEINFO
helpviewer_keywords:
- FRAMEINFO structure
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4080a0d868f154136b11058abdf29948a353b0ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="frameinfo"></a>FRAMEINFO
Yığın çerçevesi açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct tagFRAMEINFO {   
   FRAMEINFO_FLAGS    m_dwValidFields;  
   BSTR               m_bstrFuncName;  
   BSTR               m_bstrReturnType;  
   BSTR               m_bstrArgs;  
   BSTR               m_bstrLanguage;  
   BSTR               m_bstrModule;  
   UINT64             m_addrMin;  
   UINT64             m_addrMax;  
   IDebugStackFrame2* m_pFrame;  
   IDebugModule2*     m_pModule;  
   BOOL               m_fHasDebugInfo;  
   BOOL               m_fStaleCode;  
   BOOL               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
```csharp  
public struct FRAMEINFO {   
   public uint              m_dwValidFields;  
   public string            m_bstrFuncName;  
   public string            m_bstrReturnType;  
   public string            m_bstrArgs;  
   public string            m_bstrLanguage;  
   public string            m_bstrModule;  
   public ulong             m_addrMin;  
   public ulong             m_addrMax;  
   public IDebugStackFrame2 m_pFrame;  
   public IDebugModule2     m_pModule;  
   public int               m_fHasDebugInfo;  
   public int               m_fStaleCode;  
   public int               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
## <a name="members"></a>Üyeler  
 m_dwValidFields  
 Bayraklarını bileşimini [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) hangi alanların doldurulur belirtir numaralandırması.  
  
 m_bstrFuncName  
 Yığın çerçevesi ile ilişkili işlevi adı.  
  
 m_bstrReturnType  
 Yığın çerçevesi ile ilişkili dönüş türü.  
  
 m_bstrArgs  
 Yığın çerçevesi ile ilişkili işlevi bağımsız değişken.  
  
 m_bstrLanguage  
 İşlev uygulanan dili.  
  
 m_bstrModule  
 Yığın çerçevesi ile ilişkili modülü adı.  
  
 m_addrMin  
 En az fiziksel yığın adresi.  
  
 m_addrMAX  
 En fazla fiziksel yığın adresi.  
  
 m_pFrame  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) Bu yığın çerçevesi temsil eden nesne.  
  
 m_pFrame  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) Bu yığın çerçevesi içeren modülü temsil eden nesne.  
  
 m_fHasDebugInfo  
 Sıfır olmayan (`TRUE`) hata ayıklama bilgileri verilen çerçevede varsa.  
  
 m_fHasDebugInfo  
 Sıfır olmayan (`TRUE`) yığın çerçevesi artık geçerli olmayan kodu ile ilişkili ise.  
  
 m_fHasDebugInfo  
 Sıfır olmayan (`TRUE`) yığın çerçevesi (SDM) oturum hata ayıklama Yöneticisi tarafından ek açıklama eklenmişse.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) doldurulacak yöntemi. Bu yapı de içeren bir liste bulunan [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) hangi sırayla çağrısından döndürülen arabirimi [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)