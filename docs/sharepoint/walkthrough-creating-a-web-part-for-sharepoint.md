---
title: 'İzlenecek yol: SharePoint için bir Web Bölümü oluşturma | Microsoft Docs'
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
- Web Parts [SharePoint development in Visual Studio], developing
- Web Parts [SharePoint development in Visual Studio], creating
- Web Parts [SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c7430b6fc2afc5af872c9f03174451a223e05b3e
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120443"
---
# <a name="walkthrough-create-a-web-part-for-sharepoint"></a>İzlenecek yol: SharePoint için bir web bölümü oluşturma

Web Bölümleri içerik, Görünüm ve davranış SharePoint sitesi sayfalarının bir tarayıcı kullanarak doğrudan değiştirme olanağı verir. Bu kılavuzu kullanarak bir Web bölümü oluşturmak gösterilmiştir **Web Bölümü** Visual Studio 2010 öğe şablonu.

Web Bölümü çalışanlar veri kılavuzunda görüntüler. Kullanıcı çalışan verilerini içeren dosyanın konumunu belirtir. Kullanıcı veri kılavuzu de filtreleyebilirsiniz yöneticilerinin Çalışanlar yalnızca listede görüntülenir.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Visual Studio kullanarak bir Web Bölümü oluşturma **Web Bölümü** öğe şablonu.

- Bir özellik oluşturma Web Bölümü kullanıcı tarafından ayarlanmış olabilir. Bu özellik çalışan veri dosyasının konumunu belirtir.

- Web Bölümü için denetimler ekleyerek bir Web Bölümü içeriği işleme koleksiyonu denetler.

- Yeni bir menü öğesi oluşturma olarak bilinir bir *fiili* işlenmiş Web bölümünün fiiller menüsünde görünür. Fiiller Web Bölümü'nde görüntülenen verileri değiştirmek kullanıcının etkinleştirir.

- Web Bölümü SharePoint test etme.

    > [!NOTE]
    > Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

- Visual Studio 2017 veya bir sürümü, Visual Studio uygulama yaşam döngüsü yönetimi (ALM).

## <a name="create-an-empty-sharepoint-project"></a>Boş bir SharePoint projesi oluşturma

İlk olarak, boş bir SharePoint projesi oluşturun. Projeye kullanarak bir Web Bölümü daha sonra ekleyecek **Web Bölümü** öğe şablonu.

1. Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kullanarak **yönetici olarak çalıştır** seçeneği.

2. Erkek çubuğunda seçin **dosya** > **yeni** > **proje**.

3. İçinde **yeni proje** iletişim kutusunda, genişletin **SharePoint** kullanın ve ardından istediğiniz dil düğümünde **2010** düğümü.

4. İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje**ve ardından **Tamam** düğmesi.

     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir. Bu sihirbaz, proje ve çözüm güven düzeyini hata ayıklamak için kullanacağı site seçmenize olanak sağlar.

5. Seçin **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** varsayılan yerel SharePoint sitesi kabul et düğmesi.

## <a name="add-a-web-part-to-the-project"></a>Bir web bölümü projeye ekleyin

Ekleme bir **Web Bölümü** proje öğesi. **Web Bölümü** öğeyi Web Bölümü kod dosyası ekler. Daha sonra Web Bölümü içeriğini işlemek için Web Bölümü kod dosyası için kod ekleyeceksiniz.

1. Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle**.

2. İçinde **Yeni Öğe Ekle** iletişim kutusunda **yüklü şablonlar** bölmesinde, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.

3. SharePoint şablonları listesinden seçip **Web Bölümü** şablonu ve ardından **Ekle** düğmesi.

     **Web Bölümü** öğesi görünür **Çözüm Gezgini**.

## <a name="rendering-content-in-the-web-part"></a>İçerik web bölümü oluşturma

Web Bölümü sınıfı denetimler koleksiyonuna ekleyerek Web bölümünde görünmesini istediğiniz hangi denetimlerin belirtebilirsiniz.

1. İçinde **Çözüm Gezgini**, açık *WebPart1.vb* (Visual Basic'te) veya *WebPart1.cs* (C# ' ta).

     Web Bölümü kod dosyası Kod düzenleyicisinde açılır.

2. Aşağıdaki deyimleri Web Bölümü kod dosyasının üstüne ekleyin.

     [!code-csharp[SP_WebPart#1](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#1)]
     [!code-vb[SP_WebPart#1](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#1)]

3. Aşağıdaki kodu ekleyin `WebPart1` sınıfı. Bu kod, aşağıdaki alanlar bildirir:

    - Çalışanlar Web bölümünde görüntülenecek veri kılavuzu.

    - Veri Kılavuzu filtrelemede kullanılan denetiminde görüntülenen metin.

    - Veri Kılavuzu veri görüntüleyemiyor ise, bir hata görüntüleyen bir etiket.

    - Çalışan veri dosyasının yolunu içeren bir dize.

     [!code-csharp[SP_WebPart#2](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#2)]
     [!code-vb[SP_WebPart#2](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#2)]

4. Aşağıdaki kodu ekleyin `WebPart1` sınıfı. Bu kod adlı özel bir özellik ekler `DataFilePath` Web Bölümü. Bir özel özellik SharePoint'te kullanıcı tarafından ayarlanabilir bir özelliktir. Bu özellik alır ve veri kılavuzu doldurmak için kullanılan bir XML veri dosyasının konumunu ayarlar.

     [!code-csharp[SP_WebPart#3](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#3)]
     [!code-vb[SP_WebPart#3](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#3)]

5. Değiştir `CreateChildControls` aşağıdaki kod ile yöntemi. Bu kod aşağıdaki görevleri gerçekleştirir:

    - Veri Kılavuzu ve bildirdiğiniz etiketi önceki adımda ekler.

    - Veri Kılavuzu çalışan verilerini içeren bir XML dosyasına bağlar.

     [!code-csharp[SP_WebPart#4](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#4)]
     [!code-vb[SP_WebPart#4](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#4)]

6. Aşağıdaki yöntemi ekleyin `WebPart1` sınıfı. Bu kod aşağıdaki görevleri gerçekleştirir:

    - Görüntülenen fiil işlenmiş Web Bölümü Web Bölümü fiiller menüde oluşturur.

    - Kullanıcı fiiller menüde fiili seçtiğinde olayda işler. Bu kod veri kılavuzunda görünür çalışanların listesini filtreler.

     [!code-csharp[SP_WebPart#5](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#5)]
     [!code-vb[SP_WebPart#5](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#5)]

## <a name="test-the-web-part"></a>Web bölümü test

Projeyi çalıştırdığınızda, SharePoint sitesini açar. Web Bölümü SharePoint Web Bölümü Galerisi'nde otomatik olarak eklenir. Herhangi bir Web Bölümü sayfasına Web bölümü ekleyebilirsiniz.

1. Aşağıdaki XML Notepad dosyaya yapıştırın. Bu XML dosyası Web bölümünde görünür örnek verileri içerir.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
        <employees xmlns="http://schemas.microsoft.com/vsto/samples">
           <employee>
               <name>David Hamilton</name>
               <hireDate>2001-05-11</hireDate>
               <title>Sales Associate</title>
           </employee>
           <employee>
               <name>Karina Leal</name>
               <hireDate>1999-04-01</hireDate>
               <title>Manager</title>
           </employee>
           <employee>
               <name>Nancy Davolio</name>
               <hireDate>1992-05-01</hireDate>
               <title>Sales Associate</title>
           </employee>
           <employee>
               <name>Steven Buchanan</name>
               <hireDate>1955-03-04</hireDate>
               <title>Manager</title>
           </employee>
           <employee>
               <name>Suyama Michael</name>
               <hireDate>1963-07-02</hireDate>
               <title>Sales Associate</title>
           </employee>
        </employees>
    ```

2. Menü çubuğunda, Not Defteri'nde seçin **dosya** > **Kaydet**.

3. İçinde **Kaydet** iletişim kutusunda **farklı türde Kaydet** listesinde, seçin **tüm dosyaları**.

4. İçinde **dosya adı** kutusuna **data.xml**.

5. Kullanarak herhangi bir klasör seçin **klasörlere Gözat** düğmesine tıklayın ve ardından **kaydetmek** düğmesi.

6. Visual Studio'da, **F5** anahtarı.

     SharePoint sitesi açılır.

7. Üzerinde **Site eylemleri** menüsünde seçin **diğer seçenekler**.

8. İçinde **oluşturma** sayfasında, **Web Bölümü sayfası** yazın ve ardından **oluşturma** düğmesi.

9. İçinde **yeni Web Bölümü sayfası** sayfasında, sayfanın adı **SampleWebPartPage.aspx**ve ardından **oluşturma** düğmesi.

     Web Bölümü sayfası görüntülenir.

10. Web Bölümü sayfasında herhangi bir bölge seçin.

11. Sayfanın en üstünde seçin **Ekle** sekmesini ve ardından **Web Bölümü** düğmesi.

12. İçinde **kategorileri** bölmesinde seçin **özel** klasörünü seçin **WebPart1** Web Bölümü ve ardından **Ekle** düğmesi.

     Web Bölümü sayfasında görüntülenir.

## <a name="test-the-custom-property"></a>Özel özellik test

Web Bölümü'nde görüntülenen verileri kılavuz doldurmak için her bir çalışan hakkında verileri içeren XML dosyasının yolunu belirtin.

1. Web bölümü sağ tarafta görüntülenen oku seçin ve ardından **Web Bölümünü Düzenle** menüsünden görüntülenir.

     Web Bölümü için özellikleri içeren bir bölme sayfanın sağ tarafında görünür.

2. Bölmesinde **çeşitli** düğümünü seçin, daha önce oluşturduğunuz XML dosyasının yolunu girin **Uygula** düğmesine tıklayın ve ardından **Tamam** düğmesi.

     Çalışanlar Listesi Web Bölümü'nde göründüğünü doğrulayın.

## <a name="test-the-web-part-verb"></a>Web bölümü fiil test

Gösterme ve gizleme yöneticileri Web Bölümü fiiller menüsünde görüntülenen öğeyi tıklatarak olmayan çalışanlar.

1. Web bölümü sağ tarafta görüntülenen oku seçin ve ardından **yöneticileri yalnızca Göster** menüsünden görüntülenir.

     Yöneticileri olan çalışanlar Web bölümünde görüntülenir.

2. Oku yeniden seçin ve ardından **Göster tüm çalışanlar** menüsünden görüntülenir.

     Tüm çalışanlar Web bölümünde görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

[SharePoint Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)  
[Nasıl yapılır: bir SharePoint web bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part.md)  
[Nasıl yapılır: Tasarımcı kullanarak bir SharePoint web bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)  
[İzlenecek yol: Tasarımcı kullanarak bir web bölümü SharePoint için oluşturma](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)
