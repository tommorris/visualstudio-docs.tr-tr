---
title: IDebugDocumentContext2::Compare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentContext2::Compare
helpviewer_keywords: IDebugDocumentContext2::Compare
ms.assetid: 2327b1ba-52d0-42fb-a01e-63cb4b332d2f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4ed45c54b406d0e12a2909439755faf934f65941
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdocumentcontext2compare"></a>IDebugDocumentContext2::Compare
Bu belge bağlamları belirli bir dizi belge bağlamına karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Compare(   
   DOCCONTEXT_COMPARE       compare,  
   IDebugDocumentContext2** rgpDocContextSet,  
   DWORD                    dwDocContextSetLen,  
   DWORD*                   pdwDocContext  
);  
```  
  
```csharp  
int Compare(   
   enum_ DOCCONTEXT_COMPARE compare,  
   IDebugDocumentContext2[] rgpDocContextSet,  
   uint                     dwDocContextSetLen,  
   out uint                 pdwDocContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `compare`  
 [in] Arasında bir değer [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md) karşılaştırma türünü belirten numaralandırma.  
  
 `rgpDocContextSet`  
 [in] Bir dizi [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) için karşılaştırılan belge bağlamları temsil eden nesne.  
  
 `dwDocContextSetLen`  
 [in] Karşılaştırılacak belge bağlamları dizi uzunluğu.  
  
 `pdwDocContext`  
 [out] Dizine döndürür `rgpDocContextSet` karşılaştırmayı ilk belge bağlam dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` bir eşleşme bulunmazsa. Döndürür `S_FALSE` eşleşme bulunmazsa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) uygulayan aynı hata ayıklama altyapısı tarafından dizideki geçirilen nesneleri uygulanan `IDebugDocumentContext2` üzerinde; Aksi halde, çağrılan nesne karşılaştırma geçerli değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md)