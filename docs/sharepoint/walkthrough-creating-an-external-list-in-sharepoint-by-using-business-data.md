---
title: İzlenecek yol:, iş verileri kullanarak SharePoint'te dış liste oluşturma | Microsoft Docs
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
- Business Data Connectivity service [SharePoint development in Visual Studio], business data in a Web Part
- BDC [SharePoint development in Visual Studio], external list
- Business Data Connectivity service [SharePoint development in Visual Studio], business data in a SharePoint list
- BDC [SharePoint development in Visual Studio], business data in a SharePoint list
- BDC [SharePoint development in Visual Studio], business data in a Web Part
- BDC [SharePoint development in Visual Studio], entity backed list
- Business Data Connectivity service [SharePoint development in Visual Studio], entity backed list
- Business Data Connectivity service [SharePoint development in Visual Studio], external list
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d8a557ae7f08afceee49e9e797f18562b548a67c
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120441"
---
# <a name="walkthrough-create-an-external-list-in-sharepoint-by-using-business-data"></a>İzlenecek yol:, iş verileri kullanarak SharePoint'te dış liste oluşturma

İş verileri bağlantı (BDC) hizmeti, arka uç sunucu uygulamaları, Web Hizmetleri ve veritabanları iş verilerini görüntülemek SharePoint sağlar.

Bu kılavuz, bir örnek veritabanında kişiler hakkında bilgi döndürür BDC hizmeti için bir model oluşturmak nasıl gösterir. Ardından, bu modelini kullanarak da SharePoint'te dış liste oluşturur.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Proje oluşturma.
- Varlık modeli ekleme.
- Bir Bulucu yöntemi ekleme.
- Belirli bir Bulucu yöntemi ekleme.
- Projeyi test etme.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

- Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

- AdventureWorks örnek veritabanı erişimi. AdventureWorks veritabanını yükleme hakkında daha fazla bilgi için bkz: [SQL Server örnek veritabanları](http://go.microsoft.com/fwlink/?LinkID=117483).

## <a name="create-a-project-that-contains-a-bdc-model"></a>BDC modeli içeren bir proje oluşturun

1. Visual Studio menü çubuğunda seçin **dosya** > **yeni** > **proje**.

     **Yeni proje** iletişim kutusu açılır.

2. Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** öğesi.

3. İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje**, proje adı **AdventureWorksTest**ve ardından **Tamam** düğmesi .

     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir. Bu sihirbazda, projenin hata ayıklamasını ve çözüm güven düzeyini ayarlamak için kullanacağınız site belirtebilirsiniz.

4. Seçin **Grup çözümü olarak dağıtma** güven düzeyini ayarlamak için seçenek düğmesi.

5. Seçin **son** varsayılan yerel SharePoint sitesi kabul et düğmesi.

6. İçinde **Çözüm Gezgini**, SharePoint projesi düğümünü seçin.

7. Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle**.

     **Yeni Öğe Ekle** iletişim kutusu açılır.

8. İçinde **şablonları** bölmesinde seçin **iş verileri bağlantı modeli (yalnızca Grup çözüm)**, proje adı **AdventureWorksContacts**ve ardından **Ekle** düğmesi.

## <a name="add-data-access-classes-to-the-project"></a>Veri erişim sınıfları projeye ekleyin

1. Menü çubuğunda seçin **Araçları** > **veritabanına bağlan**.

     **Bağlantı Ekle** iletişim kutusu açılır.

2. SQL Server AdventureWorks örnek veritabanına bir bağlantı ekleyin.

     Daha fazla bilgi için bkz: [Ekle/Değiştir bağlantı (Microsoft SQL Server)](http://msdn.microsoft.com/fa400910-26c3-4df7-b9d1-115e688b4ea3).

3. İçinde **Çözüm Gezgini**, proje düğümünü seçin.

4. Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle**.

5. İçinde **yüklü şablonlar** bölmesinde seçin **veri** düğümü.

6. İçinde **şablonları** bölmesinde seçin **LINQ'ten SQL'e sınıflarını**.

7. İçinde **adı** kutusunda, belirtin **AdventureWorks**ve ardından **Ekle** düğmesi.

     .Dbml dosyası projeye eklenir ve Nesne İlişkisel Tasarımcısı (O/R Tasarımcısı) açar.

8. Menü çubuğunda seçin **Görünüm** > **Sunucu Gezgini**.

9. İçinde **Sunucu Gezgini**AdventureWorks örnek veritabanını temsil eder düğümünü genişletin ve ardından **tabloları** düğümü.

10. Ekleme **başvurun (kişi)** O/R Tasarımcısı üzerine tablo.

     Bir varlık sınıfı oluşturulur ve tasarım yüzeyine görünür. Varlık sınıfı başvurun (kişi) tablosundaki sütunlara eşleme özellikleri vardır.

## <a name="remove-the-default-entity-from-the-bdc-model"></a>Varsayılan varlık BDC modeli kaldırma

**İş verileri bağlantı modeli** projesini modele Entity1 adlı bir varsayılan varlık ekler. Bu varlık kaldırın. Daha sonra yeni bir varlık ekleyeceksiniz. Boş bir modelle Başlangıç Kılavuzu tamamlamak için gereken adım sayısını azaltır.

1. İçinde **Çözüm Gezgini**, genişletin **BdcModel1** düğümünü ve ardından açın *BdcModel1.bdcm* dosya.

2. İş verileri bağlantı modeli dosyası BDC Tasarımcısı'nda açılır.

3. Kısayol menüsünü Tasarımcısı'nda açmak **Entity1**ve ardından **silmek**.

4. İçinde **Çözüm Gezgini**, kısayol menüsünü açın *Entity1.vb* (Visual Basic'te) veya *Entity1.cs* (C# ' ta) ve ardından **silme** .

5. Kısayol menüsünü açın *Entity1Service.vb* (Visual Basic'te) veya *Entity1Service.cs* (C# ' ta) ve ardından **silmek**.

## <a name="add-an-entity-to-the-model"></a>Modele bir varlık ekleme

Bir varlık modeline ekleyin. Visual Studio'dan varlıklar ekleyebilirsiniz **araç** BDC tasarımcıya.

1. Menü çubuğunda seçin **Görünüm** > **araç**.

2. Üzerinde **BusinessDataConnectivity** sekmesinde **araç**, ekleme bir **varlık** BDC tasarımcıya.

     Yeni varlık Tasarımcısı üzerinde görüntülenir. Visual Studio ekler adlı bir dosyayı *EntityService.vb* (Visual Basic'te) veya *EntityService.cs* (C# ' ta) projeye.

3. Menü çubuğunda seçin **Görünüm** > **özellikleri** > **penceresi**.

4. İçinde **özellikleri** penceresindeki ayarlayın **adı** özellik değerine **kişi**.

5. Varlık için kısayol menüsünü designer'ı açın, seçin **Ekle**ve ardından **tanımlayıcısı**.

     Yeni bir tanımlayıcı varlık üzerinde görüntülenir.

6. İçinde **özellikleri** penceresinde tanımlayıcısına adını değiştirmek **ilgili kişi kimliği**.

7. İçinde **türü adı** listesinde, seçin **System.Int32**.

## <a name="add-a-specific-finder-method"></a>Belirli bir Bulucu yöntemi ekleme

Belirli bir kişi görüntülenecek BDC hizmeti etkinleştirmek için belirli bir Bulucu yöntemi eklemeniz gerekir. Bir kullanıcı bir listeden bir öğe seçer ve ardından seçer BDC hizmeti belirli bir Bulucu yöntemi çağırır **görünümü öğesi** Şerit üzerindeki düğmesi.

Belirli bir Bulucu yöntemi kullanarak kişi varlığa eklemek **BDC yöntem ayrıntıları** penceresi. Belirli bir varlık döndürmek için kodu yöntemine ekleyin.

1. BDC designer'ı seçin **kişi** varlık.

2. Menü çubuğunda seçin **Görünüm** > **diğer pencereler** > **BDC yöntem ayrıntıları**.

     BDC yöntem Ayrıntıları penceresi açılır.

3. İçinde **bir yöntem ekleyin** listesinde, seçin **oluşturma belirli bir Bulucu yöntemi**.

     Visual Studio aşağıdaki öğeleri modele ekler. Bu öğeleri görünür **BDC yöntem ayrıntıları** penceresi.

    - ReadItem adlı bir yöntem.

    - Yöntem için giriş parametresi.

    - Yönteminin dönüş parametresi.

    - Her parametre için bir tür tanımlayıcı.

    - Yöntemi için yöntem örneği.

4. İçinde **BDC yöntem ayrıntıları** penceresinde görünür listesini açın **kişi** tanımlayıcısı yazın ve ardından **Düzenle**.

     **BDC Gezgini** açar ve model hiyerarşik bir görünümünü sağlar.

5. İçinde **özellikleri** penceresinde, listenin açmak **TypeName** özelliği, seçin **geçerli projenin** sekmesini ve ardından **kişi**özelliği.

6. İçinde **BDC Gezgini**, kısayol menüsünü açmak **kişi**ve ardından **eklemek tür tanımlayıcı**.

     Adlı yeni bir tür tanımlayıcı **TypeDescriptor1** görünür **BDC Gezgini**.

7. İçinde **özellikleri** penceresindeki ayarlayın **adı** özellik değerine **ilgili kişi kimliği**.

8. Listenin açmak **TypeName** özelliği ve ardından **Int32**.

9. Listenin açmak **tanımlayıcısı** özelliği ve ardından **ilgili kişi kimliği**.

10. Aşağıdaki alanların her biri için bir tür tanımlayıcı oluşturmak için 6. adımı yineleyin.

    |Ad|Tür adı|
    |----------|---------------|
    |firstName|System.String|
    |Soyadı|System.String|
    |Telefon|System.String|
    |EmailAddress|System.String|
    |EmailPromotion|System.Int32|
    |NameStyle|System.Boolean|
    |PasswordHash|System.String|
    |PasswordSalt|System.String|

11. BDC Tasarımcısı'nda üzerinde **kişi** varlık, açık **ReadItem** yöntemi.

     Kişi hizmeti kod dosyasını Kod Düzenleyicisi'nde açar.

12. İçinde `ContactService` sınıfı, yerine `ReadItem` aşağıdaki kod ile yöntemi. Bu kod aşağıdaki görevleri gerçekleştirir:

    - Bir kayıt AdventureWorks veritabanını ilgili kişi tablosundan alır.

    - Bir kişi varlık BDC hizmetine döndürür.

    > [!NOTE]
    > Değerini `ServerName` alanını sunucunuzun adıyla.

     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]

## <a name="add-a-finder-method"></a>Bir Bulucu yöntemi ekleme

Kişiler bir listede görüntülenecek BDC hizmetini etkinleştirmek için bir Bulucu yöntemi eklemeniz gerekir. Kullanarak kişi varlığa bir Bulucu yöntemi ekleme **BDC yöntem ayrıntıları** penceresi. Varlık koleksiyonu BDC hizmete döndürmek için kodu yöntemine ekleyin.

1. BDC Tasarımcısı'nda seçin **kişi** varlık.

2. İçinde **BDC yöntem ayrıntıları** penceresinde, Daralt **ReadItem** düğümü.

3. İçinde **bir yöntem ekleyin** altında listesinde **ReadList** yöntemi seçin **oluşturma Bulucu yöntemi**.

     Visual Studio bir yöntemi, dönüş parametresi ve bir tür tanımlayıcı ekler.

4. BDC Tasarımcısı'nda üzerinde **kişi** varlık, açık **ReadList** yöntemi.

     Kişi hizmeti kod dosyasını Kod Düzenleyicisi'nde açar.

5. İçinde `ContactService` sınıfı, yerine `ReadList` aşağıdaki kod ile yöntemi. Bu kod aşağıdaki görevleri gerçekleştirir:

    - AdventureWorks veritabanını kişiler tablosundan verileri alır.

    - BDC hizmete kişi varlıkları listesini döndürür.

    > [!NOTE]
    > Değerini `ServerName` alanını sunucunuzun adıyla.

     [!code-csharp[SP_BDC#2](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#2)]

## <a name="test-the-project"></a>Projeyi test

Projeyi çalıştırdığınızda, SharePoint sitesini açar ve Visual Studio iş verileri bağlantı hizmeti modelinizi ekler. Kişi varlığı başvuran SharePoint'te dış liste oluşturun. AdventureWorks veritabanını kişiler için verileri listede görüntülenir.

> [!NOTE]
> Çözümünüzü ayıklayabilirsiniz önce SharePoint güvenlik ayarlarını değiştirmeniz gerekebilir. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).

1. Seçin **F5** anahtarı.

     SharePoint sitesi açılır.

2. Üzerinde **Site eylemleri** menüsünde seçin **diğer seçenekler** komutu.

3. Üzerinde **oluşturma** sayfasında, **dış liste** şablonu ve ardından **oluşturma** düğmesi.

4. Özel listeye ad **kişiler**.

5. Gözat düğmesini seçin **dış içerik türü** alan.

6. İçinde **dış içerik türü Seçici** iletişim kutusunda, seçin **AdventureWorksContacts.BdcModel1.Contact** öğesini ve ardından **oluşturma** düğmesi.

     SharePoint AdventureWorks örnek veritabanını kişilerden içeren dış liste oluşturur.

7. Belirli bir Bulucu yöntemi sınamak için listede bir kişi seçin.

8. Şerit'te seçin **öğeleri** sekmesini ve ardından **görünümü öğesi** komutu.

     Seçtiğiniz kişi ayrıntılarını bir form üzerinde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

SharePoint BDC hizmetinde aşağıdaki konulardan modellerinde tasarlamak hakkında daha fazla bilgi edinebilirsiniz:

- [Nasıl yapılır: bir yaratıcı yöntemi ekleme](../sharepoint/how-to-add-a-creator-method.md).
- [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md).
- [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md).

## <a name="see-also"></a>Ayrıca bkz.

[İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)  
[İş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md)  
[BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)  
[İş verilerini SharePoint ile tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md)
