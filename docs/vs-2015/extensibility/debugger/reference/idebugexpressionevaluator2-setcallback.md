---
title: IDebugExpressionEvaluator2::SetCallback | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugExpressionEvaluator2::SetCallback
- SetCallback
ms.assetid: 31e3a99e-e784-44a3-8b19-cc5ef31ed546
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 44761820b510f87a8ac007dba4a45837c7915afd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688583"
---
# <a name="idebugexpressionevaluator2setcallback"></a>IDebugExpressionEvaluator2::SetCallback
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugExpressionEvaluator2::SetCallback](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator2-setcallback).  
  
Hata ayıklayıcısı altyapısı (DE), ölçüm ayarları okumak için kullanacağı bir geri arama arabirimini belirtmek ifade değerlendirici (EE) sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT SetCallback (  
   IDebugSettingsCallback2* pCallback  
);  
```  
  
```csharp  
int SetCallback (  
   IDebugSettingsCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pCallback`  
 [in] İçin ayarları geri çağırma kullanmak için arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir ifade değerlendiricisi ölçüm ayarları okumak için kullanabileceğiniz oturum hata ayıklama Yöneticisi için bir arabirim sağlar. Ölçümler üzerinde okumak için uzaktan hata ayıklama içinde yararlıdır [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] bilgisayar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler için bu yöntemi uygulamak nasıl gösterir bir **CEE** gösteren nesne [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md) arabirimi.  
  
```cpp#  
HRESULT CEE::SetCallback(IDebugSettingsCallback2* in_pCallback)  
{  
    // precondition  
    INVARIANT( this );  
  
    // function body  
    if (NULL != this->m_LanguageSpecificUseCases.pfSetCallback)  
    {  
        EEDomain::fSetCallback DomainVal =  
        {  
            in_pCallback  
        };  
  
        BOOL bSuccess = (*this->m_LanguageSpecificUseCases.pfSetCallback)(DomainVal);  
        ENSURE( bSuccess );  
    }  
  
    // postcondition  
    INVARIANT( this );  
  
    return S_OK;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)

