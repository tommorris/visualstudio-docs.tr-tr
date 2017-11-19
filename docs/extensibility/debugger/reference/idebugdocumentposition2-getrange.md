---
title: IDebugDocumentPosition2::GetRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentPosition2::GetRange
helpviewer_keywords: IDebugDocumentPosition2::GetRange
ms.assetid: 91a06ee7-253a-4215-be22-04bf57305aa8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c1ea17c8125aea6c962c0562095ea8fba680f8b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdocumentposition2getrange"></a>IDebugDocumentPosition2::GetRange
Aralık için bu belgenin konumunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pBegPosition`  
 [içinde out] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) oturum başlangıç konumu girilir yapısı. Bu bilgileri gerekmiyorsa bu bağımsız değişken null bir değere ayarlayın.  
  
 `pEndPosition`  
 [içinde out] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) oturum bitiş konumu girilir yapısı. Bu bilgileri gerekmiyorsa bu bağımsız değişken null bir değere ayarlayın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Belge konumda bir konum kesme noktası için belirtilen aralık, önceden gerçekte kod katkıda bulunan bir deyim için arama yapmak (DE) hata ayıklama altyapısı tarafından kullanılır. Örneğin, aşağıdaki kodu göz önünde bulundurun:  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 Satır 5 ayıklanacak programa kod katkıda bulunur. 5. satırda kesme ayarlar hata ayıklayıcı DE belirli bir miktar kod katkıda bulunan ilk satırı için ileriye doğru arama yapmak isterse, hata ayıklayıcı nereye bir kesme noktası düzgün yerleştirilmesi ek adayı satırları içeren bir aralığı belirtirsiniz. Bir kesme noktası kabul edebilecek bir satır bulunamadı kadar DE sonra İleri bu satırlar arama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)