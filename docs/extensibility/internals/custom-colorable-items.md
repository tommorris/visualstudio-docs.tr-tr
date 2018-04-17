---
title: Özel Colorable öğeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, custom colorable items
ms.assetid: b4d0ddee-c04b-48dc-ba82-f6068570cef0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b23ff39abcb9a1354ea28becab3b7df867378ddf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="custom-colorable-items"></a>Özel Colorable öğeler
Dil hizmetiniz bir parçası olarak özel colorable öğeler uygulayarak türlerinin listesi renklendirme, anahtar sözcükleri ve açıklamalar gibi kılabilirsiniz.  
  
## <a name="user-settings-of-colorable-items"></a>Kullanıcı ayarlarını Colorable öğeleri  
 Görüntüleyebileceğiniz **yazı tiplerini ve renkleri** seçerek iletişim kutusu **seçenekleri** üzerinde **Araçları** menüsüne ve ardından seçerek **yazı tiplerini ve renkleri** altında **ortam**. Seçtiğinizde, bir görüntü gibi **metin düzenleyici** veya **komut penceresi**, **görüntülemek öğeleri** liste kutusu colorable tüm öğeler için görüntülenen gösterir. Görüntüleyin ve yazı tipi, boyut, ön plan rengini ve colorable her öğe için arka plan rengini değiştirin. Seçimlerinizi kayıt önbellekte depolanır ve colorable öğe adı tarafından erişilen.  
  
## <a name="presentation-of-colorable-items"></a>Colorable öğeleri sunumu  
 IDE içinde colorable öğelerin kullanıcı geçersiz kılmalarını işlemesi nedeniyle **yazı tiplerini ve renkleri** iletişim kutusu, gereksinim duyduğunuz yalnızca her özel colorable bir öğeyle bir ad sağlayın. Bu ad görünür ne olduğunu **görüntülemek öğeleri** listesi. Colorable öğeleri alfabetik olarak görüntülenir. Dil hizmetinizin özel colorable öğeleri gruplandırmak için her dil adınızı adıyla örneğin başlayabilirsiniz **NewLanguage - açıklama** ve **NewLanguage - anahtar sözcüğü**.  
  
> [!CAUTION]
>  Dil adı, varolan colorable öğe adları ile çakışmaları önlemek için colorable öğesi adı içermelidir. Geliştirme sırasında colorable öğelerinizi birinin adını değiştirirseniz, colorable öğelerinizi erişilen ilk kez oluşturulduğu önbellek sıfırlamanız gerekir. Genellikle dizininde Visual Studio SDK ile yüklenen CreateExpInstance aracıyla Deneysel önbellek sıfırlayabilirsiniz  
>   
>  **C:\Program dosyaları (x86) \Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin**  
>   
>  Önbellek sıfırlamak için arama `CreateExpInstance /Reset`. CreateExpInstance hakkında daha fazla bilgi için bkz: [CreateExpInstance yardımcı programı](../../extensibility/internals/createexpinstance-utility.md).  
  
 Listesindeki ilk öğeyi colorable öğelerinin asla başvurulmaz. İlk öğeyi 0 colorable öğesi dizine karşılık gelir ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] her zaman varsayılan metin rengini ve bu öğe için öznitelikler sağlar. Kolay başvurulmayan bu öğe postalarla bir yer tutucu colorable öğesi, listedeki ilk öğe olarak sağlamak için yoludur.  
  
## <a name="implementing-custom-colorable-items"></a>Uygulama özel Colorable öğeler  
  
1.  Dilinizde, örneğin anahtar sözcüğü, işleç ve tanımlayıcı renklendirilen gerekir tanımlayın.  
  
2.  Bu colorable öğeleri listesini oluşturun.  
  
3.  Bir Ayrıştırıcı veya tarayıcı numaralandırılmış değerler ile döndürülen belirteç türleri ilişkilendirin.  
  
     Örneğin, belirteç türleri temsil eden değerleri özel colorable öğeler numaralandırması aynı değerleri olabilir.  
  
4.  Uygulamanızda <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> yönteminde, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> nesne, öznitelikler listesi ayrıştırıcı veya tarayıcıdan döndürülen belirteç türleri karşılık gelen, özel colorable öğeler numaralandırması değerlerle doldurun.  
  
5.  Uygulayan aynı sınıfta <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> arabirimi, uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> arabirimi ve iki yöntemlerinden <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A>.  
  
6.  Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> arabirimi.  
  
7.  24 bit ya da yüksek renk değerleri desteklemek istiyorsanız, ayrıca uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> arabirimi.  
  
8.  Dil hizmeti nesnesinde içeren bir liste oluşturmak, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> nesneleri, bir ayrıştırıcı veya tarayıcı belirleyebilir colorable her öğe için.  
  
     Listedeki her öğeye karşılık gelen özel colorable öğeler numaralandırma değeri kullanarak erişebilirsiniz. Numaralandırma değerleri listeye dizin olarak kullanın. Listedeki ilk öğe hiçbir zaman erişilen, varsayılan metin karşılık olmadığından, stil [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] her zaman kendi işler. Bunun için bir yer tutucu colorable öğesi listesinin başında ekleyerek dengeleyebilirsiniz.  
  
9. Uygulamanızda <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> yöntemi, özel colorable öğeler listedeki öğe sayısını döndürür.  
  
10. Uygulamanızda <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> yöntemi, istenen colorable öğe listenizden döndürür.  
  
 Nasıl uygulayacağınıza dair bir örnek <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> arabirimleri, bkz: <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmet modeli](../../extensibility/internals/model-of-a-legacy-language-service.md)   
 [Sözdizimi özel düzenleyicilerde renklendirme](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [Eski dil hizmetinde renklendirme sözdizimi](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Sözdizimi renklendirmesi uygulama](../../extensibility/internals/implementing-syntax-coloring.md)   
 [Nasıl yapılır: Yerleşik Renklendirilebilir Öğeleri Kullanma](../../extensibility/internals/how-to-use-built-in-colorable-items.md)