---
title: "Belge kilit sahibi Yönetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - document locking
ms.assetid: fa1ce513-eb7d-42bc-b6e8-cb2433d051d5
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4bd487bd3f5a6978af9f79eb9e0a00866b5df52
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="document-lock-holder-management"></a>Belge kilit sahibi Yönetimi
Çalıştıran Belge tablosu (RDT) açık belgeler ve sahip oldukları düzenleme kilitleri sayısı tutar. Bu program aracılığıyla arka planda bir belge penceresi açık bir belgede görmesini kullanıcı olmadan düzenlendiğinde RDT belgede bir düzen kilit yerleştirebilirsiniz. Bu işlevsellik, genellikle bir grafik kullanıcı arabirimi aracılığıyla birden çok dosyalarda değişiklik tasarımcıları tarafından kullanılır.  
  
## <a name="document-lock-holder-scenarios"></a>Belge kilit sahibi senaryoları  
  
### <a name="file-a-has-a-dependence-on-file-b"></a>Dosya "a" sahip bir dosya bağımlılığı "b"  
 Dosya türü için bir standart Düzenleyici "A", uygulamadan burada bir durum düşünün "a" ve her dosya türü "a" başvuru (veya bağımlılığı) sahip bir dosya türü "b". Standart Düzenleyici "B", "b" türde dosyaları bulunmaktadır. Düzenleyici "A" dosya açıldığında "a" BT "b" karşılık gelen dosyaya başvuru alır. Dosya "b" görüntülenmez, ancak Düzenleyicisi "A" değiştirebilirsiniz. Düzenleyici "A" alır dosyasının belge verilere bir başvuru "b" den <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> yöntemi ve ayrıca dosya "b" üzerindeki düzenleme kilidi korur. Düzenleyici "A" yapıldıktan sonra "azaltma düzenleme kilit dosyası b" değiştirme saymak dosya "b" çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnlockDocument%2A> yöntemi. Çağrısı yaptığını, bu adımı atlayabilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> yöntemi parametresi ile `dwRDTLockType` kümesine <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>.  
  
### <a name="file-b-is-opened-by-a-different-editor"></a>Dosya "b" tarafından farklı bir düzenleyici açıldığında  
 Düzenleyici "A" açmaya çalıştığında "b" dosyası "B" Düzenleyicisi tarafından açılmış gelmesi durumunda, işlemek için iki ayrı senaryo vardır:  
  
-   Dosya "b" uyumlu bir düzenleyicide açık olduğunda, "dosya"b"kullanarak belgeyi Düzenle kilit kaydetmek Düzenleyicisi A" olmalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.RegisterDocumentLockHolder%2A> yöntemi. "A" düzenleyicinizi değiştirme dosya "b" yapıldıktan sonra kaydı Belgeyi Düzenle Kilitle kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnregisterDocumentLockHolder%2A> yöntemi.  
  
-   Dosya "b" uyumsuz bir biçimde açık olduğunda, "A" başarısız veya "A" kısmen açın ve uygun hata iletisini görüntüler Düzenleyicisi ile ilişkili görünümü sağlayabilirsiniz Düzenleyicisi tarafından ya da dosya "b" denenen açılmasını izin verebilirsiniz. Hata iletisi uyumlu bir düzenleyicide dosya "b" kapatmak ve "a" kullanarak dosyayı yeniden açmak için kullanıcı istemeniz gerekir Düzenleyicisi "A". Ayrıca uygulayabilirsiniz [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] yöntemi <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable2.QueryCloseRunningDocument%2A> uyumlu bir düzenleyicide açık olan dosya "b" kapatmak için kullanıcıdan istemek için. Kullanıcı dosya "b", dosyayı açma kapatırsa "a" içinde Düzenleyicisi "A" normal şekilde devam eder.  
  
## <a name="additional-document-edit-lock-considerations"></a>Ek belge düzenleme kilit dikkat edilecek noktalar  
 Bir belgeyi "b" dosya üzerindeki kilit Düzenleyicisi "B" Ayrıca belge tutuyorsa yaptığınız daha Düzenle sahip yalnızca Düzenleyicisi'ni düzenlemek "b" dosya üzerindeki kilit Düzenleyicisi "A" ise, farklı bir davranış alın. İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **Sınıf Tasarımcısı** bir düzen kilit ilişkili kodu dosyada tutmaz bir görsel tasarımcı örneğidir. Diğer bir deyişle, Tasarım görünümünde açın sınıf diyagramında kullanıcı varsa ve aynı anda ilişkili kod dosyasını açın ve kullanıcı kod dosyası değiştirir ancak değişiklikleri kaydetmeyen değişiklikler de sınıf diyagramı (.cd) dosyasına kaybolur. Varsa **Sınıf Tasarımcısı** sahip yalnızca belge kod dosya üzerindeki kilit düzenleme, kullanıcı kod dosyası kapatılırken değişiklikleri kaydetmek için istenmez. IDE yalnızca kullanıcı kapandıktan sonra değişiklikleri kaydetmek için kullanıcıdan **Sınıf Tasarımcısı**. Kaydedilen değişiklikler, her iki dosyalarında yansıtılır. Her iki **Sınıf Tasarımcısı** ve kullanıcı kod dosyası veya formun kapatırken kaydetmek için istemde sonra kod dosyası Düzenleyicisi belge düzenleme kilitleri kod dosyada tutulur.. Bu noktada değişiklikleri kaydedildi form ve kod dosyası içinde yansıtılır. Sınıf diyagramları hakkında daha fazla bilgi için bkz: [(Sınıf Tasarımcısı) Sınıf diyagramları ile çalışma](../ide/working-with-class-diagrams-class-designer.md).  
  
 Bir belge Düzenleyicisi olmayan bir düzen kilit Yerleştir gerekiyorsa, uygulamanız gereken Not <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> arabirimi.  
  
 Kod dosyaları programlı olarak değiştiren birçok kez bir UI Tasarımcısı için birden fazla dosya değişiklikleri yapar. Bu gibi durumlarda <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell2.SaveItemsViaDlg%2A> yöntemi işler yoluyla bir veya daha fazla belge kaydetme **şu öğeler için değişiklikleri kaydetmek istiyor musunuz?** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışan belge tablosu](../extensibility/internals/running-document-table.md)   
 [Kalıcılığı ve çalışan belge tablosu](../extensibility/internals/persistence-and-the-running-document-table.md)