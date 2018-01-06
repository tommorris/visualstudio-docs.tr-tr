---
title: "Metin işaretçileri eski API ile kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text markers
ms.assetid: 937a0b19-1216-45d5-a7ad-4fe1d6f73097
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 98c889bc1bc128a941f726348781a633799475de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-text-markers-with-the-legacy-api"></a>Metin işaretçileri eski API ile kullanma
Bir metin işaretçisi metin, görüntü etkileyebilecek arabelleği kayan bir dizi ve metin bir bölgenin davranışını ' dir. Kesme noktaları, yer işaretleri, dalgalı alt çizgiler ve salt okunur bölgeler işaretçileri içerir. Metin işaretçileri sözdizimi renklendirmesi gelen temelde farklıdır. Sözdizimi renklendirmesi metin bölgesiyle ilişkilendirilen dili sözdizimi iletişim kurmak için hızlı bir yoludur. Sözdizimi renklendirmesi hızı önemli olduğu durumlarda Windows ekran şekilde yeniden boyar olduğunda genellikle istendi. Sözdizimi renklendirmesi yalnızca metin rengini değiştirir. Metin işaretçileri diğer birçok metin özelliklerini değiştirebilirsiniz. Metin işaretçileri "float" ve özel davranışı uygulamak ve renklendirme.  
  
 Metin işaretçileri ile ilişkili performans yükü nedeniyle, metin arabellekleri için birçok işaretçileri oluşturmayın. Her işaret kullanıcı arabelleği içeriği düzenler her zaman güncelleştirilir.  
  
> [!NOTE]
>  Kullanıcılara görünür işaret türü ancak değil, Şekil ve stil rengini değiştirebilirsiniz. Daha fazla bilgi için bkz: [yazı tipleri ve renkler, ortam, Seçenekler iletişim kutusu](../ide/reference/fonts-and-colors-environment-options-dialog-box.md).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: standart metin işaretleyicileri ekleyin](../extensibility/how-to-add-standard-text-markers.md)|Tarafından sağlanan standart metin işaret türü eklemeyi açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek düzenleyici metin görünümü.|  
|[Nasıl yapılır: uygulama hata işaretçileri](../extensibility/how-to-implement-error-markers.md)|Örneği uygulamak açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kırmızı dalgalı alt çizgiler kullanarak hataları göstermek için kullanılan işaretçisi.|  
|[Nasıl yapılır: özel metin işaretçileri oluşturma](../extensibility/how-to-create-custom-text-markers.md)|Oluşturma ve metin görünümüne özel metin işaret türü ekleme açıklar.|  
|[Nasıl yapılır: metin işaretçileri kullanın](../extensibility/how-to-use-text-markers.md)|Metin işaretçileri ına nasıl ekleneceğini açıklar.|  
|[İçinde çekirdek Düzenleyicisi](../extensibility/inside-the-core-editor.md)|Çekirdek Düzenleyici özelliklerini açıklar ve çekirdek Düzenleyicisi'ni özelleştirme hakkında ayrıntılar sağlar.|  
|[Düzenleyicisi özellikleri](http://msdn.microsoft.com/en-us/bdac940d-1f14-4019-a01f-fd0bb3dc7198)|Uygulamasında kullanılabilen özellikleri açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici.|  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType>  
 Düzenleyicisi tarafından önceden tanımlanmış veya VSPackage tarafından kayıtlı olup olmadığını belirli bir metni işaret türü hakkında bilgi almak için Tekdüzen bir mekanizma sağlar.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLineMarker>  
 Erişim sağlar ve iki boyutlu koordinatları kullanarak metin arabelleğini bir metin işaretçisi konumunu ayarlar.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker>  
 Metin işaretçileri yönetme için yöntemleri sağlar.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>  
 Geri aramalar için sağlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE ve bir metin işaretçisi ayarlamak için kullanılan diğer işlemler.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced>  
 Aracılığıyla kullanılabilir işlevselliği genişletir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> ek geri aramalar sağlayarak arabirimi.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>  
 Aracılığıyla kullanılabilir işlevselliği genişletir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> ek geri aramalar sağlayarak arabirimi.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerColorSet>  
 Diğer işaret türleri renkleri aynı kümesini paylaşır olup olmadığını belirlemek işaretçi türü etkinleştirir.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider>  
 Metin işaretçileri çekirdek düzenleyicisinde için bağlam sağlar. Çekirdek Düzenleyicisi'nde olduğu her metin işaretçisi türü için ayrı bir IDE oluşturur <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> nesnesi.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerGlyphDropHandler>  
 İşaretçileri olan karakterlerin sürükle ve bırak düzenlemeyi desteklemek için sağlanan bir işleyici. Bir karakterin bir işaret konumunu belirten bir simgedir.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>  
 Döndürür bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> bir metin diğer VSPackages işaretleyicileri sağlayan bir hizmet arabirimden.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamMarker>  
 Erişim sağlar ve tek boyutlu koordinatları kullanarak metin arabelleğini bir metin işaretçisi konumunu ayarlar. Mümkünse, bu arabirim kullanmayın.