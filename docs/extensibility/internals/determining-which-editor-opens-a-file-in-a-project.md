---
title: "Hangi Düzenleyicisi projede bir dosyayı açar belirleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], determining which editor opens a file
- projects [Visual Studio SDK], determining which editor opens file
- project types, determining which editor opens a file
- persistence, determining which editor opens a file
ms.assetid: acbcf4d8-a53a-4727-9043-696a47369479
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f7c69bc08d0f1bb72a37b76fca2d402d73036deb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="determining-which-editor-opens-a-file-in-a-project"></a>Proje dosyasında Düzenleyicisi açan belirleme
Bir kullanıcı bir proje ile bir dosya açıldığında, ortam sonunda uygun Düzenleyicisi'ni ya da bu dosya için tasarımcı açma, bir yoklama süreci başlatılır. Standart ve özel düzenleyiciler ortamı tarafından işe ilk yordamı aynıdır. Hangi Düzenleyicisi'ni kullanarak bir dosyayı açmak için yoklama zaman ortamı çeşitli ölçütleri kullanır ve VSPackage ortamıyla bu işlem sırasında koordine gerekir.  
  
 Örneğin, bir kullanıcı seçtiğinde **açık** komutunu **dosya** menüsünde ve ardından seçer `filename`.rtf (veya başka bir dosya .rtf uzantılı) ortam çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> Çözümdeki tüm proje örnekleri sonunda dolaşma her proje için uygulaması. Projeleri Talep belgesinde öncelik sırasına göre tanımlamak bayrakları bir dizi döndürür. En yüksek öncelik, ortam uygun çağrılarını kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> yöntemi. Yoklama işlemi hakkında daha fazla bilgi için [ekleme proje ve proje öğesi şablonları](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
 Çeşitli dosyalar proje diğer projeler tarafından talep edilmeyen tüm dosyaları talepleri. Standart düzenleyicileri açmadan önce bu şekilde, özel düzenleyiciler belgeleri açabilirsiniz. Çeşitli dosyalar proje dosya talepleri, ortam çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> yöntemi dosyayı standart düzenleyiciyle açın. Ortam .rtf dosyaları işleyen bir kayıtlı düzenleyicileri, iç listesini denetler. Bu liste, aşağıdaki anahtarı kayıt bulunur:  
  
 [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\<`version`> \Editors\\{<`editor factory guid`>} \Extensions]  
  
 Ortamında, ayrıca HKEY_CLASSES_ROOT\CLSID anahtarının alt anahtar DocObject sahip herhangi bir nesne için sınıf tanımlayıcıları denetler. Dosya uzantısı var. bulunursa, Microsoft Word gibi uygulamanın katıştırılmış bir sürümü Visual Studio'da yerinde oluşturulur. Bu belge nesneleri uygulamak bileşik dosyalar olmalıdır <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage> arabirimi veya nesne uygulanmalı <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> arabirimi.  
  
 Kayıt defterinde .rtf dosyaları için bir editor fabrikası sonra ortamı HKEY_CLASSES_ROOT arar \\.rtf anahtar ve düzenleyici belirtilen var. açar. Dosya uzantısı içinde HKEY_CLASSES_ROOT bulunmazsa, ortam bir metin dosyası ise, dosyayı açmak için Visual Studio çekirdek metin Düzenleyicisi'ni kullanır.  
  
 Temel metin düzenleyici başarısız olursa, dosyayı bir metin dosyası değil, ortam dosyası İkili Düzenleyicisi sonra kullanır oluşur.  
  
 Ortam .rtf uzantısı, kayıt defterinde bir düzenleyici bulamazsa, bu Düzenleyici üreteci uygulayan VSPackage yükler. Ortam çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> yeni VSPackage yöntemi. VSPackage çağrıları `QueryService` için `SID_SVsRegistorEditor`kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> Düzenleyici üreteci ortamı ile kaydetmek için yöntem.  
  
 Ortam şimdi henüz kaydettiğimiz Düzenleyici üreteci için .rtf dosyaları bulmak için kayıtlı Düzenleyicileri'nin iç listesi yeniden denetler. Uygulamanıza ortamı çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> oluşturmak için dosya adını ve görünümü türü olarak geçirme yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>   
 <xref:Microsoft.VisualStudio.OLE.Interop.IPersistStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>