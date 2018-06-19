---
title: Ortak dil çalışma zamanı ve ifade değerlendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, and common language runtime
ms.assetid: b36c1eb5-1aaf-48a6-b287-ee7a273d2b1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 370b7963c71b74674c7d323a5fa1c2650d3f08d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108553"
---
# <a name="common-language-runtime-and-expression-evaluation"></a>Ortak dil çalışma zamanı ve ifade değerlendirme
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Derleyicileri, Visual Basic ve C (C-sharp telaffuz edilir), ortak dil çalışma zamanı (CLR) hedeflemek, #, Microsoft Ara dili (sonraki olan MSIL), üretmek gibi yerel koda derlenmiş. CLR hata ayıklama altyapısı (Sonuç kodu hata ayıklamak için DE) sağlar. Visual Studio IDE içinde özel programlama diliniz tümleştirmek planlıyorsanız için MSIL derlemek seçebilirsiniz ve bu nedenle, kendi DE yazmak zorunda kalmazsınız. Ancak, programlama diliniz bağlamında ifadelerin değerlendirirken özelliğine sahip bir ifade değerlendiricisi (EE) yazmak zorunda.  
  
## <a name="discussion"></a>Tartışma  
 Bilgisayar dili ifadeleri, genellikle bir dizi veri nesneleri ve bunları işlemek için kullanılan işleçleri kümesi oluşturmak için ayrıştırılır. Örneğin, "A + B" Toplama işleci (+) uygulamak için verileri ayrıştırılması ifadesi "A"'i ve "B, büyük olasılıkla başka bir veri nesnesinde kaynaklanan" nesneleri. Veri nesneleri, işleçler ve ilişkilendirmelerinin toplam kümesi çoğunlukla bir program olarak temsil ağaç düğümleri, işleçler ve dalları adresindeki veri nesneleri içeren bir ağacı. Ağaç forma dökümü yapılan bir ifade, çoğunlukla ayrıştırılmış bir ağaç adı verilir.  
  
 Bir ifade Ayrıştırılan sonra simge sağlayıcısı (SP) her veri nesnesi değerlendirmek için çağrılır. Örneğin, "A" hem de birden çok yöntem sonra soru tanımlanmış olması durumunda "A?" A değerini saptanabilen önce yanıtlanması gerekir. SP tarafından döndürülen yanıt "Beşinci yığın çerçevesinde üçüncü öğesi" gibi bir şey ya da "Statik bellek başlangıcı ötesinde 50 bayt A Bu yöntem için ayrılmış."  
  
 Program için MSIL oluşturan yanı sıra, CLR derleyicileri Program veritabanı (.pdb) dosyasına yazılacak çok açıklayıcı hata ayıklama bilgilerini üretebilir. Hata ayıklama bilgileri CLR derleyicileri aynı biçimde özel dil derleyici üretir sürece CLR'nin SP dil veri nesneleri adlı belirlemek mümkün değildir. Bir adlandırılmış veri nesnesi belirlendikten sonra EE bağlayıcı nesnesi ilişkilendirmek (veya bağlamak için) veri nesnesi o nesnenin değerini tutan bellek alanı kullanır. DE alın veya veri nesnesi için yeni bir değer belirleyin.  
  
 Özel bir derleyici CLR çağırarak hata ayıklama bilgileri sağlayabilir `ISymbolWriter` arabirimi (.NET Framework ad alanında tanımlı `System.Diagnostics.SymbolStore`). MSIL için derleme ve hata ayıklama bilgilerini bu arabirimleri aracılığıyla yazma, özel bir derleyici SP'yi ve CLR DE kullanabilirsiniz Bu, büyük ölçüde Visual Studio IDE içinde özel bir dil tümleştirme basitleştirir.  
  
 CLR DE bir ifade değerlendirmek için özel EE çağırdığında bir SP ve bağlayıcı nesnesi arabirimleri ile EE DE sağlar. Bu nedenle, bir hata ayıklama CLR tabanlı altyapısı yol yazma yalnızca uygun ifade değerlendiricisi arabirimleri uygulanması için gerekli; CLR bağlama ve sizin için işleme simgesi ilgilenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)