---
title: FRAMEINFO | Microsoft Docs
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
- FRAMEINFO
helpviewer_keywords:
- FRAMEINFO structure
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 00590f4ce9822eee9253196aba15019eb86de1b5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689186"
---
# <a name="frameinfo"></a>FRAMEINFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [FRAMEINFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/frameinfo).  
  
Bir yığın çerçevesini tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Bayraklarının bir birleşimi [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) hangi alanların doldurulur belirten sabit listesi.  
  
 m_bstrFuncName  
 Yığın çerçevesiyle ilgili işlevi adı.  
  
 m_bstrReturnType  
 Yığın çerçevesiyle ilgili dönüş türü.  
  
 m_bstrArgs  
 Yığın çerçevesiyle ilgili işlevi için bağımsız değişkenler.  
  
 m_bstrLanguage  
 Hangi işlevin uygulandığından dili.  
  
 m_bstrModule  
 Yığın çerçevesiyle ilgili modülü adı.  
  
 m_addrMin  
 En düşük fiziksel yığın adresi.  
  
 m_addrMAX  
 En yüksek fiziksel yığın adresi.  
  
 m_pFrame  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) Bu yığın çerçevesini temsil eden nesne.  
  
 m_pFrame  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) Bu yığın çerçevesi içeren modül temsil eden nesne.  
  
 m_fHasDebugInfo  
 Sıfır olmayan (`TRUE`) hata ayıklama bilgileri verilen çerçevede varsa.  
  
 m_fHasDebugInfo  
 Sıfır olmayan (`TRUE`) yığın çerçevesini artık geçerli değil ve kod ile ilişkili ise.  
  
 m_fHasDebugInfo  
 Sıfır olmayan (`TRUE`) yığın çerçevesini oturum hata ayıklama Yöneticisi (SDM) tarafından eklenmişse.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı geçirilir [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) doldurulması için yöntemi. Bu yapı ayrıca yer alan bir liste bulunan [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) hangi sırayla çağrısından döndürülen arabirimi [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)

