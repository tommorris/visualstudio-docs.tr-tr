---
title: "İzlenecek yol: bir temel Site tanımı projesi oluşturma | Microsoft Docs"
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
- SharePoint development in Visual Studio, site definitions
- site definitions [SharePoint development in Visual Studio]
ms.assetid: b0df5b0e-5fa0-43d8-a339-6d92f1276764
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9bea8fec27b0d53fb1cfe3405d39d271a93f5a8d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-create-a-basic-site-definition-project"></a>İzlenecek yol: Temel bir Site Tanımı Projesi Oluşturma
  Bu kılavuzda, üzerinde bazı denetimler ile visual Web bölümünü içeren bir temel site tanımı oluşturulacağını gösterir. Daha anlaşılır olması amacıyla, yalnızca birkaç denetimleri oluşturduğunuz visual Web bölümü vardır. Ancak, daha fazla işlevsellik dahil daha karmaşık SharePoint site tanımları oluşturabilirsiniz.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Kullanarak bir site tanımı oluşturma [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] proje şablonu.  
  
-   SharePoint site tanımı kullanarak bir SharePoint sitesi oluşturuluyor.  
  
-   Visual Web Bölümü çözüme ekleniyor.  
  
-   Yeni visual Web Bölümünü ekleyerek sitenin default.aspx sayfasını özelleştirme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Microsoft Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: SharePoint çözümleri geliştirmek için gereksinimleri.  
  
-   Visual Studio.  
  
## <a name="creating-a-site-definition-solution"></a>Site Tanımı Çözümü Oluşturma  
 İlk olarak, site tanımı projesi oluşturun [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
#### <a name="to-create-a-site-definition-project"></a>Bir site tanımı projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**. Menü çubuğunda Visual Basic geliştirme ayarlarını kullanmak için IDE'yi ayarlarsanız seçin **dosya**, **yeni proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  Genişletin **Visual C#** düğümü veya **Visual Basic** düğümünü genişletin **SharePoint** düğümü ve ardından **2010** düğümü.  
  
3.  İçinde **şablonları** listesinde, seçin **SharePoint 2010 proje** şablonu.  
  
4.  İçinde **adı** kutusuna **TestSiteDef**ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
5.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, istediğiniz site tanımı hata ayıklamak için SharePoint sitesi için URL'yi girin veya varsayılan konumu kullanın (http://*sistem adı*/).  
  
6.  İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, seçin **Grup çözümü olarak dağıtma** seçenek düğmesi.  
  
     Tüm site tanımı projeleri küme çözümleri dağıtılması gerekir. Küme çözümleri karşı korumalı çözümler hakkında daha fazla bilgi için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  Seçin **son** düğmesi.  
  
     Proje görünür **Çözüm Gezgini**.  
  
8.  İçinde **Çözüm Gezgini**, proje düğümünü seçin ve ardından, menü çubuğunda, **proje**, **Yeni Öğe Ekle**.  
  
9. Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
10. İçinde **şablonları** bölmesinde seçin **Site tanımı** şablonu, bırakın **adı** olarak **SiteDefinition1**ve ardından seçin **Ekleme** düğmesi.  
  
## <a name="create-a-visual-web-part"></a>Visual Web Bölümü Oluşturma  
 Ardından, site tanımının ana sayfasında görünmesi visual Web bölümü oluşturun.  
  
#### <a name="to-create-a-visual-web-part"></a>Görsel bir Web bölümü oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, seçin **tüm dosyaları göster** düğmesi.  
  
2.  Seçin **SiteDefinition1** proje düğümünü ve ardından, menü çubuğunda, **proje**, **Yeni Öğe Ekle**.  
  
     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.  
  
3.  Genişletin **Visual C#** düğümü veya **Visual Basic** düğümünü genişletin **SharePoint** düğümü ve ardından **2010** düğümü.  
  
4.  Şablonları listesinden seçip **Visual Web Bölümü** şablon, varsayılan VisualWebPart1 adlandırın ve ardından canlı **Ekle** düğmesi.  
  
     VisualWebPart1.ascx dosyasını açar.  
  
5.  Forma üç denetim eklemek için aşağıdaki biçimlendirmeyi VisualWebPart1.ascx alt kısmındaki ekleyin: bir metin kutusu, bir düğmeyi ve bir etiketi:  
  
    ```  
    <table>  
      <tr>  
        <td>  
          <asp:TextBox runat="server" ID="tbName"></asp:TextBox>  
        </td>  
        <td>  
          <asp:Button runat="server" ID="btnSubmit" Text = "Change Label Text" OnClick="btnSubmit_Click"></asp:Button>  
        </td>  
        <td>  
          <asp:Label runat="server" ID="lblName"></asp:Label>  
        </td>  
      </tr>  
    </table>  
    ```  
  
6.  VisualWebPart1.ascx altında VisualWebPart1.ascx.cs dosyasını açın (için [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)]) veya VisualWebPart1.ascx.vb (için [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) ve ardından aşağıdaki kodu ekleyin:  
  
     [!code-vb[SP_SimpleSiteDef#1](../sharepoint/codesnippet/VisualBasic/testsitedefvb/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]
     [!code-csharp[SP_SimpleSiteDef#1](../sharepoint/codesnippet/CSharp/testsitedef/sitedefinition/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]  
  
     Bu kod web bölümünün düğmesini tıklatın için işlevsellik ekler.  
  
## <a name="add-the-visual-web-part-to-the-default-aspx-page"></a>Varsayılan ASPX Sayfasına Visual Web Bölümünü Ekleme  
 Ardından, visual Web Bölümü site tanımının varsayılan ASPX sayfasına ekleyin.  
  
#### <a name="to-add-a-visual-web-part-to-the-default-aspx-page"></a>Varsayılan ASPX sayfasına bir görsel Web Bölümü eklemek için  
  
1.  Default.aspx sayfasını açın ve ardından altında aşağıdaki satırı ekleyin `WebPartPages` etiketi:  
  
    ```  
    <%@ Register Tagprefix="MyWebPartControls" Namespace="TestSiteDef.VisualWebPart1" Assembly="$SharePoint.Project.AssemblyFullName$" %>  
    ```  
  
     Bu satırı adı MyWebPartControls Web Bölümü ve kendi kod ile ilişkilendirir. *Namespace* parametreyle eşleşen VisualWebPart1.ascx kod dosyasında kullanılan ad.  
  
2.  Sonra `</asp:Content>` öğesi, tüm Değiştir `ContentPlaceHolderId="PlaceHolderMain"` bölüm ve içeriğini aşağıdaki kodla:  
  
    ```  
    <asp:Content ID="Content1" ContentPlaceHolderId="PlaceHolderMain" runat="server">  
        <MyWebPartControls:VisualWebPart1 runat="server" />      
    </asp:Content>  
    ```  
  
     Bu kod, daha önce oluşturduğunuz visual Web Bölümü için bir başvuru oluşturur.  
  
3.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SiteDefinition1** düğümünü ve ardından **başlangıç öğesi olarak ayarla**.  
  
## <a name="deploy-and-run-the-site-definition-solution"></a>Site Tanım Çözümü Çalıştırma ve Dağıtma  
 Ardından, SharePoint için projeyi dağıtın ve ardından Proje çalıştırın.  
  
#### <a name="to-deploy-and-run-the-site-definition"></a>Site tanımını dağıtmak ve çalıştırmak için  
  
-   Menü çubuğunda seçin **yapı**, **dağıtmak TestSiteDef**.  
  
-   F5 tuşuna seçin.  
  
     Visual Studio kodu derler özelliklerini ekler, dosyaların tümünü bir SharePoint çözüm (WSP) dosyasına paketleri ve WSP dosyasını SharePoint sunucusuna dağıtır. SharePoint dosyalarını yükler ve özellikleri etkinleştirir.  
  
## <a name="create-a-site-based-on-the-site-definition"></a>Site Tanımını Temel Alan Bir Site Oluşturma  
 Ardından, yeni site tanımı kullanarak bir site oluşturun.  
  
#### <a name="to-create-a-site-by-using-the-site-definition"></a>Site tanımını kullanarak bir site oluşturmak için  
  
1.  SharePoint sitesinde yeni bir SharePoint sitesi sayfası görüntülenir.  
  
2.  İçinde **başlığı ve açıklamayı** bölümünde, girin **Yeni Sitem** başlık ve sitenin açıklaması.  
  
3.  İçinde **Web sitesi adresi** bölümünde, girin **YeniSitem** içinde **URL adı** kutusu.  
  
4.  İçinde **şablonu** bölümünde, seçin **SharePoint özelleştirmeleri** sekmesi.  
  
5.  İçinde **bir şablon seçin** listesinde, seçin **SiteDefinition1**.  
  
6.  Diğer ayarları varsayılan değerlerinde bırakın ve ardından **oluşturma** düğmesi.  
  
     Yeni site görüntülenir.  
  
## <a name="test-the-new-site"></a>Yeni Siteyi sına  
 Ardından, yeni sitenin düzgün çalışıp çalışmadığını doğrulamak için test edin.  
  
#### <a name="to-test-the-new-site"></a>Yeni siteyi sınamak için  
  
-   Varsayılan ASPX sayfasında metinleri girin ve ardından **değişiklik etiket metnini** metin kutusunun yanında düğmesi.  
  
     Metin etiketi düğmesinin sağ tarafında görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: olay alıcısı oluşturma](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  