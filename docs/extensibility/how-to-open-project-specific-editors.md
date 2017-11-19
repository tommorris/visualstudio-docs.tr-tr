---
title: "Nasıl yapılır: açık projeye özgü düzenleyicileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, opening a project-specific editor
- editors [Visual Studio SDK], opening project-specific editors
- projects [Visual Studio SDK], opening folders
ms.assetid: 83e56d39-c97b-4c6b-86d6-3ffbec97e8d1
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bb60f482edeea1271c0f864fd5b907138e83d103
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-open-project-specific-editors"></a>Nasıl yapılır: açık projeye özgü düzenleyiciler
Bir projeye göre açılmakta bir öğe dosya doğası gereği, bu proje için belirli düzenleyiciye bağlıysa, projenin bir projeye özgü Düzenleyicisi'ni kullanarak dosyayı açmanız gerekir. Dosya bir düzenleyicide seçme IDE'nin mekanizması aşağıya doğru devredilemez. Örneğin, bir standart bit eşlemi Düzenleyicisi'ni kullanmak yerine, projenize için benzersizdir dosyasındaki bilgileri tanır belirli bit eşlem Düzenleyicisi belirtmek için bu projeye özgü Düzenleyici seçeneği kullanabilirsiniz.  
  
 IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> bir dosya belirli bir proje tarafından açılmalı belirlediğinde yöntemi. Daha fazla bilgi için bkz: [açık dosya komutunu kullanarak görüntüleme dosyaları](../extensibility/internals/displaying-files-by-using-the-open-file-command.md). Uygulamak için aşağıdaki kılavuzları kullanın `OpenItem` projenizi bir projeye özgü Düzenleyicisi'ni kullanarak bir dosyayı açmak için yöntem.  
  
### <a name="to-implement-the-openitem-method-with-a-project-specific-editor"></a>Bir projeye özgü düzenleyicisiyle OpenItem yöntemi uygulamak için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> (belge veri nesnesi) dosya zaten açık olup olmadığını belirlemek amacıyla yöntemi (RDT_EditLock).  
  
    > [!NOTE]
    >  Belge verileri ve belge görünümü nesneleri hakkında daha fazla bilgi için bkz: [belge verileri ve özel düzenleyiciler belge görünümünde](../extensibility/document-data-and-document-view-in-custom-editors.md).  
  
2.  Dosyanın zaten açıksa, dosyayı çağırarak resurface <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> yöntemi ve IDO_ActivateIfOpen için değeri belirterek `grfIDO` parametresi.  
  
     Açık bir dosyadır ve belge sahibi arama proje dışındaki bir proje ile başka bir projeden açılmakta Düzenleyicisi kullanıcısına bir uyarı görüntülenir. Dosya penceresini sonra ortaya.  
  
3.  Metin arabelleğini (belge veri nesnesi) zaten açık olan ve başka bir görünüm eklemek istiyorsanız, bu görünüm takma sorumludur. Bir görünüm (belge görünüm nesnesi) projeden başlatmasını önerilen yaklaşım aşağıdaki gibidir:  
  
    1.  Çağrı `QueryService` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.SLocalRegistry> gösteren bir işaretçi almak için hizmet <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2> arabirimi.  
  
    2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> belge görünümü sınıfının bir örneğini oluşturmak için yöntemi.  
  
4.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> yöntemi, belge görünüm nesnesi belirtme.  
  
     Bu yöntem, bir belge penceresi belge görünüm nesnesinde siteleri.  
  
5.  Ya da uygun çağrıları gerçekleştirdiğinizde <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.InitNew%2A> veya <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A> yöntemleri.  
  
     Bu noktada, görünüm, tamamen başlatılmış ve açılması için hazır olması gerekir.  
  
6.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> yöntemi gösterir ve görünümünü açın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açıp kaydederek proje öğeleri](../extensibility/internals/opening-and-saving-project-items.md)   
 [Nasıl yapılır: standart düzenleyicileri açın](../extensibility/how-to-open-standard-editors.md)   
 [Nasıl yapılır: açık belgeler için düzenleyicileri açın](../extensibility/how-to-open-editors-for-open-documents.md)