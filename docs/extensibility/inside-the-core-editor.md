---
title: "İçinde çekirdek Düzenleyici | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e4612f5779d6177d58cef7f087ef6e11bbe4ebd9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="inside-the-core-editor"></a>İçinde çekirdek Düzenleyicisi
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Çekirdek Düzenleyicisi'ni değiştirin ve sorgu metin bilgileri sağlayan birkaç bileşenlerine kümesidir. Eski API kullanarak çekirdek Düzenleyici özelleştirdiyseniz, düzenleyici bağdaştırıcıları aracılığıyla yönlendirilir bu özelleştirmeler kullanmaya devam edebilir. Bu, ancak yeni Düzenleyicisi API özelleştirmelerinizi uyum önerilir.  
  
 Aşağıdaki alanlarda çekirdek Düzenleyici önemli bazı yönleri şunlardır:  
  
-   Metin arabelleği  
  
-   Metin görünümü  
  
-   Kod penceresi  
  
-   Metin işaretçileri  
  
-   Metin Yöneticisi  
  
-   Dil Hizmetleri ile tümleştirme  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Eski API kullanarak çekirdek Düzenleyici örneği](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)  
 Nasıl kullanılacağı hakkında adım adım yönergeler sağlar <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> Düzenleyicisi çekirdek örneği oluşturulamadı.  
  
 [Eski API kullanarak metin arabelleği erişme](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)  
 Çekirdek düzenleyicisinde metin arabelleği rolü ele alınmıştır, arabellek erişmek için kullanılır ve metin arabelleği nesne tarafından uygulanan arabirimler listesini sağlayan ilişkili sistemleri açıklanır <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 [Eski API metin arabelleği olayları](../extensibility/text-buffer-events-in-the-legacy-api.md)  
 Metin arabelleği olayları bildirim için kullanılan arabirimleri listesini sağlar.  
  
 [Nasıl yapılır: metin arabelleği olayları eski API ile kaydetme](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)  
 Metin arabelleği olayları bildirmek amacıyla açıklar.  
  
 [Genel ayarları izlemek için metin Yöneticisi'ni kullanma](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Metin Yöneticisi çekirdek Düzenleyicisi bileşenleri ile genel tercih bilgi paylaşımı için nasıl kullanıldığı ve metin Yöneticisi olaylarını bildirim almak nasıl anlatılmaktadır.  
  
 [Eski API kullanarak getirip metin görünümü erişme](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
 Metin görünümün rolü çekirdek düzenleyicisinde açıklar ve tarafından uygulanan arabirimler listeler <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> nesnesi.  
  
 [Eski API'sini kullanarak kod Windows özelleştirme](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)  
 Nasıl bir kod penceresi metin görünümü kapsamak için kullanılan kod Pencere Yöneticisi kod penceresine düzenlemelerini sağlamak için nasıl kullanıldığını açıklar ve yeni görünümler bildirim sağlar hakkında bilgi sağlar.  
  
 [Eski API kullanarak görünüm ayarlarını değiştirme](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Görünüm ayarlarını zorlamak ve zorlanmış ayarlarını kaldırma hakkında adım adım yönergeler sağlar.  
  
 [Dil Hizmetleri ve çekirdek Düzenleyicisi](../extensibility/language-services-and-the-core-editor.md)  
 Bir dil hizmetine denetim kodu düzenlemelerini örneklemesi açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [İzlenecek yol: bir çekirdek düzenleyici oluşturma ve bir düzenleyici dosya türü kaydetme](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)  
 Yönetilen koddan çekirdek Düzenleyicisi'ni başlatın hakkında adım adım yönergeler sağlar.  
  
 [Aşağı açılan çubuğu](../extensibility/drop-down-bar.md)  
 Nasıl açılır çubuğu kod penceresinde kullanılır ve açılan çubuğu uyguladığınızda, kullanılan arabirimlerini açıklar açıklanır.  
  
 [Metin işaretçileri eski API ile kullanma](../extensibility/using-text-markers-with-the-legacy-api.md)  
 Metin işaretçileri ve bunların çekirdek Düzenleyici'de nasıl kullanıldığı kavramını açıklar ve erişmek ve metin işaretçileri yönetmek için kullanılan arabirimleri listeler.  
  
 [Nasıl yapılır: standart metin işaretleyicileri ekleyin](../extensibility/how-to-add-standard-text-markers.md)  
 Bir metin işaretçisi oluşturmak ve özel komut için kısayol menüsü ekleme hakkında adım adım yönergeler sağlar.  
  
 [Nasıl yapılır: özel metin işaretçileri oluşturma](../extensibility/how-to-create-custom-text-markers.md)  
 Özel metin işaretçisi oluşturmak ve bir hizmet olarak işaret türü sağlamak hakkında adım adım yönergeler sağlar.