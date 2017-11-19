---
title: "İzlenecek yol: bir sunucu Gezgini uzantısında SharePoint istemcisi nesne modelini çağırma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, client object model
- SharePoint commands [SharePoint development in Visual Studio]
ms.assetid: 897d3798-42c1-4fff-b280-8b84b53d80c6
caps.latest.revision: "100"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 489a11c215fe590b85e9dfaf5cbd815fdc43acb3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension"></a>İzlenecek yol: Bir Sunucu Gezgini Uzantısında SharePoint İstemcisi Nesne Modelini Çağırma
  Bu kılavuz bir uzantı için SharePoint istemcisi nesne modelini nasıl çağırılacağını **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**. SharePoint istemcisi nesne modelini kullanma hakkında daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] genişletir uzantısı **SharePoint bağlantıları** düğümünün **Sunucu Gezgini** aşağıdaki yollarla:  
  
    -   Uzantısı ekler bir **Web Bölümü Galerisi** her SharePoint sitesi düğümünde düğümünde **Sunucu Gezgini**. Bu yeni düğümü her sitede Web Bölümü Galerisi Web bölümünde temsil eden alt düğümleri içerir.  
  
    -   Uzantı yeni bir Web Bölümü örneğinin temsil eden düğüm türünü tanımlar. Bu yeni düğüm türü yeni alt düğümlerinde temelini **Web Bölümü Galerisi** düğümü. Yeni Web Bölümü düğüm türü bilgilerini görüntüler **özellikleri** penceresi düğümünü temsil eder Web Bölümü hakkında.  
  
-   Uzantı dağıtmak için Visual Studio Uzantısı (VSIX) paketi oluşturma.  
  
-   Hata ayıklama ve testi uzantısı.  
  
> [!NOTE]  
>  Bu kılavuzda oluşturma uzantısı oluşturduğunuz uzantısı benzer [izlenecek yol: Görüntü Web bölümleri için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md). Bu izlenecek yol SharePoint sunucu nesne modeli kullanır, ancak istemci nesne modelini kullanarak bu kılavuzda aynı görevleri gerçekleştirir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Windows, SharePoint ve Visual Studio sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio SDK'sı. Bu kılavuzda kullanılır **VSIX proje** SDK'sındaki uzantısını dağıtmak için VSIX paket oluşturmak için şablon. Daha fazla bilgi için bkz: [genişletme Visual Studio'da SharePoint Araçları](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
Aşağıdaki kavramlar bilgisi yararlı, ancak gerekli değildir, izlenecek yolu tamamlamak için:  
  
-   SharePoint istemcisi nesne modelini kullanarak. Daha fazla bilgi için bkz: [yönetilen istemci nesne modelini](http://go.microsoft.com/fwlink/?LinkId=177797).  
  
-   SharePoint Web Bölümleri. Daha fazla bilgi için bkz: [Web Bölümleri genel bakış](http://go.microsoft.com/fwlink/?LinkId=177803).  
  
## <a name="creating-the-projects"></a>Proje oluşturma  
 Bu izlenecek yolu tamamlamak için iki projeleri oluşturmanız gerekir:  
  
-   Dağıtmak için VSIX paketi oluşturmak için VSIX proje **Sunucu Gezgini** uzantısı.  
  
-   Uygulayan bir sınıf kitaplığı proje **Sunucu Gezgini** uzantısı.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **genişletilebilirlik**.  
  
    > [!NOTE]  
    >  **Genişletilebilirlik** düğümdür yalnızca Visual Studio SDK'sı yüklerseniz kullanılabilir. Daha fazla bilgi için bu konudaki Önkoşullar bölümüne bakın.  
  
4.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde.  
  
     SharePoint araç uzantıları .NET Framework'ün bu sürümünde özellikleri gerektirir.  
  
5.  Seçin **VSIX proje** şablonu.  
  
6.  İçinde **adı** kutusuna **WebPartNode**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **WebPartNode** için proje **Çözüm Gezgini**.  
  
#### <a name="to-create-the-extension-project"></a>Uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **Windows**.  
  
3.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde.  
  
4.  Proje şablonları listesinden seçip **sınıf kitaplığı**.  
  
5.  İçinde **adı** kutusuna **WebPartNodeExtension**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ekler **WebPartNodeExtension** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
6.  Class1 kod dosyasının projeden silin.  
  
## <a name="configuring-the-extension-project"></a>Uzantı projesi yapılandırma  
 Uzantısı oluşturmak için kod yazmadan önce kod dosyaları ve derleme başvuruları projenize ekleyin ve varsayılan ad alanını güncelleştirmeniz gerekir.  
  
#### <a name="to-configure-the-project"></a>Projeyi yapılandırmak için  
  
1.  İçinde **WebPartNodeExtension** projesi, SiteNodeExtension ve WebPartNodeTypeProvider adlı iki kod dosyaları ekleyin.  
  
2.  WebPartNodeExtension proje için kısayol menüsünü açın ve ardından **Başvuru Ekle**.  
  
3.  İçinde **başvuru Yöneticisi - WebPartNodeExtension** iletişim kutusunda, seçin **Framework** düğümünü ve ardından onay kutularını System.Windows.Forms ve System.ComponentModel.Composition için derlemeler.  
  
4.  Seçin **uzantıları** düğümü, her aşağıdaki derlemeler için onay kutusunu seçin ve ardından **Tamam** düğmesi:  
  
    -   Microsoft.SharePoint.Client  
  
    -   Microsoft.SharePoint.Client.Runtime  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  Kısayol menüsünü açın **WebPartNodeExtension** proje ve ardından **özellikleri**.  
  
     **Proje Tasarımcısı** açar.  
  
6.  Seçin **uygulama** sekmesi.  
  
7.  İçinde **varsayılan ad alanı** kutusu (C#) veya **kök ad alanı** kutusuna (Visual Basic) **ServerExplorer.SharePointConnections.WebPartNode**.  
  
## <a name="creating-icons-for-the-new-nodes"></a>Yeni düğümler için simge oluşturma  
 İki simgelerini oluşturma **Sunucu Gezgini** uzantısı: yeni bir simge **Web Bölümü Galerisi** düğümü ve her alt Web Bölümü düğümünde başka bir simge **Web Bölümü Galerisi** düğüm. Bu kılavuzda daha sonra bu simgeleri düğümleriyle ilişkilendirir kod yazacaksınız.  
  
#### <a name="to-create-icons-for-the-nodes"></a>Düğümler için simgeler oluşturmak için  
  
1.  İçinde **Proje Tasarımcısı** WebPartNodeExtension proje için seçme **kaynakları** sekmesi.  
  
2.  Bağlantıyı seçin **bu projenin varsayılan kaynak dosya içermiyor. Oluşturmak için burayı tıklatın.**  
  
     Visual Studio kaynak dosyası oluşturur ve Tasarımcısı'nda açılır.  
  
3.  Tasarımcı üstündeki ok seçin **kaynak ekleme** menü komutunu ve ardından **ekleme yeni simgesine**.  
  
4.  Girin **WebPartsNode** için yeni simgesine adlandırın ve ardından **Ekle** düğmesi.  
  
     Yeni simgesine açılır **görüntü Düzenleyicisi**.  
  
5.  Simge 16 x 16 sürümünü kolayca tanıyabilirsiniz bir tasarım olacak biçimde düzenleyin.  
  
6.  Simge 32 x 32 sürümü için kısayol menüsünü açın ve ardından **silmek görüntü türü**.  
  
7.  İkinci bir simge project kaynakları eklemek için 7 ile 3 arasındaki adımları yineleyin ve bu simgeyi ad **Web Bölümü**.  
  
8.  İçinde **Çözüm Gezgini**, **kaynakları** için klasör **WebPartNodeExtension** seçin, proje **WebPartsNode.ico**.  
  
9. İçinde **özellikleri** penceresi açık **yapı eylemi** listeleyin ve ardından **katıştırılmış kaynak**.  
  
10. İçin son iki adımı tekrarlayın **WebPart.ico**.  
  
## <a name="adding-the-web-part-gallery-node-to-server-explorer"></a>Sunucu Gezgini Web Bölümü Galerisi düğüm ekleme  
 Yeni ekler bir sınıf oluşturun **Web Bölümü Galerisi** her SharePoint sitesi düğümü düğüme. Sınıf uygular yeni düğümü eklemek için <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension> arabirimi. Varolan bir düğümünde davranışını genişletmek istediğiniz zaman bu arabirimi uygulayan **Sunucu Gezgini**, yeni bir alt düğüm için bir düğüm ekleme gibi.  
  
#### <a name="to-add-the-web-part-gallery-node-to-server-explorer"></a>Web Bölümü Galerisi düğümü için Sunucu Gezgini eklemek için  
  
1.  Aşağıdaki kodu yapıştırın **SiteNodeExtension** için kod dosyası **WebPartNodeExtension** projesi.  
  
    > [!NOTE]  
    >  Bu kod ekledikten sonra projeyi bazı derleme hataları sahip olur. Sonraki adımlarda kodu eklediğinizde, bu hataları kaybolur.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#1](../sharepoint/codesnippet/CSharp/webpartnode/webpartnodeextension/sitenodeextension.cs#1)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#1](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnode.webpartnode/webpartnodeextension/sitenodeextension.vb#1)]  
  
## <a name="defining-a-node-type-that-represents-a-web-part"></a>Web bölümünü temsil eden bir düğüm türü tanımlama  
 Yeni bir Web bölümünü temsil eden düğüm türünü tanımlayan bir sınıf oluşturun. Visual Studio alt düğümleri altında görüntülemek için bu yeni düğüm türü kullanan **Web Bölümü Galerisi** düğümü. Bu alt düğümlerin her birinde tek bir Web Bölümü SharePoint sitesinde temsil eder.  
  
 Yeni düğüm türü sınıfı uygulayan tanımlamak için <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider> arabirimi. Düğümünde yeni bir tür tanımlamak istediğiniz zaman bu arabirimi uygulayan **Sunucu Gezgini**.  
  
#### <a name="to-define-the-web-part-node-type"></a>Web Bölümü düğüm türü tanımlamak için  
  
1.  Aşağıdaki kodu yapıştırın **WebPartNodeTypeProvider** için kod dosyası **WebPartNodeExtension** projesi.  
  
     [!code-csharp[SPExtensibility.SPExplorer.WebPartNode#2](../sharepoint/codesnippet/CSharp/webpartnode/webpartnodeextension/webpartnodetypeprovider.cs#2)]
     [!code-vb[SPExtensibility.SPExplorer.WebPartNode#2](../sharepoint/codesnippet/VisualBasic/spextensibility.spexplorer.webpartnode.webpartnode/webpartnodeextension/webpartnodetypeprovider.vb#2)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 İzlenecek yol için tüm kod içinde bu noktada **Web Bölümü Galerisi** düğümdür şimdi projede. Yapı **WebPartNodeExtension** proje hatasız derlendiğinden emin olun.  
  
#### <a name="to-build-the-project"></a>Projeyi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **WebPartNodeExtension** proje ve ardından **yapı**.  
  
## <a name="creating-a-vsix-package-to-deploy-the-extension"></a>Uzantıyı dağıtmak için VSIX paket oluşturma  
 Uzantıyı dağıtmak için VSIX paketi oluşturmak için çözümünüz VSIX proje kullanın. İlk olarak VSIX paketi projeye dahil source.extension.vsixmanifest dosyasını değiştirerek yapılandırın. Çözümü derledikten sonra VSIX paketi oluşturun.  
  
#### <a name="to-configure-the-vsix-package"></a>VSIX paketi yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, **WebPartNode** proje, açık **source.extension.vsixmanifest** bildirim Düzenleyicisi'nde dosya.  
  
     Source.extension.vsixmanifest dosyanın tüm VSIX paketi gerektirir extension.vsixmanifest dosya temelini oluşturur. Bu dosya hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  İçinde **ürün adı** kutusuna **Web Bölümü Galerisi düğümü için Sunucu Gezgini**.  
  
3.  İçinde **Yazar** kutusuna **Contoso**.  
  
4.  İçinde **açıklama** kutusuna **Sunucu Gezgininde SharePoint bağlantıları için özel bir Web Bölümü Galerisi düğüm ekler**.  
  
5.  Üzerinde **varlıklar** sekmesini Düzenleyicisi, seçin **yeni** düğmesi.  
  
6.  İçinde **ekleme yeni varlık** iletişim kutusunda **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `MefComponent` extension.vsixmanifest dosyasındaki öğesi. Bu öğe VSIX paketi bir uzantı bütünleştirilmiş kodun adını belirtir. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile**.  
  
8.  İçinde **proje** listesinde, seçin **WebPartNodeExtension**ve ardından **Tamam** düğmesi.  
  
9. Menü çubuğunda seçin **yapı**, **yapı çözümü**ve ardından çözüm hatasız derlendiğinden emin olun.  
  
10. Yapı çıktı klasörüne WebPartNode projesi için şimdi WebPartNode.vsix dosya içerdiğinden emin olun.  
  
     Varsayılan olarak, yapı çıktı klasördür... Proje dosyasını içeren klasörü altındaki \bin\Debug klasörünü.  
  
## <a name="testing-the-extension"></a>Testi uzantısı  
 Yeni test etmek artık hazırsınız **Web Bölümü Galerisi** düğümünde **Sunucu Gezgini**. Visual Studio deneysel örneği uzantısı projesinde hata ayıklamak ilk olarak başlatın. Yeni kullanmak **Web Bölümleri** Visual Studio'nun deneysel örneği düğümünde.  
  
#### <a name="to-start-debugging-the-extension"></a>Hata ayıklama uzantısı başlatmak için  
  
1.  Yönetici kimlik bilgileriyle Visual Studio'yu yeniden başlatın ve sonra açmak **WebPartNode** çözümü.  
  
2.  WebPartNodeExtension projeyi açın **SiteNodeExtension** kod dosyası ve daha sonra bir kesme noktası ilk satır kod ekleyin `NodeChildrenRequested` ve `CreateWebPartNodes` yöntemleri.  
  
3.  Hata ayıklamayı başlatmak için F5 tuşuna seçin.  
  
     Visual Studio için sunucu Explorer\1.0 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Web Bölümü Galerisi düğüm uzantısı uzantıyı yükleyen ve Visual Studio Deneysel bir örneğini başlatır. Proje öğesi Visual Studio'nun bu örneği test edeceksiniz.  
  
#### <a name="to-test-the-extension"></a>Uzantı sınamak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Görünüm**, **Sunucu Gezgini**.  
  
2.  Test etmek için kullanmak istediğiniz SharePoint sitesi altında göründüğünü doğrulayın **SharePoint bağlantıları** düğümünde **Sunucu Gezgini**. Bu listede yoksa, aşağıdaki adımları izleyin:  
  
    1.  Kısayol menüsünü açın **SharePoint bağlantıları**ve ardından **Bağlantı Ekle**.  
  
    2.  İçinde **SharePoint Bağlantı Ekle** iletişim kutusunda, bağlanmak ve ardından istediğiniz SharePoint sitesi için URL'yi girin **Tamam** düğmesi.  
  
         SharePoint sitesi geliştirme bilgisayarınızda belirtmek için şunu yazın **http://localhost**.  
  
3.  (Hangi sitenizin URL'sini görüntüler) site bağlantı düğümünü genişletin ve ardından bir alt site düğümünü genişletin (örneğin, **ekip sitesi**).  
  
4.  Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `NodeChildrenRequested` yöntemi ve projeyi hata ayıklamak devam etmek için F5 tuşuna'i seçin.  
  
5.  Visual Studio Deneysel örneğini genişletin **Web Bölümü Galerisi** en üst düzey sitesi düğümünün altında görünür düğüm.  
  
6.  Visual Studio'nun diğer örnek kodda, daha önce belirlediğiniz kesme noktası durdurur doğrulayın `CreateWebPartNodes` yöntemi ve projeyi hata ayıklamak devam etmek için F5 tuşuna'i seçin.  
  
7.  Visual Studio deneysel örneğinde bağlı sitesindeki tüm Web Bölümleri altında göründüğünü doğrulayın **Web Bölümü Galerisi** düğümünde **Sunucu Gezgini**.  
  
8.  Bir Web Bölümü için kısayol menüsünü açın ve ardından **özellikleri**.  
  
9. İçinde **özellikleri** penceresinde, Web bölümünü ayrıntılarını göründüğünü doğrulayın.  
  
10. İçinde **Sunucu Gezgini**, aynı Web Bölümü için kısayol menüsünü açın ve ardından **görünen ileti**.  
  
     Görüntülenen ileti kutusunda seçin **Tamam** düğmesi.  
  
## <a name="uninstalling-the-extension-from-visual-studio"></a>Visual Studio'dan uzantısını kaldırma  
 Testi uzantısı tamamladıktan sonra Visual Studio'dan kaldırın.  
  
#### <a name="to-uninstall-the-extension"></a>Uzantıyı kaldırmak için  
  
1.  Menü çubuğunda, Visual Studio'nun deneysel örneği seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantıları listesinden seçip **Web Bölümü Galerisi düğümü için Sunucu Gezgini**ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** düğmesi.  
  
4.  Seçin **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için düğmesi.  
  
     Proje öğesi de kaldırılır.  
  
5.  Visual Studio (deneysel örneği ve Visual Studio WebPartNode çözüm açıksa örneğini) hem örneklerini kapatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md)   
 [İzlenecek yol: Web bölümlerini görüntülemek için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Simgeler için görüntü Düzenleyicisi](/cpp/windows/image-editor-for-icons)   
 [Simge veya başka görüntü &#40; görüntü Düzenleyicisi simgeler &#41;oluşturma;](/cpp/windows/creating-an-icon-or-other-image-image-editor-for-icons)  
  
  