---
title: Bir ortak dil çalışma zamanı ifade değerlendiricisi yazma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluators, tutorial
- expression evaluation, samples
- debugging [Debugging SDK], expression evaluators tutorial
ms.assetid: bd79d57f-8e0a-4e14-a417-0b1de28fa1b2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3ff2189bd80d2c5bbbc5253763e2ba07ef917d19
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="writing-a-common-language-runtime-expression-evaluator"></a>Bir ortak dil çalışma zamanı ifade değerlendiricisi yazma
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 İfade değerlendirici (EE) sözdizimi işleme bir hata ayıklama altyapısı (DE) ve ayıklanacak kodu üretilen programlama dili semantiği parçasıdır. İfadeler bir programlama dili bağlamında değerlendirilmelidir. Örneğin, bazı dillerde ifadesi "A + B" anlamına gelir "toplamı, A ve b" Diğer dillerde aynı ifadesi "A veya b" anlamına gelebilir Bu nedenle, ayrı bir EE Visual Studio IDE içinde ayıklanacak nesne kodu oluşturan her programlama dili için yazılmış olmalıdır.  
  
 Visual Studio hata ayıklama paketi bazı yönlerini programlama dili bağlamında kodu yorumlar gerekir. Örneğin, ne zaman yürütme işlemindeki bir kesme, içine kullanıcı tarafından yazılan tüm ifadeleri noktasında bir **izleme** penceresi değerlendirilir ve görüntülenir. Bir ifadeyi yazarak kullanıcı yerel bir değişkenin değerini de değiştirebilirsiniz bir **izleme** penceresi veya **hemen** penceresi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Ortak Dil Çalışma Zamanı ve İfade Değerlendirme](../../extensibility/debugger/common-language-runtime-and-expression-evaluation.md)  
 Özel programlama dili Visual Studio IDE tümleştirdiğinizde, bir EE yazma özel dil bağlamında ifadeleri değerlendirme yeteneğine, bir Microsoft Ara dili (MSIL) derlemek izin verdiğini açıklar hata ayıklama altyapısı yazmadan.  
  
 [İfade Değerlendirici Mimarisi](../../extensibility/debugger/expression-evaluator-architecture.md)  
 Gerekli EE arabirimlerini ve ortak dil çalışma zamanı simgesi sağlayıcısı (SP) ve bağlayıcı arabirimleri çağırmak nasıl ele alınmaktadır.  
  
 [İfade Değerlendiricisi Kaydetme](../../extensibility/debugger/registering-an-expression-evaluator.md)  
 EE kendisini üreteci ortak dil çalışma zamanı ve Visual Studio çalışma zamanı ortamları olarak kaydetmeniz gerekir, notlar.  
  
 [ifade Değerlendiricisi Uygulama](../../extensibility/debugger/implementing-an-expression-evaluator.md)  
 Hata ayıklama altyapısı (DE), simge sağlayıcısı (SP), bağlayıcı nesnesi ve ifade değerlendiricisi (EE) bir ifade değerlendirme işlemi nasıl içerir açıklar.  
  
 [Yerel Öğeleri Görüntüleme](../../extensibility/debugger/displaying-locals.md)  
 Hata ayıklama paket yürütme duraklatır, yerel değişkenleri ve bağımsız değişkenler listesini almak için DE nasıl çağırır açıklar.  
  
 [Gözcü Penceresi İfadesini Değerlendirme](../../extensibility/debugger/evaluating-a-watch-window-expression.md)  
 Her Gözlem listesi ifadesinde geçerli değeri belirlemek için DE Visual Studio hata ayıklama paketi nasıl çağırır belgeler.  
  
 [Yerel Bir Öğenin Değerini Değiştirme](../../extensibility/debugger/changing-the-value-of-a-local.md)  
 Yerel değerinin değiştirilmesi yerel öğeler penceresi, her satırın adını, türünü ve yerel geçerli değeri sağlayan bir ilişkili nesne olduğunu açıklar.  
  
 [Tür Görselleştiricileri ve Özel Görüntüleyiciler Uygulama](../../extensibility/debugger/implementing-type-visualizers-and-custom-viewers.md)  
 Hangi arabirimi türü görselleştiriciler ve özel görüntüleyiciler desteklemek için hangi bileşen tarafından uygulanması gerekiyor açıklanmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)