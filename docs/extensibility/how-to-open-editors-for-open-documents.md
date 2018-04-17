---
title: 'Nasıl yapılır: açık açık belgeler için düzenleyicileri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], opening for open documents
ms.assetid: 1a0fa49c-efa4-4dcc-bdc0-299b7052acdc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 621ed4436160b6f491abb34d8194c75595d9a54c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-open-editors-for-open-documents"></a>Nasıl yapılır: açık belgeler için düzenleyicileri açın
Bir belge penceresi proje açılmadan önce projeyi önce dosyanın zaten başka bir düzenleyici için belge penceresindeki açık olup olmadığını belirlemeniz gerekir. Dosya ya da açık bir projeye özgü düzenleyicisinde olabilir ya da standart düzenleyicileri birini kayıtlı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="opening-a-project-specific-editor"></a>Bir projeye özgü Düzenleyicisi'ni açma  
 Zaten açık olan bir dosya için bir proje özgü düzenleyici açmak için aşağıdaki yordamı kullanın.  
  
#### <a name="to-open-a-project-specific-editor-for-an-open-file"></a>Açık bir dosya için bir proje özgü düzenleyici açmak için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> yöntemi.  
  
     Uygunsa, belgenin hiyerarşisi, hiyerarşi öğesi ve pencere çerçevesi işaretçileri bu çağrıyı döndürür.  
  
2.  Belge açıksa, proje yalnızca bir belge veri nesnesi var olup olmadığını veya belge bir görünüm nesne varsa emin olmanız gerekir.  
  
    -   Bir belge görünüm nesnesi var ve bu görünüm farklı hiyerarşi veya hiyerarşi öğesi için ise, proje görünümün pencere çerçevesi işaretçisine varolan pencere resurface için kullanır.  
  
    -   Temel alınan belge veri nesnesine ekleyebilirsiniz, bir belge görünüm nesnesi var ve bu görünüm aynı hiyerarşiye ve hiyerarşi öğesi için ise, proje ikinci bir görünüm açabilirsiniz. Aksi takdirde, proje varolan pencere resurface için görünümün pencere çerçevesi işaretçisine kullanmanız gerekir.  
  
    -   Yalnızca belge veri nesnesi varsa, projenin bu belgeyi veri nesnesi, görünüm için kullanıp kullanamayacağını belirlemeniz gerekir. Belge verileri nesne uyumlu ise, tam adımlar ele [bir projeye özgü Düzenleyicisi'ni açma](../extensibility/how-to-open-project-specific-editors.md).  
  
     Belge veri nesnesi uyumlu değilse, dosyanın şu anda kullanımda olduğunu belirten kullanıcı bir hata görüntülenmesi gerekir. Bir dosyayı aynı anda derlendiğinde kullanıcı dışındaki bir düzenleyiciyi kullanarak dosyayı açmaya çalışıyor gibi bu hata yalnızca geçici durumlarda görüntülenmelidir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek metin düzenleyici. Temel metin düzenleyici belge veri nesnesi derleyicisi ile paylaşabilirsiniz.  
  
3.  Belge veri nesnesi veya belge görünüm nesnesi olmadığından belge açık değilse, bölümündeki adımları tamamlamanız [bir projeye özgü Düzenleyicisi'ni açma](../extensibility/how-to-open-project-specific-editors.md).  
  
## <a name="opening-a-standard-editor"></a>Bir standart Düzenleyicisi'ni açma  
 Aç zaten bir dosya için standart bir düzenleyici açmak için aşağıdaki yordamı kullanın.  
  
#### <a name="to-open-a-standard-editor-for-an-open-file"></a>Açık bir dosya için standart bir düzenleyici açmak için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.  
  
     Bu yöntem ilk belge zaten çağırarak açık olmadığını doğrular <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A>. Belge zaten açıksa, kendi Düzenleyicisi penceresini resurfaced.  
  
2.  Belge açık değilse, bölümündeki adımları tamamlamanız [nasıl yapılır: standart düzenleyicileri açmak](../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açıp kaydederek proje öğeleri](../extensibility/internals/opening-and-saving-project-items.md)   
 [Nasıl yapılır: açık projeye özgü düzenleyiciler](../extensibility/how-to-open-project-specific-editors.md)   
 [Nasıl Yapılır: Standart Düzenleyicileri Açma](../extensibility/how-to-open-standard-editors.md)