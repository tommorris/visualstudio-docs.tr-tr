---
title: IDebugDocumentPosition2::GetRange | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentPosition2::GetRange
helpviewer_keywords:
- IDebugDocumentPosition2::GetRange
ms.assetid: 91a06ee7-253a-4215-be22-04bf57305aa8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d4a80bebba1000c73af2d7e2cfd05e67fa44b1b7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109207"
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