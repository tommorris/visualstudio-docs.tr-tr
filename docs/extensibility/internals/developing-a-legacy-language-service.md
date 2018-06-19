---
title: Eski dil hizmeti geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- vs.vsip.LangServWiz.langtoks
- vs.vsip.LangServWiz.welcome
- vs.vsip.LangServWiz.langSpec
- vs.vsip.LangServWiz.langInfo
- vs.vsip.LangServWiz.langServOpts
helpviewer_keywords:
- language services, developing
ms.assetid: 6151ba88-c1c3-41de-a1cc-668f494d48d1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6cf384a22429c6314bf5e2fcbb66db7974d42c87
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129858"
---
# <a name="developing-a-legacy-language-service"></a>Eski dil hizmeti geliştirme
Bu bölümde bağlantıları yardımcı konulara eski dil hizmeti oluşturun.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Bir dil hizmeti uygulamak için yeni yolu hakkında daha fazla bilgi için bkz: [Düzenleyicisi ve dil hizmeti uzantılarını](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Eski Dil Hizmetinin Modeli](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Bir model için bir en az bir dil hizmetinin sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici. Bu model, kendi dil hizmeti oluşturmak için bir kılavuz olarak kullanabilirsiniz.  
  
 [Eski Dil Hizmeti Arabirimleri](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Bir dil hizmeti uygulamak için gereken nesneleri açıklanır ve sözdizimi vurgulama, yöntemi verilerinin ve diğer özellikleri sağlamak için kullanabileceğiniz ek nesneleri listesini sağlar.  
  
 [Eski Dil Hizmeti Komutlarını Kesme](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Metin görünümü başka türlü işleyebilirsiniz ıntercept komutları dil hizmetinize komut filtresi eklemeye açıklar.  
  
 [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Dil hizmetinizi kullanarak kaydetme hakkında bilgi sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Hata Ayıklama için Dil Hizmeti Desteği](../../extensibility/internals/language-service-support-for-debugging.md)  
 Bir dil hizmeti bir hata ayıklayıcısı desteklemek için özelliklerin nasıl sağlayabilirsiniz açıklar.  
  
 [Denetim Listesi: Eski Dil Hizmeti Oluşturma](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Oluşturma ve çekirdek Düzenleyicisi için bir dil hizmeti tümleştirmek için adım adım yönergeler sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Eski Dil Hizmetinde Söz Dizimi Renklendirmesi](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Dil hizmetinizi sözdizimi vurgulama uygulamak nasıl ele alınmaktadır.  
  
 [Eski Dil Hizmetinde Deyim Tamamlama](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Deyim tamamlama, bir dil anahtar sözcüğü veya yazmaya başladı öğesi son kullanıcılara yardımcı bir dil hizmeti tarafından işlem açıklanır.  
  
 [Eski dil hizmetindeki parametre bilgisi](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Aşırı yüklenen işlevler ve yöntemleri yöntemi ipuçları sağlamak üzere açıklar.  
  
 [Nasıl yapılır: Eski Dil Hizmetinde Gizli Metin Desteği Sağlama](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Bir gizli metni bölge amacını açıklayan ve gizli metni bölge gerçekleştirme hakkında yönergeler sağlar.  
  
 [Nasıl yapılır: Eski Dil Hizmetinde Genişletilmiş Ana Hat Oluşturma Desteği Sağlama](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Destekleyen ötesinde dilinizi anahat desteğini genişletmek iki seçenekleri açıklanmaktadır *daraltmak için tanımları* komutu.