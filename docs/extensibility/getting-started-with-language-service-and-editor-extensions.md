---
title: Dil hizmeti ve düzenleyici uzantıları ile çalışmaya başlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: 6b151891-c06d-40b1-9867-42298caa8492
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5e36f4a6b0f8cb37a5ede782c24c7593285b7705
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="getting-started-with-language-service-and-editor-extensions"></a>Dil hizmeti ve düzenleyici uzantıları ile çalışmaya başlama
Anahat oluşturma, eşleşen ayraç, IntelliSense ve ampuller gibi dil hizmet özellikleri programlama diliniz veya herhangi bir içerik türüne eklemek için düzenleyici uzantıları kullanabilirsiniz. Ayrıca, Görünüm ve Visual Studio düzenleyicisinde, Örneğin Renklendirme, kenar boşlukları, adornments ve diğer görsel öğelere metin davranışını özelleştirebilirsiniz. Ayrıca, kendi içerik türünü tanımlayın ve görünümü ve davranışı içeriğinizi göründüğü metin görünümlerini belirtin.  
  
 Düzenleyici uzantıları yazmaya başlamak için Visual Studio SDK'sı bir parçası olarak yüklenen Düzenleyicisi proje şablonları kullanın. Visual Studio SDK'sı daha kolay VSPackages kullanılarak veya Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanarak Visual Studio uzantılar geliştirmek için Araçlar indirilebilir kümesidir.  
  
> [!NOTE]
>  Visual Studio SDK'sı hakkında daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
 Kendi Düzenleyici uzantıları yazmadan önce aşağıdaki kavramlar ve teknolojileri hakkında bilgi öneririz.  
  
## <a name="the-windows-presentation-foundation-wpf-and-editor-extensions"></a>Windows Presentation Foundation (WPF) ve düzenleyici uzantıları  
 Visual Studio Düzenleyicisi kullanıcı arabirimi (UI), Windows Presentation Foundation (WPF) kullanılarak uygulanır. WPF zengin bir görsel deneyimi ve iş mantığından kodu görsel yönlerini ayıran tutarlı bir programlama modeli sağlar. Düzenleyici uzantıları oluşturduğunuzda, çok sayıda WPF öğeleri ve özelliklerini kullanabilirsiniz. Daha fazla bilgi için bkz: [Windows Presentation Foundation](/dotnet/framework/wpf/index).  
  
## <a name="the-managed-extensibility-framework-mef-and-editor-extensions"></a>Yönetilen Genişletilebilirlik Çerçevesi (MEF) ve düzenleyici uzantıları  
 Visual Studio düzenleyicisinde Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşenleri ve uzantıları yönetmek için kullanır. MEF, geliştiricilerin daha fazla Visual Studio gibi bir ana bilgisayar uygulaması için Uzantılar kolayca oluşturmanıza da olanak sağlar. Bu çerçeve uzantı MEF sözleşme göre tanımlayın ve bir MEF Bileşeni parçası olarak verin. Ana bilgisayar uygulaması bileşen parçalarını bunları bulma, bunları kaydetme ve doğru bağlamına uygulanan emin yönetir.  
  
> [!NOTE]
>  MEF Düzenleyicisi'nde hakkında daha fazla bilgi için bkz: [Yönetilen Genişletilebilirlik Çerçevesi Düzenleyicisi'nde](../extensibility/managed-extensibility-framework-in-the-editor.md).  
  
## <a name="visual-studio-editor-extension-points-and-extensions"></a>Visual Studio düzenleyicisinde uzantı noktaları ve uzantıları  
 Düzenleyici uzantısı özelleştirmek ve genişletmek MEF Bileşeni bölümleri noktalarıdır. Bazı durumlarda arabirimi uygulama ve doğru meta verilerle birlikte dışarı aktarma tarafından uzantı noktası genişletir. Diğer durumlarda, yalnızca bir uzantı bildirme ve belirli bir tür olarak dışa aktarın.  
  
 Düzenleyici uzantıları temel tür bazıları şunlardır:  
  
-   Kenar boşlukları ve kaydırma çubukları  
  
-   Etiketler  
  
-   Adornments  
  
-   Seçenekler  
  
-   IntelliSense  
  
 Düzenleyici uzantı noktaları hakkında daha fazla bilgi için bkz: [dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md).  
  
## <a name="deploying-editor-extensions"></a>Düzenleyici uzantıları dağıtma  
 Visual Studio'da Çözüm oluşturma çözüme source.extension.vsixmanifest adlı bir meta veri dosyası ekleyerek ve ardından ikili dosyaları ve bildirim bir kopyasını Visual Studio için bilinen bir klasörde ekleyerek Düzenleyici uzantıları dağıtın. Bildirim dosyası (örneğin, ad, yazar, sürüm ve içerik türünü) uzantısı hakkındaki temel gerçekleri tanımlar. VSIX bildirim dosyası ve uzantıları dağıtma hakkında daha fazla bilgi için bkz: [sevkiyat Visual Studio uzantıları](../extensibility/shipping-visual-studio-extensions.md).  
  
 Uzantı bir bilgisayara yüklediğinizde, Visual Studio için bilinen klasörünün bir alt ikili dosyaları ve bildirimini içerir.  
  
> [!WARNING]
>  Visual Studio'daki Düzenleyici genişletilebilirlik şablonlarından birini kullanıyorsanız, bildirimleri ve dağıtım konumlarında ayrıntıları hakkında endişelenmeniz gerekmez. Şablonları kaydetmek ve uzantı dağıtmak için gereken her şeyi içerir.  
  
## <a name="running-extensions-in-the-experimental-instance"></a>Deneysel örneğinde çalışan uzantıları  
 Aşağıdaki Deneysel klasöründe (Windows Vista ve Windows 7) dağıtarak uzantı geliştirirken Visual Studio çalışma sürümünüz verenlerden:  
  
 *% LOCALAPPDATA %*\VisualStudio\10.0Exp\Extensions\\*şirket*\\*Extensionıd*  
  
 Burada *LOCALAPPDATA %* oturum açan kullanıcı adı *şirket* uzantısına sahip şirket adı ve *Extensionıd* uzantısı kimliğidir.  
  
 Deneysel konuma uzantı dağıttığınızda, hata ayıklama modunda çalışır. Visual Studio ikinci bir örneğini başlatılır ve adlı **Microsoft Visual Studio - deneysel örneği**.  
  
## <a name="managing-extensions"></a>Uzantılarını yönetme  
 Visual Studio uzantıları listelenir **Uzantılar ve güncelleştirmeler** (üzerinde **Araçları** menüsü). Uzantı deneysel örneğinde sınıyorsanız, listelenen **Uzantılar ve güncelleştirmeler** deneysel örneğinde geliştirme örneğinde listelenmeyen ancak.  
  
 Daha fazla bilgi için bkz: [bulma ve Visual Studio uzantılarını kullanarak](../ide/finding-and-using-visual-studio-extensions.md).  
  
## <a name="using-templates-to-create-editor-extensions"></a>Şablonları kullanarak Düzenleyici uzantıları oluşturma  
 Düzenleyici şablonları sınıflandırıcı, adornments ve kenar boşlukları özelleştirme MEF uzantılarının oluşturmak için kullanabilirsiniz. Hem C# ve Visual Basic projeleri için şablonlar vardır. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
 VSIX proje şablonu, uzantıları oluşturmak için de kullanabilirsiniz. Bu şablonu yalnızca uzantısı herhangi bir tür dağıtmak ve source.extension.vsixmanifest dosya, gerekli derleme başvurularını ve dağıtmanıza olanak sağlamak derleme görevleri içeren bir proje dosyası eklemek için gereken öğeleri sağlar uzantı. Daha fazla bilgi için bkz: [VSIX proje şablonu](../extensibility/vsix-project-template.md).  
  
 Visual Studio Paketi uzantısından MEF Bileşenleri Düzenleyicisi de oluşturabilirsiniz. Ayrıntılar için aşağıdaki izlenecek bakın:  
  
-   [İzlenecek Yol: Düzenleyici Uzantısı ile Kabuk Komutu Kullanma](../extensibility/walkthrough-using-a-shell-command-with-an-editor-extension.md)  
  
-   [İzlenecek Yol: Düzenleyici Uzantısı ile Kısayol Tuşu Kullanma](../extensibility/walkthrough-using-a-shortcut-key-with-an-editor-extension.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Hizmeti ve Düzenleyici Uzantı Noktaları](../extensibility/language-service-and-editor-extension-points.md)