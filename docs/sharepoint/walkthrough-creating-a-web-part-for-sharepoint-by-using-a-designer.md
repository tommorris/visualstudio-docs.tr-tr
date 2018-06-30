---
title: 'İzlenecek yol: Tasarımcı kullanarak bir Web Bölümü SharePoint için oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], designer
- Web Parts [SharePoint development in Visual Studio], creating
- Web Parts [SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 01efc1972ea4833900b5e6f002d36ae51fa63a85
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120434"
---
# <a name="walkthrough-create-a-web-part-for-sharepoint-by-using-a-designer"></a>İzlenecek yol: Tasarımcı kullanarak bir web bölümü SharePoint için oluşturma

Bir SharePoint sitesi için web bölümleri oluşturursanız, kullanıcılarınızın doğrudan içerik, görünümü ve davranışı sitedeki sayfaların bir tarayıcı kullanarak değiştirebilirsiniz. Bu kılavuzda SharePoint kullanarak bir web bölümü görsel olarak oluşturmak gösterilmiştir **Visual Web Bölümü** Visual Studio Proje şablonu.

Oluşturacağınız web bölümü sitesinde aylık takvim görünümü ve her takvim listesi için onay kutusu görüntüler. Kullanıcılar, onay kutularını işaretleyerek aylık takvim görünümünde eklemek için hangi takvim listeler belirtebilirsiniz.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Kullanarak bir web bölümü oluşturma **Visual Web Bölümü** proje şablonu.
- Visual Studio'da Visual Web Developer Tasarımcısını kullanarak web bölümünü tasarlama.
- Web bölümü denetimlere olayları işlemek için kod ekleme.
- Web bölümü SharePoint test etme.

    > [!NOTE]
    > Bilgisayarınız aşağıdaki yönergelerde yer farklı adlar veya konumlar kullanıcı arabiriminin bazı öğeler için Visual Studio için gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Windows ve SharePoint sürümleri desteklenir. Bkz: [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

## <a name="create-a-web-part-project"></a>Bir web bölümü projesi oluşturma

İlk olarak kullanarak bir web bölümü projesi oluşturma **Visual Web Bölümü** proje şablonu.

1. Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kullanarak **yönetici olarak çalıştır** seçeneği.

2. Menü çubuğunda seçin **dosya** > **yeni** > **proje**.

     **Yeni proje** iletişim kutusu görüntülenir.

3. İçinde **yeni proje** iletişim kutusunda, ya da altında **Visual C#** veya **Visual Basic**, genişletin **Office/SharePoint**ve ardından seçin **SharePoint çözümlerini** kategorisi.

4. Şablonları listesinden seçip **SharePoint 2013 - Visual Web Bölümü** şablonu ve ardından **Tamam** düğmesi.

     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir. Bu sihirbazı kullanarak, proje ve çözüm güven düzeyini hata ayıklamak için kullanacağınız site belirtebilirsiniz.

5. İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, seçin **Grup çözümü olarak dağıtma** seçenek düğmesi.

6. Seçin **son** varsayılan yerel SharePoint sitesi kabul et düğmesi.

## <a name="designing-the-web-part"></a>Web bölümü tasarlama

Web bölümü denetimlerden ekleyerek tasarım **araç** Visual Web Developer Tasarımcı yüzeyine.

1. Visual Web Developer designer'ı seçin **tasarım** Tasarım görünümüne geçmek için sekme.

2. Menü çubuğunda seçin **Görünüm** > **araç**.

3. İçinde **standart** düğümünün **araç**, seçin **CheckBoxList** denetlemek ve aşağıdaki adımlardan birini gerçekleştirin:

    - Kısayol menüsünü açın **CheckBoxList** denetlemek, seçin **kopya**Tasarımcısı'nda ilk satırı için kısayol menüsünü açın ve ardından **Yapıştır**.

    - Sürükleme **CheckBoxList** gelen denetim **araç kutusu**ve ilk satırın Tasarımcısı'nda denetimi bağlanın.

4. Önceki adımı yineleyin, ancak bir düğme Tasarımcısı'nın bir sonraki satıra taşıma.

5. Tasarımcıda seçin **Button1** düğmesi.

6. Menü çubuğunda seçin **Görünüm** > **Özellikler penceresini**.

     **Özellikleri** penceresi açılır.

7. İçinde **metin** düğmesinin özelliğini girin **güncelleştirme**.

## <a name="handling-the-events-of-controls-on-the-web-part"></a>Web bölümü denetimlerin olaylarını işleme

Takvimler Ana Takvim görünümüne eklemek kullanıcının sağlayan kodu ekleyin.

1. Aşağıdaki adım kümelerinden birini uygulayın:

    - Tasarımcıda çift **güncelleştirme** düğmesi.

    - İçinde **özellikleri** penceresi **güncelleştirme** düğmesini tıklatın, seçin **olayları** düğmesi. İçinde **tıklatın** özelliği girin **Button1_Click**ve ardından Enter tuşuna seçin.

     Kod Düzenleyicisi'nde kullanıcı denetimi kod dosyasını açar ve `Button1_Click` olay işleyicisi görüntülenir. Daha sonra bu olay işleyicisi için kod ekleyeceksiniz.

2. Aşağıdaki deyimleri kullanıcı denetimi kod dosyasının üstüne ekleyin.

     [!code-vb[SP_VisualWebPart#1](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]
     [!code-csharp[SP_VisualWebPart#1](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]

3. Aşağıdaki kod satırını ekleyin `VisualWebPart1` sınıfı. Bu kod bir aylık takvim görünüm denetimi bildirir.

     [!code-vb[SP_VisualWebPart#2](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#2)]
     [!code-csharp[SP_VisualWebPart#2](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#2)]

4. Değiştir `Page_Load` yöntemi `VisualWebPart1` aşağıdaki kodla sınıfı. Bu kod aşağıdaki görevleri gerçekleştirir:

    - Aylık takvim görünümü kullanıcı denetimini ekler.

    - Bir onay kutusu her takvim listesi için sitesinde ekler.

    - Her görünür öğesi türü için bir şablon Takvim görünümünde belirtir.

     [!code-vb[SP_VisualWebPart#3](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#3)]
     [!code-csharp[SP_VisualWebPart#3](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#3)]

5. Değiştir `Button1_Click` yöntemi `VisualWebPart1` aşağıdaki kodla sınıfı. Bu kod öğeleri her seçili takvimden Ana Takvim görünümüne ekler.

     [!code-vb[SP_VisualWebPart#4](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#4)]
     [!code-csharp[SP_VisualWebPart#4](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#4)]

## <a name="test-the-web-part"></a>Web bölümü test

Projeyi çalıştırdığınızda, SharePoint sitesini açar. Web bölümü SharePoint Web Bölümü Galerisi'nde otomatik olarak eklenir. Bu projeyi test etmek için aşağıdaki görevleri gerçekleştirmeniz:

- Bir olay her iki ayrı takvim liste ekleyin.
- Web bölümünü bir web bölümü sayfasına ekleyin.
- Aylık takvim görünümünde eklemek için liste belirtin.

### <a name="to-add-events-to-calendar-lists-on-the-site"></a>Olaylar sitedeki Takvim listeleri eklemek için

1. Visual Studio'da, **F5** anahtarı.

     SharePoint sitesi açılır ve [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] Hızlı Başlatma çubuğu sayfada görünür.

2. Hızlı Başlatma çubuğunda altında **listeler**, seçin **Takvim** bağlantı.

     **Takvim** sayfası görüntülenir.

     Hızlı Başlatma çubuğunda hiçbir Takvim bağlantısı görünürse seçin **Site içeriğinin** bağlantı. Site içeriği sayfa görünmüyorsa bir **Takvim** öğesi, bir tane oluşturun.

3. Takvim sayfasında, bir gün seçin ve ardından **Ekle** bir olay eklemek için seçilen günün bağlantı.

4. İçinde **başlık** kutusuna **varsayılan takvim olayda**ve ardından **kaydetmek** düğmesi.

5. Seçin **Site içeriğinin** bağlamak ve ardından **bir uygulama ekleyin** döşeme.

6. Üzerinde **oluşturma** sayfasında, **Takvim** yazın, Takvim adını ve ardından **oluşturma** düğmesi.

7. Yeni takvim için bir olay eklemek için olay adı **özel Takvim olayda**ve ardından **kaydetmek** düğmesi.

### <a name="to-add-the-web-part-to-a-web-part-page"></a>Bir web bölümü sayfasına web bölümü eklemek için

1. Üzerinde **Site içeriğinin** sayfasında, açık **sitesi sayfalarını** klasör.

2. Şerit'te seçin **dosyaları** sekmesi, açık **yeni belge** menüsünde ve ardından **Web Bölümü sayfası** komutu.

3. Üzerinde **yeni Web Bölümü sayfası** sayfasında, sayfanın adı **SampleWebPartPage.aspx**ve ardından **oluşturma** düğmesi.

     Web bölümü sayfası görüntülenir.

4. Web bölümü sayfasının üst bölgede seçin **Ekle** sekmesini ve ardından **Web Bölümü** düğmesi.

5. Seçin **özel** klasörünü seçin **VisualWebPart1** web bölümü ve ardından **Ekle** düğmesi.

     Web bölümü sayfasında görüntülenir. Aşağıdaki denetimleri web bölümü görünür:

    - Aylık takvim görünümü.

    - Bir **güncelleştirme** düğmesi.

    - A **Takvim** onay kutusu.

    - A **özel Takvim** onay kutusu.

### <a name="to-specify-lists-to-include-in-the-monthly-calendar-view"></a>Aylık takvim görünümünde içerecek şekilde belirtmek için listeler

Aylık takvim görünümünde eklemek ve ardından istediğiniz takvimleri web bölümünde belirtmek **güncelleştirme** düğmesi.

Belirttiğiniz tüm takvimlerdeki olaylar aylık takvim görünümünde görünür.

## <a name="see-also"></a>Ayrıca bkz.

[SharePoint Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)  
[Nasıl yapılır: bir SharePoint web bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part.md)  
[İzlenecek yol: SharePoint için bir web bölümü oluşturma](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)
