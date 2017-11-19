---
title: "İzlenecek yol: özel Site iş akışı etkinliği oluşturma | Microsoft Docs"
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
- custom workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, custom workflow activities
- site workflows [SharePoint development in Visual Studio]
- workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, site workflows
ms.assetid: 8219a779-c27b-4186-92c9-5bda03328aa9
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6d3579c3d537dc13723cbe285b454b24d079fe1f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-create-a-custom-site-workflow-activity"></a>İzlenecek yol: Özel Site İş Akışı Faaliyeti Oluşturma
  Bu kılavuzu kullanarak bir site düzeyinde iş akışı için özel bir etkinlik oluşturmak gösterilmiştir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. (Yalnızca listesini sitesindeki tüm site için site düzeyinde iş akışları geçerlidir.) Özel Etkinlik bir yedek Duyurular listesi oluşturur ve ardından Duyurular listesi içeriğini kopyalar.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Site düzeyinde iş akışı oluşturma.  
  
-   Özel iş akışı etkinliği oluşturma.  
  
-   Oluşturma ve bir SharePoint listesi silme.  
  
-   Öğeleri bir listeden diğerine kopyalama.  
  
-   Hızlı Başlatma çubuğunda listesini görüntüleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] ve SharePoint. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="creating-a-site-workflow-custom-activity-project"></a>Site iş akışı özel etkinlik proje oluşturma  
 İlk olarak tutun ve test özel iş akışı etkinliği için bir proje oluşturun.  
  
#### <a name="to-create-a-site-workflow-custom-activity-project"></a>Bir site iş akışı özel etkinlik projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
2.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
3.  İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje** şablonu.  
  
4.  İçinde **adı** kutusuna **AnnouncementBackup**ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
5.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** kabul et düğmesi güven düzeyi ve varsayılan site.  
  
     Bu adım çözümü için güven düzeyini Grup çözümü, iş akışı projeleri için kullanılabilir tek seçenek olarak ayarlar.  
  
6.  İçinde **Çözüm Gezgini**, proje düğümünü seçin ve ardından, menü çubuğunda, **proje**, **Yeni Öğe Ekle**.  
  
7.  Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
8.  İçinde **şablonları** bölmesinde seçin **sıralı iş akışı (yalnızca Grup çözümünün)** şablonu ve ardından **Ekle** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
9. Üzerinde **hata ayıklama için iş akışı adını** sayfasında, varsayılan adı (AnnouncementBackup - Workflow1) kabul edin. İş akışı şablon türü değiştirme **Site iş akışı**ve ardından **sonraki** düğmesi.  
  
10. Seçin **son** geri kalan varsayılan ayarları kabul etmek için düğmesi.  
  
## <a name="adding-a-custom-workflow-activity-class"></a>Özel iş akışı etkinliği sınıf ekleme  
 Ardından, özel iş akışı etkinliği kodunu içerecek projesi için bir sınıf ekleyin.  
  
#### <a name="to-add-a-custom-workflow-activity-class"></a>Özel iş akışı etkinliği sınıf eklemek için  
  
1.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle** görüntülemek için **Yeni Öğe Ekle** iletişim kutusu.  
  
2.  İçinde **yüklü şablonlar** ağaç görünümü, seçin **kod** düğümünü ve ardından **sınıfı** Şablonu proje öğesi şablonları listesinde. Class1 varsayılan adı kullanın. Seçin **Ekle** düğmesi.  
  
3.  Tüm Class1 kodu aşağıdakilerle değiştirin:  
  
     [!code-csharp[SP_AnnBackup#1](../sharepoint/codesnippet/CSharp/announcementbackup/class1.cs#1)]
     [!code-vb[SP_AnnBackup#1](../sharepoint/codesnippet/VisualBasic/announcementbackupvb/class1.vb#1)]  
  
4.  Projeyi kaydedin ve ardından, menü çubuğunda, **yapı**, **yapı çözümü**.  
  
     Özel bir eylem olarak Class1 görünür **araç** üzerinde **AnnouncementBackup bileşenleri** sekmesi.  
  
## <a name="adding-the-custom-activity-to-the-site-workflow"></a>Site iş akışı için özel etkinlik ekleme  
 Ardından, özel kod içerecek şekilde iş akışına bir etkinlik ekleyin.  
  
#### <a name="to-add-a-custom-activity-to-the-site-workflow"></a>Özel Etkinlik iş akışı siteye eklemek için  
  
1.  Tasarım görünümünde iş akışı Tasarımcısı'nda Workflow1 açın.  
  
2.  Sürükleme Class1 gelen **araç** altında görünmesi `onWorkflowActivated1` etkinlik veya Class1 için kısayol menüsünü Aç'ı seçin **kopyalama**, satırın altında için kısayol menüsünü açın `onWorkflowActivated1` etkinlik ve ardından **Yapıştır**.  
  
3.  Projeyi kaydedin.  
  
## <a name="testing-the-site-workflow-custom-activity"></a>Site iş akışı özel etkinlik test etme  
 Ardından, projeyi çalıştırın ve site iş akışı başlatın. Özel Etkinlik yedekleme duyuruları listesini oluşturur ve içeriği geçerli duyuruları listesinden kopyalar. Kod ayrıca yedekleme listesini zaten bir oluşturmadan önce mevcut olup olmadığını denetler. Yedek liste zaten varsa, bu silinir. Kod Ayrıca SharePoint sitesinin Hızlı Başlat çubuğunda Yeni liste bir bağlantı ekler.  
  
#### <a name="to-test-the-site-workflow-custom-activity"></a>Site iş akışı özel etkinlik sınamak için  
  
1.  Projeyi çalıştırın ve SharePoint'e dağıtmak için F5 tuşuna seçin.  
  
2.  Hızlı Başlatma çubuğunda seçin **listeler** tüm SharePoint sitesinde kullanılabilir olan listesini görüntülemek için bağlantı. Adlı duyuruları için yalnızca bir liste fark **duyuruları**.  
  
3.  SharePoint Web sayfasının en üstünde seçin **Site iş akışları** bağlantı.  
  
4.  Yeni iş akışı bölümü başlangıç altında seçin **AnnouncementBackup - Workflow1** bağlantı. Bu site iş akışı başlatır ve özel eylemi kodu çalıştırır.  
  
5.  Hızlı Başlatma çubuğunda seçin **duyuruları yedekleme** bağlantı. Dikkat tüm bulunan duyuruları **duyuruları** listesi için bu yeni liste kopyalanmış.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: olay alıcısı oluşturma](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  