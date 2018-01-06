---
title: Eski dil Hizmeti Arabirimleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IVsLanguageInfo interface
- language services, objects
ms.assetid: 03b2d507-f463-417e-bc22-bdac68eeda52
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 82555c861a6bf250a818b185de57fc48f143e4f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="legacy-language-service-interfaces"></a>Eski dil Hizmeti Arabirimleri
Belirli bir programlama dili için aynı anda dil hizmetinin yalnızca bir örneği olabilir. Ancak, tek bir dil hizmeti birden fazla Düzenleyicisi hizmet verebilir.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]bir dil hizmeti belirli bir düzenleyiciyle ilişkilendirmez. Bu nedenle, bir dil hizmet işlemi istediğinde, parametre olarak uygun olan düzenleyici tanımlamanız gerekir.  
  
## <a name="common-interfaces-associated-with-language-services"></a>Dil hizmetlerle ilgili ortak arabirimleri  
 Düzenleyici çağırarak dil hizmetinizi alır <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> uygun VSPackage üzerinde. Bu çağrı kimliği (SID) geçirilen hizmeti istenen dil hizmet tanımlar.  
  
 Ayrı sınıf herhangi bir sayıda çekirdek dil Hizmeti Arabirimleri uygulayabilirsiniz. Ancak, tek bir sınıfta aşağıdaki arabirimleri uygulamak için ortak bir yaklaşım şöyledir:  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageBlock>(isteğe bağlı)  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> Tüm dil Services'de arabirimi uygulanmadı. Dil hizmeti ve bir Renklendirici alma ile ilişkilendirilmiş dosya adı uzantıları dil yerelleştirilmiş adı gibi dil hizmetiniz hakkında bilgi sağlar.  
  
## <a name="additional-language-service-interfaces"></a>Ek dil Hizmeti Arabirimleri  
 Diğer arabirimleri dil hizmetiniz ile sağlanabilir. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Bu arabirimleri metin arabelleği her örneği için ayrı bir örneği ister. Bu nedenle, bu arabirimlerin her biri kendi nesnesinde uygulamalıdır. Aşağıdaki tabloda metin arabelleği örneği başına bir örneğini gerektirir arabirimler gösterilir.  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|Aşağı açılan çubuğu gibi kodu penceresi adornments yönetir. Bu arabirimi kullanarak alabileceğiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> yöntemi. Bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> kod penceresi başına.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>|Dil anahtar sözcükleri ve sınırlayıcı renklendirmez. Bu arabirimi kullanarak alabileceğiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> yöntemi. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>Paint zaman çağrılır. Hesaplama yoğunluklu iş içinde kaçının <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> veya performans düşebilir.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>|IntelliSense parametre araç ipuçları sağlar. Dil hizmeti bu yöntemi verileri gösteren bir karakter olmalıdır tanıdığında, açık bir parantez gibi görüntülenen çağırır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> metin bildirmek için yöntemi görüntülemek dil hizmeti bir parametre bilgileri araç ipucu görüntülemek hazırdır. Metin görünümü daha sonra geri dil hizmeti tarafından içine yöntemleri kullanılarak çağırır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> araç ipucu görüntülemek için gerekli olan bilgileri almak için arabirim.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet>|IntelliSense deyim tamamlama sağlar. Dil hizmeti tamamlanma listesini görüntülemek hazır olduğunda, çağıran <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metin görünümü yöntemi. Metin görünümü daha sonra geri dil hizmeti tarafından içine yöntemleri kullanarak çağırır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> nesnesi.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter>|Komut işleyici kullanarak metin görünümü değiştirilmek üzere sağlar. İçinde uygulamadan sınıfı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> arabirimi ayrıca uygulanmalı <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi. Metin görünümü alır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> sorgulama nesne <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> içine geçirilen nesne <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> yöntemi. Olması gerektiğini bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> her görünüm için nesne.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Kullanıcı kodu penceresine türleri komutları kesintiye uğratır. İzleme çıktısı, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> özel tamamlama bilgileri sağlayın ve değişikliği görmek için uygulama<br /><br /> Geçirmek için <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> metin görünümü, çağrı nesnesine <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti geliştirme](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [Denetim Listesi: Eski Dil Hizmeti Oluşturma](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)