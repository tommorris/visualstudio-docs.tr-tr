---
title: "İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma | Microsoft Docs"
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
- actions panes [Office development in Visual Studio], controlling from Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Ribbon Designer [Office development in Visual Studio]
- customizing the Ribbon, tabs
- custom Ribbon, tabs
- Custom tab [Office development in Visual Studio]
ms.assetid: 312865e6-950f-46ab-88de-fe7eb8036bfe
caps.latest.revision: "68"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f5503bed26a5e2657bb499a7a25098c373e149e1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer"></a>İzlenecek Yol: Şerit Tasarımcısını Kullanarak Özel Sekme Oluşturma
  Şerit Tasarımcısını kullanarak, özel sekme oluşturabilir ve ardından ekleyin ve onu denetimlere getirin.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   [Eylemler bölmeleri oluşturma](#BKMK_CreateActionsPanes).  
  
-   [Özel sekme oluşturma](#BKMK_CreateCustomTab).  
  
-   [Gizleme ve özel sekmesinde düğmeleri kullanarak Eylemler bölmeleri gösterme](#BKMK_HideShowActionsPane).  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel  
  
## <a name="creating-an-excel-workbook-project"></a>Bir Excel çalışma kitabı projesi oluşturma  
 Şerit Tasarımcısı'nı kullanarak adımları tüm Office uygulamaları için neredeyse aynıdır. Bu örnek, bir Excel çalışma kitabı kullanır.  
  
#### <a name="to-create-an-excel-workbook-project"></a>Bir Excel çalışma kitabı projesi oluşturmak için  
  
-   Adında bir Excel çalışma kitabı projesi oluşturun **ne MyExcelRibbon**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio Tasarımcısı'nda yeni bir çalışma kitabı açılır ve ekler **ne MyExcelRibbon** için proje **Çözüm Gezgini**.  
  
##  <a name="BKMK_CreateActionsPanes"></a>Eylemler bölmeleri oluşturma  
 İki Özel Eylemler bölmeleri projenize ekleyin. Daha sonra gösterme ve gizleme bu Eylemler bölmeleri özel sekmesine düğmeleri ekler.  
  
#### <a name="to-create-actions-panes"></a>Eylemler bölmeleri oluşturmak için  
  
1.  Üzerinde **proje** menüsünde seçin **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **ActionsPaneControl'u**ve ardından **Ekle**.  
  
     **ActionsPaneControl1.cs** veya **ActionsPaneControl1.vb** dosya Tasarımcısı'nda açılır.  
  
3.  Gelen **ortak denetimler** sekmesinde **araç**, Tasarımcı yüzeyine bir etiket ekleyin.  
  
4.  İçinde **özellikleri** penceresindeki ayarlayın **metin** için label1 özelliğinin **Eylemler bölmesinde 1**.  
  
5.  1 ile ikinci eylemler bölmesini ve etiket oluşturmak için 5 arasındaki adımları yineleyin. Ayarlama **metin** İkinci etiketin özelliğini **Eylemler bölmesi 2**.  
  
##  <a name="BKMK_CreateCustomTab"></a>Özel sekme oluşturma  
 Office uygulaması tasarım yönergeleri kullanıcıların Office uygulama kullanıcı Arabirimi her zaman denetlemeleri biridir. Eylemler bölmeleri için bu özelliği eklemek için gösterir ve her özel sekme Şerit üzerindeki Eylemler bölmesinden gizleyen düğmeler ekleyebilirsiniz. Özel sekme oluşturmak için Ekle bir **Şerit (Görsel Tasarımcı)** proje öğesi. Tasarımcı ekleyin ve denetimleri getirin, denetim özelliklerini ayarlamak ve denetim olayları işlemek yardımcı olur.  
  
#### <a name="to-create-a-custom-tab"></a>Özel sekme oluşturmak için  
  
1.  Üzerinde **proje** menüsünde seçin **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Şerit (Görsel Tasarımcı)**.  
  
3.  Yeni Şerit adını değiştirmek **MyRibbon**ve seçin **Ekle**.  
  
     **MyRibbon.cs** veya **MyRibbon.vb** dosyası Şerit Tasarımcısı'nda açılır ve varsayılan bir sekme ve grup görüntüler.  
  
4.  Şerit Tasarımcısı'nda varsayılan sekmesini seçin.  
  
5.  İçinde **özellikleri** penceresinde genişletin **ControlId** özelliğini ayarlayın ve ardından **ControlIdType** özelliğine **özel**.  
  
6.  Ayarlama **etiket** özelliğine **My özel sekmesini**.  
  
7.  Şerit Tasarımcısı'nda seçin **group1**.  
  
8.  İçinde **özellikleri** penceresindeki ayarlayın **etiket** için **Eylemler Bölmesi Yöneticisi**.  
  
9. Gelen **Office Şerit denetimleri** sekmesinde **araç**, bir düğmesine sürükleyin **group1**.  
  
10. Seçin **button1**.  
  
11. İçinde **özellikleri** penceresindeki ayarlayın **etiket** için **Show Eylemler bölmesinde 1**.  
  
12. İkinci düğme eklemek **group1**ve **etiket** özelliğine **Göster Eylemler bölmesi 2**.  
  
13. Gelen **Office Şerit denetimleri** sekmesinde **araç**, sürükleyin bir **ToggleButton** üzerine kontrol **group1**.  
  
14. Ayarlama **etiket** özelliğine **Eylemler Bölmesini Gizle**.  
  
##  <a name="BKMK_HideShowActionsPane"></a>Gizleme ve özel sekmesinde düğmeleri kullanarak Eylemler bölmeleri gösterme  
 Son adım, kullanıcıya yanıt kodu eklemektir. Olay işleyicileri ekleme <xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click> iki düğmelerin olayları ve <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> iki durumlu düğme olayı. Kod gizleme ve Eylemler bölmeleri gösterme etkinleştirmek için bu olay işleyicileri ekleyin.  
  
#### <a name="to-hide-and-show-actions-panes-by-using-buttons-in-the-custom-tab"></a>Eylemler bölmeleri özel sekmede düğmelerini kullanarak gösterme ve gizleme için  
  
1.  İçinde **Çözüm Gezgini**MyRibbon.cs veya MyRibbon.vb için kısayol menüsünü açın ve ardından **görünümü kodu**.  
  
2.  En üst kısmına aşağıdaki kodu ekleyin `MyRibbon` sınıfı. Bu kod iki Eylemler bölmesi nesnesi oluşturur.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab/MyRibbon.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab/MyRibbon.vb#1)]  
  
3.  Değiştir `MyRibbon_Load` aşağıdaki kod ile yöntemi. Bu kod Eylemler bölmesi nesnelerini ekler <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> toplama ve nesneleri görünümden gizler. Visual C# kodu temsilciler birkaç Şerit denetim olayları da ekler.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab#2](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab/MyRibbon.cs#2)]
     [!code-vb[Trin_Ribbon_Custom_Tab#2](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab/MyRibbon.vb#2)]  
  
4.  Aşağıdaki üç olay işleyicisi yöntemi Ekle `MyRibbon` sınıfı. Bu yöntemler işlemek <xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click> iki düğmelerin olayları ve <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> iki durumlu düğme olayı. Olay işleyicileri button1 ve button2 diğer eylemler bölmesini göster. Olay işleyicisi toggleButton1 gösterir ve etkin eylemler bölmesini gizler.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab#3](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab/MyRibbon.cs#3)]
     [!code-vb[Trin_Ribbon_Custom_Tab#3](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab/MyRibbon.vb#3)]  
  
## <a name="testing-the-custom-tab"></a>Özel sekme test etme  
 Programını çalıştırdığınızda proje, Excel başlatır ve **My özel sekmesini** sekmesi Şerit'te görünür. Düğmeleri seçin **My özel sekmesini** göstermek ve Eylemler bölmeleri gizlemek için.  
  
#### <a name="to-test-the-custom-tab"></a>Özel sekme sınamak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Seçin **My özel sekmesini** sekmesi.  
  
3.  İçinde **Özel Eylemler Bölmesi Yöneticisi** grubunda, seçin **Show Eylemler bölmesinde 1**.  
  
     Eylemler bölmesinde görünür ve etiketini görüntüler **Eylemler bölmesinde 1**.  
  
4.  Seçin **Göster Eylemler bölmesinde 2**.  
  
     Eylemler bölmesinde görünür ve etiketini görüntüler **Eylemler bölmesi 2**.  
  
5.  Seçin **Eylemler Bölmesini Gizle**.  
  
     Eylemler bölmeleri artık görünür değildir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Aşağıdaki konulardan Office kullanıcı arabirimini özelleştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Bağlam tabanlı UI hiçbir belge düzeyi özelleştirme ekleyin. Daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md).  
  
-   Standart veya özel bir Microsoft Office Outlook form genişletir. Daha fazla bilgi için bkz: [izlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Nasıl yapılır: Şeritteki sekmenin konumunu değiştirme](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)   
 [Nasıl yapılır: Backstage görünümüne denetimler ekleme](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Şerit Nesne Modeline Genel Bakış](../vsto/ribbon-object-model-overview.md)  
  
  