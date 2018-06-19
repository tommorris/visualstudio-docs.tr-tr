---
title: DISASSEMBLY_STREAM_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_STREAM_FIELDS
helpviewer_keywords:
- DISASSEMBLY_STREAM_FIELDS enumeration
ms.assetid: cfc9b4de-c756-4844-bea7-d9f186a51d1b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1a8735992574699ba2b108fc493e9003ca52c9b2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103532"
---
# <a name="disassemblystreamfields"></a>DISASSEMBLY_STREAM_FIELDS
Ayrıştırılmış alan hakkında almak için hangi bilgilerin belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
typedef DWORD DISASSEMBLY_STREAM_FIELDS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
```  
  
## <a name="members"></a>Üyeler  
 DSF_ADDRESS  
 Başlatma/kullanım `bstrAddress` alan.  
  
 DSF_ADDRESSOFFSET  
 Başlatma/kullanım `bstrAddressOffset` alan.  
  
 DSF_CODEBYTES  
 Başlatma/kullanım `bstrCodeBytes` alan.  
  
 DSF_OPCODE  
 Başlatma/kullanım `bstrOpCode` alan.  
  
 DSF_OPERANDS  
 Başlatma/kullanım `bstrOperands` alan.  
  
 DSF_SYMBOL  
 Başlatma/kullanım `bstrSymbol` alan.  
  
 DSF_CODELOCATIONID  
 Başlatma/kullanım `uCodeLocationId` alan.  
  
 DSF_POSITION  
 Başlatma/kullanım `posBeg` ve `posEnd` alanları.  
  
 DSF_DOCUMENTURL  
 Başlatma/kullanım `bstrDocumentUrl` alan.  
  
 DSF_BYTEOFFSET  
 Başlatma/kullanım `dwByteOffset` alan.  
  
 DSF_FLAGS  
 Başlatma/kullanım `dwFlags` ([DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)) alan.  
  
 DSF_OPERANDS_SYMBOLS  
 Simge adlarında `bstrOperands` alan.  
  
 DSF_ALL  
 Tüm alanlar için ayrıştırılmış akış belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre olarak geçirilen [okuma](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) hangi alanlarının belirtmek için yöntemi [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) yapısı başlatılması üzeresiniz.  
  
 İçin kullanılan `dwFields` üyesi `DisassemblyData` yapısı döndürüldüğünde hangi alanların kullanılan ve geçerli olduğunu belirtmek için yapısı.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [Okuma](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)