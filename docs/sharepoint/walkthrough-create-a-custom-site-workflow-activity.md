---
title: 'İzlenecek yol: özel Site iş akışı etkinliği oluşturma | Microsoft Docs'
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
- custom workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, custom workflow activities
- site workflows [SharePoint development in Visual Studio]
- workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, site workflows
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 614a2e04cd1a7cba054ca209784619021b128e5e
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120445"
---
# <a name="walkthrough-create-a-custom-site-workflow-activity"></a>İzlenecek yol: özel site iş akışı etkinliği oluşturma
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
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] ve SharePoint. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="create-a-site-workflow-custom-activity-project"></a>Bir site iş akışı özel etkinlik projesi oluşturma
 İlk olarak tutun ve test özel iş akışı etkinliği için bir proje oluşturun.  
  
#### <a name="to-create-a-site-workflow-custom-activity-project"></a>Bir site iş akışı özel etkinlik projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya** > **yeni** > **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
2.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
3.  İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje** şablonu.  
  
4.  İçinde **adı** kutusuna **AnnouncementBackup**ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
5.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** kabul et düğmesi güven düzeyi ve varsayılan site.  
  
     Bu adım çözümü için güven düzeyini Grup çözümü, iş akışı projeleri için kullanılabilir tek seçenek olarak ayarlar.  
  
6.  İçinde **Çözüm Gezgini**, proje düğümünü seçin ve ardından, menü çubuğunda, **proje** > **Yeni Öğe Ekle**.  
  
7.  Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
8.  İçinde **şablonları** bölmesinde seçin **sıralı iş akışı (yalnızca Grup çözümünün)** şablonu ve ardından **Ekle** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
9. Üzerinde **hata ayıklama için iş akışı adını** sayfasında, varsayılan adı (AnnouncementBackup - Workflow1) kabul edin. İş akışı şablon türü değiştirme **Site iş akışı**ve ardından **sonraki** düğmesi.  
  
10. Seçin **son** geri kalan varsayılan ayarları kabul etmek için düğmesi.  
  
## <a name="add-a-custom-workflow-activity-class"></a>Özel iş akışı etkinlik sınıfı ekleme
 Ardından, özel iş akışı etkinliği kodunu içerecek projesi için bir sınıf ekleyin.  
  
#### <a name="to-add-a-custom-workflow-activity-class"></a>Özel iş akışı etkinliği sınıf eklemek için  
  
1.  Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle** görüntülemek için **Yeni Öğe Ekle** iletişim kutusu.  
  
2.  İçinde **yüklü şablonlar** ağaç görünümü, seçin **kod** düğümünü ve ardından **sınıfı** Şablonu proje öğesi şablonları listesinde. Class1 varsayılan adı kullanın. Seçin **Ekle** düğmesi.  
  
3.  Tüm Class1 kodu aşağıdakilerle değiştirin:  
  
     [!code-csharp[SP_AnnBackup#1](../sharepoint/codesnippet/CSharp/announcementbackup/class1.cs#1)]
     [!code-vb[SP_AnnBackup#1](../sharepoint/codesnippet/VisualBasic/announcementbackupvb/class1.vb#1)]  
  
4.  Projeyi kaydedin ve ardından, menü çubuğunda, **yapı** > **yapı çözümü**.  
  
     Özel bir eylem olarak Class1 görünür **araç** üzerinde **AnnouncementBackup bileşenleri** sekmesi.  
  
## <a name="add-the-custom-activity-to-the-site-workflow"></a>Site iş akışı için özel etkinlik ekleme
 Ardından, özel kod içerecek şekilde iş akışına bir etkinlik ekleyin.  
  
#### <a name="to-add-a-custom-activity-to-the-site-workflow"></a>Site iş akışı için özel bir aktivite eklemek için
  
1.  Tasarım görünümünde iş akışı Tasarımcısı'nda Workflow1 açın.  
  
2.  Sürükleme Class1 gelen **araç** altında görünmesi `onWorkflowActivated1` etkinlik veya Class1 için kısayol menüsünü Aç'ı seçin **kopyalama**, satırın altında için kısayol menüsünü açın `onWorkflowActivated1` etkinlik ve ardından **Yapıştır**.  
  
3.  Projeyi kaydedin.  
  
## <a name="test-the-site-workflow-custom-activity"></a>Site iş akışı özel etkinlik test
 Ardından, projeyi çalıştırın ve site iş akışı başlatın. Özel Etkinlik yedekleme duyuruları listesini oluşturur ve içeriği geçerli duyuruları listesinden kopyalar. Kod ayrıca yedekleme listesini zaten bir oluşturmadan önce mevcut olup olmadığını denetler. Yedek liste zaten varsa, bu silinir. Kod Ayrıca SharePoint sitesinin Hızlı Başlat çubuğunda Yeni liste bir bağlantı ekler.  
  
#### <a name="to-test-the-site-workflow-custom-activity"></a>Site iş akışı özel etkinlik sınamak için  
  
1.  Seçin **F5** projeyi çalıştırın ve SharePoint'e dağıtmak için anahtar.  
  
2.  Hızlı Başlatma çubuğunda seçin **listeler** tüm SharePoint sitesinde kullanılabilir olan listesini görüntülemek için bağlantı. Adlı duyuruları için yalnızca bir liste fark **duyuruları**.  
  
3.  SharePoint Web sayfasının en üstünde seçin **Site iş akışları** bağlantı.  
  
4.  Yeni iş akışı bölümü başlangıç altında seçin **AnnouncementBackup - Workflow1** bağlantı. Bu site iş akışı başlatır ve özel eylemi kodu çalıştırır.  
  
5.  Hızlı Başlatma çubuğunda seçin **duyuruları yedekleme** bağlantı. Dikkat tüm bulunan duyuruları **duyuruları** listesi için bu yeni liste kopyalanmış.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Nasıl yapılır: olay alıcısı oluşturma](../sharepoint/how-to-create-an-event-receiver.md)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
