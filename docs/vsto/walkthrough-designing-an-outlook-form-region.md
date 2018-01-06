---
title: "İzlenecek yol: Outlook Form Bölgesi Tasarlama | Microsoft Docs"
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
helpviewer_keywords: form regions [Office development in Visual Studio], creating
ms.assetid: b033fc06-cdeb-4d7f-804b-86d15bfa022a
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 715d58e205442511db9709a5e57b1b689e008628
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-designing-an-outlook-form-region"></a>İzlenecek Yol: Outlook Form Bölgesi Tasarlama
  Özel form bölgeleri standart veya özel Microsoft Office Outlook Form genişletir. Bu kılavuzda, bir kişi öğesinin Inspector penceresinde yeni bir sayfa olarak görünen özel form bölgesi tasarlama. Bu form bölgesi Windows Live yerel arama Web sitesine adres bilgilerini göndererek kişi için listelenen her adresin haritasını görüntüler. Form bölgeleri hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Yeni bir Outlook VSTO eklenti projesi oluşturma.  
  
-   VSTO eklenti projesine form bölgesi ekleme.  
  
-   Form bölgesini düzeni tasarlama.  
  
-   Form bölgesini davranışını özelleştirme.  
  
-   Outlook form bölgesi test etme.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)]veya [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)].  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") bu konuda video sürümü için bkz: [Video nasıl yapılır: Outlook Form Bölgesi Tasarlama](http://go.microsoft.com/fwlink/?LinkID=140824).  
  
## <a name="creating-a-new-outlook-vsto-add-in-project"></a>Eklenti yeni bir Outlook VSTO projesi oluşturma  
 Önce temel bir VSTO eklenti projesi oluşturun.  
  
#### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>Yeni bir Outlook VSTO eklenti projesi oluşturmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], Outlook VSTO eklenti projesindeki adlı oluşturun **MapItAddIn**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **çözüm için dizin oluştur**.  
  
3.  Projeyi herhangi bir dizine kaydedin.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="adding-a-form-region-to-the-outlook-vsto-add-in-project"></a>Outlook VSTO eklenti projesine Form bölgesi ekleme  
 Outlook VSTO eklenti çözümünü bir veya daha fazla Outlook form bölgesi öğesi içerebilir. Form bölgesi öğesi kullanarak projenize ekleme **yeni Outlook Form bölgesi** Sihirbazı.  
  
#### <a name="to-add-a-form-region-to-the-outlook-vsto-add-in-project"></a>Form bölgesini Outlook VSTO eklenti projesine eklemek için  
  
1.  İçinde **Çözüm Gezgini**seçin **MapItAddIn** projesi.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Outlook Form bölgesi**, dosya adı **MapIt**ve ardından **Ekle**.  
  
     **NewOutlook Form bölgesi** Sihirbazı'nı başlatır.  
  
4.  Üzerinde **nasıl form bölgesi oluşturmak istediğinizi seçin** sayfasında, **yeni bir form bölgesi tasarlama**ve ardından **sonraki**.  
  
5.  Üzerinde **oluşturmak istediğiniz form bölgesini seçin** sayfasında, **ayrı**ve ardından **sonraki**.  
  
     A *ayrı* form bölgesini Outlook form için yeni bir sayfa ekler. Form bölgesi türleri hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
6.  Üzerinde **açıklayıcı metin sağlayın ve görüntüleme tercihlerini seçin** sayfasında, **Map It** içinde **adı** kutusu.  
  
     Kişi öğesi açık olduğunda bu ad Inspector penceresinin Şerit'te görünür.  
  
7.  Seçin **bulunan denetçiler oluşturma modu** ve **Okuma modunda olan denetçiler**ve ardından **sonraki**.  
  
8.  Üzerinde **bu form bölgesini görüntüleyecek ileti sınıflarını tanımlayın** sayfasında, Temizle **posta iletisi**seçin **kişi**ve ardından **Son**.  
  
     MapIt.cs veya MapIt.vb dosyası projenize eklenir.  
  
## <a name="designing-the-layout-of-the-form-region"></a>Form bölgesini düzeni tasarlama  
 Form bölgeleri görsel olarak kullanarak geliştirmek *form bölgesi tasarımcısı*. Yönetilen denetimleri form bölgesi tasarımcı yüzeyine sürükleyin. Designer'ı kullanın ve **özellikleri** pencere denetim düzenini ve görünümünü ayarlayın.  
  
#### <a name="to-design-the-layout-of-the-form-region"></a>Form bölgesini düzenini tasarlamak için  
  
1.  İçinde **Çözüm Gezgini**, genişletin **MapItAddIn** proje ve MapIt.cs veya MapIt.vb Form bölgesi tasarımcısını açmak için çift tıklatın.  
  
2.  Tasarımcısı'nı sağ tıklatın ve ardından **özellikleri**.  
  
3.  İçinde **özellikleri** penceresindeki ayarlayın **boyutu** için **664, 469**.  
  
     Bu form bölgesini haritayı görüntülemek için yeterli büyüklükte olmasını sağlar.  
  
4.  Üzerinde **Görünüm** menüsünde tıklatın **araç**.  
  
5.  Gelen **ortak denetimler** sekmesinde **araç**, ekleme bir **WebBrowser** form bölgesine.  
  
     **WebBrowser** kişi için listelenen her adresin haritasını görüntüler.  
  
## <a name="customizing-the-behavior-of-the-form-region"></a>Form bölgesini davranışını özelleştirme  
 Çalışma zamanında bir form bölgesi biçimini özelleştirmek üzere form bölgesi olay işleyicilerine kodu davranır ekleyin. Bu form bölgesi için kod Outlook öğesinin özelliklerini inceler ve Map It form bölgesini görüntülenip görüntülenmeyeceğini belirler. Form bölgesini görüntüler, kod Windows Live Local Search'e gider ve Outlook kişi öğesinde listelenen her adresin haritasını yükler.  
  
#### <a name="to-customize-the-behavior-of-the-form-region"></a>Form bölgesini davranışını özelleştirmek için  
  
1.  İçinde **Çözüm Gezgini**MapIt.cs veya MapIt.vb sağ tıklayın ve ardından **görünümü kodu**.  
  
     MapIt.cs veya MapIt.vb kod Düzenleyicisi'nde açar.  
  
2.  Genişletme **Form bölgesi fabrikası** kod bölgesini.  
  
     Form bölgesi üretici sınıfı adlı `MapItFactory` sunulur.  
  
3.  Aşağıdaki kodu ekleyin `MapItFactory_FormRegionInitializing` olay işleyicisi. Bir kişi öğesi kullanıcı oturum açtığında bu olay işleyicisi çağrılır. Aşağıdaki kod, kişi öğesini bir adres içerip içermediğini belirler. Kişi öğesini bir adres içermiyorsa, bu kod ayarlar <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> özelliği <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> sınıfının **doğru** ve form bölgesi görüntülenmez. Aksi takdirde, VSTO eklenti başlatır <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> olay ve form bölgesini görüntüler.  
  
     [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
     [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
4.  Aşağıdaki kodu ekleyin <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> olay işleyicisi. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Kişi öğesindeki her adresi art arda ekler ve URL dizesi oluşturur.  
  
    -   Çağrıları <xref:System.Windows.Forms.WebBrowser.Navigate%2A> yöntemi <xref:System.Windows.Forms.WebBrowser> nesne ve URL dizesi parametre olarak geçirir.  
  
     Yerel arama Web sitesine Map It form bölgesinde görünür ve her adresi karalama defterinde sunar.  
  
     [!code-csharp[Trin_Outlook_FR_Separate#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#2)]
     [!code-vb[Trin_Outlook_FR_Separate#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#2)]  
  
## <a name="testing-the-outlook-form-region"></a>Outlook Form bölgesi test etme  
 Projeyi çalıştırdığınızda, Visual Studio Outlook açar. Map It form bölgesini görüntülemek için bir kişi öğesini açın. Map It form bölgesini bir adresi içeren herhangi bir kişi öğesinin biçiminde bir sayfa olarak görünür.  
  
#### <a name="to-test-the-map-it-form-region"></a>Map It form bölgesini sınamak için  
  
1.  Projeyi çalıştırmak için F5 tuşuna basın.  
  
     Outlook açar.  
  
2.  Outlook'ta, üzerinde **giriş** sekmesini tıklatın, **yeni öğeler**ve ardından **kişi**.  
  
3.  Kişi biçiminde yazın **Ann Beebe** ilgili kişi olarak adlandırın ve ardından aşağıdaki üç adresi belirtin.  
  
    |Adres türü|Adres|  
    |------------------|-------------|  
    |**İş**|**4567 Ana St. İstanbul, NY**|  
    |**Giriş**|**1234 Kuzey St. İstanbul, NY**|  
    |**Diğer**|**3456 ana St. Seattle, WA**|  
  
4.  Kaydedin ve kişi öğesini kapatın.  
  
5.  Yeniden açın **Ann Beebe** kişi öğesi.  
  
6.  İçinde **Göster** öğesi'nin Şerit grubuna tıklayın **Map It** Map It form bölgesini açmak için.  
  
     Map It form bölgesini görünür ve yerel arama Web sitesine görüntüler. **İş**, **giriş**, ve **diğer** adresleri karalama defterinde görünür. Karalama defterinde eşlemek istediğiniz bir adres seçin.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Aşağıdaki konulardan Outlook uygulamasının kullanıcı arabirimini özelleştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Outlook öğesinin Şerit özelleştirme hakkında bilgi edinmek için [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Outlook Form bölgeleri oluşturma yönergeleri](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook'ta tasarlanan Form bölgesini içeri aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [Outlook Form bölgelerindeki özel eylemler](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Nasıl Yapılır: Outlook'un Form Bölgesini Görüntülemesini Engelleme](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)  
  
  