---
title: Eski API kullanarak bir dil Hizmet bağlamı sağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - language service context
ms.assetid: daa2df22-9181-4bad-b007-a7d40302bce1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3556fcce3d14d5069854c64d81cb780123a979d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="providing-a-language-service-context-by-using-the-legacy-api"></a>Eski API kullanarak bir dil Hizmet bağlamı sağlama
Kullanıcı bağlamı kullanarak sağlamak için bir dil hizmeti için iki seçenek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici: metin işaretçisi bağlam sağlamak ya da tüm kullanıcı bağlamı sağlar. Her arasındaki farklar burada özetlenmektedir.  
  
 Kendi düzenleyiciye bağlı bir dil hizmeti bağlamına sağlama ile ilgili daha fazla bilgi için bkz: [nasıl yapılır: düzenleyicileri sağlamak bağlamının](../extensibility/how-to-provide-context-for-editors.md).  
  
## <a name="provide-text-marker-context-to-the-editor"></a>Düzenleyiciye metin işaretçisi bağlamı sağlar  
 Metin işaretçileri belirttiği derleyici hataları içerik sağlamak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici, uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> arabirimi. Bu senaryoda, yalnızca imleci bir metin işaretçisi olduğunda dil hizmeti bağlamı sağlar. Bu anahtar için imlecin sağlamak üzere Düzenleyicisi sağlar **dinamik yardımcı** penceresi özniteliği yok.  
  
## <a name="provide-all-user-context-to-the-editor"></a>Tüm kullanıcı bağlamı düzenleyiciye sağlayın  
 Bir dil hizmeti oluşturma ve kullanmakta olduğunuz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , uygulayabileceğiniz sonra Düzenleyici, çekirdek <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> dil hizmetiniz için içerik sağlamak için arabirim.  
  
 Uygulama için `IVsLanguageContextProvider`, bir içerik paketi (toplama) İçerik Paketi güncelleştirmek için sorumlu Düzenleyicisi bağlı. Zaman **dinamik yardımcı** penceresi çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.Update%2A> bu içerik paketi boşta kalma zaman, içerik paketi arabirimde sorgular için bir güncelleştirme Düzenleyici. Düzenleyici dil hizmeti, düzenleyici güncelleştirmeniz gerekir ve bağlam Torba işaretçi geçirmeden sonra bildirir. Bu çağırarak yapılır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider.UpdateLanguageContext%2A> dil hizmetine düzenleyicisinden yöntemi. İşaretçinin içerik paketi kullanarak, dil hizmeti şimdi ekleyip çıkarabilirsiniz öznitelikleri ve anahtar sözcükler. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider>.  
  
 Uygulamak için iki farklı yolla `IVsLanguageContextProvider`:  
  
-   İçerik Paketi için bir anahtar sözcüğü girin  
  
     İçerik Paketi güncelleştirmeye Düzenleyicisi çağrıldığında uygun anahtar sözcükleri ve öznitelikleri geçirin ve sonra geri dönüp `S_OK`. Bu dönüş değeri yerine anahtar sözcüğü ve öznitelik içeriğinizi korumak için içerik paketi imlecin anahtar sözcüğü girin düzenleyiciye söyler.  
  
-   İmlecin anahtar sözcüğü ile anahtar sözcüğü alın  
  
     İçerik Paketi güncelleştirmeye Düzenleyicisi çağrıldığında, uygun öznitelik geçirin ve sonra geri dönüp `E_FAIL`. Bu dönüş değeri içerik paketi, öznitelikleri korur ancak imlecin anahtar sözcüğüyle içerik paketi güncelleştirmek için Düzenleyicisi söyler.  
  
 Aşağıdaki diyagramda bağlam uygulayan bir dil Hizmeti'ni nasıl sağlandığını gösterir `IVsLanguageContextProvider`.  
  
 ![LangServiceImplementation2 grafik](../extensibility/media/vslanguageservice2.gif "vsLanguageService2")  
Bağlam için bir dil hizmeti  
  
 Diyagramda görüldüğü gibi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek metin düzenleyici bağlı bir içerik paketi vardır. Bu içerik paketi için üç ayrı üzere paketler işaret: dil hizmeti, varsayılan düzenleyici ve metin işaretçisi. Dil hizmeti ve metin işaretçisi üzere paketler öznitelikleri ve dil hizmeti için anahtar sözcükleri varsayarsak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> arabirimi uygulanır ve metin işaretçileri varsa <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> arabirimi uygulanır. Bu arabirimleri birini kullanılmaz, düzenleyici varsayılan Düzenleyicisi üzere pakette imlecin anahtar sözcüğü için bağlamı sağlar.  
  
## <a name="context-guidelines-for-editors-and-designers"></a>Düzenleyiciler ve tasarımcıları için bağlam yönergeleri  
 Tasarımcılar ve düzenleyiciler Düzenleyicisi veya tasarımcı penceresi için bir genel anahtar sözcüğü sağlamanız gerekir. Bu, böylece kullanıcı F1 tuşuna bastığında genel, ancak uygun Yardım konusunun Tasarımcısı veya Düzenleyicisi için görüntüler gerçekleştirilir. Bir düzenleyici gerekir Buna ek olarak, imlecin geçerli anahtar sözcüğü girin veya geçerli seçimi temel alan bir anahtar terimi sağlayın. Bu metin ya da kullanıcı Arabirimi öğesi için bir Yardım konusu işaret veya kullanıcı F1 tuşuna bastığında görüntüler seçili emin olmak için gerçekleştirilir. Bir tasarımcı bir formda bir düğmesi gibi bir Tasarımcısı'nda seçilen bir öğe için bağlamı sağlar. Düzenleyicileri ve tasarımcıları ayrıca bağlanması için bir dil hizmeti kısmında özetlendiği gibi [eski dil hizmeti Essentials](../extensibility/internals/legacy-language-service-essentials.md).