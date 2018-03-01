---
title: "İzlenecek yol: Quıckınfo araç ipuçlarını görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - QuickInfo
ms.assetid: 23fb8384-4f12-446f-977f-ce7910347947
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9cd3e9d5e10e6946b4cae8ce02a5a39511e4baaf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-quickinfo-tooltips"></a>İzlenecek yol: Quıckınfo araç ipuçlarını görüntüleme
Quıckınfo yöntem imzaları görüntüleyen bir IntelliSense özelliğidir ve açıklamaları bir kullanıcı bir yöntem adı işaretçinin taşır. Quıckınfo açıklamaları sağlamak istediğiniz tanımlayıcıları tanımlama ve ardından içeriği görüntülemek için bir araç ipucunda oluşturarak Quıckınfo gibi dil tabanlı özellikler uygulayabilirsiniz. Bir dil hizmeti bağlamında Quıckınfo tanımlayabilirsiniz kendi dosya adı uzantısı ve içerik türünü tanımlayın ve yalnızca bu tür için Quıckınfo görüntülemek veya varolan bir içerik türü (örneğin, "metin") için Quıckınfo görüntüleyebilirsiniz. Bu kılavuzda "metin" içerik türü için Quıckınfo görüntülemek nasıl gösterir.  
  
 Bir kullanıcı bir yöntem adı işaretçi geldiğinde bu kılavuzda Quıckınfo örnek araç ipuçları görüntüler. Bu tasarım, bu dört arabirimlerini gerektirir:  
  
-   Kaynak arabirimi  
  
-   Kaynak sağlayıcı arabirimi  
  
-   denetleyici arabirimi  
  
-   Denetleyici sağlayıcı arabirimi  
  
 Kaynak ve denetleyici sağlayıcıları Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni bölümleri, kaynak ve denetleyici sınıfları dışarı aktarma için sorumludur ve alma hizmetleri gibi aracıların <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>, araç ipucu metni oluşturur Arabellek ve <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker>, Quıckınfo oturum tetikler.  
  
 Bu örnekte, yöntem adları ve açıklamaları, sabit kodlanmış listesini Quıckınfo kaynak kullanır, ancak tam uygulamalarında dil hizmeti ve dil belgelerine içerik sağlamak için sorumludur.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Bir MEF projesi oluşturma  
  
#### <a name="to-create-a-mef-project"></a>Bir MEF projesi oluşturmak için  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `QuickInfoTest`.  
  
2.  Bir düzenleyici sınıflandırıcı öğe şablonu projeye ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
## <a name="implementing-the-quickinfo-source"></a>Quıckınfo kaynağı uygulama  
 Quıckınfo kaynak tanımlayıcılar ve açıklamalarının kümesini toplamak ve tanımlayıcıları birini karşılaşıldığında araç ipucu metni arabelleğin içerik ekleme sorumludur. Bu örnekte, tanımlayıcılarını ve açıklamalarının yalnızca kaynak oluşturucuda eklenir.  
  
#### <a name="to-implement-the-quickinfo-source"></a>Quıckınfo kaynak uygulamak için  
  
1.  Bir sınıf dosyası ekleyin ve adını `TestQuickInfoSource`.  
  
2.  Microsoft.VisualStudio.Language.IntelliSense bir başvuru ekleyin.  
  
3.  Aşağıdaki içeri aktarmaları ekleyin.  
  
     [!code-vb[VSSDKQuickInfoTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_1.vb)]
     [!code-csharp[VSSDKQuickInfoTest#1](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_1.cs)]  
  
4.  Uygulayan bir sınıf bildirme <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource>ve adlandırın `TestQuickInfoSource`.  
  
     [!code-vb[VSSDKQuickInfoTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_2.vb)]
     [!code-csharp[VSSDKQuickInfoTest#2](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_2.cs)]  
  
5.  Quıckınfo kaynak sağlayıcısı, metin arabelleği ve bir dizi yöntem adları ve yöntem imzaları için alanlar ekleyin. Bu örnekte, yöntem adları ve imzalar, başlatılmış `TestQuickInfoSource` Oluşturucusu.  
  
     [!code-vb[VSSDKQuickInfoTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_3.vb)]
     [!code-csharp[VSSDKQuickInfoTest#3](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_3.cs)]  
  
6.  Quıckınfo kaynak sağlayıcısı ve metin arabelleği ayarlar ve yöntem adları ve yöntem imzaları ve açıklamaları kümesi dolduran bir oluşturucu ekleyin.  
  
     [!code-vb[VSSDKQuickInfoTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_4.vb)]
     [!code-csharp[VSSDKQuickInfoTest#4](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_4.cs)]  
  
7.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource.AugmentQuickInfoSession%2A> yöntemi. İmleç bir satır veya bir metin arabelleği sonunda ise bu örnekte, geçerli word veya önceki word yöntemi bulur. Word yöntemi adlarından birini kullanıyorsanız, bu yöntem adı açıklamasını Quıckınfo içeriği eklenir.  
  
     [!code-vb[VSSDKQuickInfoTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_5.vb)]
     [!code-csharp[VSSDKQuickInfoTest#5](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_5.cs)]  
  
8.  Dispose() yöntemi beri uygulamalıdır <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource> uygulayan <xref:System.IDisposable>:  
  
     [!code-vb[VSSDKQuickInfoTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_6.vb)]
     [!code-csharp[VSSDKQuickInfoTest#6](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_6.cs)]  
  
## <a name="implementing-a-quickinfo-source-provider"></a>Quıckınfo kaynak sağlayıcıyı uygulama  
 Quıckınfo kaynak sağlayıcısı öncelikle kendisini MEF Bileşeni parçası olarak dışarı ve Quıckınfo kaynak örneği sınırlandırır. Bir MEF bileşen parçası olduğundan, diğer MEF Bileşeni bölümleri içeri aktarabilirsiniz.  
  
#### <a name="to-implement-a-quickinfo-source-provider"></a>Quıckınfo kaynak sağlayıcısını uygulamak için  
  
1.  Adlı bir Quıckınfo kaynak sağlayıcısı bildirimini `TestQuickInfoSourceProvider` uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider>ve onunla verme bir <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "Araç ipucu Quıckınfo kaynağının" bir <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> , önce = "varsayılan" ve <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "metin".  
  
     [!code-vb[VSSDKQuickInfoTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_7.vb)]
     [!code-csharp[VSSDKQuickInfoTest#7](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_7.cs)]  
  
2.  İki Düzenleyicisi Hizmetleri almak <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> ve <xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>, özellikleri olarak `TestQuickInfoSourceProvider`.  
  
     [!code-vb[VSSDKQuickInfoTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_8.vb)]
     [!code-csharp[VSSDKQuickInfoTest#8](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_8.cs)]  
  
3.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider.TryCreateQuickInfoSource%2A> yeni döndürülecek `TestQuickInfoSource`.  
  
     [!code-vb[VSSDKQuickInfoTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_9.vb)]
     [!code-csharp[VSSDKQuickInfoTest#9](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_9.cs)]  
  
## <a name="implementing-a-quickinfo-controller"></a>Quıckınfo denetleyicisi uygulama  
 Quıckınfo denetleyicileri Quıckınfo ne zaman görüntüleneceğini belirler. Bu örnekte, yöntem adları birine karşılık gelen bir sözcük üzerinden işaretçidir Quıckınfo görüntülenir. Quıckınfo denetleyicisi Quıckınfo oturum tetikleyen bir fare vurgulu olay işleyicisi uygular.  
  
#### <a name="to-implement-a-quickinfo-controller"></a>Quıckınfo denetleyicisi uygulamak için  
  
1.  Uygulayan bir sınıf bildirme <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController>ve adlandırın `TestQuickInfoController`.  
  
     [!code-vb[VSSDKQuickInfoTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_10.vb)]
     [!code-csharp[VSSDKQuickInfoTest#10](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_10.cs)]  
  
2.  Özel alanları metin görünümü için metin görünümü, Quıckınfo oturumu ve Quıckınfo controller sağlayıcısı temsil metin arabelleği ekleyin.  
  
     [!code-vb[VSSDKQuickInfoTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_11.vb)]
     [!code-csharp[VSSDKQuickInfoTest#11](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_11.cs)]  
  
3.  Alanları ayarlar ve fare vurgulu olay işleyicisi ekleyen bir oluşturucu ekleyin.  
  
     [!code-vb[VSSDKQuickInfoTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_12.vb)]
     [!code-csharp[VSSDKQuickInfoTest#12](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_12.cs)]  
  
4.  Quıckınfo oturum tetikler fare vurgulu olay işleyicisi ekleyin.  
  
     [!code-vb[VSSDKQuickInfoTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_13.vb)]
     [!code-csharp[VSSDKQuickInfoTest#13](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_13.cs)]  
  
5.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.Detach%2A> denetleyicisi metin görünümünden ayrılmış olduğunda bu BT fare vurgulu olay işleyicisi kaldırır şekilde yöntemi.  
  
     [!code-vb[VSSDKQuickInfoTest#14](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_14.vb)]
     [!code-csharp[VSSDKQuickInfoTest#14](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_14.cs)]  
  
6.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.ConnectSubjectBuffer%2A> yöntemi ve <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController.DisconnectSubjectBuffer%2A> yöntemi bu örnek için boş yöntemleri olarak.  
  
     [!code-vb[VSSDKQuickInfoTest#15](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_15.vb)]
     [!code-csharp[VSSDKQuickInfoTest#15](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_15.cs)]  
  
## <a name="implementing-the-quickinfo-controller-provider"></a>Quıckınfo denetleyicisi sağlayıcıyı uygulama  
 Quıckınfo denetleyicisi sağlayıcısı öncelikle kendisini MEF Bileşeni parçası olarak dışarı ve Quıckınfo denetleyici örneği sınırlandırır. Bir MEF bileşen parçası olduğundan, diğer MEF Bileşeni bölümleri içeri aktarabilirsiniz.  
  
#### <a name="to-implement-the-quickinfo-controller-provider"></a>Quıckınfo denetleyicisi sağlayıcısını uygulamak için  
  
1.  Adlı bir sınıf bildirme `TestQuickInfoControllerProvider` uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider>ve onunla verme bir <xref:Microsoft.VisualStudio.Utilities.NameAttribute> "Araç ipucu Quıckınfo denetleyicisinin" ve <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "metin":  
  
     [!code-vb[VSSDKQuickInfoTest#16](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_16.vb)]
     [!code-csharp[VSSDKQuickInfoTest#16](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_16.cs)]  
  
2.  İçeri aktarma <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker> özelliği olarak.  
  
     [!code-vb[VSSDKQuickInfoTest#17](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_17.vb)]
     [!code-csharp[VSSDKQuickInfoTest#17](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_17.cs)]  
  
3.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseControllerProvider.TryCreateIntellisenseController%2A> Quıckınfo denetleyici örneği tarafından yöntemi.  
  
     [!code-vb[VSSDKQuickInfoTest#18](../extensibility/codesnippet/VisualBasic/walkthrough-displaying-quickinfo-tooltips_18.vb)]
     [!code-csharp[VSSDKQuickInfoTest#18](../extensibility/codesnippet/CSharp/walkthrough-displaying-quickinfo-tooltips_18.cs)]  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için QuickInfoTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
#### <a name="to-build-and-test-the-quickinfotest-solution"></a>Derleme ve QuickInfoTest çözüm sınamak için  
  
1.  Çözümü oluşturun.  
  
2.  Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
3.  Bir metin dosyası ve türü sözcükler içeren bazı metin "Ekle" ve "çıkarma" oluşturun.  
  
4.  İşaretçinin "Ekle" oluşumlarının birinin üzerine taşıyın. İmza ve açıklamasını `add` yöntemi görüntülenmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Bir İçerik Türünü Dosya Adı Uzantısına Bağlama](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)