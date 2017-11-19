---
title: "İzlenecek yol: Şerit XML kullanarak özel sekme oluşturma | Microsoft Docs"
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
- Ribbon [Office development in Visual Studio], tabs
- customizing the Ribbon, tabscustom Ribbon, tabs
- Ribbon [Office development in Visual Studio], XML
- XML [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Custom tab [Office development in Visual Studio]
ms.assetid: f6391a01-df1a-4a0f-bfbb-a9526c73b2b3
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fbb628ffc8f52de34aa67ad5888b7110d1bc7da2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-custom-tab-by-using-ribbon-xml"></a>İzlenecek Yol: Şerit XML Kullanarak Özel Sekme Oluşturma
  Bu kılavuzu kullanarak özel bir Şerit sekmesi oluşturmak gösterilmiştir **Şerit (XML)** öğesi.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Düğmelere ekleme **eklentileri** sekmesi. **Eklentileri** sekme Şerit XML dosyasında tanımlanan varsayılan bir sekme kullanılır.  
  
-   Düğmeleri kullanarak Microsoft Office Word'ü Otomatikleştirme **eklentileri** sekmesi.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word.  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 İlk adım bir Word VSTO eklenti projesi oluşturmaktır. Daha sonra özelleştireceğiniz **eklentileri** bu belgenin sekmesi.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Oluşturma bir **Word eklenti** adlı proje **MyRibbonAddIn**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]açılır **ThisAddIn.cs** veya **ThisAddIn.vb** kod dosyası ve ekler **MyRibbonAddIn** için proje **Çözüm Gezgini**.  
  
## <a name="creating-the-vsto-add-ins-tab"></a>VSTO eklentileri sekme oluşturma  
 Oluşturmak için **eklentileri** sekmesinde, eklemek bir **Şerit (XML)** projenize öğesi. Bu kılavuzda daha sonra bu sekmeye bazı düğmeler ekleyeceksiniz.  
  
#### <a name="to-create-the-add-ins-tab"></a>Add-Ins sekmesini oluşturmak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Şerit (XML)**.  
  
3.  Yeni Şerit adını değiştirmek **MyRibbon**, tıklatıp **Ekle**.  
  
     **MyRibbon.cs** veya **MyRibbon.vb** dosya Tasarımcısı'nda açılır. Adlı bir XML dosyası **MyRibbon.xml** projenize de eklenir.  
  
4.  İçinde **Çözüm Gezgini**, sağ **ThisAddIn.cs** veya **ThisAddIn.vb**ve ardından **görünümü kodu**.  
  
5.  Aşağıdaki kodu ekleyin **ThisAddIn** sınıfı. Bu kod yöntemini geçersiz kılar ve Şerit XML sınıfını Office uygulamaya döndürür.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
6.  İçinde **Çözüm Gezgini**, sağ **MyRibbonAddIn** proje ve ardından **yapı**. Projenin hatasız oluşturulduğunu doğrulayın.  
  
## <a name="adding-buttons-to-the-add-ins-tab"></a>Eklentiler sekmesi ekleyerek düğmeleri  
 Kullanıcıların ortak metin ve belirli bir tablo etkin belgeye ekleme olanağı vermek için bu VSTO eklenti için belirtilir. Kullanıcı arabirimi sağlamak üzere iki düğmelere ekleme **eklentileri** Şerit XML dosyasını değiştirerek sekmesi. Bu kılavuzda daha sonra geri arama yöntemleri düğmelerinin tanımlayacaksınız. Şerit XML dosyası hakkında daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
#### <a name="to-add-buttons-to-the-add-ins-tab"></a>Düğmeleri eklentileri sekmesine eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **MyRibbon.xml** ve ardından **açık**.  
  
2.  Değiştir **sekmesini** olan aşağıdaki XML öğesi. Bu XML varsayılan denetim grubuna etiketini değiştirir **içerik**, ve etiketlerle iki yeni düğmeler ekler **metin Ekle** ve **Tablo Ekle**.  
  
    ```  
    <tab idMso="TabAddIns">  
        <group id="ContentGroup" label="Content">  
            <button id="textButton" label="Insert Text"  
                 screentip="Text" onAction="OnTextButton"  
                 supertip="Inserts text at the cursor location."/>  
            <button id="tableButton" label="Insert Table"  
                 screentip="Table" onAction="OnTableButton"  
                 supertip="Inserts a table at the cursor location."/>  
        </group>  
    </tab>  
    ```  
  
## <a name="automating-the-document-by-using-the-buttons"></a>Düğmeleri kullanarak belgeyi otomatikleştirme  
 Eklemelisiniz `onAction` için geri çağırma yöntemleri **metin Ekle** ve **Tablo Ekle** kullanıcı bunları tıklattığında eylemleri gerçekleştirmek için düğmeler. Şerit denetimleri için geri çağırma yöntemleri hakkında daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
#### <a name="to-add-callback-methods-for-the-buttons"></a>Geri arama yöntemleri düğmelerinin eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **MyRibbon.cs** veya **MyRibbon.vb**ve ardından **açık**.  
  
2.  En üst kısmına aşağıdaki kodu ekleyin **MyRibbon.cs** veya **MyRibbon.vb** dosya. Bu kod için diğer ad oluşturur <xref:Microsoft.Office.Interop.Word> ad alanı.  
  
     [!code-csharp[Trin_RibbonButtons#1](../vsto/codesnippet/CSharp/Trin_RibbonButtons/MyRibbon.cs#1)]
     [!code-vb[Trin_RibbonButtons#1](../vsto/codesnippet/VisualBasic/Trin_RibbonButtons/MyRibbon.vb#1)]  
  
3.  Aşağıdaki yöntemi ekleyin `MyRibbon` sınıfı. Bir geri çağırma yöntemi budur **metin Ekle** İmlecin geçerli konumundaki etkin belge için bir dize ekler düğmesi.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#2](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.cs#2)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#2](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.vb#2)]  
  
4.  Aşağıdaki yöntemi ekleyin `MyRibbon` sınıfı. Bir geri çağırma yöntemi budur **Tablo Ekle** İmlecin geçerli konumundaki etkin belge için bir tablo ekler düğmesi.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#3](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.cs#3)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#3](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/MyRibbon.vb#3)]  
  
## <a name="testing-the-vsto-add-in"></a>VSTO eklentisinin test etme  
 Proje, Word açar ve adlı sekmesini çalıştırdığınızda **eklentileri** Şerit'te görünür. Tıklatın **metin Ekle** ve **Tablo Ekle** üzerinde düğmeleri **eklentileri** kodu test etmek için sekme.  
  
#### <a name="to-test-your-vsto-add-in"></a>VSTO eklentinizi sınamak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Onaylayın **eklentileri** sekme Şerit'te görünür olur.  
  
3.  Tıklatın **eklentileri** sekmesi.  
  
4.  Onaylayın **içerik** grubudur Şerit'te görünür.  
  
5.  Tıklatın **metin Ekle** düğmesini **içerik** grubu.  
  
     Bir dize İmlecin geçerli konumundaki belgeye eklenir.  
  
6.  Tıklatın **Tablo Ekle** düğmesini **içerik** grubu.  
  
     Bir tablo İmlecin geçerli konumundaki belgeye eklenir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Aşağıdaki konulardan Office kullanıcı arabirimini özelleştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Farklı bir Office uygulaması Şerit özelleştirin. Şeridi özelleştirme destekleyen uygulamalar hakkında daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
-   Bir Office uygulamasının şeridini Şerit Tasarımcısını kullanarak özelleştirin. Daha fazla bilgi için bkz: [Şerit Tasarımcısı](../vsto/ribbon-designer.md).  
  
-   Özel Eylemler bölmesi oluşturun. Daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md).  
  
-   Microsoft Office Outlook UI Outlook Form bölgeleri kullanarak özelleştirin. Daha fazla bilgi için bkz: [izlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  