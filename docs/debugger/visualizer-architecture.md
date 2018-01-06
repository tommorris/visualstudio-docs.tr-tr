---
title: "Görselleştirici mimarisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 6aad395f-7170-4d9e-b2b8-a5faf453380e
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d2cf2e4b68ba8902d5b93935ea188243fb36d68f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="visualizer-architecture"></a>Görselleştirici Mimarisi
Hata ayıklayıcı Görselleştirici mimarisi iki bölümden oluşur:  
  
-   *Hata ayıklayıcı yan* Visual Studio hata ayıklayıcısı içinde çalışır. Hata ayıklayıcı tarafı kod oluşturur ve sizin Görselleştirici için kullanıcı arabirimi görüntüler.  
  
-   *Ayıklayıcı yan* Visual Studio hata ayıklama işlemi içinde çalıştırılan ( *ayıklayıcı*).  
  
 Görselleştirici görüntülenecek hata ayıklayıcı sağlayan bir hata ayıklayıcı bileşenidir (*görselleştirmek*) bir veri nesnesi anlamlı, anlaşılır formunda içeriğini. Bazı görselleştiriciler veri nesnesi de düzenlemeyi destekler. Özel görselleştiriciler yazarak, kendi özel veri türleri işlemek için hata ayıklayıcı genişletebilirsiniz.  
  
 Görselleştirilen için veri nesnesi ayıkladığınız sürecine dahil ( *ayıklayıcı* işlem). Verileri görüntüler kullanıcı arabirimi, Visual Studio hata ayıklayıcı işlem içinde oluşturulur:  
  
|Hata ayıklayıcı işlem|Ayıklayıcı işlem|  
|----------------------|----------------------|  
|Kullanıcı Arabirimi (DataTips, Gözcü penceresi QuickWatch) hata ayıklayıcı|Veri nesnesi görselleştirilen|  
  
 Hata ayıklayıcı arabiriminden veri nesnesi görselleştirmek için iki işlemler arasında iletişim kurmak için kod gerekir. Sonuç olarak, Görselleştirici mimarisi iki bölümden oluşur: *hata ayıklayıcı yan* kod ve *ayıklayıcı yan* kodu.  
  
 Hata ayıklayıcı arabiriminden bir DataTip, Gözcü penceresi veya QuickWatch gibi çağrılan kendi kullanıcı arabirimi hata ayıklayıcı tarafı kodu oluşturur. Görselleştirici arabirimi kullanılarak oluşturulan <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> sınıfı ve <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> arabirimi. Tüm Görselleştirici API'leri, DialogDebuggerVisualizer ve IDialogVisualizerService bulunan gibi <xref:Microsoft.VisualStudio.DebuggerVisualizers> ad alanı.  
  
|Hata ayıklayıcı yan|Ayıklayıcı yan|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer sınıfı<br /><br /> IDialogVisualizerService arabirimi|Veri nesnesi|  
  
 Kullanıcı arabirimi hata ayıklayıcı tarafında var olan bir nesne sağlayıcısı, görselleştirilen için verileri alır:  
  
|Hata ayıklayıcı yan|Ayıklayıcı yan|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer sınıfı<br /><br /> IDialogVisualizerService arabirimi|Veri nesnesi|  
|Nesne sağlayıcısı (uygulayan <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider>)||  
  
 Nesne kaynak adlı ayıklayıcı tarafında karşılık gelen bir nesne yok:  
  
|Hata ayıklayıcı yan|Ayıklayıcı yan|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer sınıfı<br /><br /> IDialogVisualizerService arabirimi|Veri nesnesi|  
|Nesne sağlayıcısı (uygulayan <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider>)|Kaynak nesne (türetilmiş <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>)|  
  
 Nesne sağlayıcısı Görselleştirici UI görselleştirilen nesne verileri sağlar. Nesne sağlayıcı nesne kaynak nesne verilerini alır. Nesne sağlayıcısı ve nesne kaynak nesne verilerini hata ayıklayıcı yan debugee yan arasındaki iletişim için API'ler sağlar.  
  
 Her Görselleştirici görselleştirilen için veri nesnesi almanız gerekir. Aşağıdaki tablo, nesne sağlayıcı ve nesne kaynağı bu amaçla kullanabileceğiniz ilgili API'leri gösterir:  
  
|Nesne sağlayıcısı|Nesne kaynak|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A><br /><br /> —veya—<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A>|  
  
 Nesne sağlayıcısı ya da kullanabilirsiniz bildirim <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A> veya <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>. Her iki API çağrısı sonuçlanıyor <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A> nesne kaynağı. Çağrı <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A?displayProperty=fullName> doldurur bir <xref:System.IO.Stream?displayProperty=fullName>, görselleştirilen nesnenin seri hale getirilmiş bir formu temsil eder.  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName>Forma sonra ile oluşturduğunuz kullanıcı arabiriminde görüntüleyebilen geri nesnesi, verileri seri durumdan çıkarır <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>. <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName>bir ham verileri doldurur `Stream`, hangi kendiniz seri durumdan gerekir. <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName>çalışır çağırarak <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName> serileştirilmiş almak için `Stream`, verileri seri durumdan sonra. Kullanım <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName> zaman nesne tarafından .NET seri hale getirilebilir değil ve özel seri hale getirme gerektirir. Bu durumda, ayrıca geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.Serialize%2A?displayProperty=fullName> yöntemi.  
  
 Oluşturmakta olduğunuz, salt okunur Görselleştirici, tek yönlü iletişim <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A> veya <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A> yeterlidir. Veri nesnelerini düzenleme destekleyen Görselleştirici oluşturuyorsanız, daha fazla yapmanız gerekir. Nesne kaynak nesne Sağlayıcısı'ndan bir veri nesnesi da Gönder olması gerekir. Aşağıdaki tabloda, nesne kaynak bu amaç için kullanılan API'leri ve nesne sağlayıcısı gösterilmektedir:  
  
|Nesne sağlayıcısı|Nesne kaynak|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A><br /><br /> —veya—<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>|  
  
 Yeniden nesne sağlayıcısı kullanabileceğiniz iki API'leri olduğuna dikkat edin. Verileri her zaman gönderildiği nesne Sağlayıcısı'ndan nesnesi kaynağı olarak bir `Stream`, ancak <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A> nesnesine seri hale gerektiren bir `Stream` kendiniz.  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A>sağlarsanız, nesne bir içine serileştiren bir `Stream`, daha sonra çağırır <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A> göndermek için `Stream` için <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>.  
  
 Değiştir yöntemlerden birini kullanarak yeni bir veri nesnesi görselleştirilen nesnenin yerini ayıklayıcı içinde oluşturur. Özgün nesne içeriğini değiştirme olmadan değiştirmek istiyorsanız, aşağıdaki tabloda gösterilen aktarımı yöntemlerden birini kullanın. Bu API'leri görselleştirilen nesne değiştirmeden aynı anda iki yönde de veri aktarın:  
  
|Nesne sağlayıcısı|Nesne kaynak|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferData%2A><br /><br /> —veya—<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.TransferData%2A>|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Görselleştirici yazma](../debugger/how-to-write-a-visualizer.md)   
 [İzlenecek yol: Görselleştirici C# ile yazma](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [İzlenecek yol: Visual Basic'de Görselleştirici yazma](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [İzlenecek yol: Visual Basic'de Görselleştirici yazma](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [Görselleştirici güvenlik konuları](../debugger/visualizer-security-considerations.md)