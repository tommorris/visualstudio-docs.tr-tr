---
title: 'Nasıl yapılır: açık standart düzenleyicileri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], opening
- projects [Visual Studio SDK], opening standard editors
ms.assetid: d5ce10f9-047a-4b74-aa1d-295128898b89
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2adcdc0f2d05061c412c5233a16e21a1b9fb252a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129264"
---
# <a name="how-to-open-standard-editors"></a>Nasıl yapılır: standart düzenleyicileri açın
Standart Düzenleyici açtığınızda, dosya için bir proje özgü Düzenleyici belirtme yerine bir dosya türü için standart bir düzenleyici belirlemek IDE sağlar.  
  
 Uygulamak için aşağıdaki yordamı tamamlayın <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> yöntemi. Bu proje dosyası standart bir düzenleyicide açın.  
  
### <a name="to-implement-the-openitem-method-with-a-standard-editor"></a>Standart düzenleyiciyle OpenItem yöntemi uygulamak için  
  
1.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> (`RDT_EditLock`) belgesi veri nesnesi dosyası zaten açık olup olmadığını belirlemek için.  
  
2.  Dosyanın zaten açıksa, dosyayı çağırarak resurface <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> yöntemi, bir değer olarak belirtmek `IDO_ActivateIfOpen` için `grfIDO` parametresi.  
  
     Açık bir dosyadır ve belge sahibi arama proje daha farklı bir proje ile projenizin açılmakta olan başka bir projeden düzenleyicisidir bir uyarı alır. Dosya penceresini sonra ortaya.  
  
3.  Çalışan belge tablosunda yok veya belge açık değilse çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> yöntemi (`OSE_ChooseBestStdEditor`) dosyası için bir standart Düzenleyici açın.  
  
     Yöntemini çağırdığınızda, IDE aşağıdaki görevleri gerçekleştirir:  
  
    1.  IDE düzenleyicileri tarar / {guidEditorType} / Uzantıları alt hangi Düzenleyicisi belirlemek için kayıt defteri anahtarında dosyayı açabilir ve bunu yapmak için en yüksek önceliğe sahip.  
  
    2.  IDE hangi düzenleyicinin dosyayı açabilmek için belirledi sonra IDE çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>. Bu yöntemin kullanımı Düzenleyicisi'nin IDE çağırmak gerekli olan bilgiler verir <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> ve yeni açılan belgeyi site.  
  
    3.  Son olarak, her zamanki Kalıcılık arabirimi kullanarak IDE belge yükler <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>.  
  
    4.  IDE önceden hiyerarşi öğesi veya hiyerarşi kullanılabilir olduğunu belirlerse, IDE çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> yöntemi bir proje düzeyi içeriği almak için projedeki <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> geri ile geçirmek için işaretçi <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> yöntem çağrısı.  
  
4.  Dönüş bir <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> IDE çağırdığında IDE işaretçi <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.GetItemContext%2A> projenizi projenizi Düzenleyicisi get bağlamından izin vermek istiyorsanız.  
  
     Bu adımı gerçekleştirmenin düzenleyiciye Proje teklif ek hizmetler sağlar.  
  
     Belge Görünümü ya da belge görünüm nesnesi bir pencere çerçevesi başarıyla tarihli, nesneyi kendi verilerle çağrılarak başlatılır <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.LoadDocData%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Açıp kaydederek proje öğeleri](../extensibility/internals/opening-and-saving-project-items.md)   
 [Nasıl yapılır: açık projeye özgü düzenleyiciler](../extensibility/how-to-open-project-specific-editors.md)   
 [Nasıl yapılır: açık belgeler için düzenleyicileri açın](../extensibility/how-to-open-editors-for-open-documents.md)   
 [Dosya Aç Komutunu Kullanarak Dosyaları Görüntüleme](../extensibility/internals/displaying-files-by-using-the-open-file-command.md)