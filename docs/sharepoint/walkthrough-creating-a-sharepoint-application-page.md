---
title: "İzlenecek yol: SharePoint uygulama sayfası oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- application pages [SharePoint development in Visual Studio], developing
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 33c718707ce284179b69e33677d5b29f0d4433c7
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="walkthrough-creating-a-sharepoint-application-page"></a>İzlenecek Yol: SharePoint Uygulama Sayfası Oluşturma
 
Uygulama sayfası, ASP.NET sayfası özel bir biçimidir. Uygulama sayfaları SharePoint ana sayfa ile birleştirilmiş içeriği kapsar. Daha fazla bilgi için bkz: [oluşturma uygulama sayfaları SharePoint'in](../sharepoint/creating-application-pages-for-sharepoint.md).

Bu kılavuzda uygulama sayfası oluşturma ve yerel bir SharePoint sitesi kullanarak debug gösterilmektedir. Bu sayfa, her kullanıcının oluşturduğu veya sunucu grubundaki tüm sitelerde değiştiren tüm öğeleri gösterir.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Bir SharePoint projesi oluşturma.
- Uygulama sayfası SharePoint projesine ekleniyor.
- ASP.NET denetimleri uygulama sayfasına ekleme.
- ASP.NET denetimleri arka plan kod ekleniyor.
- Uygulama sayfası test etme.

> [!NOTE]
> Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Önkoşullar

- Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

## <a name="creating-a-sharepoint-project"></a>SharePoint Projesi Oluşturma

İlk olarak, oluşturma bir **boş SharePoint proje**. Daha sonra ekleyecek bir **uygulama sayfası** bu proje öğesi.

1. Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].

2. Açık **yeni proje** iletişim kutusunda, genişletin **Office/SharePoint** kullanın ve ardından istediğiniz dil düğümünde **SharePoint çözümlerini** düğümü.

3. İçinde **yüklü Visual Studio şablonları** bölmesinde seçin **SharePoint 2010 - boş proje** şablonu. Proje adı **MySharePointProject**ve ardından **Tamam** düğmesi.

     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir. Bu sihirbaz, proje ve çözüm güven düzeyini hata ayıklamak için kullanacağı site seçmenize olanak sağlar.

4. Seçin **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** varsayılan yerel SharePoint sitesi kabul et düğmesi.

## <a name="creating-an-application-page"></a>Uygulama Sayfası Oluşturma

Uygulama sayfası oluşturma, ekleme bir **uygulama sayfası** proje öğesi.

1. İçinde **Çözüm Gezgini**, seçin **MySharePointProject** projesi.

2. Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.

3. İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **uygulama sayfası (yalnızca Grup çözüm** şablonu.

4. Sayfa adı **SearchItems**ve ardından **Ekle** düğmesi.

     Visual Web Developer Tasarımcısı'nda uygulama sayfası görüntüler **kaynak** burada görebilirsiniz sayfanın HTML öğeleri görünüm. Tasarımcı işaretleme birkaç için görüntüler <xref:System.Web.UI.WebControls.Content> kontrol eder. Her denetim eşleyen bir <xref:System.Web.UI.WebControls.ContentPlaceHolder> varsayılan uygulama ana sayfada tanımlı denetim.

## <a name="designing-the-layout-of-the-application-page"></a>Uygulama Sayfasının Düzenini Tasarlama

Uygulama sayfası öğesi uygulama ASP.NET denetimleri eklemek için bir tasarımcı kullanmanıza olanak sağlar. Bu tasarımcı Visual Web Developer ile kullanılan aynı Tasarımcısı olur. Bir etiketi, bir radyo düğmesi listesi ve bir tabloya eklemek **kaynak** tasarımcısına görüntülemek ve tüm standart ASP.NET sayfası tasarlarken yaptığınız gibi özellikleri ayarlayın.

1. Menü çubuğunda seçin **Görünüm**, **araç**.

2. Standart düğümünde **araç**, aşağıdaki adımlardan birini gerçekleştirin:

    - Kısayol menüsünü açın **etiket** öğesi, seçin **kopya**, satırın altında için kısayol menüsünü açın **PlaceHolderMain** içerik denetimi Tasarımcısı'nda ve ardından seçin **Yapıştır**.

    - Sürükleme **etiket** gelen öğe **araç** gövdesini üzerine **PlaceHolderMain** içerik denetimi.

3. Eklemek için önceki adımı yineleyin bir **DropDownList** öğesi ve bir **tablo** öğesinin **PlaceHolderMain** içerik denetimi.

4. Designer'ı değerini değiştirme `Text` etiket denetimi özniteliği **tüm öğeleri göster**.

5. Designer'ı değiştirin `<asp:DropDownList>` olan aşağıdaki XML öğesi.

    ```xml
    <asp:DropDownList ID="DropDownList1" runat="server" AutoPostBack="true"
     OnSelectedIndexChanged="DropDownList1_SelectedIndexChanged">
        <asp:ListItem Text="Created by me" Value="Author"></asp:ListItem>
        <asp:ListItem Text="Modified by me" Value="Editor"></asp:ListItem>
    </asp:DropDownList>
    ```

## <a name="handling-the-events-of-controls-on-the-page"></a>Sayfadaki Denetim Olaylarını İşleme

Tüm ASP.NET sayfası gibi bir uygulama sayfasını denetimlerinde işleyin. Bu yordamda, işleyecek `SelectedIndexChanged` aşağı açılan listesinin olay.

1. Üzerinde **Görünüm** menüsünde seçin **kod**.

     Uygulama sayfası kod dosyası Kod Düzenleyicisi'nde açılır.

2. Aşağıdaki yöntemi ekleyin `SearchItems` sınıfı. Bu kod işleme <xref:System.Web.UI.WebControls.ListControl.SelectedIndexChanged> olayı <xref:System.Web.UI.WebControls.DropDownList> daha sonra bu kılavuzda oluşturacak bir yöntemini çağırarak.

     [!code-vb[SP_ApplicationPage#5](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#5)]
     [!code-csharp[SP_ApplicationPage#5](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#5)]

3. Aşağıdaki deyimleri uygulama sayfası kod dosyasının üstüne ekleyin.

     [!code-vb[SP_ApplicationPage#1](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#1)]
     [!code-csharp[SP_ApplicationPage#1](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#1)]

4. Aşağıdaki yöntemi ekleyin `SearchItems` sınıfı. Bu yöntem, sunucu grubundaki tüm siteleri dolaşır ve oluşturulan ya da geçerli kullanıcı tarafından değiştirilmiş öğeleri arar.

     [!code-vb[SP_ApplicationPage#2](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#2)]
     [!code-csharp[SP_ApplicationPage#2](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#2)]

5. Aşağıdaki yöntemi ekleyin `SearchItems` sınıfı. Bu yöntem tablosunda geçerli kullanıcı tarafından oluşturulmuş veya değiştirilmiş öğelerini görüntüler.

     [!code-vb[SP_ApplicationPage#3](../sharepoint/codesnippet/VisualBasic/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.vb#3)]
     [!code-csharp[SP_ApplicationPage#3](../sharepoint/codesnippet/CSharp/sp_applicationpage/layouts/sp_applicationpage/SearchItems.aspx.cs#3)]

## <a name="testing-the-application-page"></a>Uygulama Sayfasını Sınama

Projeyi çalıştırdığınızda, SharePoint sitesini açar ve uygulama sayfası görüntülenir.

1. İçinde **Çözüm Gezgini**uygulama sayfası için kısayol menüsünü açın ve ardından **başlangıç öğesi olarak ayarla**.

2. F5 tuşuna seçin.

     SharePoint sitesi açılır.

3. Uygulama sayfasında seçin **Tarafımdan değiştirildi** seçeneği.

     Uygulama sayfa yenilenir ve ardından, sunucu grubundaki tüm sitelerde değiştirdiğiniz tüm öğeleri görüntüler.

4. Uygulama sayfasında seçin **oluşturduğum** listesinde.

     Uygulama sayfa yenilenir ve sunucu grubundaki tüm sitelerde oluşturduğunuz tüm öğeleri görüntüler.

## <a name="next-ateps"></a>Sonraki ateps

SharePoint uygulama sayfaları hakkında daha fazla bilgi için bkz: [oluşturma uygulama sayfaları SharePoint'in](../sharepoint/creating-application-pages-for-sharepoint.md).

Visual Web Tasarımcısı aşağıdaki konulardan kullanarak SharePoint sayfası içeriği tasarlamak hakkında daha fazla bilgi edinebilirsiniz:

- [SharePoint için Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md).

- [Web Bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Uygulama Sayfası Oluşturma](../sharepoint/how-to-create-an-application-page.md)  
[Uygulama _layouts sayfa türü](http://go.microsoft.com/fwlink/?LinkID=169274)
