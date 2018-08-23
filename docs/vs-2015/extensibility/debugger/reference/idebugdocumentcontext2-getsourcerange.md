---
title: IDebugDocumentContext2::GetSourceRange | Microsoft Docs
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
- IDebugDocumentContext2::GetSourceRange
helpviewer_keywords:
- IDebugDocumentContext2::GetSourceRange
ms.assetid: 5903c75e-5390-4d13-9314-1ee276255313
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73600b81c71a1337470a1975902c40292ab4dcef
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697279"
---
# <a name="idebugdocumentcontext2getsourcerange"></a>IDebugDocumentContext2::GetSourceRange
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugDocumentContext2::GetSourceRange](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange).  
  
Bu belge bağlamına kaynak kod aralığını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT GetSourceRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetSourceRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pBegPosition`  
 [out içinde] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) başlangıç konumu ile doldurulmuş yapısı. Bu bilgiler gerekli değildir, bu bağımsız değişken null bir değere ayarlayın.  
  
 `pEndPosition`  
 [out içinde] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) oturum bitiş konumu girilir yapısının. Bu bilgiler gerekli değildir, bu bağımsız değişken null bir değere ayarlayın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kaynak aralıktaki tüm kaynak koddan kod katkıda önceki deyiminden sonra yalnızca geçerli deyim arka aralığıdır. Kaynak aralığı genellikle Ayrıştırılmış kod penceresinde kodu, Yorumlar dahil olmak üzere kaynak deyimlerini karıştırmak için kullanılır.  
  
 Yalnızca bu belge bağlamı içinde yer alan kod deyimlerini aralığı almak için arama [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)

