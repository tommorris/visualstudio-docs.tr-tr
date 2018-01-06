---
title: "İzlenecek yol: özel bir ana sayfa ve Site içeri aktarma bir görüntüyle | Microsoft Docs"
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
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
ms.assetid: d1703957-81e2-47e1-b4ca-6a8d550d8da2
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: ef55a90b55314bf7ab2c5aa6259f09b62a350da3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-import-a-custom-master-page-and-site-page-with-an-image"></a>İzlenecek yol: Bir Görüntü İçeren Özel bir Ana Sayfa ve Site Sayfasını İçeri Aktarma
  Bu anlatımda bir SharePoint özel ana sayfa ve görüntüye sahip bir site sayfası nasıl içeri aktarılacağı gösterilir bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint Proje.  
  
 Bu kılavuz aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir:  
  
-   Özel bir ana sayfa ve site sayfasını SharePoint Tasarımcısı'nda bir görüntüsünü kullanarak oluşturun.  
  
-   Özel ana sayfa, görüntü ve site sayfasını bir SharePoint çözüm (.wsp) dosyasına aktarın.  
  
-   İçeri aktarın ve dağıtın .wsp dosyasına bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] alma SharePoint çözüm paketi proje kullanarak SharePoint Proje.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenler yüklü olmalıdır:  
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] ve SharePoint. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
-   SharePoint Designer 2010.  
  
## <a name="create-items-in-sharepoint-designer"></a>SharePoint Tasarımcısı'nda öğeleri oluşturma  
 Bu örnek üç öğelerinin SharePoint Tasarımcısı'nda dışa aktarmak için nasıl oluşturulacağını gösterir: özel bir ana sayfa, özel ana sayfa ve site sayfasında görüntülenecek bir görüntü dosyasına başvuruda bulunan bir site sayfası. Görüntü SharePoint /images/ klasöründe eklenir.  
  
#### <a name="to-create-a-custom-master-page-in-sharepoint-designer"></a>SharePoint Tasarımcısı'nda bir özel ana sayfa oluşturmak için  
  
1.  Gezinti bölmesinde, SharePoint Tasarımcısı'nda seçin **ana sayfalar** site nesnesi.  
  
2.  Üzerinde **ana sayfalar** Şerit, seçin **boş ana sayfa**.  
  
3.  Yeni ana sayfa seçin ve ardından **ana sayfalar** Şerit, seçin **Düzenle dosya**.  
  
4.  SharePoint Designer'ın altındaki seçin **kod** sekmesi.  
  
5.  Varolan biçimlendirme aşağıdaki biçimlendirme ile değiştirin.  
  
    ```  
    <%@ Master Language="C#" %>  
    <%@ Register tagprefix="SharePoint" namespace="Microsoft.SharePoint.WebControls" assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <html dir="ltr">  
    <head runat="server">  
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">  
    <SharePoint:RobotsMetaTag runat="server" __designer:Preview="" __designer:Values="<P N='InDesign' T='False' /><P N='ID' T='ctl00' /><P N='Page' ID='1' /><P N='TemplateControl' ID='2' /><P N='AppRelativeTemplateSourceDirectory' R='-1' />"></SharePoint:RobotsMetaTag>  
    <title>Web Page</title>  
    </head>  
    <body>  
    <form id="form1" runat="server">  
    <asp:ContentPlaceHolder id="ContentPlaceHolderMain"   
            runat="server">  
          </asp:ContentPlaceHolder>  
    </form>  
    </body>  
    </html>  
    ```  
  
6.  Sayfayı kaydedin, seçin **ana sayfalar** sekmesini tıklatın ve ana sayfa olarak yeniden adlandır **mybasic1.master**.  
  
## <a name="add-an-image-to-the-content-database-in-sharepoint-designer"></a>SharePoint Designer içerik veritabanında bir görüntü ekleyin  
 Artık site sayfasında görüntülenecek bir görüntü ekleyebilirsiniz. Görüntü SharePoint içerik veritabanını dağıtılır.  
  
#### <a name="to-add-an-image-to-the-content-database-in-sharepoint-designer"></a>SharePoint Designer içerik veritabanında bir resim eklemek için  
  
1.  Gezinti Bölmesi'nde seçin **tüm dosyaları** site nesne ve ardından, ağaç görünümünde **görüntüleri** klasör.  
  
2.  Üzerinde **tüm dosyaları** Şerit, seçin **alma dosyaları**, tercih ettiğiniz bir dosya seçin ve ardından **Tamam** düğmesi. Bu örnekte, dosya adında **myimg1.png**.  
  
     İsteğe bağlı olarak, görüntüleri düzenlenmesine yardımcı olmak için bir alt klasör oluşturabilirsiniz.  
  
3.  Kapat **alma** iletişim kutusu.  
  
## <a name="create-a-site-page"></a>Bir Site sayfası oluşturun  
 Bu temel site sayfası özel ana sayfa kullanır ve önceki adımda eklediğiniz görüntüsünü görüntüler.  
  
#### <a name="to-create-a-site-page"></a>Bir site sayfası oluşturmak için  
  
1.  Gezinti Bölmesi'nde seçin **sitesi sayfalarını** nesnesi.  
  
2.  Üzerinde **sayfaları** Şerit, seçin **sayfa** düğmesini tıklatın, seçin **ASPX** sayfa türü ve yeni dosya adı **mycontentpage1.aspx**.  
  
     İsteğe bağlı olarak, site sayfaları düzenlenmesine yardımcı olmak için bir alt klasör oluşturabilirsiniz.  
  
3.  Site sayfa listesinden seçin **MyContentPage1.aspx** , Özellikler sayfasını açın ve ardından sayfanın alt kısmındaki seçin **düzenleme dosya** bağlantı.  
  
     Bir ileti görüntülenir ve bu sayfa güvenli modda düzenlenebilir bölgeler içermiyor diyor ve bu sayfayı Gelişmiş modunda açın, seçin isteyip istemediğinizi sorar **Evet** düğmesi.  
  
4.  Sayfanın alt kısmındaki seçin **kod** düğmesi.  
  
5.  Varolan biçimlendirme aşağıdaki biçimlendirme ile değiştirin.  
  
    ```  
    <%@ Import Namespace="Microsoft.SharePoint.ApplicationPages" %>  
    <%@ Register Tagprefix="SharePoint" Namespace="Microsoft.SharePoint.WebControls" Assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Register Tagprefix="Utilities" Namespace="Microsoft.SharePoint.Utilities" Assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Register Tagprefix="asp" Namespace="System.Web.UI" Assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" %>  
    <%@ Import Namespace="Microsoft.SharePoint" %>  
    <%@ Assembly Name="Microsoft.Web.CommandUI, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Page Language="C#" Inherits="Microsoft.SharePoint.WebControls.LayoutsPageBase" MasterPageFile="../_catalogs/masterpage/mybasic1.master" meta:progid="SharePoint.WebPartPage.Document" %>  
  
    <asp:Content ID="Main" ContentPlaceHolderID="ContentPlaceHolderMain" runat="server">  
    <img alt="My Image" longdesc="My image from images folder" src="../images/myimg1.png" />  
    </asp:Content>  
    ```  
  
6.  Güncelleştirilmiş site sayfası kaydedin.  
  
## <a name="export-the-items-from-sharepoint"></a>Dışa Aktar SharePoint'ten öğeleri  
 Öğeleri SharePoint'ten bir SharePoint çözüm (.wsp) dosyasına aktarın.  
  
#### <a name="to-export-items-from-sharepoint-designer"></a>Öğeleri SharePoint Tasarımcısı'ndan dışarı aktarmak için  
  
1.  Gezinti bölmesinde, SharePoint Tasarımcısı'nda seçin **ekip sitesi** nesnesi ve ardından **Site** Şerit, seçin **şablon olarak Kaydet**.  
  
2.  İçinde **şablon olarak Kaydet** iletişim kutusunda, bir dosya adı ve şablon adı, select girin **dahil içerik** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
     Bu sitenin içeriğini .wsp dosyasına kaydeder.  
  
3.  Çözüm aktarır sonra tercih **çözüm Galerisi** kullanılabilir çözüm dosyaların listesini görüntülemek için bağlantı.  
  
4.  Yeni .wsp dosyası için kısayol menüsünü açın ve ardından **Hedefi Farklı Kaydet** sistemine kaydetmek için.  
  
## <a name="import-the-items-into-visual-studio"></a>Öğeleri Visual Studio'ya içeri aktarma  
 .wsp aktarmak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. İçerik alındıktan sonra özelleştirin, daha fazla öğe ekleyin ve ardından dağıtın.  
  
#### <a name="to-import-items-from-the-wsp-file-into-visual-studio"></a>Visual Studio'ya .wsp dosyasından öğelerini içe aktarmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], oluşturma bir **alma SharePoint 2010 çözüm paketi** projesi.  
  
2.  Üzerinde **almak için öğeleri seçin** sayfasında **Modülü** içinde **türü** sütun, içeri aktarma için aşağıdaki tabloda yalnızca dosyalar için onay kutularını seçin.  
  
    |Dosya Adı|Açıklama|  
    |---------------|-----------------|  
    |_catalogsmasterpage\_|Özel ana sayfa.|  
    |images_|SharePoint dosya sistemindeki görüntü dosyası.|  
    |SitePages_|Sitesi sayfası.|  
  
3.  Seçin **son** seçilen öğeleri içe aktarmak için düğmeyi.  
  
4.  İçinde **Çözüm Gezgini**, _catalogsmasterpage seçin\_ düğümü ve değerini kendi **dağıtım Çakışma çözümlemesi** özelliğine **otomatik**.  
  
     Bu, herhangi bir dağıtım çakışması otomatik olarak çözülen sağlamaya yardımcı olur.  
  
5.  Yeni ana sayfanızın varolan bir sayfayı aynı ada sahipse, var olan sayfanın varsayılan bir ana sayfa veya SharePoint Tasarımcısı'nda bir özel ana sayfası olarak işaretlenmemiş emin olun.  
  
     Varolan bir ana sayfayı varsayılan ana sayfa veya özel bir ana sayfa olarak işaretlenmişse, ana sayfa silinemiyor belirten bir dağıtım hatası alırsınız. Bu sorunu önlemek için şunu yapın:  
  
    -   Geçici olarak başka bir ana sayfa varolan ana sayfa varsayılan ana sayfa olarak ayarlanırsa, varsayılan ana sayfa olarak ayarlayın. SharePoint için dosyaları dağıttıktan sonra yeni ana sayfanızın varsayılan ana sayfa olarak ayarlayın.  
  
    -   Geçici olarak başka bir ana sayfa varolan ana sayfa özel bir ana sayfa olarak ayarlanırsa, özel bir ana sayfa olarak ayarlayın. SharePoint için dosyaları dağıttıktan sonra yeni ana sayfanızın özel bir ana sayfa olarak ayarlayın.  
  
6.  Menü çubuğunda seçin **yapı**, **çözümü Dağıt**.  
  
7.  Dağıtılan öğeleri görüntülemek için SharePoint sitesini açın.  
  
 Dosyaları içine aktarmak için alternatif bir yol [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve onlara dağıtmanız SharePoint olan modüllere dosyaları eklemek için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][Nasıl yapılır: bir ana sayfa veya temayı içeri aktarma](../sharepoint/how-to-import-a-master-page-or-theme.md) ve [çözümde dosyaları eklemeyi modüllerini kullanma](../sharepoint/using-modules-to-include-files-in-the-solution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mevcut bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [Web Bölümleri veya Uygulama Sayfaları için Yeniden Kullanılabilir Denetimler Oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  