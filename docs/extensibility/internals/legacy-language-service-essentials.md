---
title: Eski dil hizmeti Essentials | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- languages, integrating into Visual Studio
- language services, integrating programming languages
- Visual Studio, integrating programming languages
- programming languages, integrating into Visual Studio
ms.assetid: c15e0ccb-e7c5-4dbb-affb-fe3d3244debe
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 577010320dc4aa0a726e7c0befba8173245681e7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-language-service-essentials"></a>Eski dil hizmeti temelleri
Bir programlama dili Visual Studio'ya tümleştirmek için bir dil hizmeti sağlamanız gerekir. Bu konu eski dil hizmetlerinde kullanılabilen özellikleri açıklar.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Bir dil hizmeti uygulamak için yeni yolu hakkında daha fazla bilgi için bkz: [Düzenleyicisi ve dil hizmeti uzantılarını](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
 Eski dil Hizmetleri aşağıdaki özellikleri sağlar:  
  
|Özellik|Açıklama|  
|-------------|-----------------|  
|Sözdizimi renklendirmesi|Farklı renk ve yazı tipi stillerini dilinin farklı öğeler için görüntülenecek Düzenleyicisi görünümü neden olur. Bu ayrım, dosyaları okuyup kolaylaştırabilir.<br /><br /> Genel bilgi için bkz: [sözdizimi renkleri eski dil hizmetindeki](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).<br /><br /> Yönetilen paket framework (MPF)'deki bu özellik hakkında daha fazla bilgi için bkz: [söz dizimi renklendirme eski dil hizmetindeki](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md).|  
|Deyim tamamlama|Bir deyim veya kullanıcı yazmaya başladı anahtar sözcüğü tamamlar. Deyim tamamlama, kullanıcıların zor deyimleri daha az yazarak ve daha az hata olasılığını daha kolay girin yardımcı olur.<br /><br /> Genel bilgi için bkz: [deyim tamamlama eski dil hizmetindeki](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md).<br /><br /> MPF'deki bu özellik hakkında daha fazla bilgi için bkz: [Sözcük tamamlama eski dil hizmetindeki](../../extensibility/internals/word-completion-in-a-legacy-language-service.md).|  
|Ayraç eşleştirme|Küme ayraçları gibi eşleştirilmiş karakterler vurgular. Ne zaman kullanıcı türleri kapatma karakterini gibi "}", eşleşen ayraç vurgular karakteri gibi açma karşılık gelen "{". Birkaç düzeyinden birini karakterini olduğunda, bu özelliği kullanıcıları kapsayan karakterleri doğru eşlenmemiş onaylayın yardımcı olur.<br /><br /> MPF'deki bu özellik hakkında daha fazla bilgi için bkz: [eşleşen ayraç eski dil hizmetindeki](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md).|  
|Parametre bilgileri araç ipuçları|Kullanıcı şu anda yazarak aşırı yüklenmiş metodun olası imzaları listesini görüntüler.<br /><br /> Genel bilgi için bkz: [parametre bilgisi eski dil hizmetindeki](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md).<br /><br /> MPF'deki bu özellik hakkında daha fazla bilgi için bkz: [parametre bilgisi eski dil hizmetindeki](../../extensibility/internals/parameter-info-in-a-legacy-language-service2.md).|  
|Hata işaretçileri|Kırmızı dalgalı alt, olarak da bilinen bir dalgalı, sözdizimi kurallarına göre yanlış metin altında görüntüler. Hata işaretçileri genellikle kullanıcılar yanlış yazılmış anahtar sözcükler, kapatılmamış parantez, geçersiz karakterler ve benzer hatalar haberdar olmak için kullanılır.<br /><br /> MPF sınıflarında hata işaretçileri otomatik olarak işlenir <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> yöntemi <xref:Microsoft.VisualStudio.Package.AuthoringSink> sınıfı.|  
  
 Bu özelliklerin çoğu, kaynak kodu ayrıştırmak için dil hizmeti gerektirir. Genellikle belirtece dönüştürmek ve derleyici veya yorumlayıcı kodunu ayrıştırma yeniden kullanabilirsiniz.  
  
 Aşağıdaki özellikler programlama dilleri için destek ile ilgili ancak dil Hizmetleri'nin parçası değildir:  
  
|Özellik|Açıklama|  
|-------------|-----------------|  
|İfade değerlendiricileri|Destekler [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] görüntülenmesini kesme noktaları doğrulama ve bir ifade listesini sağladığı tarafından hata ayıklayıcı **otomobiller** hata ayıklama penceresi.<br /><br /> Daha fazla bilgi için bkz: [dil hizmeti hata ayıklama desteği](../../extensibility/internals/language-service-support-for-debugging.md).|  
|Simgenin tarama araçları|Destekler **Nesne Tarayıcısı**, **sınıf görünümü**, **çağrısı tarayıcı**, ve **Bul simgesi sonuçları**.|