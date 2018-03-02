---
title: "İzlenecek yol: Proje Görev listesi tanımını dağıtma | Microsoft Docs"
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
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: cae6b4590c2bb0382b1ff46af51e9c79dfdd9c0e
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-deploying-a-project-task-list-definition"></a>İzlenecek yol: Proje Görev Listesi Tanımını Dağıtma

Bu kılavuz size nasıl kullanılacağını gösterir [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] oluşturmak için özelleştirme, hata ayıklama ve proje görevleri izlemek için bir SharePoint listesi dağıtın.

[!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

- Visual Studio 2017 veya bir sürümü, Visual Studio uygulama yaşam döngüsü yönetimi (ALM).

## <a name="CreatingListDef"></a> Bir SharePoint listesi oluşturma

Bir SharePoint listesi projesi oluşturun ve liste tanımını görevleri ile ilişkilendirin.

1. Açık **yeni proje** iletişim kutusunda, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.

2. İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje** şablonu, proje adı **ProjectTaskList**ve ardından **Tamam**düğmesi.

     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.

3. Hata ayıklama için kullandığınız Yerel SharePoint sitesini belirtmek seçin **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** düğmesi.

4. Proje kısayol menüsünü açın ve ardından **Ekle**, **yeni öğe**.

5. İçinde **şablonları** bölmesinde seçin **listesi** şablonu ve ardından **Ekle** düğmesi.

     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.

6. İçinde **hangi adı için listenizi görüntülemek istiyor musunuz?** kutusuna **proje görev listesi**.

7. Seçin **bir varolan liste türüne göre özelleştirilemez listesini oluşturmak** seçenek düğmesine ve ardından, kendi listesinde **görevleri**ve ardından **son** düğmesi.

     Liste, özellik ve paket görünür **Çözüm Gezgini**.

## <a name="AddEventRcvr"></a> Olay alıcısı ekleme

Görev listesindeki son otomatik olarak ayarlayan olay alıcı ekleyebilirsiniz tarih ve görev açıklaması. Aşağıdaki yordamda basit olay işleyicisi listesi örneğine bir olay alıcısı olarak ekler.

1. Proje düğümünün kısayol menüsünü açın, seçin **Ekle**ve ardından **yeni öğe**.

2. SharePoint şablonları listesinden seçip **olay alıcısı** şablonu ve ardından ad **ProjectTaskListEventReceiver**.

     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.

3. Üzerinde **olay alıcı ayarlarını seçin** sayfasında, **liste öğesi olayları** olay alıcı türü olarak **ne tür bir olay alıcısına istediğiniz** listesi.

4. İçinde **öğesinin ne olay kaynağı olmalıdır** listesinde, seçin **görevleri**.

5. Olayları işlemek için listesinde yanındaki onay kutusunu seçin **bir öğe eklendi**ve ardından **son** düğmesi.

     Yeni bir olay alıcı düğüm adlı bir kod dosyası projeye eklenen **ProjectTaskListEventReceiver**.

6. Kodu ekleyin `ItemAdded` yönteminde **ProjectTaskListEventReceiver** kod dosyası. Her zaman yeni bir görev eklenir, görev için varsayılan bir son tarih ve bir açıklama eklenir. Varsayılan son 1 Temmuz 2009 tarihidir.

     [!code-vb[SPProjectTaskList#1](../sharepoint/codesnippet/VisualBasic/projecttasklist1/projecttasklisteventreceiver/projecttasklisteventreceiver.vb#1)]
     [!code-csharp[SPProjectTaskList#1](../sharepoint/codesnippet/CSharp/projecttasklist/projecttasklisteventreceiver/projecttasklisteventreceiver.cs#1)]

## <a name="CustomizeFeature"></a> Proje Görev listesi özelliğini özelleştirme

Bir SharePoint çözüm oluşturduğunuzda, Visual Studio Proje öğeleri varsayılan özellikleri otomatik olarak oluşturur. Özellik Tasarımcı kullanarak SharePoint sitesi için proje görev listesi ayarları özelleştirebilirsiniz.

1. İçinde **Çözüm Gezgini**, genişletin **özellikleri**.

2. Kısayol menüsünü açın **Feature1**ve ardından **Görünüm Tasarımcısı**.

3. İçinde **başlık** kutusuna **proje görev listesi özelliği**.

4. İçinde **kapsam** listesinde, seçin **Web**.

5. İçinde **özellikleri** penceresinde girin **1.0.0.0** değeri olarak **sürüm** özelliği.

## <a name="CustomizePackage"></a> Proje Görev listesi paketi özelleştirme

Bir SharePoint proje oluşturduğunuzda, Visual Studio Paketi için varsayılan proje öğeleri içeren özellikleri otomatik olarak ekler. Paket Tasarımcısını kullanarak SharePoint sitesi için proje görev listesi ayarları özelleştirebilirsiniz.

1. İçinde **Solution Explorer'da**, kısayol menüsünü açın **paket**ve ardından **Görünüm Tasarımcısı**.

2. İçinde **adı** kutusuna **ProjectTaskListPackage**.

3. Seçin **sıfırlama Web sunucusu** onay kutusu.

## <a name="BuildTest"></a> Derleme ve test proje görev listesi

Projeyi çalıştırdığınızda, SharePoint sitesini açar. Ancak, el ile görev listesi konuma gitmeniz gerekir.

1. Derleme ve proje görev listesi dağıtma için F5 tuşuna seçin.

     SharePoint sitesi açılır.

2. Seçin **giriş** sekmesi.

3. Sol Kenar çubuğunda seçin **proje görev listesi** bağlantı.

     Proje Görev listesi sayfası görüntülenir.

4. İçinde **liste Araçları** sekmesinde, seçin **öğeleri** sekmesi.

5. İçinde **öğeleri** grubunda, seçin **yeni öğe** düğmesi.

6. İçinde **başlık** metin kutusuna **Task1**.

7. Seçin **kaydetmek** düğmesi.

     Site yenilendikten sonra **Task1** görev 1/7/2009 son tarihi görüntülenir.

8. Seçin **Task1**.

     Görev ayrıntılı görünümünü görünür ve Açıklama "Kritik görev oluşur." gösterir

## <a name="Deploy"></a> Proje Görev listesi dağıtma

Derleme ve proje görev listesi test sonra kendisine dağıtabilirsiniz *yerel sistem* veya *uzak sistem*. Uzak bir sisteme farklı bir bilgisayara iken yerel çözüm geliştirilen aynı bilgisayar sistemidir.

### <a name="to-deploy-the-project-task-list-to-the-local-system"></a>Proje Görev listesi için yerel sistemi dağıtmak için

Visual Studio menü çubuğunda seçin **yapı**, **çözümü Dağıt**.

Visual Studio IIS uygulama havuzu geri dönüştürüldüğünde varolan çözüm sürümlerini geri çeker için SharePoint çözüm paketi (.wsp) dosyası kopyalar ve özelliklerini etkinleştirir. SharePoint çözüm artık kullanabilirsiniz. Dağıtım yapılandırma adımları hakkında daha fazla bilgi için bkz: [nasıl yapılır: SharePoint dağıtım yapılandırmasını düzenleme](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md).

### <a name="to-deploy-the-project-task-list-to-a-remote-system"></a>Uzak bir sisteme proje görev listesi dağıtmak için

1. Visual Studio menü çubuğunda seçin **yapı**, **Yayımla**.

2. İçinde **Yayımla** iletişim kutusunda, seçin **dosya sistemi Yayımla** seçenek düğmesi.

     Hedef konumda değiştirebileceğiniz **Yayımla** iletişim kutusunda üç nokta düğmesini seçerek ![üç nokta simgesi](../sharepoint/media/ellipsisicon.gif "üç nokta simgesi") ve başka bir konuma gezinme.

3. Seçin **Yayımla** düğmesi.

     .Wsp dosyası çözüm için oluşturulur.

4. .Wsp dosyası uzak SharePoint sisteme kopyalayın.

5. PowerShell kullanmak `Add-SPUserSolution` uzak SharePoint yükleme paketini yüklemek için komutu. (Küme çözümleri için kullanmak `Add-SPSolution` komutu.)

     Örneğin, `Add-SPUserSolution C:\MyProjects\ProjectTaskList\ProjectTaskList\bin\Debug\ProjectTaskList.wsp`.

6. PowerShell kullanmak `Install-SPUserSolution` çözümü dağıtmak için komutu. (Küme çözümleri için kullanmak `Install-SPSolution` komutu.)

     Örneğin, `Install-SPUserSolution -Identity ProjectTaskList.wsp -Site http://NewSiteName`.

     Uzaktan dağıtım hakkında daha fazla bilgi için bkz: [kullanan çözümler](http://go.microsoft.com/fwlink/?LinkId=217680) ve [ekleme ve SharePoint 2010 PowerShell'de dağıtma çözümleriyle](http://go.microsoft.com/fwlink/?LinkId=217682).

## <a name="next-steps"></a>Sonraki Adımlar

Özelleştirme ve aşağıdaki konulardan SharePoint çözümlerini dağıtma hakkında daha fazla bilgi edinebilirsiniz:

- [İzlenecek yol: SharePoint için Site Sütunu, İçerik Türü ve Liste Oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)

- [Nasıl yapılır: Olay Alıcısı Oluşturma](../sharepoint/how-to-create-an-event-receiver.md)

- [SharePoint Server 2010 için Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=217684)

## <a name="see-also"></a>Ayrıca Bkz.

[SharePoint Çözümlerini Paketleme ve Dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)