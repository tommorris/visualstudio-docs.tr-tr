---
title: 'İzlenecek yol: İmza Yardım görüntüleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - signature help/parameter info
ms.assetid: 4a6a884b-5730-4b54-9264-99684f5b523c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a714fdb268f44fd2a65d04184d899ced3de53bb9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-displaying-signature-help"></a>İzlenecek yol: İmza Yardım görüntüleme
İmza Yardım (olarak da bilinen *parametre bilgisi*) kullanıcı parametre listesi başlangıç karakteri (genellikle bir açma ayracı) yazdığında bir yöntem imzası ipucunda görüntüler. Bir parametre ve parametre ayırıcı (genellikle bir virgül) yazılan gibi araç ipucu sonraki parametrenin kalın olarak göstermek üzere güncelleştirilir. Bir dil hizmeti bağlamında imza yardımcı tanımlayabilirsiniz kendi dosya adı uzantısı ve içerik türünü tanımlayın ve yalnızca bu tür için imza Yardımı'nı görüntülemek veya varolan bir içerik türü (örneğin, "metin") için imza Yardım görüntüleyebilirsiniz. Bu kılavuzda "metin" içerik türü için imza Yardımı'nı görüntülemek nasıl gösterir.  
  
 İmza Yardım, belirli bir karakterin, örneğin, yazarak genellikle tetiklenir "(" (açma parantezi) ve başka bir karakter yazarak kapatılır ")" (kapanış parantezi). Tuş vuruşları için bir komut işleyici kullanarak bir karakter yazarak tetiklenen IntelliSense özellikleri uygulanabilir ( <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi) ve gerçekleştiren bir işleyici sağlayıcı <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> arabirimi. İmza Yardımı'na katılmak imzaları listesidir, imza yardımcı kaynak oluşturmak için uygulaması <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource> arabirimi ve gerçekleştiren bir kaynak sağlayıcı <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider> arabirimi. Sağlayıcılar Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni bölümleri ve kaynak ve denetleyici sınıfları dışarı aktarma ve Hizmetleri ve aracıların, örneğin, içeri aktarma sorumlu <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, metin arabelleği gezinmenizi sağlayan ve <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker>, imza Yardım oturumu tetikler.  
  
 Bu kılavuzda, imza yardımcı tanımlayıcıları sabit kodlanmış kümesi için uygulama gösterilmektedir. Tam uygulamalarında dil içeriğin sağlamaktan sorumludur.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Bir MEF projesi oluşturma  
  
#### <a name="to-create-a-mef-project"></a>Bir MEF projesi oluşturmak için  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `SignatureHelpTest`.  
  
2.  Bir düzenleyici sınıflandırıcı öğe şablonu projeye ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
4.  Aşağıdaki başvuruları projeye ekleyin ve emin olun **CopyLocal** ayarlanır `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
     Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
## <a name="implementing-signature-help-signatures-and-parameters"></a>İmza uygulama imzalar ve parametreleri yardımcı olur.  
 İmza yardımcı kaynak uygulayan imzaları dayalı <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature>, her biri uygulamak parametreleri içeren <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>. Tam bir uygulama bu bilgileri dil belgelerinden alınabileceğinden, ancak bu örnekte, sabit kodlanmış imzalar.  
  
#### <a name="to-implement-the-signature-help-signatures-and-parameters"></a>İmza yardımcı imza ve parametreleri uygulamak için  
  
1.  Bir sınıf dosyası ekleyin ve adını `SignatureHelpSource`.  
  
2.  Aşağıdaki içeri aktarmaları ekleyin.  
  
     [!code-vb[VSSDKSignatureHelpTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_1.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_1.cs)]  
  
3.  Adlı bir sınıf ekleyin `TestParameter` uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>.  
  
     [!code-vb[VSSDKSignatureHelpTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_2.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_2.cs)]  
  
4.  Tüm özellikleri ayarlar bir oluşturucu ekleyin.  
  
     [!code-vb[VSSDKSignatureHelpTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_3.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_3.cs)]  
  
5.  Özelliklerini eklemek <xref:Microsoft.VisualStudio.Language.Intellisense.IParameter>.  
  
     [!code-vb[VSSDKSignatureHelpTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_4.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_4.cs)]  
  
6.  Adlı bir sınıf ekleyin `TestSignature` uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature>.  
  
     [!code-vb[VSSDKSignatureHelpTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_5.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_5.cs)]  
  
7.  Bazı özel alanlar ekleyin.  
  
     [!code-vb[VSSDKSignatureHelpTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_6.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_6.cs)]  
  
8.  Alanları ayarlar ve abone bir oluşturucu ekleyin <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> olay.  
  
     [!code-vb[VSSDKSignatureHelpTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_7.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_7.cs)]  
  
9. Bildirme bir `CurrentParameterChanged` olay. Parametrelerden biri imzada kullanıcı doldurur bu olay tetiklenir.  
  
     [!code-vb[VSSDKSignatureHelpTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_8.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_8.cs)]  
  
10. Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.CurrentParameter%2A> şekilde başlatır özelliğini `CurrentParameterChanged` özellik değeri değiştiğinde olay.  
  
     [!code-vb[VSSDKSignatureHelpTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_9.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_9.cs)]  
  
11. Başlatan bir yöntemi ekleme `CurrentParameterChanged` olay.  
  
     [!code-vb[VSSDKSignatureHelpTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_10.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_10.cs)]  
  
12. Geçerli parametre virgül kullanımı sayısı karşılaştırarak hesaplar bir yöntem ekleyin <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.ApplicableToSpan%2A> imza virgül kullanımı sayısı.  
  
     [!code-vb[VSSDKSignatureHelpTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_11.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_11.cs)]  
  
13. Bir olay işleyicisi ekleme <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> çağırır olay `ComputeCurrentParameter()` yöntemi.  
  
     [!code-vb[VSSDKSignatureHelpTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_12.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_12.cs)]  
  
14. Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISignature.ApplicableToSpan%2A> özelliği. Bu özellik tutan bir <xref:Microsoft.VisualStudio.Text.ITrackingSpan> karşılık gelen imza uygulandığı arabelleğinde metin aralık.  
  
     [!code-vb[VSSDKSignatureHelpTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_13.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_13.cs)]  
  
15. Diğer parametreler uygulayın.  
  
     [!code-vb[VSSDKSignatureHelpTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_14.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_14.cs)]  
  
## <a name="implementing-the-signature-help-source"></a>İmza Yardım kaynağı uygulama  
 İmza yardımcı kaynak bilgileri sağlayın imzaları kümesidir.  
  
#### <a name="to-implement-the-signature-help-source"></a>İmza yardımcı kaynak uygulamak için  
  
1.  Adlı bir sınıf ekleyin `TestSignatureHelpSource` uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource>.  
  
     [!code-vb[VSSDKSignatureHelpTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_15.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_15.cs)]  
  
2.  Metin arabelleği bir başvuru ekleyin.  
  
     [!code-vb[VSSDKSignatureHelpTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_16.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_16.cs)]  
  
3.  Metin arabelleği ve imza yardımcı kaynak sağlayıcısı ayarlar bir oluşturucu ekleyin.  
  
     [!code-vb[VSSDKSignatureHelpTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_17.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_17.cs)]  
  
4.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource.AugmentSignatureHelpSession%2A> yöntemi. Bu örnekte, sabit kodlanmış imzalar, ancak tam uygulamasında dil belgelerinden bu bilgiler elde edebileceğiniz.  
  
     [!code-vb[VSSDKSignatureHelpTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_18.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_18.cs)]  
  
5.  Yardımcı yöntemi `CreateSignature()` yalnızca çizim için sağlanmıştır.  
  
     [!code-vb[VSSDKSignatureHelpTest#19](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_19.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#19](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_19.cs)]  
  
6.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource.GetBestMatch%2A> yöntemi. Bu örnekte, yalnızca iki imzalar, her biri iki parametreye sahip vardır. Bu nedenle, bu yöntem gerekli değildir. Birden fazla imza yardımcı kaynak kullanılabilir olduğu daha eksiksiz bir uygulamasında bu yöntem, en yüksek öncelikli imza yardımcı kaynak eşleşen imza sağlayabilir karar vermek için kullanılır. Başaramazsa yöntemi null değerini döndürür ve next-en yüksek öncelikli kaynak bir eşleşme sağlamanız istenir.  
  
     [!code-vb[VSSDKSignatureHelpTest#20](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_20.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#20](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_20.cs)]  
  
7.  Dispose() yöntemini uygulayın:  
  
     [!code-vb[VSSDKSignatureHelpTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_21.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#21](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_21.cs)]  
  
## <a name="implementing-the-signature-help-source-provider"></a>İmza Yardım kaynak sağlayıcıyı uygulama  
 İmza yardımcı kaynak sağlayıcısı, Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni bölümü dışarı aktarma ve imza yardımcı kaynak başlatmasını sorumludur.  
  
#### <a name="to-implement-the-signature-help-source-provider"></a>İmza yardımcı kaynak sağlayıcısını uygulamak için  
  
1.  Adlı bir sınıf ekleyin `TestSignatureHelpSourceProvider` uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider>ve onunla verme bir <xref:Microsoft.VisualStudio.Utilities.NameAttribute>, <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "metin" ve bir <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> , önce = "varsayılan".  
  
     [!code-vb[VSSDKSignatureHelpTest#22](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_22.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#22](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_22.cs)]  
  
2.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider.TryCreateSignatureHelpSource%2A> örneği tarafından `TestSignatureHelpSource`.  
  
     [!code-vb[VSSDKSignatureHelpTest#23](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_23.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#23](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_23.cs)]  
  
## <a name="implementing-the-command-handler"></a>Komut işleyici uygulama  
 İmza Yardım tarafından tetiklenen genellikle bir (karakter ve tarafından kapatıldı bir) karakter. Bu tuş vuruşları uygulayarak işleyebilir bir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> zaman alan bir imza yardımcı oturumu tetikler böylece bir (karakter bilinen yöntemi adıyla öncesinde ve ne zaman aldığı oturumu kapatılır bir) karakter.  
  
#### <a name="to-implement-the-command-handler"></a>Komut işleyici uygulamak için  
  
1.  Adlı bir sınıf ekleyin `TestSignatureHelpCommand` uygulayan <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
     [!code-vb[VSSDKSignatureHelpTest#24](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_24.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#24](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_24.cs)]  
  
2.  Özel alanlar için ekleme <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> (komut işleyici komuta zincirini işleyicilerine eklemenize olanak sağlayan) bağdaştırıcısı, metin görünümü, imza yardımcı aracısı ve oturumu bir <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator>ve sonraki <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
     [!code-vb[VSSDKSignatureHelpTest#25](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_25.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#25](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_25.cs)]  
  
3.  Bu alanların başlatılamadı ve komuta zincirini filtreleri komutu filtre eklemek için bir oluşturucu ekleyin.  
  
     [!code-vb[VSSDKSignatureHelpTest#26](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_26.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#26](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_26.cs)]  
  
4.  Uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> zaman komutu filtresini alır imza Yardım oturumu tetiklemek için yöntemi bir (bilinen yöntemi adları ve ne zaman aldığı oturumu kapatmak için sonra karakteri bir) oturumu etkin durumdayken karakter. Her durumda komutu iletilir.  
  
     [!code-vb[VSSDKSignatureHelpTest#27](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_27.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#27](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_27.cs)]  
  
5.  Uygulama <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> , BT'nin her zaman komutu iletir şekilde yöntemi.  
  
     [!code-vb[VSSDKSignatureHelpTest#28](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_28.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#28](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_28.cs)]  
  
## <a name="implementing-the-signature-help-command-provider"></a>İmza Yardım komutu sağlayıcıyı uygulama  
 İmza Help komutunu uygulayarak sağlayabilir <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> metin görünümü oluşturulduğunda komut işleyici örneği oluşturmak için.  
  
#### <a name="to-implement-the-signature-help-command-provider"></a>İmza yardımcı komutu sağlayıcısı uygulamak için  
  
1.  Adlı bir sınıf ekleyin `TestSignatureHelpController` uygulayan <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> ve onunla verme <xref:Microsoft.VisualStudio.Utilities.NameAttribute>, <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>, ve <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>.  
  
     [!code-vb[VSSDKSignatureHelpTest#29](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_29.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#29](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_29.cs)]  
  
2.  İçeri aktarma <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> (almak için kullanılan <xref:Microsoft.VisualStudio.Text.Editor.ITextView>, verilen <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> nesnesi), <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> (geçerli sözcüğü bulmak için kullanılan) ve <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker> (imza Yardım oturumu tetiklemek için).  
  
     [!code-vb[VSSDKSignatureHelpTest#30](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_30.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#30](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_30.cs)]  
  
3.  Uygulama <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener.VsTextViewCreated%2A> örneği tarafından yöntemi `TestSignatureCommandHandler`.  
  
     [!code-vb[VSSDKSignatureHelpTest#31](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-signature-help_31.vb)]
     [!code-csharp[VSSDKSignatureHelpTest#31](../extensibility/codesnippet/CSharp/walkthrough-displaying-signature-help_31.cs)]  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için SignatureHelpTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
#### <a name="to-build-and-test-the-signaturehelptest-solution"></a>Derleme ve SignatureHelpTest çözüm sınamak için  
  
1.  Çözümü oluşturun.  
  
2.  Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
3.  Bir metin dosyası ve "Ekle" sözcüğünü içeren belirli bir metin yazın ve bir açma ayracı oluşturun.  
  
4.  Parantez yazdıktan sonra iki imzaları listesini görüntüleyen bir araç ipucu görmelisiniz `add()` yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Bir İçerik Türünü Dosya Adı Uzantısına Bağlama](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)