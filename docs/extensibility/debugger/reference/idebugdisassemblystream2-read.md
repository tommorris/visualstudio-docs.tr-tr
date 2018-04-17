---
title: IDebugDisassemblyStream2::Read | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::Read
helpviewer_keywords:
- IDebugDisassemblyStream2::Read
ms.assetid: 7db5f6bb-73ee-45bc-b187-c1b6aa2dfdd5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d9143abac4ce10a2b7305889e1d1a5236c1e9b07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdisassemblystream2read"></a>IDebugDisassemblyStream2::Read
Ayrıştırılmış akışında geçerli konumundan başlayarak yönergeleri okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Read(   
   DWORD                     dwInstructions,  
   DISASSEMBLY_STREAM_FIELDS dwFields,  
   DWORD*                    pdwInstructionsRead,  
   DisassemblyData*          prgDisassembly  
);  
```  
  
```csharp  
int Read(   
   uint                           dwInstructions,  
   enum_DISASSEMBLY_STREAM_FIELDS dwFields,  
   out uint                       pdwInstructionsRead,  
   DisassemblyData[]              prgDisassembly  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwInstructions`  
 [in] Ayrıştırmak için yönergeler sayısı. Bu değer ayrıca uzunluk üst sınırı olan `prgDisassembly` dizi.  
  
 `dwFields`  
 [in] Bayraklarını bileşimini [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) hangi alanlarının belirten numaralandırma `prgDisassembly` doldurulması üzeresiniz.  
  
 `pdwInstructionsRead`  
 [out] Gerçekte çözülürken yönerge sayısını döndürür.  
  
 `prgDisassembly`  
 [out] Bir dizi [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) artık hata ayıklayabildiğinize yönerge her bir yapı kodunda bir artık hata ayıklayabildiğinize girilir yapıları. Bu dizi uzunluğu, tarafından dikte edilir `dwInstructions` parametresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli kapsamda kullanılabilir yönergeleri sayısı çağırarak elde edilebilir [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md) yöntemi.  
  
 Burada sonraki yönerge okunur gelen geçerli konumu çağırarak değiştirilebilir [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) yöntemi.  
  
 `DSF_OPERANDS_SYMBOLS` Bayrağı eklenebilir `DSF_OPERANDS` içinde bayrak `dwFields` sembol adları yönergeleri ayırma zaman kullanılması gerektiğini belirtmek için parametre.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)   
 [Arama](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)