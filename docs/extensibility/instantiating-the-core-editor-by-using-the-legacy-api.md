---
title: "Eski API kullanarak çekirdek Düzenleyici başlatmasını | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - instantiating editor
ms.assetid: dda23b18-96ef-43c6-b0dc-06d15cbe5cbb
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e508bda0b22c798246b0f6abf4dfb03c41a92d6d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="instantiating-the-core-editor-by-using-the-legacy-api"></a>Eski API kullanarak çekirdek Düzenleyici örneği
Düzenleyici metin ekleme, silme, kopyalama ve yapıştırma gibi işlevleri düzenleme sorumludur. Bu işlevler metin renklendirme, girinti ve IntelliSense deyim tamamlama gibi dil Hizmetleri tarafından sağlanan ile birleştirir.  
  
 Çekirdek Düzenleyici'de, üç şekilde örneği örneğini oluşturabilirsiniz:  
  
-   Açıkça çekirdek örneği bir pencerede Düzenleyicisi oluşturun.  
  
-   Çekirdek Düzenleyici örneğini döndüren bir düzenleyici üreteci sağlar  
  
-   Proje hiyerarşiden bir dosyayı açın.  
  
 Aşağıdaki bölümlerde eski API Düzenleyici örneği oluşturmak için nasıl kullanılacağı açıklanmaktadır.  
  
## <a name="explicitly-opening-a-core-editor-instance"></a>Açıkça çekirdek Düzenleyici örneği açma  
 Çekirdek Düzenleyici örneği açıkça edinirken:  
  
-   Elde bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> düzenlenmekte olan belge veri nesnesi tutmak için.  
  
-   Belge veri nesnesi bir satır yönelimli gösterimini oluşturma bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> alanından arabirim <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> arabirimi.  
  
-   Ayarlama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> varsayılan uygulaması örneği için belge veri nesnesi olarak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> arabirimi, kullanılarak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetBuffer%2A> yöntemi.  
  
     Ana bilgisayar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> örneğini bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> kullanarak arabirimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateToolWindow%2A> yöntemi.  
  
 Bu noktada, görüntüleme <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> çekirdek Düzenleyici örneği içeren bir pencere arabirim sağlar.  
  
 Olmamasından kısayol tuşları sahip veya gelişmiş özelliklere erişmek ancak, bu çok kullanışlı bir örneği değil. Kısayol tuşları ve Gelişmiş Özellikler erişim elde etmek için:  
  
-   Kullanım <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> dil hizmeti ve düzenleyici kullanan belge veri nesnesi ilişkilendirilecek yöntemi.  
  
-   Kendi kısayol tuşları oluşturmak ya da sistem varsayılan ayarlayarak kullanın <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> nesnelerin özelliklerini görüntüleme. Bunu yapmak için arama <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetGuidProperty%2A> yöntemiyle <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> özelliği.  
  
     Alın ve standart olmayan kısayol tuşlarını kullanmak için bunları .vsct dosyasını kullanarak oluşturur. Daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="how-to-use-an-editor-factory-to-obtain-the-core-editor"></a>Bir düzenleyici üreteci çekirdek Düzenleyicisi'ni elde etmek için nasıl kullanılacağını  
 Bir çekirdek düzenleyicisi kullanarak bir düzenleyici üreteci ile uygularken <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi, açıkça barındırmak için önceki bölümde özetlendiği tüm adımları bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> kullanarak bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> belge veri nesnesi bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> nesne.  
  
 Metni görüntülemek için elde bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> alanından arabirim <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> nesne ve çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi.  
  
 Düzenleyici bir dil hizmet sağlamak için arama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> yöntemi içinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi.  
  
 Kısayol tuşları, önceki bölümde farklı varsayılan almak için tarafından döndürülen komutu bağlam kullanın <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> çekirdek Düzenleyicisi'nden edinirken yöntemi <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi.  
  
 Varsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> yöntemi döndürür aynı komut GUID olarak metin düzenleyici, çekirdek Düzenleyici örneği varsayılan kısayol tuşları otomatik olarak alır.  
  
 Genel bilgi için bkz: [izlenecek yol: bir çekirdek düzenleyici oluşturma ve bir düzenleyici dosya türü kaydetme](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçinde çekirdek Düzenleyicisi](../extensibility/inside-the-core-editor.md)   
 [Açıp kaydederek proje öğeleri](../extensibility/internals/opening-and-saving-project-items.md)   
 [İzlenecek yol: bir çekirdek düzenleyici oluşturma ve bir düzenleyici dosya türü kaydetme](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)