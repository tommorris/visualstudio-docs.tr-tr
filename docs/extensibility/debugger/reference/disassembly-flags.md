---
title: DISASSEMBLY_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DISASSEMBLY_FLAGS
helpviewer_keywords:
- DISASSEMBLY_FLAGS enumeration
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c22724bbf8ba55e866a5139479bf2a56b5bf63fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
Ayrıştırılmış bayrakları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
typedef DWORD DISASSEMBLY_FLAGS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
```  
  
## <a name="members"></a>Üyeler  
 DF_DOCUMENTCHANGE  
 Bu yönerge önceki olandan farklı bir belge olduğunu gösterir.  
  
 DF_DISABLED  
 Bu yönerge çalıştırılmayacak gösterir.  
  
 DF_INSTRUCTION_ACTIVE  
 Bu yönerge yürütülecek sonraki yönergeleri biri olduğunu gösterir (olabilir birden fazla).  
  
 DF_DATA  
 Bu yönerge gerçekten verilerin (kod değil) olduğunu gösterir.  
  
 DF_HASSOURCE  
 Bu yönerge kaynak sahip olduğunu gösterir. Profil oluşturma veya atık toplama kodu gibi bazı yönergeler, karşılık gelen hiçbir kaynak vardır.  
  
 DF_DOCUMENT_CHECKSUM  
 Belirten `bstrDocumentUrl` alanı sonra belgesi URL'si sağlama toplamı veri içeriyor. Açıklamalar bölümüne bakın [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) sağlama toplamı verilerin depolanma şeklini yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Olarak kullanılan `dwFlags` üyesi [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) yapısı.  
  
 Bu bayrakların bit ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)