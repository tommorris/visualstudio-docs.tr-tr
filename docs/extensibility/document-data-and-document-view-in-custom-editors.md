---
title: "Belge verileri ve belgeyi görüntülemek özel düzenleyicilerde | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - document data and document view
ms.assetid: 71eea623-f566-4feb-84cd-ca1ba71bc493
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ab3506a6906c4223888a14132339cbe5499c92d1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="document-data-and-document-view-in-custom-editors"></a>Belge verileri ve belge görünümünde özel düzenleyiciler
Özel bir düzenleyici iki bölümden oluşur: bir belgeyi veri nesnesi ve bir belge görünüm nesnesi. Adları önermek gibi belge veri nesnesi görüntülenecek metin verileri temsil eder ve belge görünüm nesnesi (veya "Görünüm") belgenin veri nesnesi görüntülemek üzere bir veya daha fazla windows temsil eder.  
  
## <a name="document-data-object"></a>Belge veri nesnesi  
 Bir belge veri nesnesi bir metin arabelleği metinde veri gösterimidir. Belge metni ve diğer bilgileri depolar, belge Kalıcılık işler ve birden çok görünüm verilerini sağlayan bir COM nesnesi değil. Daha fazla bilgi için bkz.  
  
 <xref:EnvDTE80.Window2.DocumentData%2A>ve [belge Windows](../extensibility/internals/document-windows.md).  
  
 Özel düzenleyicileri ve tasarımcıları kullanmak için kabul <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> nesne veya kendi özel arabellek. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>Basitleştirilmiş katıştırma modeli için standart bir düzenleyici izler, birden çok görünüm destekler ve birden çok görünüm yönetmek için kullanılan olay arabirimleri sağlar.  
  
## <a name="document-view-object"></a>Belge görünüm nesnesi  
 Kod ve diğer metin görüntüleyen bir pencere bir belge olarak bilinen görünüm veya görünüm. Bir düzenleyici oluşturduğunuzda, metin tek bir pencerede görüntülenir tek bir görünüm veya metin birden fazla penceresinde görüntülenir birden çok görünüm seçebilirsiniz. Tercih ettiğiniz, uygulamaya bağlı olarak değişir. Örneğin, yan yana düzenleme gerekiyorsa, birden çok görünüm seçmelisiniz. Her görünüm Belge tablosu (RDT) çalıştıran tümleşik geliştirme ortamı (IDE) bir girdi ile ilişkilidir. Bir projeye ait görünüm windows veya bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> nesnesi.  
  
 Bir belge veri nesnesinin birden çok görünüm düzenleyicinizi destekliyorsa, belge verilerinizi ve belge görünümü nesneleri ayrı olmalıdır. Aksi takdirde, bunlar birlikte gruplandırılabilir. Daha fazla bilgi için bkz: [destekleyen birden çok belge görünümleri](../extensibility/supporting-multiple-document-views.md).  
  
 IDE çalışan belge tablosundaki her giriş için bir öğe tanımlayıcısı (ItemId) eşleştirerek görünümleri (örneğin, bir belge içeren bir çözüm kapatıldığında) olayları hakkında uyarır. Bunun hakkında daha fazla bilgi için bkz: [çalıştıran Belge tablosu](../extensibility/internals/running-document-table.md).  
  
 Bir görünümü için bir özel düzenleyici oluşturma için iki seçenek vardır. Görünüm bir ActiveX denetimi veya bir belge veri nesnesi kullanılarak bir pencerede barındırıldığı yerinde etkinleştirme modeli biridir. Tarafından görünümü barındırıldığı Basitleştirilmiş katıştırma modeli, ikincisinin [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> pencere komutları işlemek için uygulanır. Yerinde etkinleştirme modeli hakkında daha fazla bilgi için bkz: [yerinde etkinleştirme](../extensibility/in-place-activation.md). Basitleştirilmiş katıştırma modeli hakkında daha fazla bilgi için bkz: [Basitleştirilmiş katıştırma](../extensibility/simplified-embedding.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok belge görünümleri destekleme](../extensibility/supporting-multiple-document-views.md)   
 [Basitleştirilmiş katıştırma](../extensibility/simplified-embedding.md)   
 [Nasıl yapılır: veri belgelemek için görünümler ekleme](../extensibility/how-to-attach-views-to-document-data.md)   
 [Belge kilit sahibi Yönetimi](../extensibility/document-lock-holder-management.md)   
 [Tek ve birden çok sekme görünümleri](../extensibility/single-and-multi-tab-views.md)   
 [Standart belgeyi kaydetme](../extensibility/internals/saving-a-standard-document.md)   
 [Kalıcılığı ve çalışan belge tablosu](../extensibility/internals/persistence-and-the-running-document-table.md)   
 [Proje dosyasında Düzenleyicisi açan belirleme](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)   
 [Düzenleyici oluşturucuları](../extensibility/editor-factories.md)