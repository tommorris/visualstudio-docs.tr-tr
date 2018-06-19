---
title: Standart bir belgeyi kaydetmeyi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], saving standard documents
- projects [Visual Studio SDK], saving standard documents
- persistence, saving standard documents
ms.assetid: d692fedf-b46e-4d60-84bd-578635042235
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 45fa2c5acfad8195ed2853d7e21413b77262a6b4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132795"
---
# <a name="saving-a-standard-document"></a>Standart belgeyi kaydetme
Ortam Kaydet, Farklı Kaydet ve Tümünü Kaydet komutları işler. Bir kullanıcı seçtiğinde **kaydetmek**, **Kaydet**, veya **Tümünü Kaydet** gelen **dosya** menü ya da sonuçta çözüm kapatır bir  **Tümünü Kaydet**, aşağıdaki süreç gerçekleşir.  
  
 ![Standart Düzenleyici](../../extensibility/internals/media/public.gif "ortak")  
Kaydet Kaydet ve Tümünü Kaydet komut için standart bir düzenleyici işleme  
  
 Bu işlem aşağıdaki adımlarda ayrıntılı olarak açıklanmıştır:  
  
1.  Zaman **kaydetmek** ve **Kaydet** komutları seçildi, ortamı kullanır <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> etkin belge penceresini belirlemek için hizmet ve böylece hangi öğeler kaydedilmelidir. Etkin belge penceresini bilinen sonra ortamı öğe tanımlayıcısı (ItemId) ve hiyerarşi işaretçi çalışan belge tablosu belgede bulur. Daha fazla bilgi için bkz: [çalıştıran Belge tablosu](../../extensibility/internals/running-document-table.md).  
  
     Zaman **Tümünü Kaydet** komutu seçildiğinde, ortam bilgileri kaydetmek için tüm öğeleri listesi derlemek için çalışan belge tablosunda kullanır.  
  
2.  Çözümü zaman alan bir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> çağrısı, seçilen öğeleri kümesi içinde tekrarlanan (tarafından sunulan başka bir deyişle, birden çok seçimin <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> hizmet).  
  
3.  Seçilen her bir öğede çözüm çağırmak için hiyerarşi işaretçisi kullanır <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> belirlemek amacıyla yöntemi olup olmadığını **kaydetmek** menü komutu etkinleştirilmesi gerekir. Bir veya daha fazla öğe kirli olarak varsa sonra **kaydetmek** komutu etkindir. Hiyerarşi Standart Düzenleyici kullanıyorsa, ardından sorgulanırken hiyerarşi temsilciler Düzenleyicisi durumuna çağırarak kirli <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> yöntemi.  
  
4.  Kirli her seçili öğeye bağlı, çözüm çağırmak için hiyerarşi işaretçisi kullanır <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> uygun hiyerarşileri yöntemi.  
  
     Belgeyi düzenlemek için bir standart Düzenleyicisi'ni kullanmak hiyerarşi için yaygın bir durumdur. Bu durumda, bu Düzenleyicisi'ni desteklemesi gereken için belge veri nesnesi <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> arabirimi. Alma sırasında <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> yöntem çağrısı proje bildirin. belge çağırarak kaydedilmekte olduğu Düzenleyicisi'ni <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.SaveDocData%2A> belge veri nesnesi üzerinde yöntemi. Düzenleyici işlemek için ortamı izin verebilir **Kaydet** çağırarak iletişim kutusu, `Query Service` için <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> arabirimi. Bu bir işaretçi döndürür <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> arabirimi. Düzenleyici sonra çağırmalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A> yöntemi, bir işaretçi düzenleyicinin geçirme <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> uygulama yoluyla `pPersistFile` parametresi. Ortam daha sonra kaydetme işlemi gerçekleştirir ve sağlar **Kaydet** Düzenleyicisi iletişim kutusu. Ortam sonra geri düzenleyiciyle çağrılar <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>.  
  
5.  Kullanıcı adsız bir belge (diğer bir deyişle, daha önce kaydedilmemiş bir belge) kaydetmeye çalışıyor, Farklı Kaydet komut gerçekte gerçekleştirilir.  
  
6.  Farklı Kaydet komutu için kullanıcıdan bir dosya adı için Farklı Kaydet iletişim kutusunda, ortam görüntüler.  
  
     Dosya adının değişip sonra bilgilerini çağırarak önbelleğe alma belge çerçeve güncelleştirmek için hiyerarşi sorumludur <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A>(VSFPROPID_MkDocument).  
  
 Varsa **Kaydet** komutu belgesinin konumunu taşır ve hiyerarşi belge konuma duyarlıdır ve ardından hiyerarşi devre dışı açık belge penceresine sahipliğini başka bir hiyerarşiye teslim etme için sorumludur. Örneğin, dosyayı proje ile ilgili bir iç veya dış dosyası (çeşitli) olup proje izliyorsa bu oluşur. Çeşitli dosyalar projesine bir dosya sahipliğini değiştirmek için aşağıdaki yordamı kullanın.  
  
## <a name="changing-file-ownership"></a>Dosya sahipliğini değiştirme  
  
#### <a name="to-change-file-ownership-to-the-miscellaneous-files-project"></a>Çeşitli dosyalar projesine dosya sahipliğini değiştirmek için  
  
1.  Hizmeti için sorgu <xref:Microsoft.VisualStudio.Shell.Interop.SVsExternalFilesManager> arabirimi.  
  
     Bir işaretçi <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2> döndürülür.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2.TransferDocument%2A> (`pszMkDocumentNew`, `punkWindowFrame`) yeni hiyerarşiye belge aktarım yöntemi. Farklı Kaydet komut kullanıldığında hiyerarşi bu yöntemi çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [Proje Öğelerini Açma ve Kaydetme](../../extensibility/internals/opening-and-saving-project-items.md)