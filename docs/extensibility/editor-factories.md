---
title: "Düzenleyici oluşturucuları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - editor factories
ms.assetid: cf4e8164-3546-441d-b465-e8a836ae7216
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0bfef7e641bc8f7e041242ce28110845855c2a65
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="editor-factories"></a>Düzenleyici oluşturucuları
Bir düzenleyici üreteci Düzenleyicisi nesneleri oluşturur ve bunları fiziksel bir görünüm olarak bilinen bir pencere çerçevesi koyar. Belge verileri ve düzenleyicileri ve tasarımcıları oluşturmak için gerekli olan belge görünümü nesneleri oluşturur. Bir düzenleyici üreteci, Visual Studio çekirdek Düzenleyicisi'ni ve herhangi bir standart Düzenleyicisi oluşturmak için gereklidir. Özel bir düzenleyici Ayrıca isteğe bağlı olarak bir düzenleyici üreteci ile oluşturulabilir.  
  
 Bir düzenleyici üreteci uygulayarak oluşturduğunuz <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> arabirimi. Aşağıdaki örnekte nasıl uygulandığını gösterir <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> bir düzenleyici üreteci oluşturmak için:  
  
 [!code-vb[VSSDKEditorFactories#1](../extensibility/codesnippet/VisualBasic/editor-factories_1.vb)]
 [!code-csharp[VSSDKEditorFactories#1](../extensibility/codesnippet/CSharp/editor-factories_1.cs)]  
  
 Bir düzenleyici bu Düzenleyicisi tarafından işlenen bir dosya türünü açmayı ilk kez yüklenir. Belirli bir düzenleyici veya varsayılan Düzenleyicisi'ni açmak seçebilirsiniz. Varsayılan Düzenleyicisi'ni seçerseniz, tümleşik geliştirme ortamı (IDE) açmak için doğru Düzenleyicisi belirler ve ardından açar. Daha fazla bilgi için bkz: [projede açılır bir dosyayı hangi Düzenleyicisi'ni belirleme](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md).  
  
## <a name="registering-editor-factories"></a>Düzenleyici oluşturucuları kaydetme  
 Oluşturduğunuz bir düzenleyici kullanmadan önce hakkında bilgi işlemek dosya uzantıları dahil olmak üzere kaydetmeniz gerekir.  
  
 Yönetilen kodda, VSPackage yazılmışsa yönetilen paket Framework (MPF) yöntemini kullanabilirsiniz <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> , VSPackage yüklendikten sonra Düzenleyici üreteci kaydetmek için. Yönetilmeyen kodunda, VSPackage yazılır sonra kullanarak Düzenleyici üreteci kaydolmalıdır <xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterEditors> hizmet.  
  
### <a name="registering-an-editor-factory-by-using-managed-code"></a>Yönetilen kod kullanarak bir düzenleyici üreteci kaydetme  
 Düzenleyici üreteci, VSPackage içinde 's kaydetmeniz gerekir `Initialize` yöntemi. İlk çağrı `base.Initialize`ve ardından arama <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> her Düzenleyici üreteci için  
  
 Yönetilen kodda bir düzenleyici üreteci kaydını gerek yoktur VSPackage bu sizin için işleyecek olduğundan. Ayrıca, düzenleyici üreteci uyguluyorsa <xref:System.IDisposable>, kaydı olduğunda otomatik olarak atıldı.  
  
### <a name="registering-an-editor-factory-by-using-unmanaged-code"></a>Yönetilmeyen kod kullanarak bir düzenleyici üreteci kaydetme  
 İçinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> Düzenleyicisi paketinizi kullanmak için uygulama `QueryService` çağrılacak yöntem `SVsRegisterEditors`. Bunu yapmak için bir işaretçi döndürür <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors>. Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> uygulamanıza geçirerek yöntemi <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> arabirimi. Mplement gerekir <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> ayrı bir sınıf.  
  
## <a name="the-editor-factory-registration-process"></a>Düzenleyici üreteci kayıt işlemi  
 Visual Studio, düzenleyici üreteci kullanarak düzenleyicinizi yüklediğinde aşağıdaki süreç gerçekleşir:  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Proje sistem çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.  
  
2.  Bu yöntem Düzenleyici üreteci döndürür. Proje Sistemi Düzenleyicisi için gereken gerçek kadar düzenleyicisinin paketi, ancak yüklenirken visual Studio gecikme olabilir.  
  
3.  Visual Studio Proje Sistemi Düzenleyicisi gerektiğinde çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>, belge görünümü ve belgenin veri nesneleri döndüren özel bir yöntem.  
  
4.  Varsa, Fabrika Düzenleyicisi için Visual Studio tarafından çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> bir belge veri nesnesi ve bir belge görünüm nesnesi döndürür, Visual Studio sonra belge penceresine oluşturur, belge görünüm nesnesi yerleştirir ve bir giriş çalışan belgesine yapar Belge veri nesnesi tablosu (RDT).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>   
 [Çalışan belge tablosu](../extensibility/internals/running-document-table.md)