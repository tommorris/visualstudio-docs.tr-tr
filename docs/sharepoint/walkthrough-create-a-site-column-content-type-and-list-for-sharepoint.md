---
title: 'İzlenecek yol: bir Site sütunu, içerik türü ve SharePoint listesi oluşturun | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.ListDesigner.GeneralMessageHelp
- Microsoft.VisualStudio.SharePoint.Designers.ListDesigner.ViewModels.ListViewModel.SortingAndGrouping
- VS.SharePointTools.ListDesigner.SortingGrouping
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, list definitions
- SharePoint development in Visual Studio, list instances
- SharePoint development in Visual Studio, fields
- SharePoint development in Visual Studio, content types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0dfcf3166e3fe4aa5ce17f51d696187cc060639b
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="walkthrough-create-a-site-column-content-type-and-list-for-sharepoint"></a>İzlenecek yol: SharePoint için Site Sütunu, İçerik Türü ve Liste Oluşturma
  Aşağıdaki yordamlar özel SharePoint site sütunları oluşturulacağını göstermektedir — veya *alanları*— yanı sıra site sütunlarını kullanan bir içerik türü. Ayrıca, yeni içerik türünü kullanan bir listesinin nasıl oluşturulacağı gösterilir.  
  
 Bu izlenecek yol aşağıdaki görevleri içerir:  
  
-   [Özel Site sütunları oluşturma](#BKMK_CreatingCustSiteCols).  
  
-   [Özel bir içerik türü oluşturma](#BKMK_CreateCustContType).  
  
-   [Liste oluşturma](#BKMK_CreateList).  
  
-   [Liste oluşturma](#BKMK_CreateList).  
  
-   [Uygulamayı test etme](#BKMK_TestApp).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
##  <a name="BKMK_CreatingCustSiteCols"></a> Özel Site sütunları oluşturma  
 Bu örnek, hastaneler hastalar yönetmek için bir liste oluşturur. İlk olarak, bir SharePoint Proje oluşturmalısınız [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve site sütunları, aşağıdaki gibi ekleyin.  
  
#### <a name="to-create-the-project"></a>Proje oluşturmak için  
  
1.  Üzerinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] **dosya** menüsünde seçin **yeni**, **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından seçin**2010**.  
  
3.  İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje**, projeye adını değiştirmek **Clinic**ve ardından **Tamam** düğme.  
  
     Bu örnekte, site sütunları ve daha sonra eklenen diğer proje öğeleri kapsamak için kullanılmış boş proje için SharePoint 2010 proje şablonudur.  
  
4.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, yeni özel alan öğesi eklemek istediğiniz yerel SharePoint sitesi için URL'yi girin veya varsayılan konumu kullanın (`http://<`*SystemName* `>/)`.  
  
5.  İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, varsayılan değeri kullanın **korumalı bir çözüm olarak dağıtma**.  
  
     Korumalı hakkında daha fazla bilgi ve Grup çözümleri için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
6.  Seçin **son** düğmesi. Proje içinde artık listelenmelidir **Çözüm Gezgini**.  
  
#### <a name="to-add-site-columns"></a>Site sütunları eklemek için  
  
1.  Yeni bir site sütunu ekleyin. Bunu yapmak için **Çözüm Gezgini**, kısayol menüsünü açın **Clinic**ve ardından **Ekle**, **yeni öğe**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **Site sütunu**, adına değiştirme **hasta adı**ve ardından **Ekle** düğmesi.  
  
3.  Site sütunun Elements.xml dosyasında bırakın **türü** olarak ayarlama **metin**, değiştirip **grup** ayarını **Clinic Site sütunları**. Tamamlandığında, site sütunun Elements.xml dosyasını aşağıdaki gibi görünmelidir.  
  
    ```xml  
    <Field  
         ID="{f9ba60d1-5631-41fb-b016-a38cf48eef63}"  
         Name="Clinic - Patient Name"  
         DisplayName="Patient Name"  
         Type="Text"  
         Required="FALSE"  
         Group="Clinic Site Columns">  
    </Field>  
    ```  
  
4.  Aynı yordamı kullanarak, iki daha fazla site sütunları projeye ekleyin: **hasta kimliği** (tür = "Tamsayı") ve **Doctor adı** (tür = "Text"). Grup değerlerine ayarlayın **Clinic Site sütunları**.  
  
##  <a name="BKMK_CreateCustContType"></a> Özel bir içerik türü oluşturma  
 Ardından, bir içerik türü oluşturma — kişiler içerik türüne göre — önceki yordamda oluşturduğunuz site sütunları içerir. Varolan bir içerik türü bir içerik türü alma tarafından temel içerik türü için yeni içerik türü kullanımda birkaç site sütunları sağladığından zamandan tasarruf edebilirsiniz.  
  
#### <a name="to-create-a-custom-content-type"></a>Özel bir içerik türü oluşturmak için  
  
1.  Bir içerik türü projeye ekleyin. Bunu yapmak için **Çözüm Gezgini**, proje düğümüne seçin  
  
2.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.  
  
3.  Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
4.  İçinde **şablonları** bölmesinde seçin **içerik türü** şablon adla değiştirin **hasta bilgisi**ve ardından **Ekle** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** açar.  
  
5.  İçinde **hangi temel içerik türü bu içerik türü devralınmalıdır** listesinde, seçin **kişi** yeni içerik türünü temel ve ardından içerik türü olarak **Son**düğmesi.  
  
     Bunun yapılması, önceden tanımlanmış site sütunları yanı sıra kişi içerik türündeki diğer olası yararlı site sütunları erişmenizi sağlar.  
  
6.  İçerik türü sonra Tasarımcısı, içinde görünür **sütunları** sekmesinde, üç site daha önce tanımlanan sütunları ekleyin: **hasta adı**, **hasta kimliği**ve **Doctor adı**. Bu sütun eklemek için site sütunları listenin altında ilk liste kutusunu seçin. **görünen adı**ve ardından her site sütunu listede biri aynı anda seçin.  
  
    > [!TIP]  
    >  Daha hızlı site sütunları seçmek için sütunun adının ilk birkaç harfini girerek listesini filtreleyin.  
  
7.  Üç özel site sütunları yanı sıra eklemek **açıklamaları** site sütunları listesinden site sütunu.  
  
8.  Seçin **gerekli** onay kutusunu **hasta adı** ve **hasta kimliği** bunları yapmak için site sütunları gerekli alanları.  
  
9. Üzerinde **içerik türü** sekmesinde, içerik türü adı olduğundan emin olun **hasta bilgisi**ve açıklamayı değiştirin **hasta bilgi kartını**.  
  
10. Değişiklik **grup adı** için **Clinic içerik türleri**ve diğer ayarları varsayılan değerlerinde bırakın.  
  
11. Menü çubuğunda seçin **dosya**, **Tümünü Kaydet**, içerik türü Tasarımcısı'nı kapatın.  
  
##  <a name="BKMK_CreateList"></a> Liste oluşturma  
 Artık, yeni içerik türü ve site sütunlarını kullanan bir liste oluşturur.  
  
#### <a name="to-create-a-list"></a>Bir liste oluşturmak için  
  
1.  Bir liste projeye ekleyin. Bunu yapmak için **Çözüm Gezgini**, proje düğümünü seçin.  
  
2.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.  
  
3.  Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
4.  İçinde **şablonları** bölmesinde seçin **listesi** şablonu, adına değiştirmek **hastalar**ve ardından **Ekle** düğmesi.  
  
5.  Bırakın **dayanan liste özelleştirme** olarak ayarlama **varsayılan (boş)** ve ardından **son** düğmesi.  
  
6.  Liste Tasarımcısı'nda seçin **içerik türleri** görüntülemek için düğmesini **içerik türü ayarları** iletişim kutusu.  
  
7.  Yeni satır seçin, seçin **hasta bilgisi** içerik türü listesinde içerik türlerinin ve ardından **Tamam** düğmesi.  
  
     Bunun yapılması, ekler tüm site sütunlarından **hasta bilgisi** içerik listeye türü.  
  
8.  Tüm site sütunları listesinde aşağıdaki dışında sil:  
  
    -   Hasta kimliği  
  
    -   Hasta adı  
  
    -   Ev Telefonu  
  
    -   E-posta  
  
    -   Doktor adı  
  
    -   Açıklamalar  
  
9. Altında **sütun görünen adı**, boş bir satırı seçin, özel bir liste sütun ekleyin ve adlandırın **Hastanenin**. Veri türü olarak bırakın **tek satır metin**.  
  
     Özel bir liste sütun bu listede yalnızca geçerlidir. Özel liste sütununu liste eklediğinizde, listeye eklenen tüm sütunlar dahil olmak üzere yeni bir liste içerik türü, oluşturulur ve varsayılan listesi olarak ayarlayın.  
  
    > [!TIP]  
    >  Site sütunları listesinden bir sütun seçerseniz, varolan bir site sütunu kullanılır. Hiçbir sütun listesinde seçerek olmadan bir sütun adı değeri girerseniz, bile aynı ada sahip bir sütun zaten listede var. ancak, özel bir liste sütun, oluşturulur.  
  
     Ayar için özel bir liste sütun veri türü yerine isteğe bağlı olarak, **tek satır metin**, bunun yerine bu sütunun veri türü için arama ayarlayabilir ve değerlerinin bir tablo veya başka bir listeden alınması. Arama sütunları hakkında daha fazla bilgi için bkz: [SharePoint 2010 listesi ilişkilerde](http://go.microsoft.com/fwlink/?LinkId=224994) ve [aramaları ve liste ilişkileri](http://go.microsoft.com/fwlink/?LinkID=224995).  
  
10. Yanına **hasta kimliği** ve **hasta adı** kutuları, select **gerekli** onay kutusu.  
  
11. Üzerinde **görünümleri** sekmesinde, bir görünüm oluşturmak için boş bir satırı seçin. Girin **hasta ayrıntıları**.  
  
     Üzerinde **görünümleri** sekmesi, SharePoint listesindeki görünmesini istediğiniz sütunları belirtebilirsiniz.  
  
12. Yeni seçin **hasta ayrıntıları** satır ve ardından **varsayılan olarak ayarla** düğmesi.  
  
     Yeni görünüm listesi için varsayılan görünümü sunulmuştur.  
  
13. Aşağıdaki sütunlara eklemek **seçili sütun** aşağıdaki sırayla listesi:  
  
    -   Hasta kimliği  
  
    -   Hasta adı  
  
    -   Ev Telefonu  
  
    -   E-posta  
  
    -   Doktor adı  
  
    -   Hastanenin  
  
    -   Açıklamalar  
  
14. İçinde **özellikleri** listesinde, seçin **sıralama ve Gruplama** özelliği ve ardından üç nokta düğmesine ![üç nokta simgesi](../sharepoint/media/ellipsisicon.gif "üç nokta simgesi")görüntülemek için **sıralama ve Gruplama** iletişim kutusu.  
  
15. İçinde **sütun adı** listesinde, seçin **hasta adı**, olduğundan emin olun **sıralama** sütunu olarak ayarlanmış **artan**ve ardından seçin **Tamam** düğmesi.  
  
##  <a name="BKMK_TestApp"></a> Uygulamayı test etme  
 Özel site sütunları, içerik türü ve liste hazır, SharePoint'e dağıtmak ve test için uygulamayı çalıştırın.  
  
#### <a name="to-test-the-application"></a>Uygulamayı test etmek için  
  
1.  Menü çubuğunda seçin **dosya**, **Tümünü Kaydet**.  
  
2.  Uygulamayı çalıştırmak için F5 tuşuna seçin.  
  
     Uygulama derlenir ve ardından özelliklerini SharePoint'e dağıtılan ve etkinleştirildi.  
  
3.  Hızlı Gezinti çubuğunda seçin **hastalar** görüntülemek için bağlantıyı **hastalar** listesi.  
  
     Sütun adları listesi, girdiğiniz eşleşmelidir **görünümleri** sekmesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
4.  Seçin **Yeni Öğe Ekle** hasta bilgi kartını oluşturmak için bağlantı.  
  
5.  Alanlara bilgileri girin ve ardından **kaydetmek** düğmesi.  
  
     Yeni kayıttaki listede görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint için site sütunları, içerik türleri ve listeler oluşturma](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [Nasıl yapılır: özel alan türü oluşturma](http://go.microsoft.com/fwlink/?LinkId=192079)   
 [İçerik türleri](http://go.microsoft.com/fwlink/?LinkId=192080)   
 [sütunları](http://go.microsoft.com/fwlink/?LinkId=192081)  
  
  