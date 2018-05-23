---
title: 'İzlenecek yol: Web bölümlerini görüntülemek için Sunucu Gezgini genişletme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint commands
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 688c4d8d9193ec33f0dcb63923673826a453c9be
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="walkthrough-extending-server-explorer-to-display-web-parts"></a>İzlenecek yol: Sunucu Gezginini Web Bölümlerini Görüntülemek Üzere Genişletme
  Visual Studio'da kullandığınız **SharePoint bağlantıları** düğümünün **Sunucu Gezgini** SharePoint sitelerinde bileşenleri görüntülemek için. Ancak, **Sunucu Gezgini** bazı bileşenler varsayılan olarak görüntülemez. Bu kılavuzda, genişletme **Sunucu Gezgini** Web Bölümü Galerisi görüntüler böylece her SharePoint sitesine bağlı.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Visual Studio uzantısı oluşturma genişletir **Sunucu Gezgini** aşağıdaki yollarla:  
  
    -   Uzantısı ekler bir **Web Bölümü Galerisi** her SharePoint sitesi düğümünde düğümünde **Sunucu Gezgini**. Bu yeni düğümü her sitede Web Bölümü Galerisi Web bölümünde temsil eden alt düğümleri içerir.  
  
    -   Uzantı yeni bir Web Bölümü örneğinin temsil eden düğüm türünü tanımlar. Bu yeni düğüm türü yeni alt düğümlerinde temelini **Web Bölümü Galerisi** düğümü. Yeni Web Bölümü düğüm türü bilgilerini görüntüler **özellikleri** penceresi temsil ettiği Web Bölümü hakkında. Düğüm türü için Web Bölümü ile ilgili diğer görevleri gerçekleştirmek için bir başlangıç noktası olarak kullanabileceğiniz özel kısayol menü öğesi de içerir.  
  
-   İki özel SharePoint komutu oluşturma uzantısı derleme çağrıları. SharePoint komutları API'leri için SharePoint sunucusu nesne modelinde kullanmak için uzantı derlemeleri tarafından çağrılan yöntemler şunlardır. Bu kılavuzda, geliştirme bilgisayarındaki yerel SharePoint sitesinden Web bölümü bilgilerini almak komutları oluşturur. Daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
-   Uzantı dağıtmak için Visual Studio Uzantısı (VSIX) paketi oluşturma.  
  
-   Hata ayıklama ve testi uzantısı.  
  
> [!NOTE]  
>  SharePoint için kendi sunucu nesne modeli yerine istemci nesne modelini kullanan bu kılavuzda alternatif bir sürümü için bkz: [izlenecek yol: bir sunucu Gezgini uzantısında SharePoint istemcisi nesne modelini çağırma](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Windows, SharePoint ve Visual Studio sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK'sı. Bu kılavuzda kullanılır **VSIX proje** Şablonu proje öğesi dağıtmak için VSIX paket oluşturmak için SDK. Daha fazla bilgi için bkz: [genişletme Visual Studio'da SharePoint Araçları](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Aşağıdaki kavramlar bilgisi yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   Sunucu nesne modeli için SharePoint kullanma. Daha fazla bilgi için bkz: [SharePoint Foundation Sunucu tarafı nesne modelini kullanarak](http://go.microsoft.com/fwlink/?LinkId=177796).  
  
-   Web Bölümleri SharePoint çözümlerinde. Daha fazla bilgi için bkz: [Web Bölümleri genel bakış](http://go.microsoft.com/fwlink/?LinkId=177803).  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
 Bu izlenecek yolu tamamlamak için üç projeleri oluşturmanız gerekir:  
  
-   Uzantı dağıtmak için VSIX paketi oluşturmak için bir VSIX proje.  
  
-   Uzantı arabirimini uygulayan bir sınıf kitaplığı projesi. Bu proje .NET Framework 4.5 hedeflemesi gerekir.  
  
-   Özel SharePoint komutları tanımlayan bir sınıf kitaplığı proje. Bu proje.NET Framework 3.5 hedeflemesi gerekir.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **genişletilebilirlik** düğümü.  
  
    > [!NOTE]  
    >  **Genişletilebilirlik** düğümdür yalnızca Visual Studio SDK'sı yüklerseniz kullanılabilir. Daha fazla bilgi için bu konudaki Önkoşullar bölümüne bakın.  
  
4.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde.  
  
5.  Seçin **VSIX proje** şablonu, proje adı **WebPartNode**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **WebPartNode** için proje **Çözüm Gezgini**.  
  
#### <a name="to-create-the-extension-project"></a>Uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** düğümü veya **Visual Basic** düğümünü ve ardından seçin **Windows** düğümü.  
  
3.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde.  
  
4.  Proje şablonları listesinden seçip **sınıf kitaplığı**, proje adı **WebPartNodeExtension**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **WebPartNodeExtension** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
#### <a name="to-create-the-sharepoint-commands-project"></a>SharePoint komutları projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** düğümü veya **Visual Basic** düğümünü ve ardından **Windows** düğümü.  
  
3.  İletişim kutusunun üstündeki seçin **.NET Framework 3.5** .NET Framework sürümleri listesinde.  
  
4.  Proje şablonları listesinden seçip **sınıf kitaplığı**, proje adı **WebPartCommands**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **WebPartCommands** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
## <a name="configuring-the-projects"></a>Projeleri yapılandırma  
 Uzantı oluşturmak için kod yazmadan önce ve derleme başvurularını kod dosyaları ekleyin ve proje ayarlarını yapılandırmanız gerekir.  
  
#### <a name="to-configure-the-webpartnodeextension-project"></a>WebPartNodeExtension projeyi yapılandırmak için  
  
1.  WebPartNodeExtension projesinde aşağıdaki adlara sahip dört kod dosyaları ekleyin:  
  
    -   SiteNodeExtension  
  
    -   WebPartNodeTypeProvider  
  
    -   WebPartNodeInfo  
  
    -   WebPartCommandIds  
  
2.  Kısayol menüsünü açın **WebPartNodeExtension** proje ve ardından **Başvuru Ekle**.  
  
3.  İçinde **başvuru Yöneticisi - WebPartNodeExtension** iletişim kutusunda, seçin **Framework** sekmesini ve ardından her aşağıdaki derlemeler için onay kutusunu seçin:  
  
    -   System.ComponentModel.Composition  
  
    -   System.Windows.Forms  
  
4.  Seçin **uzantıları** sekmesinde Microsoft.VisualStudio.SharePoint derlemesi için onay kutusunu seçin ve ardından **Tamam** düğmesi.  
  
5.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **WebPartNodeExtension** proje düğümünü ve ardından **özellikleri**.  
  
     **Proje Tasarımcısı** açar.  
  
6.  Seçin **uygulama** sekmesi.  
  
7.  İçinde **varsayılan ad alanı** kutusu (C#) veya **kök ad alanı** kutusunu ([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]), girin **ServerExplorer.SharePointConnections.WebPartNode**.  
  
#### <a name="to-configure-the-webpartcommands-project"></a>WebPartCommands projeyi yapılandırmak için  
  
1.  WebPartCommands projesinde WebPartCommands adlı bir kod dosyası ekleyin.  
  
2.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **WebPartCommands** proje düğümünü, seçin **Ekle**ve ardından **varolan öğeyi**.  
  
3.  İçinde **varolan öğeyi Ekle** iletişim kutusunda, WebPartNodeExtension projesi için kod dosyaları içeren klasöre gidin ve ardından WebPartNodeInfo ve WebPartCommandIds kod dosyaları seçin.  
  
4.  Oku seçin **Ekle** düğmesine tıklayın ve ardından **bağlantı olarak Ekle** menüde görünür.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kod dosyaları bağlantılar olarak WebPartCommands projeye ekler. Sonuç olarak, kod dosyaları WebPartNodeExtension projesinde bulunur, ancak dosyalarındaki kod ayrıca WebPartCommands projesinde derlenmiş.  
  
5.  Kısayol menüsünü açın **WebPartCommands** yeniden proje ve seçin **Başvuru Ekle**.  
  
6.  İçinde **başvuru Yöneticisi - WebPartCommands** iletişim kutusunda, seçin **uzantıları** sekmesinde, her aşağıdaki derlemeler için onay kutusunu seçin ve ardından **Tamam** düğmesi:  
  
    -   Microsoft.SharePoint  
  
    -   Microsoft.VisualStudio.SharePoint.Commands  
  
7.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **WebPartCommands** yeniden proje ve ardından **özellikleri**.  
  
     **Proje Tasarımcısı** açar.  
  
8.  Seçin **uygulama** sekmesi.  
  
9. İçinde **varsayılan ad alanı** kutusu (C#) veya **kök ad alanı** kutusunu ([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]), girin **ServerExplorer.SharePointConnections.WebPartNode**.  
  
## <a name="creating-icons-for-the-new-nodes"></a>Yeni düğümler için simge oluşturma  
 İki simgelerini oluşturma **Sunucu Gezgini** uzantısı: yeni bir simge **Web Bölümü Galerisi** düğümü ve her alt Web Bölümü düğümünde başka bir simge **Web Bölümü Galerisi** düğüm. Bu kılavuzda daha sonra bu simgeleri düğümleriyle ilişkilendirir kod yazacaksınız.  
  
#### <a name="to-create-icons-for-the-nodes"></a>Düğümler için simgeler oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **WebPartNodeExtension** proje ve ardından **özellikleri**.  
  
2.  **Proje Tasarımcısı** açar.  
  
3.  Seçin **kaynakları** sekmesini ve ardından **bu projenin varsayılan kaynak dosya içermiyor. Bir oluşturmak için buraya tıklayın** bağlantı.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kaynak dosyası oluşturur ve Tasarımcısı'nda açar.  
  
4.  En üstünde Tasarımcısı'nın yanındaki oku seçin **kaynak ekleme** menü komutunu ve ardından **ekleme yeni simgesine** görüntülenen menüde.  
  
5.  İçinde **yeni kaynak ekleme** iletişim kutusunda, yeni simgesine adı **WebPartsNode**ve ardından **Ekle** düğmesi.  
  
     Yeni simgesine açılır **görüntü Düzenleyicisi**.  
  
6.  Simge 16 x 16 sürümünü kolayca tanıyabilirsiniz bir tasarım olacak biçimde düzenleyin.  
  
7.  Simge 32 x 32 sürümü için kısayol menüsünü açın ve ardından **silmek görüntü türü**.  
  
8.  İkinci bir simge project kaynakları eklemek için 8 ile 5 arasındaki adımları yineleyin ve bu simgeyi ad **Web Bölümü**.  
  
9. İçinde **Çözüm Gezgini**altında **kaynakları** için klasör **WebPartNodeExtension** proje, kısayol menüsünü açın **WebPartsNode.ico**.  
  
10. İçinde **özellikleri** penceresinde oku seçin **yapı eylemi**ve ardından **katıştırılmış kaynak** menüsünde görüntülenir.  
  
11. İçin son iki adımı tekrarlayın **WebPart.ico**.  
  
## <a name="adding-the-web-part-gallery-node-to-server-explorer"></a>Sunucu Gezgini Web Bölümü Galerisi düğüm ekleme  
 Yeni ekler bir sınıf oluşturun **Web Bölümü Galerisi** her SharePoint sitesi düğümü düğüme. Sınıf uygular yeni düğümü eklemek için <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> arabirimi. Varolan bir düğümünde davranışını genişletmek istediğiniz zaman bu arabirimi uygulayan **Sunucu Gezgini**, bir alt düğüm için bir düğüm ekleme gibi.  
  
#### <a name="to-add-the-web-part-gallery-node-to-server-explorer"></a>Web Bölümü Galerisi düğümü için Sunucu Gezgini eklemek için  
  
1.  WebPartNodeExtension proje SiteNodeExtension kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
    > [!NOTE]  
    >  Ne zaman bu kodu ekleyin, proje bazı derleme hataları sahip olur, ancak hemen alınacaktır sonra daha sonraki adımlarda kodu ekleyin.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#1](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/sitenodeextension.vb#1)]  
  
## <a name="defining-a-node-type-that-represents-a-web-part"></a>Web bölümünü temsil eden bir düğüm türü tanımlama  
 Yeni bir Web bölümünü temsil eden düğüm türünü tanımlayan bir sınıf oluşturun. Visual Studio alt düğümleri altında görüntülemek için bu yeni düğüm türü kullanan **Web Bölümü Galerisi** düğümü. Her alt düğümü tek bir Web Bölümü SharePoint sitesinde temsil eder.  
  
 Yeni düğüm türü sınıfı uygulayan tanımlamak için <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> arabirimi. Düğümünde yeni bir tür tanımlamak istediğiniz zaman bu arabirimi uygulayan **Sunucu Gezgini**.  
  
#### <a name="to-define-the-web-part-node-type"></a>Web Bölümü düğüm türü tanımlamak için  
  
1.  WebPartNodeExtension proje WebPartNodeTypeProvder kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartnodetypeprovider.vb#2)]
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#2](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartnodetypeprovider.cs#2)]  
  
## <a name="defining-the-web-part-data-class"></a>Web Bölümü veri sınıfları tanımlama  
 Tek bir Web Bölümü SharePoint sitesinde ilgili verileri içeren bir sınıf tanımlayın. Bu kılavuzda daha sonra sitedeki her bir Web bölümünü hakkındaki verileri alır ve ardından bu sınıfın örnekleri için verileri atayan özel bir SharePoint komutu oluşturur.  
  
#### <a name="to-define-the-web-part-data-class"></a>Web Bölümü veri sınıfı tanımlamak için  
  
1.  WebPartNodeExtension proje WebPartNodeInfo kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartnodeinfo.vb#3)]
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#3](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartnodeinfo.cs#3)]  
  
## <a name="defining-the-ids-for-the-sharepoint-command"></a>Kimlikler için SharePoint komutu tanımlama  
 Özel SharePoint komutları tanımlamak birkaç dizeleri tanımlayın. Bu kılavuzda daha sonra bu komutları gerçekleştireceksiniz.  
  
#### <a name="to-define-the-command-ids"></a>Komut kimlikleri tanımlamak için  
  
1.  WebPartNodeExtension proje WebPartCommandIds kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../sharepoint/codesnippet/CSharp/WebPartNode/webpartnodeextension/webpartcommandids.cs#4)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#4](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartnodeextension/webpartcommandids.vb#4)]  
  
## <a name="creating-the-custom-sharepoint-commands"></a>Özel SharePoint komutları oluşturma  
 SharePoint Web Bölümleri SharePoint sitesinde ilgili verileri almak için sunucu nesne modeline çağrı özel komutlar oluşturun. Her komut sahip bir yöntemdir <xref:Microsoft.VisualStudio.SharePoint.Commands.SharePointCommandAttribute> uygulanmış.  
  
#### <a name="to-define-the-sharepoint-commands"></a>SharePoint komutları tanımlamak için  
  
1.  WebPartCommands proje WebPartCommands kod dosyasını açın ve ardından aşağıdaki kodu yapıştırın.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../sharepoint/codesnippet/CSharp/WebPartNode/WebPartCommands/WebPartCommands.cs#6)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNodeWithCommands#6](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnodewithcommands.webpartnode/webpartcommands/webpartcommands.vb#6)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 İzlenecek yol için tüm kod içinde bu noktada **Web Bölümü Galerisi** düğümü ve SharePoint komutları olan şimdi projelerinde. Her iki proje derleme hataları emin olmak için çözümü oluşturun.  
  
#### <a name="to-build-the-solution"></a>Çözümü derlemek için  
  
1.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
    > [!WARNING]  
    >  Bu noktada, VSIX bildirim dosyası yazar için bir değer olmadığından WebPartNode proje derleme hatası olabilir. Sonraki adımlarda değeri eklediğinizde, bu hata kaybolur.  
  
## <a name="creating-a-vsix-package-to-deploy-the-extension"></a>Uzantıyı dağıtmak için VSIX paket oluşturma  
 Uzantıyı dağıtmak için VSIX paketi oluşturmak için çözümünüz VSIX proje kullanın. İlk olarak VSIX paketi VSIX proje source.extension.vsixmanifest dosyasını değiştirerek yapılandırın. Çözümü derledikten sonra VSIX paketi oluşturun.  
  
#### <a name="to-configure-the-vsix-package"></a>VSIX paketi yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, WebPartNode projesi altında açmak **source.extension.vsixmanifest** bildirim Düzenleyicisi'nde dosya.  
  
     Source.extension.vsixmanifest dosyanın tüm VSIX paketi gerektirir extension.vsixmanifest dosya temelini oluşturur. Bu dosya hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  İçinde **ürün adı** kutusuna **Web Bölümü Galerisi düğümü için Sunucu Gezgini**.  
  
3.  İçinde **Yazar** kutusuna **Contoso**.  
  
4.  İçinde **açıklama** kutusuna **Sunucu Gezgininde SharePoint bağlantıları için özel bir Web Bölümü Galerisi düğüm ekler. Bu uzantı sunucusu nesne modeline çağırmak için özel bir SharePoint komut kullanır.**  
  
5.  Seçin **varlıklar** Düzenleyicisi'ni sekmesini ve ardından **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
6.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `MefComponent` extension.vsixmanifest dosyasındaki öğesi. Bu öğe VSIX paketi bir uzantı bütünleştirilmiş kodun adını belirtir. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
8.  İçinde **proje** listesinde, seçin **WebPartNodeExtension** ve ardından **Tamam** düğmesi.  
  
9. Bildirim düzenleyicisinde seçin **yeni** yeniden düğmesine tıklayın.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
10. İçinde **türü** kutusuna **SharePoint.Commands.v4**.  
  
    > [!NOTE]  
    >  Bu öğe, Visual Studio Uzantısı'nda dahil etmek istediğiniz özel bir uzantı belirtir. Daha fazla bilgi için bkz: [varlık öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/9fcfc098-edc7-484b-9d4c-acd17829d737).  
  
11. İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile** liste öğesi.  
  
12. İçinde **proje** listesinde, seçin **WebPartCommands**ve ardından **Tamam** düğmesi.  
  
13. Menü çubuğunda seçin **yapı**, **yapı çözümü**ve ardından çözüm hatasız derlendiğinden emin olun.  
  
14. Yapı çıktı klasörüne WebPartNode projesi için şimdi WebPartNode.vsix dosya içerdiğinden emin olun.  
  
     Varsayılan olarak, yapı çıktı klasördür... Proje dosyasını içeren klasörü altındaki \bin\Debug klasörünü.  
  
## <a name="testing-the-extension"></a>Testi uzantısı  
 Yeni test etmek artık hazırsınız **Web Bölümü Galerisi** düğümünde **Sunucu Gezgini**. İlk olarak, Visual Studio deneysel örneği uzantı hata ayıklama başlatılamıyor. Ardından, yeni kullanmak **Web Bölümleri** deneysel örneği düğümünde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
#### <a name="to-start-debugging-the-extension"></a>Hata ayıklama uzantısı başlatmak için  
  
1.  Yeniden [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] yönetici kimlik bilgilerini ve WebPartNode çözümü açın.  
  
2.  WebPartNodeExtension projesinde SiteNodeExtension kod dosyasını açın ve daha sonra bir kesme noktası kod ilk satırı ekleyin `NodeChildrenRequested` ve `CreateWebPartNodes` yöntemleri.  
  
3.  Hata ayıklamayı başlatmak için F5 tuşuna seçin.  
  
     Visual Studio için sunucu Explorer\1.0 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Web Bölümü Galerisi düğüm uzantısı uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Proje öğesi Visual Studio'nun bu örnekte test edeceğiz.  
  
#### <a name="to-test-the-extension"></a>Uzantı sınamak için  
  
1.  Deneysel örneğinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], menü çubuğunda seçin **Görünüm**, **Sunucu Gezgini**.  
  
2.  Test etmek için kullanmak istediğiniz SharePoint sitesi altında görünmüyorsa aşağıdaki adımları **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**:  
  
    1.  İçinde **Sunucu Gezgini**, kısayol menüsünü açın **SharePoint bağlantıları**ve ardından **Bağlantı Ekle**.  
  
    2.  İçinde **SharePoint Bağlantı Ekle** iletişim kutusunda, bağlanmak ve ardından istediğiniz SharePoint sitesi için URL'yi girin **Tamam** düğmesi.  
  
         SharePoint sitesi geliştirme bilgisayarınızda belirtmek için girin **http://localhost**.  
  
3.  (Hangi sitenizin URL'sini görüntüler) site bağlantı düğümünü genişletin ve ardından bir alt site düğümünü genişletin (örneğin, **ekip sitesi**).  
  
4.  Doğrulayın diğer örneklerini kodda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] daha önce belirlediğiniz kesme noktası duruyor `NodeChildrenRequested` yöntemi ve projeyi hata ayıklamak devam etmek için F5'i seçin.  
  
5.  Visual Studio deneysel örneğinde adlı yeni bir düğüm doğrulayın **Web Bölümü Galerisi** en üst düzey sitesi düğümünün altında görünür ve ardından genişletin **Web Bölümü Galerisi** düğümü.  
  
6.  Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `CreateWebPartNodes` yöntemi ve projeyi hata ayıklamak devam etmek için F5 tuşuna'i seçin.  
  
7.  Visual Studio deneysel örneğinde bağlı sitesindeki tüm Web Bölümleri altında göründüğünü doğrulayın **Web Bölümü Galerisi** düğümünde **Sunucu Gezgini**.  
  
8.  İçinde **Sunucu Gezgini**, Web bölümlerini biri için kısayol menüsünü açın ve ardından **özellikleri**.  
  
9. Örneğindeki [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hatalarını ayıkladığınız, Web bölümünü ayrıntılarını göründüğünü doğrulayın **özellikleri** penceresi.  
  
## <a name="uninstalling-the-extension-from-visual-studio"></a>Visual Studio'dan uzantısını kaldırma  
 Testi uzantısı tamamladıktan sonra uzantıyı Visual Studio'dan kaldırın.  
  
#### <a name="to-uninstall-the-extension"></a>Uzantıyı kaldırmak için  
  
1.  Deneysel örneğinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], menü çubuğunda seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **Web Bölümü Galerisi düğüm uzantısı için Sunucu Gezgini**ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** uzantısı kaldırın ve ardından istediğinizi onaylamak için düğmesini **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için düğmesi.  
  
4.  Visual Studio (deneysel örneği ve Visual Studio WebPartNode çözüm açıksa örneğini) hem örneklerini kapatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [İzlenecek yol: bir sunucu Gezgini uzantısında SharePoint istemcisi nesne modelini çağırma](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)   
 [Simgeler için görüntü Düzenleyicisi](/cpp/windows/image-editor-for-icons)   
 [Simge veya başka görüntü oluşturma &#40;simgeler için görüntü Düzenleyicisi&#41;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  