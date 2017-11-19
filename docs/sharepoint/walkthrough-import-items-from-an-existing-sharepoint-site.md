---
title: "İzlenecek yol: Mevcut bir SharePoint sitesinden öğeleri içeri aktarma | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
ms.assetid: faac3309-88d7-4fb2-8392-feda07fc00e5
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 602615426a8aeca118f6faba65e21778136b0ce6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-import-items-from-an-existing-sharepoint-site"></a>İzlenecek yol: Mevcut bir SharePoint Sitesinden Öğeleri İçeri Aktarma
  Bu anlatımda bir SharePoint sitesinden öğeleri içeri aktarma gösterilir bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint Proje.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Özel site sütunu ekleyerek bir SharePoint sitesi özelleştirme (olarak da bilinen bir *alan*.  
  
-   Bir SharePoint sitesi .wsp dosyasına dışarı aktarma.  
  
-   .Wsp dosyasına içe [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] .wsp alma proje kullanarak SharePoint.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] ve SharePoint. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="customizing-a-sharepoint-site"></a>Bir SharePoint sitesi özelleştirme  
 Bu örnekte, oluşturabilir ve bir SharePoint alt site için yeni bir site sütunu ekleyerek ve daha sonra kullanmak için başka bir alt site oluşturma özelleştirebilirsiniz. Daha sonra ilk alt .wsp dosyasına aktarın ve ardından özel site sütunu ikinci alt siteye .wsp alma projesi kullanarak içeri aktarın.  
  
#### <a name="to-create-and-customize-a-sharepoint-site"></a>Oluşturma ve bir SharePoint sitesi özelleştirmek için  
  
1.  Http:// gibi bir Web tarayıcısı kullanarak bir SharePoint sitesi açmak*sistem adı*/SitePages/Home.aspx.  
  
2.  Bir alt ana SharePoint site dışına açarak oluşturmak **Site eylemleri** menüsüne ve ardından seçme **Yeni Site**.  
  
3.  Sitenin **oluşturma** iletişim kutusunda, seçin **boş Site** türü.  
  
4.  İçinde **başlık** kutusuna **Site sütun Test 1**; **URL adı** kutusuna **columntest1**; diğer ayarlar, varsayılan olarak bırakın değerleri; ve ardından **oluşturma** düğmesi.  
  
5.  Site oluşturulduktan sonra tarayıcıya ana site gezinme http://*sistem adı*/SitePages/Home.aspx.  
  
6.  Tekrar açarak ana SharePoint site dışına boş bir alt oluşturmak **Site eylemleri** menüsünde seçerek **Yeni Site**ve ardından **boş Site** türü.  
  
7.  İçinde **başlık** kutusuna **Site sütunu Test 2**; **URL adı** kutusuna **columntest2**; diğer ayarlar, varsayılan olarak bırakın değerleri; ve ardından **oluşturma** düğmesi.  
  
8.  İlk alt siteye geri gidin http://*SystemName*/columntest1/default.aspx.  
  
9. Üzerinde **Site eylemleri** menüsünde seçin **Site Ayarları** Site Ayarları sayfasında görüntülenecek.  
  
10. İçinde **galerileri** bölümünde, seçin **Site sütunları** bağlantı.  
  
11. Üstündeki **Site sütun galerisini** sayfasında, **oluşturma** düğmesi.  
  
12. İçinde **sütun adı** kutusuna **Test sütun**diğer varsayılan değerleri koruyun ve ardından **Tamam** düğmesi.  
  
13. **Test sütun** sütunu görünür altında özel sütun başlığı Site sütunu Galerisi'nde.  
  
## <a name="exporting-the-sharepoint-site"></a>SharePoint sitesi dışarı aktarma  
 Ardından, SharePoint öğelerini ve içeri aktarmak istediğiniz öğeleri içeren bir SharePoint kurulumu (.wsp) dosyası elde, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint Proje. .Wsp dosyası zaten yoksa, sonra var olan bir SharePoint sitesinden oluşturmanız gerekir. Bu örnekte, varsayılan SharePoint sitesi .wsp dosyasına aktarır.  
  
> [!IMPORTANT]  
>  Aşağıdaki yordamı gerçekleştirmeden çalışma zamanı hatası alırsanız, SharePoint sitesine erişimi olan bir sistemde yordamı yapmanız gerekir.  
  
#### <a name="to-export-an-existing-sharepoint-site"></a>Var olan bir SharePoint sitesi dışarı aktarmak için  
  
1.  SharePoint sitesi seçin **Site Ayarları** üzerinde **Site eylemleri** Site Ayarları sayfasında görüntülenecek sekmesi.  
  
2.  İçinde **Site eylemleri** bölüm Site Ayarları sayfasında, seçin **şablon olarak Kaydet site** bağlantı.  
  
3.  İçinde **dosya adı** kutusuna **ExampleSite**hem de **şablon adı** kutusuna **örnek Site**.  
  
4.  Bu örnekte, bırakın **dahil içerik** onay kutusunun işaretini kaldırın.  
  
     Bu kutuyu seçerseniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] tüm listeleri ve belge kitaplıklarını ve bunların içeriğini .wsp dosyasına kaydeder. Bazı durumlarda kullanışlıdır ancak bu örnek için gerekli değildir.  
  
5.  İşlem başarıyla tamamlandığında seçin **çözüm Galerisi** .wsp dosyayı görüntülemek için bağlantı.  
  
     Daha sonra açık Çözümleri Galerisi sayfasını görüntülemek için **Site eylemleri** menüsünde seçin **Site Ayarları**, seçin **en üst düzey site ayarlarına Git** bağlamak  **Site Koleksiyonu Yönetimi** bölümünde ve ardından **çözümleri** bağlamak **galerileri** bölümü.  
  
6.  Çözümleri Galerisi'nde seçin **ExampleSite** bağlantı.  
  
7.  İçinde **dosyasını indirin** iletişim kutusunda, seçin **kaydetmek** düğmesi yüklemeleri klasörünüzdeki varsayılan olarak yerel sisteminizde dosyayı kaydedin.  
  
## <a name="importing-the-wsp-file"></a>.Wsp dosya alma  
 (Özel site sütun Test sütun) yeniden kullanmak istediğiniz öğeyi içeren bir .wsp dosyası sahip olduğunuza göre erişmek için .wsp dosyasını içeri aktarın.  
  
#### <a name="to-import-a-wsp-file"></a>.Wsp dosyasını içeri aktarmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], menü çubuğunda seçin **dosya**, **yeni**, **proje** görüntülemek için **yeni proje** iletişim kutusu. Menü çubuğunda Visual Basic geliştirme ayarlarını kullanmak için IDE'yi ayarlarsanız seçin **dosya**, **yeni proje**.  
  
2.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
3.  Seçin **alma SharePoint 2010 çözüm paketi** şablonunda **şablonları** bölmesinde WspImportProject1 olarak projesinin adı bırakın ve ardından **Tamam** düğme.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
4.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** want [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] daha önce oluşturduğunuz ikinci SharePoint alt site için. Yeni özel ekleyeceksiniz http:// öğesi, alan*sistem adı*o alt sitede /columntest2.  
  
5.  İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, seçimi olarak bırakın **korumalı bir çözüm olarak dağıtma**.  
  
6.  İçinde **yeni proje kaynak** sayfasında, sistem üzerindeki kaydettiğiniz .wsp dosyası önceden konumuna göz atın ve ardından **sonraki** düğmesi.  
  
    > [!NOTE]  
    >  Seçerseniz **son** bu sayfada, .wsp dosyasındaki tüm kullanılabilir öğeler düğmesi içeri aktarılacak.  
  
7.  İçinde **almak için öğeleri seçin** kutusunda, tüm dışında listesinde onay kutularını temizleyin **Test sütun**ve ardından **son** düğmesi.  
  
     Liste çok sayıda öğe içerdiğinden, Ctrl + A tuşlarını listesinde, tüm öğeleri seçmek için onay kutularının tümünü temizlemek için Ara çubuğuna anahtarı seçin ve yalnızca onay kutusunun yanına seçin seçebilirsiniz **Test sütun** öğesi.  
  
     İçeri aktarma işlemi tamamlandığında sonra adlı yeni bir proje **WspImportProject1** oluşturulan adlı bir klasör içeren **alanları**. Bu klasörde özel site sütundur **Test sütun** ve Elements.xml tanımı dosyası.  
  
## <a name="deploying-the-project"></a>Projeyi dağıtma  
 Son olarak, dağıtmak **WspImportProject1** ikinci SharePoint alt site özel site sütunu görüntülemek için daha önce oluşturduğunuz.  
  
#### <a name="to-deploy-the-project"></a>Projeyi dağıtmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], dağıtmak ve .wsp alma proje çalıştırmak için F5 tuşuna seçin.  
  
2.  SharePoint sitesinde açın **Site eylemleri** menüsünde ve ardından **Site Ayarları** Site Ayarları sayfasında görüntülenecek.  
  
3.  İçinde **galerileri** bölümünde, seçin **Site sütunları** bağlantı.  
  
4.  Ekranı aşağı kaydırarak **özel sütunları** bölümü.  
  
     İlk SharePoint sitesinden alınan özel site sütun listesinde görüntülendiğine dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mevcut bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [Web Bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  