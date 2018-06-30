---
title: 'İzlenecek yol: bir SharePoint proje uzantısı oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 407936d68310a675aebe1c7ea712f46aea45e807
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120667"
---
# <a name="walkthrough-create-a-sharepoint-project-extension"></a>İzlenecek yol: bir SharePoint proje uzantısı oluşturma
  Bu kılavuzda nasıl SharePoint projeleri için bir uzantı oluşturulacağı gösterilmektedir. Bir proje zaman eklenmiş, silinmiş veya yeniden adlandırılmış gibi proje düzeyi olaylarına tepki vermek için bir proje uzantısı kullanabilirsiniz. Ayrıca, özel özellikler ekleyebilir veya bir özellik değeri değiştiğinde yanıt. Proje öğesi uzantılarının aksine, project uzantıları belirli bir SharePoint proje türü ile ilişkilendirilemez. Bir proje uzantısı oluşturma, herhangi bir SharePoint proje türünü açıldığında uzantıyı yükler [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
 Bu kılavuzda, oluşturulan herhangi bir SharePoint projesine eklenen özel bir Boolean özelliği oluşturacak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Ayarlandığında **doğru**, yeni özellik ekler veya eşler, projenizin bir görüntüler kaynak klasörüne. Ayarlandığında **yanlış**, varsa görüntüler klasörüne kaldırıldı. Daha fazla bilgi için bkz: [nasıl yapılır: eşlenmiş klasörler ekleyip](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] aşağıdaki uzantısı SharePoint projeleri için:  
  
    -   Özel proje özelliği için Özellikler penceresini ekler. Özellik herhangi bir SharePoint projesine uygulanır.  
  
    -   Eşlenmiş bir klasör için bir proje eklemek için SharePoint projesi nesne modeli kullanır.  
  
    -   Kullanan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otomasyon nesne modeli (projeden eşlenen bir klasörü silmek için DTE).  
  
-   Derleme bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] proje özelliğin uzantı derlemesi dağıtmak için uzantı (VSIX) paketi.  
  
-   Hata ayıklama ve test proje özelliği.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için geliştirme bilgisayarındaki aşağıdaki bileşenler gerekir:  
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)], SharePoint ve [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. Bu kılavuzda kullanılır **VSIX proje** şablonunda [!INCLUDE[TLA2#tla_sdk](../sharepoint/includes/tla2sharptla-sdk-md.md)] proje özellik uzantısı dağıtmak için VSIX paket oluşturmak için. Daha fazla bilgi için bkz: [Visual Studio'da SharePoint araçları genişletmek](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="create-the-projects"></a>Projeleri oluşturma
 Bu izlenecek yolu tamamlamak için iki projeleri oluşturmanız gerekir:  
  
-   Proje uzantısı dağıtmak için VSIX paketi oluşturmak için bir VSIX proje.  
  
-   Proje uzantısı uygulayan bir sınıf kitaplığı proje.  
  
 İzlenecek yol projeleri oluşturarak başlayın.  
  
#### <a name="to-create-the-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya** > **yeni** > **proje**.  
  
3.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **genişletilebilirlik** düğümü.  
  
    > [!NOTE]  
    >  Bu düğüm, yalnızca Visual Studio SDK'sı yüklerseniz kullanılabilir. Daha fazla bilgi için bu konudaki Önkoşullar bölümüne bakın.  
  
4.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde ve ardından **VSIX proje** şablonu.  
  
5.  İçinde **adı** kutusuna **ProjectExtensionPackage**ve ardından **Tamam** düğmesi.  
  
     **ProjectExtensionPackage** proje görünür **Çözüm Gezgini**.  
  
#### <a name="to-create-the-extension-project"></a>Uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm düğümü için kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** düğümleri ve ardından **Windows**.  
  
3.  İletişim kutusunun üstündeki seçin **.NET Framework 4.5** .NET Framework sürümleri listesinde ve ardından **sınıf kitaplığı** proje şablonu.  
  
4.  İçinde **adı** kutusuna **ProjectExtension**ve ardından **Tamam** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **ProjectExtension** çözüme proje ve varsayılan Class1 kod dosyasını açar.  
  
5.  Class1 kod dosyasının projeden silin.  
  
## <a name="configure-the-project"></a>Projeyi Yapılandırma
 Proje uzantısı oluşturma için kod yazmadan önce ve uzantı projesi derleme başvurularını kod dosyaları ekleyin.  
  
#### <a name="to-configure-the-project"></a>Projeyi yapılandırmak için  
  
1.  Adlı bir kod dosyasına ekleyin **CustomProperty** ProjectExtension projeye.  
  
2.  Kısayol menüsünü açın **ProjectExtension** proje ve ardından **Başvuru Ekle**.  
  
3.  İçinde **başvuru Yöneticisi - CustomProperty** iletişim kutusunda, seçin **Framework** düğümü ve System.ComponentModel.Composition ve System.Windows.Forms derlemelerine yanındaki onay kutusunu seçin.  
  
4.  Seçin **uzantıları** düğümü, Microsoft.VisualStudio.SharePoint ve EnvDTE derlemeler yanındaki onay kutusunu seçin ve ardından **Tamam** düğmesi.  
  
5.  İçinde **Çözüm Gezgini**altında **başvuruları** için klasör **ProjectExtension** seçin, proje **EnvDTE**.  
  
6.  İçinde **özellikleri** penceresinde, değişiklik **birlikte çalışma türlerini katıştır** özelliğine **False**.  
  
## <a name="define-the-new-sharepoint-project-property"></a>Yeni SharePoint proje özelliği tanımlayın
 Proje uzantısı ve yeni proje özelliği davranışını tanımlayan bir sınıf oluşturun. Yeni proje uzantısı sınıfı uygulayan tanımlamak için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> arabirimi. Bir SharePoint proje için bir uzantı tanımlamak istediğiniz zaman bu arabirimi uygular. Ayrıca, ekleme <xref:System.ComponentModel.Composition.ExportAttribute> sınıfa. Bu öznitelik sağlar [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] bulmak ve yüklemek için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> uygulaması. Geçirmek <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> özniteliğin oluşturucuya türü.  
  
#### <a name="to-define-the-new-sharepoint-project-property"></a>Yeni SharePoint proje özelliği tanımlamak için  
  
1.  Aşağıdaki kod CustomProperty kod dosyasına yapıştırın.  
  
     [!code-vb[SPExt_ProjectExtension#1](../sharepoint/codesnippet/VisualBasic/projectextension/customproperty.vb#1)]
     [!code-csharp[SPExt_ProjectExtension#1](../sharepoint/codesnippet/CSharp/projectextension/customproperty.cs#1)]  
  
## <a name="build-the-solution"></a>Çözümü oluşturun
 Ardından, hatasız derlendiğinden emin olmak için çözümü oluşturun.  
  
#### <a name="to-build-the-solution"></a>Çözümü derlemek için  
  
1.  Menü çubuğunda seçin **yapı** > **yapı çözümü**.  
  
## <a name="create-a-vsix-package-to-deploy-the-project-property-extension"></a>Proje özelliği uzantısı dağıtmak için VSIX paket oluşturma
 Proje uzantısı dağıtmak için VSIX paketi oluşturmak için çözümünüz VSIX proje kullanın. İlk olarak VSIX paketi VSIX projeye dahil source.extension.vsixmanifest dosyasını değiştirerek yapılandırın. Çözümü derledikten sonra VSIX paketi oluşturun.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Yapılandırmak ve VSIX paketi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**source.extension.vsixmanifest dosya için kısayol menüsünü açın ve ardından **açmak** düğmesi.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] dosya bildirim Tasarımcısı'nda açılır. İçinde görüntülenen bilgileri **meta veri** sekmesi de görüntülenir **Uzantılar ve güncelleştirmeler**. Tüm VSIX paketi extension.vsixmanifest dosya gerektirir. Bu dosya hakkında daha fazla bilgi için bkz: [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  İçinde **ürün adı** kutusuna **özel Proje özelliği**.  
  
3.  İçinde **Yazar** kutusuna **Contoso**.  
  
4.  İçinde **açıklama** kutusuna **görüntüleri kaynak klasörünü projeye eşleme değiştirir özel bir SharePoint proje özelliği**.  
  
5.  Seçin **varlıklar** sekmesini ve ardından **yeni** düğmesi.  
  
     **Ekleme yeni varlık** iletişim kutusu görüntülenir.  
  
6.  İçinde **türü** listesinde, seçin **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Bu değer karşılık gelen `MEFComponent` extension.vsixmanifest dosyasındaki öğesi. Bu öğe VSIX paketi bir uzantı bütünleştirilmiş kodun adını belirtir. Daha fazla bilgi için bkz: [MEFComponent öğesi (VSX Şeması)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  İçinde **kaynak** listesinde, seçin **geçerli çözümdeki bir proje ile** seçenek düğmesi.  
  
8.  İçinde **proje** listesinde, seçin **ProjectExtension**.  
  
     Bu değer projede oluşturmakta olduğunuz derlemenin adını tanımlar.  
  
9. Seçin **Tamam** kapatmak için **ekleme yeni varlık** iletişim kutusu.  
  
10. Menü çubuğunda seçin **dosya** > **Tümünü Kaydet** zaman, son ve bildirim Tasarımcısı'nı kapatın.  
  
11. Menü çubuğunda seçin **yapı** > **yapı çözümü**ve projeyi hatasız derlendiğinden emin olun.  
  
12. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ProjectExtensionPackage** proje ve seçin **klasörünü dosya Gezgini'nde Aç** düğmesi.  
  
13. İçinde **dosya Gezgini**ProjectExtensionPackage proje derleme çıkış klasörünü açın ve klasörü ProjectExtensionPackage.vsix adlı bir dosya içerdiğini doğrulayın.  
  
     Varsayılan olarak, yapı çıktı klasördür... Proje dosyasını içeren klasörü altındaki \bin\Debug klasörünü.  
  
## <a name="test-the-project-property"></a>Proje özelliği test
 Artık özel Proje özelliği test etmek hazırsınız. Hata ayıklama ve yeni proje özellik uzantısı bir Deneysel kopyasında test en kolayıdır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Bu örneği [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] bir VSIX veya diğer genişletilebilirlik projesi çalıştırdığınızda oluşturulur. Projenin hata ayıklamasını sonra sisteminizde uzantısını yükleyin ve hata ayıklama ve normal bir kopyasında test devam [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
#### <a name="to-debug-and-test-the-extension-in-an-experimental-instance-of-visual-studio"></a>Hata ayıklama ve Visual Studio deneysel örneğinde uzantısı sınamak için  
  
1.  Yeniden [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] yönetici kimlik bilgilerini ve ProjectExtensionPackage çözümü açın.  
  
2.  Hata ayıklama derlemesi projenizin seçerek Başlat **F5** anahtar veya menü çubuğu seçme **hata ayıklama** > **hata ayıklamayı Başlat**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0Exp\Extensions\Contoso\Custom proje Property\1.0 uzantıyı yükleyen ve Deneysel bir örneğini başlatır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
3.  Deneysel örneğinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bir Grup çözümü için SharePoint projesi oluşturun ve sihirbazdaki diğer değerler için varsayılan değerleri kullanın.  
  
    1.  Menü çubuğunda seçin **dosya** > **yeni** > **proje**.  
  
    2.  Üstündeki **yeni proje** iletişim kutusunda, seçin **.NET Framework 3.5** .NET Framework sürümleri listesinde.  
  
         SharePoint araç uzantıları gerektiren özellikler bu sürümünde [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].  
  
    3.  Altında **şablonları** düğümünü genişletin **Visual C#** veya **Visual Basic** düğümü seçin **SharePoint** düğümü ve 'iseçin**2010** düğümü.  
  
    4.  Seçin **SharePoint 2010 proje** şablonu ve ardından girin **ModuleTest** projenizin adı olarak.  
  
4.  İçinde **Çözüm Gezgini**, seçin **ModuleTest** proje düğümüne.  
  
     Yeni bir özel özellik **Haritası görüntüler klasörüne** görünür **özellikleri** varsayılan değerini penceresiyle **False**.  
  
5.  Bu özelliğin değerini değiştirmek **doğru**.  
  
     Görüntüleri kaynak klasörünü SharePoint projesine eklenir.  
  
6.  Bu özelliğin değeri başa değişiklik **False**.  
  
     Seçerseniz **Evet** düğmesini **görüntüler klasörüne silme?** iletişim kutusu, kaynak klasörünü, SharePoint projeden silinir görüntüler.  
  
7.  Deneysel örneklerini kapatın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint projeleri genişletme](../sharepoint/extending-sharepoint-projects.md)   
 [Nasıl yapılır: SharePoint projelerine özellik ekleme](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [SharePoint Proje sistem türleri ve diğer Visual Studio Proje türleri arasında dönüştürme](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)  
  
