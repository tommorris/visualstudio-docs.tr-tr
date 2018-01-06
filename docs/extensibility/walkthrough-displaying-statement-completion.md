---
title: "İzlenecek yol: Deyim tamamlama görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - statement completion
ms.assetid: f3152c4e-7673-4047-a079-2326941d1c83
caps.latest.revision: "36"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d9c3b44bd46c34a864896cbf1002505085be5143
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-statement-completion"></a>İzlenecek yol: Deyim tamamlama görüntüleme
Dil tabanlı deyim tamamlama, tamamlama sağlamak istediğiniz tanımlayıcıları tanımlama ve ardından bir tamamlanma oturumu tetikleme uygulayabilirsiniz. Deyim tamamlama dil hizmeti bağlamında tanımlayabilir, kendi dosya adı uzantısı ve içerik türünü tanımlayın ve yalnızca bu tür için tamamlama görüntülemek ya da mevcut bir içerik türü için tamamlama tetikleyebilir — Örneğin, "düz metin". Bu kılavuz, içerik türü metin dosyaları olan "düz metin" içerik türü için ifade tamamlama tetiklemek gösterilmiştir. Kod ve XML dosyaları dahil olmak üzere tüm diğer içerik türleri, üst "metin" içerik türü değil.  
  
 Deyim tamamlama, belirli karakterler yazarak genellikle tetiklenir — Örneğin, "kullanarak" gibi bir tanımlayıcı yazmaya tarafından. Bu genellikle bir seçim yapılması için boşluk, sekme ya da Enter tuşuna basarak kapatılır. Tuş vuruşları için bir komut işleyici kullanarak bir karakter yazarak tetiklenen IntelliSense özellikleri uygulayabilirsiniz ( <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi) ve gerçekleştiren bir işleyici sağlayıcı <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> arabirimi. Tamamlanmasında katılmak tanımlayıcıları listesidir, tamamlama kaynak oluşturmak için uygulaması <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource> arabirimi ve tamamlanma kaynak sağlayıcısı ( <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider> arabirimi). Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni bölümleri sağlayıcılarıdır. Kaynak ve denetleyici sınıfları dışarı aktarma ve Hizmetleri ve aracıların alma sorumlu — Örneğin, <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, metin arabelleği gezinti sağlar ve <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>, tamamlama oturum tetikler.  
  
 Bu kılavuz, sabit kodlanmış bir tanımlayıcıları Kümesi için ifade tamamlama uygulamak gösterilmiştir. Tam uygulamalarında dil hizmeti ve dil belgelerine içerik sağlamak için sorumludur.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Bir MEF projesi oluşturma  
  
#### <a name="to-create-a-mef-project"></a>Bir MEF projesi oluşturmak için  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `CompletionTest`.  
  
2.  Bir düzenleyici sınıflandırıcı öğe şablonu projeye ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
4.  Proje için aşağıdaki başvuruları ekleyin ve olduğundan emin olun **CopyLocal** ayarlanır `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
     Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.Shell.Immutable.10.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
## <a name="implementing-the-completion-source"></a>Tamamlama kaynağı uygulama  
 Tamamlama kaynak tanımlayıcıları kümesini toplamak ve bir kullanıcı bir tanımlayıcı ilk harfini gibi tamamlama tetikleyicinin yazdığında içerik tamamlama penceresine ekleme sorumludur. Bu örnekte, sabit kodlanmış tanımlayıcıları ve açıklamalarının <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource.AugmentCompletionSession%2A> yöntemi. Çoğu gerçek kullanır, tamamlanma listesini doldurmak için belirteçleri almak için dilinizi 's ayrıştırıcı kullanırsınız.  
  
#### <a name="to-implement-the-completion-source"></a>Tamamlama kaynak uygulamak için  
  
1.  Bir sınıf dosyası ekleyin ve adını `TestCompletionSource`.  
  
2.  Bu içeri aktarmaları ekleyin:  
  
     [!code-csharp[VSSDKCompletionTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_1.cs)]
     [!code-vb[VSSDKCompletionTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_1.vb)]  
  
3.  Sınıf bildirimi değiştirme `TestCompletionSource` böylece bunu uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource>:  
  
     [!code-csharp[VSSDKCompletionTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_2.cs)]
     [!code-vb[VSSDKCompletionTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_2.vb)]  
  
4.  Kaynak sağlayıcısı, metin arabelleği ve bir listesi için özel alanlar ekleyin <xref:Microsoft.VisualStudio.Language.Intellisense.Completion> (tamamlama oturumunda katılacak tanımlayıcıları karşılık gelir) nesneler:  
  
     [!code-csharp[VSSDKCompletionTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_3.cs)]
     [!code-vb[VSSDKCompletionTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_3.vb)]  
  
5.  Kaynak sağlayıcısı ve arabellek ayarlar bir oluşturucu ekleyin. `TestCompletionSourceProvider` Sınıfı, sonraki adımlarda tanımlanır:  
  
     [!code-csharp[VSSDKCompletionTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_4.cs)]
     [!code-vb[VSSDKCompletionTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_4.vb)]  
  
6.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource.AugmentCompletionSession%2A> bağlamda sağlamak istediğiniz tamamlamalar içeren bir tamamlanma kümesi ekleyerek yöntemi. Bir dizi her tamamlama kümesi içeren <xref:Microsoft.VisualStudio.Language.Intellisense.Completion> tamamlamalar ve tamamlanma penceresi seçeneğine karşılık gelir. (Visual Basic projelerinde tamamlama penceresi sekmeleri adlı **ortak** ve **tüm**.) FindTokenSpanAtPosition yöntemi sonraki adımda tanımlanır.  
  
     [!code-csharp[VSSDKCompletionTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_5.cs)]
     [!code-vb[VSSDKCompletionTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_5.vb)]  
  
7.  Aşağıdaki yöntem, geçerli imleç konumu Word'den bulmak için kullanılır:  
  
     [!code-csharp[VSSDKCompletionTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_6.cs)]
     [!code-vb[VSSDKCompletionTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_6.vb)]  
  
8.  Uygulama `Dispose()` yöntemi:  
  
     [!code-csharp[VSSDKCompletionTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_7.cs)]
     [!code-vb[VSSDKCompletionTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_7.vb)]  
  
## <a name="implementing-the-completion-source-provider"></a>Tamamlama kaynak sağlayıcıyı uygulama  
 Tamamlama kaynak sağlayıcısı tamamlama kaynak başlatır MEF Bileşeni parçasıdır.  
  
#### <a name="to-implement-the-completion-source-provider"></a>Tamamlama kaynak sağlayıcısını uygulamak için  
  
1.  Adlı bir sınıf ekleyin `TestCompletionSourceProvider` uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider>. Bu sınıfla verme bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "düz metin" olarak ve bir <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "test tamamlanma".  
  
     [!code-csharp[VSSDKCompletionTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_8.cs)]
     [!code-vb[VSSDKCompletionTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_8.vb)]  
  
2.  İçeri aktarma bir <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, geçerli sözcüğü tamamlama kaynak bulmak için kullanılır.  
  
     [!code-csharp[VSSDKCompletionTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_9.cs)]
     [!code-vb[VSSDKCompletionTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_9.vb)]  
  
3.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider.TryCreateCompletionSource%2A> tamamlama kaynak örneği oluşturmak için yöntem.  
  
     [!code-csharp[VSSDKCompletionTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_10.cs)]
     [!code-vb[VSSDKCompletionTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_10.vb)]  
  
## <a name="implementing-the-completion-command-handler-provider"></a>Tamamlama komut işleyici sağlayıcıyı uygulama  
 Tamamlama komut işleyici sağlayıcısı türetilmiş bir <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener>, bir metin görünümü oluşturma olayını dinler ve görünümden dönüştürür bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>— Visual Studio Kabuğu komut zinciri komutuna eklenmesi sağlayan — bir için<xref:Microsoft.VisualStudio.Text.Editor.ITextView>. Bu sınıf bir MEF export olduğundan, ayrıca bu komut işleyici kendisi tarafından gerekli hizmetleri almak için kullanabilirsiniz.  
  
#### <a name="to-implement-the-completion-command-handler-provider"></a>Tamamlama komut işleyici sağlayıcısını uygulamak için  
  
1.  Adlı bir dosya eklemek `TestCompletionCommandHandler`.  
  
2.  Bunlar using deyimlerini ekleyin:  
  
     [!code-csharp[VSSDKCompletionTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_11.cs)]
     [!code-vb[VSSDKCompletionTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_11.vb)]  
  
3.  Adlı bir sınıf ekleyin `TestCompletionHandlerProvider` uygulayan <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener>. Bu sınıfla verme bir <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "belirteci tamamlama işleyicisinin" bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "düz metin" olarak ve bir <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> , <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Editable>.  
  
     [!code-csharp[VSSDKCompletionTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_12.cs)]
     [!code-vb[VSSDKCompletionTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_12.vb)]  
  
4.  İçeri aktarma <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>, dönüştürme sağlayan bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>, <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>ve bir <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> standart Visual Studio hizmetlerine erişim sağlar.  
  
     [!code-csharp[VSSDKCompletionTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_13.cs)]
     [!code-vb[VSSDKCompletionTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_13.vb)]  
  
5.  Uygulama <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener.VsTextViewCreated%2A> komut işleyici örneği oluşturmak için yöntem.  
  
     [!code-csharp[VSSDKCompletionTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_14.cs)]
     [!code-vb[VSSDKCompletionTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_14.vb)]  
  
## <a name="implementing-the-completion-command-handler"></a>Tamamlama komut işleyici uygulama  
 Deyim tamamlama tamamlayarak tetiklendiğinden uygulamalıdır <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> almak ve tetiklemek, yürütme ve tamamlanma oturumu kapatmak tuş vuruşları işlemek için arabirim.  
  
#### <a name="to-implement-the-completion-command-handler"></a>Tamamlama komut işleyici uygulamak için  
  
1.  Adlı bir sınıf ekleyin `TestCompletionCommandHandler` uygulayan <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>:  
  
     [!code-csharp[VSSDKCompletionTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_15.cs)]
     [!code-vb[VSSDKCompletionTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_15.vb)]  
  
2.  (Olduğu geçirdiğiniz komutu) sonraki komut işleyici, metin görünümü, (çeşitli hizmetlere erişim sağlayan) komut işleyici sağlayıcısı için özel alanlar ekleyin ve tamamlanma oturum:  
  
     [!code-csharp[VSSDKCompletionTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_16.cs)]
     [!code-vb[VSSDKCompletionTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_16.vb)]  
  
3.  Metin görünümü ve sağlayıcı alanları ayarlar ve komut zinciri komutu ekleyen bir oluşturucu ekleyin:  
  
     [!code-csharp[VSSDKCompletionTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_17.cs)]
     [!code-vb[VSSDKCompletionTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_17.vb)]  
  
4.  Uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> boyunca komutu geçirerek yöntemi:  
  
     [!code-csharp[VSSDKCompletionTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_18.cs)]
     [!code-vb[VSSDKCompletionTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_18.vb)]  
  
5.  Uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi. Bu yöntem bir tuş vuruşu aldığında, bunlardan birini yapmanız gerekir:  
  
    -   Arabelleğe yazılan ve ardından veya tamamlama filtrelemek karakter izin verir. (Yazdırma karakter bunu.)  
  
    -   Tamamlama yürütme ancak arabelleğe yazılacak karakter izin vermez. (Bir tamamlanma oturumu görüntülendiğinde, boşluk, sekme ve Enter bunu.)  
  
    -   Sonraki işleyicisine geçirilen için komutu izin verir. (Tüm diğer komutlar.)  
  
     Bu yöntem kullanıcı arabirimini görüntüleyen çünkü çağrı <xref:Microsoft.VisualStudio.Shell.VsShellUtilities.IsInAutomationFunction%2A> bir Otomasyon bağlamında çağrılmaz emin olmak için:  
  
     [!code-csharp[VSSDKCompletionTest#19](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_19.cs)]
     [!code-vb[VSSDKCompletionTest#19](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_19.vb)]  
  
6.  Bu kod tamamlama oturum tetikleyen özel bir yöntemdir:  
  
     [!code-csharp[VSSDKCompletionTest#20](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_20.cs)]
     [!code-vb[VSSDKCompletionTest#20](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_20.vb)]  
  
7.  Sonraki örnek alanından işlemleri özel bir yöntemdir <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSession.Dismissed> olay:  
  
     [!code-csharp[VSSDKCompletionTest#21](../extensibility/codesnippet/CSharp/walkthrough-displaying-statement-completion_21.cs)]
     [!code-vb[VSSDKCompletionTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-statement-completion_21.vb)]  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için CompletionTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
#### <a name="to-build-and-test-the-completiontest-solution"></a>Derleme ve CompletionTest çözüm sınamak için  
  
1.  Çözümü oluşturun.  
  
2.  Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
3.  Bir metin dosyası oluşturun ve "Ekle" sözcüğünü içeren belirli bir metin yazın.  
  
4.  "A" ve "d" sonra ilk yazarken, "ekleme" ve "uyarlama" içeren bir liste görüntülenmesi gerekir. Toplama seçildiğini dikkat edin. Başka bir "d" yazdığınızda, listenin "şimdi seçilen yalnızca ek olarak" içermelidir. Boşluk, sekme ya da Enter tuşuna basarak "toplama" yürütün veya Esc veya başka bir anahtar yazarak listesi yok sayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Bir İçerik Türünü Dosya Adı Uzantısına Bağlama](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)