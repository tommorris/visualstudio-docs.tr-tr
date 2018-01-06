---
title: "Özel düzenleyicileri ve tasarımcıları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designers [Visual Studio SDK]
- editors [Visual Studio SDK], custom
ms.assetid: b6a5e8b2-0ae1-4fc3-812d-09d40051b435
caps.latest.revision: "31"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d8d354333545a6ec2b637e160818d506fa049c29
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-custom-editors-and-designers"></a>Özel düzenleyicileri ve tasarımcıları oluşturma
Visual Studio tümleşik geliştirme ortamı (IDE) Düzenleyicisi farklı türlerde barındırabilir:  
  
-   Visual Studio çekirdek Düzenleyicisi  
  
-   Özel düzenleyiciler  
  
-   Dış düzenleyiciler  
  
-   Tasarımcılar  
  
 Aşağıdaki bilgiler ihtiyacınız Düzenleyicisi türünü seçmenize yardımcı olur.  
  
## <a name="types-of-editor"></a>Düzenleyicisi türü  
 Visual Studio çekirdek Düzenleyicisi hakkında daha fazla bilgi için bkz: [Düzenleyicisi ve dil Hizmetleri genişletme](../extensibility/extending-the-editor-and-language-services.md).  
  
##### <a name="custom-editors"></a>Özel düzenleyiciler  
 Özel bir düzenleyici özel durumlarda çalışmak üzere tasarlanmış biridir. Örneğin, okuma ve Microsoft Exchange server gibi belirli bir depo veri yazmak için işlevi olan bir düzenleyici oluşturabilirsiniz. Bir düzenleyici isterseniz, yalnızca birkaç belirli komutları olan ya da yalnızca, proje türü ile çalışan bir düzenleyici istiyorsanız özel bir düzenleyici seçin. Ancak, kullanıcılar standart düzenlemek için özel bir düzenleyici kullanmanız mümkün olmayacaktır unutmayın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projeleri.  
  
 Özel bir düzenleyici bir düzenleyici üreteci kullanın ve düzenleyici bilgilerini kayıt defterine ekleyin. Ancak, özel düzenleyici ile ilişkili proje türü diğer yollarla özel düzenleyici örneğini oluşturabilirsiniz.  
  
 Özel bir düzenleyici yerinde etkinleştirme veya Basitleştirilmiş katıştırma bir görünüm uygulamak için kullanabilirsiniz.  
  
##### <a name="external-editors"></a>Dış düzenleyiciler  
 Dış düzenleyicileri Microsoft Word, Not Defteri veya Microsoft FrontPage gibi Visual Studio uygulamasına tümleştirilmişse Düzenleyicileri ' dir. Örneğin, metin için, VSPackage geçtiğiniz varsa, bu tür bir düzenleyici deniyor olabilir. Dış düzenleyicileri kendilerini kaydetmek ve Visual Studio dışında kullanılabilir. Ardından harici bir düzenleyici çağırmak ve bir ana bilgisayar penceresinde katıştırılabilen, IDE bir pencerede görüntülenir. Aksi durumda, ardından IDE ayrı bir pencere için oluşturur.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> Yöntemini kullanarak belge önceliği ayarlar <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> numaralandırması. Varsa `DP_External` değeri belirtilmişse, dosya bir dış Düzenleyicisi tarafından açılabilir.  
  
## <a name="editor-design-decisions"></a>Düzenleyici tasarım kararları  
 Aşağıdaki tasarım soruları, uygulamanız için uygun Düzenleyicisi en iyi türünü seçmek için yardımcı olur:  
  
-   Uygulamanız kendi veri dosyalarında veya kaydeder? Dosyalarda verileri kaydedecek, özel veya standart bir biçimde olacak mı?  
  
     Standart bir dosya biçimi kullanıyorsanız, projenizi yanı sıra diğer proje türleri açabilir ve okuma/veri kendilerine yazma olacaktır. Ancak, bir özel dosya biçimi kullanırsanız, yalnızca, proje türü açabilir ve okuma/veri kendilerine yazma olacaktır.  
  
     Projenizi dosyaları kullanıyorsa, standart Düzenleyici özelleştirmeniz gerekir. Projenizi dosyalarını kullanmaz, ancak bunun yerine bir veritabanı veya farklı bir depoda öğelerde kullanır, özel bir düzenleyici oluşturmanız gerekir.  
  
-   Düzenleyicinizi ActiveX denetimlerini barındırma gerekiyor mu?  
  
     Düzenleyicinizi ActiveX denetimlerini barındırıyorsa, bir yerinde etkinleştirme Düzenleyicisi kısmında özetlendiği gibi uygulama [yerinde etkinleştirme](../extensibility/in-place-activation.md). ActiveX denetimleri barındırmıyorsa sonra basitleştirilmiş bir katıştırma düzenleyicisi kullanın ya da özelleştirme [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] varsayılan düzenleyici.  
  
-   Düzenleyicinizi birden çok görünüm destekleyecek mi? Varsayılan Düzenleyicisi'ni aynı zamanda görünür olmasını düzenleyicinizi görünümlerini istiyorsanız, birden çok görünüm desteklemesi gerekir.  
  
     Düzenleyicinizi birden çok görünüm desteklemesi gerekiyorsa, belge verileri ve belge görünümü nesneleri Düzenleyicisi için ayrı nesneler olması gerekir. Daha fazla bilgi için bkz: [destekleyen birden çok belge görünümleri](../extensibility/supporting-multiple-document-views.md).  
  
     Birden çok görünüm düzenleyicinizi destekliyorsa, kullanmayı planlıyor musunuz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Düzenleyicisi'nin metin arabelleği uygulama çekirdek (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> nesnesi) belge veri nesne? Diğer bir deyişle, düzenleyici görünümü yan yana ile desteklemek istediğiniz yapmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek Düzenleyici? Bunu yapmak için özelliği forms Tasarımcısı temelini...  
  
-   İçinde bir dış Düzenleyicisi'ni barındırmak gerekiyorsa, düzenleyici katıştırılabilen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]?  
  
     Gömülü olması durumunda, bir ana penceresi dış Düzenleyicisi oluşturun ve ardından çağırın <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> yöntemi ve kümesi <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> numaralandırma değeri `DP_External`. Düzenleyici katıştırılmış, IDE otomatik olarak için ayrı bir pencerede oluşturur.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İzlenecek Yol: Özel Düzenleyici Oluşturma](../extensibility/walkthrough-creating-a-custom-editor.md)  
 Bir özel düzenleyici oluşturma açıklanmaktadır.  
  
 [İzlenecek Yol: Bir Özel Düzenleyiciye Özellik Ekleme](../extensibility/walkthrough-adding-features-to-a-custom-editor.md)  
 Özel bir düzenleyici özelliklere açıklanmaktadır.  
  
 [Tasarımcıyı Başlatma ve Meta Verileri Yapılandırma](../extensibility/designer-initialization-and-metadata-configuration.md)  
 Bir tasarımcı başlatılacağı açıklanmaktadır.  
  
 [Tasarımcılara Geri Alma Desteği Sağlama](../extensibility/supplying-undo-support-to-designers.md)  
 Tasarımcıları için geri alma desteği sağlamak üzere açıklanmaktadır.  
  
 [Özel Düzenleyicilerde Söz Dizimi Renklendirmesi](../extensibility/syntax-coloring-in-custom-editors.md)  
 Sözdizimi çekirdek Düzenleyicisi'ni ve özel düzenleyiciler renklendirme arasındaki farkı açıklar.  
  
 [Özel Düzenleyicilerde Belge Verileri ve Belge Görünümü](../extensibility/document-data-and-document-view-in-custom-editors.md)  
 Belge verileri ve belge görünümleri özel düzenleyicilerde uygulamak açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Eski arabirimleri Düzenleyicisi'nde](../extensibility/legacy-interfaces-in-the-editor.md)  
 Eski API yoluyla çekirdek Düzenleyicisi'ne erişmek açıklanmaktadır.  
  
 [Eski Dil Hizmeti Geliştirme](../extensibility/internals/developing-a-legacy-language-service.md)  
 Bir dil hizmeti uygulama açıklanmaktadır.  
  
 [Visual Studio’nun Diğer Bölümlerini Genişletme](../extensibility/extending-other-parts-of-visual-studio.md)  
 Kalan eşleşen kullanıcı Arabirimi öğeleri oluşturma açıklanmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>