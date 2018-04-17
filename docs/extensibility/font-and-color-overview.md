---
title: Yazı tipi ve renk genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], font and color
- font and color control [Visual Studio SDK], editors
ms.assetid: 2203e4e7-8b7f-44ec-8884-6ff718d4f278
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8185d5c931ccf0b3b15fba10405cf050eb7c6241
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="font-and-color-overview"></a>Yazı tipi ve renk genel bakış
Bu konuda ele alınmıştır metin yazı tipi ve renk ayarlarında [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE). Ayrıca bir kategori ve öğeleri görüntüleme kavramlar tanıtılır ve VSPackages ve çekirdek düzenleyici metin özniteliklerini kullanımını açıklar.  
  
## <a name="the-fonts-and-colors-property-page"></a>Yazı tipleri ve renkler özellik sayfası  
 Görüntülenen metin özniteliklerini yönetebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) üzerinden **yazı tiplerini ve renkleri** özellik sayfası. Bulmak için **yazı tiplerini ve renkleri** özellik sayfasında **Araçları** menüsünde tıklatın **seçenekleri**. Genişletme **ortam**ve ardından **yazı tiplerini ve renkleri**.  
  
## <a name="categories-and-display-items"></a>Kategoriler ve öğeleri görüntüleme  
 Yazı tipleri ve renkler halinde düzenlenir **kategorileri** ve **öğeleri görüntüleme**.  
  
-   A **kategori** bir mantıksal veya işlev sayısı için kapsayıcıdır **öğeleri görüntüleme**.  
  
     Listesini **kategorileri** yer **ayarlarını göster** açılan kutusunda **yazı tiplerini ve renkleri** özellik sayfası.  
  
-   A **görüntü öğesi** bir yorum, bir dize veya görüntülendiğinde renklendirilen için bir denetim yapısı gibi iyi tanımlanmış metin varlıktır.  
  
 Her **görüntü öğesi** içinde benzersiz şekilde tanımlanan **kategori** , içerir. Sonuç olarak, birden fazla **kategori** olabilir bir **görüntü öğesi** aynı ada sahip.  
  
## <a name="vspackage-control-of-fonts-and-colors"></a>Yazı tipleri ve renkler VSPackage denetim  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] İçin VSPackages sağlar:  
  
-   Yazı tipi ve renk tanımlamak **kategorileri**.  
  
-   Yazı tipleri ve renkler sunmak için kullanılan belirtin **öğeleri görüntüleme**.  
  
-   Etkileşim **yazı tiplerini ve renkleri** özellik sayfası.  
  
-   Birleşik birden çok **kategorileri** gruplar.  
  
-   Varsayılan ayarlarında değişiklikler kalır.  
  
 İçindeki yazı tipi ve renk seçimleri ile etkileşim kurmak için iki yolla [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)].  
  
-   Tek yönlü olarak adlandırılır *sözdizimi renkleri*. Varolan özelleştirir bir VSPackage tarafından kullanılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dil hizmeti uygulamak ve düzenleyici bir kaynak oluşturmak için düzenleyici.  
  
     Yalnızca bir **kategori** Bu mekanizma, yani destekler, **metin düzenleyici**.  
  
-   Daha fazla genel bir alternatif diğer tüm destekleyen **kategorileri** ve kullanıcı arabirimi bileşenlerini metin görüntülerken, Kaynak Düzenleyicisi dışında. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>.  
  
## <a name="core-editor-text-settings"></a>Çekirdek Düzenleyici metni ayarları  
 Bir dil hizmeti nesnesinin çekirdek düzenleyici için yazı tipi ve renk ayarları tarafından yönetilir **metin EditorCategory** bulunan **ayarlarını göster** açılan kutusunda **yazı tiplerini ve renkleri** özellik sayfası.  
  
 Düzenleyiciler ile çalışırken, özel yazı tipi ve denetlemek ve genişletmek için dil hizmeti sağlayan renk denetimi mekanizmasını kullanması gereken **metin düzenleyici** ayarlar. Mekanizması olarak adlandırılır *sözdizimi renklendirmesi* ve sağlar:  
  
-   Yazı tipleri ve renkler görünen öğeleri yönetmek için basitleştirilmiş bir teknik.  
  
     Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem>.  
  
-   İyi tanımlanmış ve en iyi duruma getirilmiş renklendirme mekanizması.  
  
     Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>.  
  
-   Her ikisi de yeteneği kullanmak yerleşik görüntü öğelerinden **metin EditorCategory** ve bunları genişletmek için.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: kullanım yerleşik Colorable öğeleri](../extensibility/internals/how-to-use-built-in-colorable-items.md) ve [özel Colorable öğeleri](../extensibility/internals/custom-colorable-items.md).  
  
-   Geçerli durumunu hem yerleşik ve özel otomatik kalıcılığı görüntülemek öğeleriyle **metin düzenleyici** kategorisi.  
  
 Bkz: renklendirme sözdizimi hakkında daha fazla bilgi için [söz dizimi renklendirme eski dil hizmetindeki](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski arabirimleri Düzenleyicisi'nde](../extensibility/legacy-interfaces-in-the-editor.md)   
 [Eski Dil Hizmetinde Söz Dizimi Renklendirmesi](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)