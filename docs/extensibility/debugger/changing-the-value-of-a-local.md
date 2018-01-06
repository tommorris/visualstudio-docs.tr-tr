---
title: "Yerel değerin değiştirilmesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, changing values programmatically
ms.assetid: 8407d3df-d38a-4328-82d1-98084bef43ec
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 03e6acb4ee9756d0bbb14a6e3667375d32cafba9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="changing-the-value-of-a-local"></a>Yerel değerini değiştirme
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Yeni bir değer değer alanına türü ne zaman **Yereller** penceresi, hata ayıklama paket geçirir dize, ifade değerlendiricisi (EE) yazıldığı gibi. EE basit bir değer veya ifade içerebilir ve çıkan değeri ilişkili yerel depolar Bu dize değerlendirir.  
  
 Bu bir yerel değerini değiştirme işlemine genel bakış.  
  
1.  Kullanıcı yeni bir değer girdikten sonra Visual Studio çağırır [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) üzerinde [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) yerel ile ilişkili nesne.  
  
2.  `IDebugProperty2::SetValueAsString`Aşağıdaki görevleri gerçekleştirir:  
  
    1.  Bir değer üretmek için dize değerlendirir.  
  
    2.  İlişkili bağlar [IDebugField](../../extensibility/debugger/reference/idebugfield.md) elde etmek için nesne bir [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) nesnesi.  
  
    3.  Değer bir dizi bayt dönüştürür.  
  
    4.  Çağrıları [SetValue](../../extensibility/debugger/reference/idebugobject-setvalue.md) ayıklanacak program bunlara erişebilmesini değerinin bayt belleğe yerleştirilecek.  
  
3.  Visual Studio yeniler **Yereller** görüntüleme (bkz [görüntüleme Yereller](../../extensibility/debugger/displaying-locals.md) Ayrıntılar için).  
  
 Bu yordamı da bir değişkenin değerini değiştirmek için kullanılan **izleme** penceresi dışında `IDebugProperty2` yerine kullanılan yerel değeriyle ilişkili nesne `IDebugProperty2` yerel ile ilişkili nesne kendisi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Örnek Değer Değiştirme Uygulaması](../../extensibility/debugger/sample-implementation-of-changing-values.md)  
 Değerlerini değiştirme işleminde size adım adım MyCEE örnek kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Yerel Öğeleri Görüntüleme](../../extensibility/debugger/displaying-locals.md)