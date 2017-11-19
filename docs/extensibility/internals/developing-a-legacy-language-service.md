---
title: "Eski dil hizmeti geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.vsip.LangServWiz.langtoks
- vs.vsip.LangServWiz.welcome
- vs.vsip.LangServWiz.langSpec
- vs.vsip.LangServWiz.langInfo
- vs.vsip.LangServWiz.langServOpts
helpviewer_keywords: language services, developing
ms.assetid: 6151ba88-c1c3-41de-a1cc-668f494d48d1
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e05fb3f0a33c0f033733c40b17d636243c18ee22
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="developing-a-legacy-language-service"></a>Eski dil hizmeti geliştirme
Bu bölümde bağlantıları yardımcı konulara eski dil hizmeti oluşturun.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Bir dil hizmeti uygulamak için yeni yolu hakkında daha fazla bilgi için bkz: [Düzenleyicisi ve dil hizmeti uzantılarını](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Eski dil hizmet modeli](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Bir model için bir en az bir dil hizmetinin sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici. Bu model, kendi dil hizmeti oluşturmak için bir kılavuz olarak kullanabilirsiniz.  
  
 [Eski dil Hizmeti Arabirimleri](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Bir dil hizmeti uygulamak için gereken nesneleri açıklanır ve sözdizimi vurgulama, yöntemi verilerinin ve diğer özellikleri sağlamak için kullanabileceğiniz ek nesneleri listesini sağlar.  
  
 [Kesintiye uğratan eski dil hizmeti komutları](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Metin görünümü başka türlü işleyebilirsiniz ıntercept komutları dil hizmetinize komut filtresi eklemeye açıklar.  
  
 [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Dil hizmetinizi kullanarak kaydetme hakkında bilgi sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Hata ayıklama için dil hizmeti desteği](../../extensibility/internals/language-service-support-for-debugging.md)  
 Bir dil hizmeti bir hata ayıklayıcısı desteklemek için özelliklerin nasıl sağlayabilirsiniz açıklar.  
  
 [Denetim listesi: eski dil hizmet oluşturma](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Oluşturma ve çekirdek Düzenleyicisi için bir dil hizmeti tümleştirmek için adım adım yönergeler sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Eski dil hizmetinde renklendirme sözdizimi](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Dil hizmetinizi sözdizimi vurgulama uygulamak nasıl ele alınmaktadır.  
  
 [Eski dil hizmetindeki deyim tamamlama](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Deyim tamamlama, bir dil anahtar sözcüğü veya yazmaya başladı öğesi son kullanıcılara yardımcı bir dil hizmeti tarafından işlem açıklanır.  
  
 [Eski dil hizmetindeki parametre bilgisi](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Aşırı yüklenen işlevler ve yöntemleri yöntemi ipuçları sağlamak üzere açıklar.  
  
 [Nasıl yapılır: eski dil hizmetindeki gizli metin desteği sağlar](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Bir gizli metni bölge amacını açıklayan ve gizli metni bölge gerçekleştirme hakkında yönergeler sağlar.  
  
 [Nasıl yapılır: eski dil hizmetindeki genişletilmiş anahat desteği sağlar](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Destekleyen ötesinde dilinizi anahat desteğini genişletmek iki seçenekleri açıklanmaktadır *daraltmak için tanımları* komutu.