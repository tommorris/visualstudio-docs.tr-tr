---
title: "İzlenecek yol: Outlook'ta tasarlanan Form bölgesini içeri aktarma | Microsoft Docs"
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
- importing form regions
- form regions [Office development in Visual Studio], importing
ms.assetid: 86b0ef1a-6d7e-4ea5-b90e-458ffe4e1d10
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: cf5b5ff9f2c3b2db5d7082e4eecd9eee4e235866
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-importing-a-form-region-that-is-designed-in-outlook"></a>İzlenecek Yol: Outlook'ta Tasarlanan Form Bölgesini İçeri Aktarma
  Bu kılavuz, Microsoft Office Outlook form bölgesi tasarlama ve ardından form bölgesini bir Outlook VSTO eklenti projesine kullanarak içeri aktarmak gösterilmiştir **Yeni Form bölgesi** Sihirbazı. Outlook form bölgesi tasarlama yerel Outlook denetimleri form bölgesini Outlook verilere bağlama eklemek mümkün kılar. Form bölgesini içeri aktardıktan sonra her denetim olaylarını işleyebilir.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Outlook form bölgesi tasarımcısını kullanarak bir form bölgesi tasarlama.  
  
-   Bir form bölgesini Outlook VSTO eklenti projesi aktarma.  
  
-   Form bölgesini denetimlerin olaylarını işleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)]veya [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)].  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: oluşturmak Outlook Form bölgeleri kullanarak Visual Studio 2008?](http://go.microsoft.com/fwlink/?LinkID=130305).  
  
## <a name="designing-a-form-region-by-using-the-form-region-designer-in-outlook"></a>Outlook Form bölgesi tasarımcısını kullanarak bir Form Bölgesi Tasarlama  
 Bu adımda Outlook form bölgesi tasarlama. Ardından kaydetme olacak form bölgesi bulma kolay bir konuma içine aktarabilirsiniz böylece [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
 Bu örnekte form bölgesi normal görev formuyla tamamen değiştirir. Bu ana görev çalıştırılmadan önce tamamlanması gereken tüm görevlerin ilerlemesini izlemek için bir yol (ön koşul görevlerini) gerçekleştirilen sağlar. Form bölgesi önkoşul görevlerinin bir listesini görüntüler ve listede her görev için tamamlanma durumu gösterir. Kullanıcılar, görevleri listeye ekleyin ve bunları kaldırın. Bunlar, ayrıca her görevin tamamlanma durumunu yenileyebilirsiniz.  
  
#### <a name="to-design-a-form-region-by-using-the-form-region-designer-in-outlook"></a>Form bölgesini Outlook form bölgesi tasarımcısını kullanarak tasarlamak için  
  
1.  Microsoft Office Outlook başlatın.  
  
2.  Outlook'ta, üzerinde **Geliştirici** sekmesini tıklatın, **Form tasarlama**. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  İçinde **tasarım formu** kutusunda, **görev**ve ardından **açık**.  
  
4.  Outlook'ta, üzerinde **Geliştirici** sekmesinde **tasarım** grubunda **Yeni Form bölgesi**.  
  
     Yeni bir form bölgesi açılır. Varsa **alan Seçici** görüntülenmiyorsa, tıklatın **alan Seçici** içinde **Araçları** grubu.  
  
5.  Sürükleme **konu** alan ve **tamamlanma yüzdesi** alanının **alan Seçici** form bölgesine.  
  
6.  İçinde **Araçları** grubunda **Denetim araç** açmak için **araç**.  
  
7.  Bir etiketinden sürükleyin **araç** form bölgesine. Etiket altına getirin **konu** ve **tamamlanma yüzdesi** alanları.  
  
8.  Etikete sağ tıklayın ve ardından **Gelişmiş Özellikler**.  
  
9. İçinde **özellikleri** penceresindeki ayarlayın **resim yazısı** özelliğine **bu görev aşağıdaki görevlere bağlıdır**ayarlayın **genişliği** özelliği **200**ve ardından **Uygula**.  
  
10. ListBox denetimi bağlantısı sürükleyin **araç** form bölgesine. Liste kutusunu altına getirin **bu görev aşağıdaki görevlere bağlıdır** etiketi.  
  
11. Yeni eklediğiniz liste kutusunu seçin.  
  
12. İçinde **özellikleri** penceresindeki ayarlayın **genişliği** için **300**ve ardından **Uygula**.  
  
13. Bir etiketinden sürükleyin **araç** form bölgesine. Etiket liste kutusunu altına getirin.  
  
14. Yeni eklediğiniz etiketi seçin.  
  
15. İçinde **özellikleri** penceresindeki ayarlayın **resim yazısı** özelliğine **bağımlı görevler listesine eklemek için bir görev seçin**ayarlayın **genişliği** özelliğine **200**ve ardından **Uygula**.  
  
16. ComboBox denetimi bağlantısı sürükleyin **araç** form bölgesine. Birleşik giriş kutusunu altına getirin **bağımlı görevler listesine eklemek için bir görev seçin** etiketi.  
  
17. Yeni eklediğiniz birleşik giriş kutusunu seçin.  
  
18. İçinde **özellikleri** penceresindeki ayarlayın **genişliği** özelliğine **300**ve ardından **Uygula**.  
  
19. CommandButton denetimden sürükleyin **araç** form bölgesine. Komut düğmesi yanındaki açılan kutusu yerleştirin.  
  
20. Yeni eklediğiniz komut düğmesini seçin.  
  
21. İçinde **özellikleri** penceresindeki ayarlayın **adı** için **AddDependentTask**ayarlayın **resim yazısı** için **bağımlı Görev Ekle**ayarlayın **genişliği** için **100**ve ardından **Uygula**.  
  
22. İçinde **alan Seçici**, tıklatın **yeni**.  
  
23. İçinde **yeni alan** iletişim kutusuna **hiddenField** içinde **adı** alan ve ardından **Tamam**.  
  
24. Sürükleme **hiddenField** alanının **alan Seçici** form bölgesine.  
  
25. İçinde **özellikleri** penceresindeki ayarlayın **görünür** için **0 - False**ve ardından **Uygula**.  
  
26. Outlook'ta, üzerinde **Geliştirici** sekmesinde **tasarım** grubunda **kaydetmek** düğmesine tıklayın ve ardından **Form Bölgesini Farklı Kaydet**.  
  
     Form bölgesi adı **TaskFormRegion** ve yerel bir dizine bilgisayarınıza kaydedin.  
  
     Outlook form bölgesini Outlook Form Depolama (.ofs) dosyası olarak kaydeder. Form bölgesi TaskFormRegion.ofs adıyla kaydedilir.  
  
27. Outlook çıkın.  
  
## <a name="creating-a-new-outlook-add-in-project"></a>Yeni Outlook eklenti projesi oluşturma  
 Bu adımda, Outlook VSTO eklenti projesindeki oluşturur. Bu kılavuzda daha sonra projeye form bölgesini içeri aktaracak.  
  
#### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>Yeni bir Outlook VSTO eklenti projesi oluşturmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], Outlook VSTO eklenti projesindeki adlı oluşturun **TaskAddIn**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **çözüm için dizin oluştur**.  
  
3.  Projeyi varsayılan proje dizinine kaydedin.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="importing-the-form-region"></a>Form bölgesini içeri aktarma  
 Kullanarak Outlook VSTO eklenti projesine Outlook'ta tasarlanan form bölgesini içeri aktarabilirsiniz **yeni Outlook Form bölgesi** Sihirbazı.  
  
#### <a name="to-import-the-form-region-into-the-outlook-vsto-add-in-project"></a>Outlook VSTO eklenti projesine form bölgesini içeri aktarmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **TaskAddIn** proje, fareyle **Ekle**ve ardından **yeni öğe**.  
  
2.  İçinde **şablonları** bölmesinde, **Outlook Form bölgesi**, dosya adı **TaskFormRegion**ve ardından **Ekle**.  
  
     **NewOutlook Form bölgesi** Sihirbazı'nı başlatır.  
  
3.  Üzerinde **nasıl form bölgesi oluşturmak istediğinizi seçin** sayfasında, **Outlook Form Depolama (.ofs) dosyasını içeri aktarma**ve ardından **Gözat**.  
  
4.  İçinde **varolan Outlook Form bölgesi dosya konumu** iletişim kutusunda, konumuna gözatın **TaskFormRegion.ofs**seçin **TaskFormRegion.ofs**, tıklatın**Açık**ve ardından **sonraki**.  
  
5.  Üzerinde **oluşturmak istediğiniz form bölgesini seçin** sayfasında, **Tümünü Değiştir**ve ardından **sonraki**.  
  
     A *Tümünü Değiştir* form bölgesini Outlook formun tamamı yerine geçer. Form bölgesi türleri hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
6.  Üzerinde **açıklayıcı metin sağlayın ve görüntüleme tercihlerini seçin** sayfasında, **sonraki**.  
  
7.  Üzerinde **bu form bölgesini görüntüleyecek ileti sınıflarını tanımlayın** sayfasında **hangi özel ileti sınıfları bu form bölgesini görüntüleyecek** alanında, yazın **IPM. Task.TaskFormRegion**ve ardından **son**.  
  
     TaskFormRegion.cs veya TaskFormRegion.vb dosyası projenize eklenir.  
  
## <a name="handling-the-events-of-controls-on-the-form-region"></a>Form bölgesini denetimlerin olaylarını işleme  
 Projedeki form bölgesi sahip olduğunuza göre Outlook form bölgesi eklenen düğmesinin Microsoft.Office.Interop.Outlook.OlkCommandButton.Click olayı işleyen kodu ekleyebilirsiniz.  
  
 Ayrıca, kodu ekleyin <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> form bölgesi göründüğünde, form bölgesini denetimleri güncelleyen olay.  
  
#### <a name="to-handle-the-events-of-controls-on-the-form-region"></a>Form bölgesini denetimlere olayları işlemek için  
  
1.  İçinde **Çözüm Gezgini**TaskFormRegion.cs veya TaskFormRegion.vb sağ tıklayın ve ardından **görünümü kodu**.  
  
     TaskFormRegion.cs veya TaskFormRegion.vb kod Düzenleyicisi'nde açar.  
  
2.  Aşağıdaki kodu ekleyin `TaskFormRegion` sınıfı. Bu kod, form bölgesini Outlook görevleri klasöründeki her görevin konu satırı ile birleşik giriş kutusunu doldurur.  
  
     [!code-csharp[Trin_Outlook_FR_Import#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#1)]
     [!code-vb[Trin_Outlook_FR_Import#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#1)]  
  
3.  Aşağıdaki kodu ekleyin `TaskFormRegion` sınıfı. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Çağırarak Görevler klasöründe Microsoft.Office.Interop.Outlook.TaskItem bulur `FindTaskBySubjectName` yardımcı yöntem ve istenen görevi konu geçirme. Ekleyeceksiniz `FindTaskBySubjectName` sonraki adımda yardımcı yöntemi.  
  
    -   Microsoft.Office.Interop.Outlook.TaskItem.Subject ve Microsoft.Office.Interop.Outlook.TaskItem.percentComplete değerlerini bağımlı görev liste kutusuna ekler.  
  
    -   Form bölgesini gizli alanı görev konu ekler. Gizli alan bu değerleri Outlook öğesi bir parçası olarak depolar.  
  
     [!code-csharp[Trin_Outlook_FR_Import#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#2)]
     [!code-vb[Trin_Outlook_FR_Import#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#2)]  
  
4.  Aşağıdaki kodu ekleyin `TaskFormRegion` sınıfı. Bu kod yardımcı yöntem sağlar `FindTaskBySubjectName` önceki adımda açıklanan.  
  
     [!code-csharp[Trin_Outlook_FR_Import#3](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#3)]
     [!code-vb[Trin_Outlook_FR_Import#3](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#3)]  
  
5.  Aşağıdaki kodu ekleyin `TaskFormRegion` sınıfı. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Form bölgesi geçerli tamamlanma durumunu içeren liste kutusunda, her bağımlı görevin yeniler.  
  
    -   Bağımlı her görevin konusunu elde etmek için gizli metin alanı ayrıştırır. Ardından her Microsoft.Office.Interop.Outlook.TaskItem Görevler klasöründe çağırarak bulur `FindTaskBySubjectName` yardımcı yöntem ve her görevin konusunu geçirme.  
  
    -   Microsoft.Office.Interop.Outlook.TaskItem.Subject ve Microsoft.Office.Interop.Outlook.TaskItem.percentComplete değerlerini bağımlı görev liste kutusuna ekler.  
  
     [!code-csharp[Trin_Outlook_FR_Import#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#4)]
     [!code-vb[Trin_Outlook_FR_Import#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#4)]  
  
6.  Değiştir `TaskFormRegion_FormRegionShowing` aşağıdaki kod ile olay işleyicisi. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Form bölgesi göründüğünde görev konularıyla form bölgesi birleşik giriş kutusunu doldurur.  
  
    -   Çağrıları `RefreshTaskListBox` form bölgesi göründüğünde yardımcı yöntemi. Bu öğe daha önce açıldığında, liste kutusu eklenen herhangi bir bağımlı görevi görüntüler.  
  
     [!code-csharp[Trin_Outlook_FR_Import#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#5)]
     [!code-vb[Trin_Outlook_FR_Import#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#5)]  
  
## <a name="testing-the-outlook-form-region"></a>Outlook Form bölgesi test etme  
 Form bölgesini sınamak için form bölgesi önkoşul görevleri listesine görevler ekleyin. Önkoşul bir görevin tamamlanma durumunu güncelleştirin ve ardından önkoşul görev listesinde görev güncelleştirilmiş tamamlanma durumunu görüntüleyin.  
  
#### <a name="to-test-the-form-region"></a>Form bölgesini sınamak için  
  
1.  Projeyi çalıştırmak için F5 tuşuna basın.  
  
     Outlook'u başlatır.  
  
2.  Outlook'ta, üzerinde **giriş** sekmesini tıklatın, **yeni öğeler**ve ardından **görev**.  
  
3.  Görev biçiminde yazın **bağımlı görev** içinde **konu** alan.  
  
4.  Üzerinde **görev** Şerit sekmesi, **Eylemler** grubunda **Kaydet ve Kapat**.  
  
5.  Outlook'ta, üzerinde **giriş** sekmesini tıklatın, **yeni öğeler**, tıklatın **diğer öğeler**ve ardından **Form Seç**.  
  
6.  İçinde **Form Seç** iletişim kutusu, tıklatın **TaskFormRegion**ve ardından **açık**.  
  
     **TaskFormRegion** form bölgesi görünür. Bu form tüm görev formu değiştirir. **Bağımlı görevler listesine eklemek için bir görev seçin** birleşik giriş kutusu Görevler klasöründeki diğer görevleri ile doldurulur.  
  
7.  Görev formdaki içinde **konu** alanında, yazın **birincil görev**.  
  
8.  İçinde **bağımlı görevler listesine eklemek için bir görev seçin** birleşik giriş kutusu, select **bağımlı görev**ve ardından **bağımlı Görev Ekle**.  
  
     **%0 tamamlandı--bağımlı görev** görünür **bu görev aşağıdaki görevlere bağlıdır** liste kutusu. Bu düğmenin Microsoft.Office.Interop.Outlook.OlkCommandButton.Click olay başarıyla işlenen gösterir.  
  
9. Kaydet ve Kapat **birincil görev** öğesi.  
  
10. Outlook'ta bağımlı görev öğeyi yeniden açın.  
  
11. Bağımlı Görev formunda değiştirme **tamamlanma yüzdesi** alanı **% 50**.  
  
12. Üzerinde **görev** bağımlı görev Şerit sekmesi, **Eylemler** grubunda **Kaydet ve Kapat**.  
  
13. Yeniden **birincil görev** Outlook öğesi.  
  
     **% 50 tamamlandı--bağımlı görev** görüntülenir **bu görev aşağıdaki görevlere bağlıdır** liste kutusu.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Aşağıdaki konulardan Outlook uygulamasının kullanıcı arabirimini özelleştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Yönetilen denetimleri görsel tasarımcıya sürükleyerek form bölgesini görünümünü tasarlamak hakkında daha fazla bilgi için bkz: [izlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
-   Outlook öğesinin Şerit özelleştirme hakkında bilgi edinmek için [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md).  
  
-   Outlook için bir özel görev bölmesi ekleme hakkında daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Outlook Form bölgeleri oluşturma yönergeleri](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [Outlook Form bölgelerindeki özel eylemler](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Nasıl Yapılır: Outlook'un Form Bölgesini Görüntülemesini Engelleme](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)  
  
  