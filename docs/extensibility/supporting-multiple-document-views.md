---
title: "Birden çok belge görünümlerini destekleyen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], custom - multiple document views
ms.assetid: c7ec2366-91c4-477f-908d-e89068bdb3e3
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4efd76830356996bdf75c923f457d19d2381763c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="supporting-multiple-document-views"></a>Birden çok belge görünümleri destekleme
Ayrı belge verileri ve belge görünümü nesneleri için düzenleyici oluşturarak, bir belgenin birden fazla görünümü sağlayabilirsiniz. Bir ek belge görünümü yararlı olabilecek bazı durumlarda şunlardır:  
  
-   Yeni pencere desteği: düzenleyicide açık bir pencere zaten olan bir kullanıcının yeni bir pencere seçerek açabilirsiniz böylece aynı türde iki veya daha fazla görünümlerini sağlamak üzere, Düzenleyicisi istediğiniz **yeni pencere** komutunu **penceresi** menüsü.  
  
-   Form ve kod görüntülemek desteği: farklı görünümlerini sağlamak üzere, Düzenleyicisi istiyor. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], örneğin, bir form görünümü ve kod görünümü sağlar.  
  
 Bu konu hakkında daha fazla bilgi için Visual Studio Paketi şablonu tarafından oluşturulan özel düzenleyici proje EditorFactory.cs dosyasında CreateEditorInstance yordamına bakın. Bu proje hakkında daha fazla bilgi için bkz: [izlenecek yol: bir özel düzenleyici oluşturma](../extensibility/walkthrough-creating-a-custom-editor.md).  
  
## <a name="synchronizing-views"></a>Görünümler eşitleniyor  
 Birden çok görünüm uyguladığınızda, belge veri nesnesi tüm görünümleri veri ile eşitlenmiş tutmak için sorumludur. Olay üzerinde arabirimleri işleme kullanabilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> verilerle birden çok görünüm eşitlenecek.  
  
 Kullanmıyorsanız, <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> belge veri nesnesine yapılan değişiklikler işlemek için kendi olay sistem uygulamalıdır sonra birden çok görünüm eşitlemek için nesne. Birden çok görünüm güncel tutmak için farklı ayrıntı düzeyleri kullanabilirsiniz. En fazla ayrıntı düzeyi ayarı ile tek bir görünümde yazarken diğer görünümlere hemen güncelleştirilir. Bunlar etkinleştirilinceye kadar en düşük ayrıntı düzeyi diğer görünümlerle güncelleştirilmez.  
  
## <a name="determining-whether-document-data-is-already-open"></a>Zaten açık olan belge verileri olup olmadığını belirleme  
 Tümleşik geliştirme ortamı (IDE) çalışan belge tablosunda (RDT), bir belge için veri zaten aşağıdaki çizimde gösterildiği gibi açık olup olmadığını izlemek yardımcı olur.  
  
 ![DocDataView grafiği](../extensibility/media/docdataview.gif "Docdataview")  
Birden çok görünüm  
  
 Varsayılan olarak her görünümün (belge görünüm nesnesi) kendi pencere çerçevesi yer alır (<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>). Önceden belirtildiği gibi ancak belge verileri birden çok görünümlerde görüntülenebilir. Bunu etkinleştirmek için Visual Studio RDT söz konusu belgede zaten bir düzenleyicide açık olup olmadığını belirlemek için denetler. IDE çağırdığında <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> Düzenleyicisi oluşturmak için boş olmayan bir değer döndürdü `punkDocDataExisting` parametresi belge zaten başka bir düzenleyicide açık olduğunu gösterir. RDT işlevler hakkında daha fazla bilgi için bkz: [çalıştıran Belge tablosu](../extensibility/internals/running-document-table.md).  
  
 İçinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> uygulaması, döndürülen belge veri nesnesi inceleyin `punkDocDataExisting` belge verileri Düzenleyicisi için uygun olup olmadığını belirlemek için. (Örneğin, yalnızca HTML verileri bir HTML düzenleyicisi tarafından görüntülenmesi gerekir.) Uygun değilse, düzenleyici üreteci için veri ikinci bir görünüm sağlamalıdır. Varsa `punkDocDataExisting` parametresi `NULL`, ya da mümkündür belge veri nesnesi başka bir düzenleyicide açık veya, büyük olasılıkla, belge verileri zaten aynı Düzenleyicisi ile farklı bir görünümde açık olduğunu. Belge verileri Düzenleyicisi Fabrikanızda desteklemediği farklı bir düzenleyici açıksa, Visual Studio, düzenleyici üreteci açılması başarısız. Daha fazla bilgi için bkz: [nasıl yapılır: belge verileri ekleme görünümlerine](../extensibility/how-to-attach-views-to-document-data.md).