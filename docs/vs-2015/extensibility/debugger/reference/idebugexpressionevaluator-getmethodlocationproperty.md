---
title: IDebugExpressionEvaluator::GetMethodLocationProperty | Microsoft Docs
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
- IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a11013ba2450685798796d0645486cf178950fc1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696048"
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugExpressionEvaluator::GetMethodLocationProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator-getmethodlocationproperty).  
  
Bu yöntem, bir bellek adresi bir yöntem konum ve uzaklık dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 [in] Sembol sağlayıcısı olarak ifade edilen bir [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) nesne.  
  
 `pAddress`  
 [in] Bir adresi olarak ifade edilen metodundaki bir [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) nesne.  
  
 `pBinder`  
 [in] Bağlayıcı olarak ifade edilen bir [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) nesne.  
  
 `ppProperty`  
 [out] Döndürür bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) bellek adresini temsil eden arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen adresi, örneğin bir kesme noktası ayarlamak için kullanılabilir.  
  
 Adına rağmen `upstrFullyQualifiedMethodPlusOffset`, bu parametre, kısmen nitelenmiş yöntem adı geçirilebilir. Bu durumda, seçilen yöntemi kapsayan sertifikadır `pAddress`. Bu parametre nasıl yorumlanacağını ifade değerlendiricisi ve desteklediği dil kadar uygulamasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)

