---
title: IDebugExpressionEvaluator::GetMethodLocationProperty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords: IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fa5f72d33fff87d9f20f33621d53a92ac1221533
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
Bu yöntem, bir bellek adresine yöntemi konumu ve uzaklık dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetMethodLocationProperty(   
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```csharp  
int GetMethodLocationProperty(  
   string               upstrFullyQualifiedMethodPlusOffset,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `upstrFullyQualifiedMethodPlusOffset`  
 [in] Uzaklık ve yöntemi konumunu bir dize olarak ifade.  
  
 `pSymbolProvider`  
 [in] Sembol sağlayıcısı olarak ifade edilen bir [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) nesnesi.  
  
 `pAddress`  
 [in] Bir adresi olarak ifade edilen yöntem içinde bir [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) nesnesi.  
  
 `pBinder`  
 [in] Bağlayıcı olarak ifade edilen bir [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) nesnesi.  
  
 `ppProperty`  
 [out] Döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) bellek adresi temsil eden arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen adresi, örneğin bir kesme noktası ayarlamak için kullanılabilir.  
  
 Adı rağmen `upstrFullyQualifiedMethodPlusOffset`, bu parametre bir kısmen tam yöntem adı geçirilebilir. Bu durumda, seçili kapsayan bir yöntemdir `pAddress`. Bu parametre nasıl yorumlanacağını ifade değerlendiricisi ve desteklenen dil kadar uygulamasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)