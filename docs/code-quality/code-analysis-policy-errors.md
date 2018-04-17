---
title: Kod çözümleme İlkesi hataları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.policyfailures
helpviewer_keywords:
- policy errors, code analysis
ms.assetid: d1f221cd-68c0-4277-9397-b76ad0dbae77
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f9c46dae012a35dcb616366682aeffd584da70a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="code-analysis-policy-errors"></a>Kod Çözümleme İlkesi Hataları
Kod çözümleme İlkesi giriş sırasında gerçekleşmedi aşağıdaki hatalar oluşur:  
  
 **Kod çözümleme ayarları bir veya daha fazla projeleri için Kod Analizi ilkesiyle uyumlu değildir.**  
  
 Bir veya daha fazla kod projeler için takım projesi kaynak denetimine iade kod çözümlemesi gereksinimleri karşılanmadı. Bu hata, bir veya daha fazla aşağıdaki koşullardan biri tarafından kaynaklanabilir:  
  
1.  Kod çözümleme yapı tüm Çözümdeki projeler için etkin değil.  
  
2.  Visual Studio projesi daha az kısıtlayıcı olan ayarlamanız yerel kural **eylem** takım projesi kural Örneğin, ayarlamak için bir kural kümesi daha ayarı **eylem**=**hata**  sunucu üzerinde kendi **eylem** kümesine **uyarı** veya **hiçbiri** kural Visual Studio'da çalıştırılmayı kümesi içinde).  
  
3.  Visual Studio'da belirtilen kural tüm kural takım projesi için Kod Analizi İade İlkesi'nde belirtilen kümesi içinde belirtilen kurallar içermiyor.  
  
 **Kod çözümleme İlkesi başarısız oldu. Proje {0} hataları var veya yapı güncel değil.**  
  
 Derleme hataları içeriyor veya hataları düzeltilen ancak kod analizi sonra düzeltme gerçekleştirilmedi.  
  
 **İade başarısız oldu. Kod çözümleme İlkesi aracılığıyla Visual Studio ile açık olan bir çözüm iade olmasını gerektirir.**  
  
 Kod çözümleme İlkesi iade edildi tüm dosyalar şu anda açık çözümde olmasını gerektirir. Bu hatayı düzeltmek için iade edilmesi dosyasını içeren çözümü açın.  
  
 **Tüm bekleyen onay bileşeninde içinde şu anda açık olan çözüm dosyalarıdır.**  
  
 Kod çözümleme İlkesi iade edildi tüm dosyalar şu anda açık çözümde olmasını gerektirir. Bu hata, açık olan bir çözüm yoktur, ancak "bekleyen onay işareti" görünümünde bazı dosyalar şu anda açık çözüm parçası olmayan tetiklenir. Bu hatayı düzeltmek için iade edilmesi dosyasını içeren çözümü açın.  
  
 **'{0}' sürümü doğru değil. Güçlü-ilkesinde belirtilen adı '{1}' dir.**  
  
 Bu hata, .NET projeler için geçerlidir. Kod çözümleme İlkesi tarafından istenen bir kural .dll yerel bilgisayarda var ancak sürüm/ortak anahtar eşleşmiyor. Bu hatayı düzeltmek için ilke Oluşturucusu .dll güncelleştirmeniz gerekir *C:\Program Files\Microsoft Visual Studio 8\Team Tools\Static analiz Tools\FxCop\Rules\\*  bilgisayarlarında dizin.  
  
 **ilkede belirtilen '{0}' derlemesi yok.**  
  
 Bu hata, .NET projeler için geçerlidir. Kod çözümleme İlkesi tarafından istenen bir kural, istemci bilgisayarda yüklü karşılık gelen dll yok. Bu hatayı düzeltmek için ilke Oluşturucusu DLL'de güncelleştirmelisiniz *C:\Program Files\Microsoft Visual Studio 8\Team Tools\Static analiz Tools\FxCop\Rules\\*  bilgisayarlarında dizin.  
  
 **Proje {0} kural ayarları kod çözümleme İlkesi uyumlu değildir.**  
  
 Bu hata, .NET projeler için geçerlidir. Yönetilen kod kural ayarları İlkesi gerektiriyor olarak kesin değildir. Bu hatayı düzeltmek için istemci ayarını aynı olması gerekir veya sunucu üzerindeki ilke daha katı.  
  
 **Kod çözümleme etkin yapılandırmasına etkin değil. Yapılandırma {0} geçin ve iade etmeden önce proje {1} oluşturun.**  
  
 İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]etkin yapılandırma etkin Kod Analizi yok ancak etkinleştirilmiş en az bir kod analizi yok.  
  
 **Proje {0} Özellikleri'nde yönetilen ikili dosyaları için Kod Analizi etkinleştirin ve iade etmeden önce yapı gerekir.**  
  
 Bu hata uygulandığı [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] .NET uygulamaları. Gerçekleştirilecek yönetilen kod çözümleme İlkesi gerektiriyor, ancak geçerli projede istemci üzerinde etkin değil.  
  
 **Kod çözümleme proje {0} Özellikleri'nde etkinleştirmek ve iade etmeden önce yapı gerekir.**  
  
 Bu hata uygulanan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projeleri ve Web projeleri. Gerçekleştirilecek yönetilen kod çözümleme İlkesi gerektiriyor, ancak geçerli projede istemci üzerinde etkin değil.  
  
 **C/C++ Kod Analizi proje {0} özellikleri etkinleştirmek ve iade etmeden önce yapı gerekir.**  
  
 Bu hata, yönetilmeyen projeler için geçerlidir. Kod çözümleme İlkesi C/C++ için Kod Analizi gerektirir, ancak geçerli projede istemci üzerinde etkin değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod Çözümleme Uygulama Hataları](../code-quality/code-analysis-application-errors.md)