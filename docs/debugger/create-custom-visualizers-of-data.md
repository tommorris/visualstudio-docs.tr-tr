---
title: "Veri özel Görselleştiriciler oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 06/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.visualizer.troubleshoot
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers
ms.assetid: c24c006f-f2ac-429f-89db-677fc0c6e1ea
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 23985c56ba61e5a788232523611a48cfde902335
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="create-custom-visualizers-of-data"></a>Özel Görselleştiriciler veri oluşturma
 Görselleştiriciler olan bileşenleri [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] hata ayıklayıcı kullanıcı arabirimi. A *görselleştiricisi* bir iletişim kutusu veya bir değişken veya nesne veri türü için uygun bir şekilde görüntülemek için başka bir arabirim oluşturur. Örneğin, bir HTML Görselleştirici bir HTML dizesi olarak yorumlar ve sonucu bir tarayıcı penceresinde görüneceği şekilde görüntüler; bit eşlem Görselleştirici bir bit eşlem yapısı yorumlar ve onu gösteren grafiği görüntüler. Bazı görselleştiriciler yanı sıra değiştirme verileri görüntülemek etkinleştirin.

 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] Hata ayıklayıcı altı standart görselleştiriciler içerir. Metin, HTML, XML ve JSON görselleştiriciler tümü dize nesneler üzerinde çalışır, bunlar; bir WPF nesne görsel ağaç özelliklerini görüntülemek için WPF ağacı görselleştiricisini, ve veri kümesi, DataView ve DataTable nesneleri için çalışır veri kümesi görselleştiricisi. Ek görselleştiriciler gelecekte Microsoft Corporation'ın İndirilebilecek olabilir ve Üçüncü taraflardan ve topluluk kullanılabilir. Ayrıca, kendi görselleştiriciler yazmak ve bunları yüklemek [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] hata ayıklayıcı.

 > [!NOTE]
 > Yerel kod için özel Görselleştirici oluşturmak için bkz: [SQLite yerel hata ayıklayıcı Görselleştirici](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/SqliteVisualizer) örnek. UWP ve Windows 8.x uygulamalarında özel görselleştiriciler desteklenmez.

 Hata Ayıklayıcısı'ndaki görselleştiriciler Büyüteç simgesini tarafından temsil edilen ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi"). Büyüteç simgesini gördüğünüzde bir **DataTip**, bir hata ayıklayıcı penceresinde **izleme** penceresinde veya **QuickWatch** iletişim kutusu için Büyüteç tıklatabilirsiniz karşılık gelen nesne veri türü için uygun Görselleştirici seçin.

## <a name="overview-of-custom-visualizers"></a>Özel görselleştiriciler genel bakış

Herhangi bir yönetilen sınıf dışında bir nesne için özel Görselleştirici yazma <xref:System.Object> veya <xref:System.Array>.  
  
 Hata ayıklayıcı Görselleştirici mimarisi iki bölümden oluşur:  
  
-   *Hata ayıklayıcı yan* Visual Studio hata ayıklayıcısı içinde çalışır. Hata ayıklayıcı tarafı kod oluşturur ve sizin Görselleştirici için kullanıcı arabirimi görüntüler.  
  
-   *Ayıklayıcı yan* Visual Studio hata ayıklama işlemi içinde çalıştırılan ( *ayıklayıcı*).  
  
 (Bir dize nesnesi, örneğin gibi) görselleştirmek için istediğiniz veri nesnesi ayıklayıcı işleminde bulunmaktadır. Bu nedenle, bu veri nesnesi daha sonra oluşturduğunuz kullanıcı arabirimini kullanarak görüntüleyebilirsiniz hata ayıklayıcı tarafa göndermek ayıklayıcı yan sahiptir.  
  
 Hata ayıklayıcı yan gelen görselleştirilen için bu veri nesnesi alır bir *nesne sağlayıcısı* uygulayan <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> arabirimi. Üzerinden veri nesnesine ayıklayıcı yan gönderir *nesne kaynak*, türetilen <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>. Nesne sağlayıcı veri sağlayan görüntüler yanı sıra düzenler bir Görselleştirici yazma, nesne kaynak verileri yedekleyin de gönderebilirsiniz. İfade değerlendirici ve, bu nedenle, nesne kaynak konuşmaya nesne sağlayıcısı geçersiz kılınabilir  
  
 Başka ayıklayıcı yan ve hata ayıklayıcı tarafı iletişim <xref:System.IO.Stream>. Yöntemler, bir veri nesnesine serileştirmek için sağlanan bir <xref:System.IO.Stream> ve seri durumdan <xref:System.IO.Stream> yeniden içine bir veri nesnesi.  
  
 Ayıklayıcı tarafı kodu DebuggerVisualizer özniteliği kullanılarak belirtilir (<xref:System.Diagnostics.DebuggerVisualizerAttribute>).  
  
 Hata ayıklayıcı tarafında Görselleştirici kullanıcı arabirimi oluşturmak üzere öğesinden devralınan bir sınıf oluşturun <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> ve geçersiz kılma <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> arabirimi görüntülenecek yöntemi.  
  
 Kullanabileceğiniz <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> Windows forms iletişim kutuları ve, Görselleştirici denetimlerden görüntülemek için.  
  
 Genel türler için destek sınırlıdır. Yalnızca genel tür açık bir tür ise genel bir tür bir hedef için Görselleştirici yazabilirsiniz. Bu kısıtlama kısıtlama kullanırken aynıdır `DebuggerTypeProxy` özniteliği. Ayrıntılar için bkz [DebuggerTypeProxy özniteliğini kullanarak](../debugger/using-debuggertypeproxy-attribute.md).  
  
 Özel görselleştiriciler güvenlik konuları olabilir. Bkz: [Görselleştirici güvenlik konuları](../debugger/visualizer-security-considerations.md).  
  
 Aşağıdaki yordamlar, Görselleştirici oluşturmak için yapmanız gerekenler üst düzey bir görünümünü verir. Daha ayrıntılı bir açıklaması için bkz: [izlenecek yol: C# ile Görselleştirici yazma](../debugger/walkthrough-writing-a-visualizer-in-csharp.md).  
  
### <a name="to-create-the-debugger-side"></a>Hata ayıklayıcı yan oluşturmak için  
  
1.  Kullanım <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider> hata ayıklayıcı tarafında görselleştirilmiş nesnesini almak için yöntemleri.  
  
2.  Öğesinden devralınan bir sınıf oluşturun <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>.  
  
3.  Geçersiz kılma <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer.Show%2A?displayProperty=fullName> Arabiriminizin görüntülenecek yöntemi. Kullanım <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> Windows forms iletişim kutuları ve denetimleri Arabiriminizin bir parçası olarak görüntülenecek yöntemleri.  
  
4.  Uygulama <xref:System.Diagnostics.DebuggerVisualizerAttribute>, Görselleştirici vermiş (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>).  
  
### <a name="to-create-the-debuggee-side"></a>Ayıklayıcı yan oluşturmak için  
  
1.  Uygulama <xref:System.Diagnostics.DebuggerVisualizerAttribute>, Görselleştirici vermiş (<xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer>) ve bir nesne kaynak (<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>). Bir varsayılan nesne kaynak nesne kaynak atlarsanız, kullanılır.  
  
2.  Veri nesneleri düzenleyebilir, Görselleştirici istiyorsanız de bunları görüntüleme gibi geçersiz kılmak gerekir `TransferData` veya `CreateReplacementObject` yöntemleri <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource>.   
  
## <a name="in-this-section"></a>Bu Bölümde
  
 [İzlenecek yol: Görselleştirici C# ile yazma](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)  

 [İzlenecek yol: Visual Basic'de Görselleştirici yazma](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)  
  
 [Nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md)  
  
 [Nasıl yapılır: Test ve hata ayıklama Görselleştirici](../debugger/how-to-test-and-debug-a-visualizer.md)  
  
 [Görselleştirici API Başvurusu](../debugger/visualizer-api-reference.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Görünüm verilerini hata ayıklayıcı](../debugger/viewing-data-in-the-debugger.md)