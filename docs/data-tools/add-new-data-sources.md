---
title: Yeni veri kaynakları ekleyin
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.datasource.datasourcefieldspicker
helpviewer_keywords:
- data [Visual Studio], data sources
- data sources
ms.assetid: ed28c625-bb89-4037-bfde-cfa435d182a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a4196e21eaf5cdb01e549f45292880ede7d63e58
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845151"
---
# <a name="add-new-data-sources"></a>Yeni veri kaynakları ekleyin
Visual Studio'da .NET veri araçları bağlamında terimi *veri kaynağı* , bir veri deposuna bağlanmak ve .NET uygulama verileri kullanıma .NET nesneleri gösterir. Visual Studio tasarımcıları veritabanı nesnelerini sürükleyip yükleyen formlara veri bağlar Demirbaş kod oluşturmak için veri kaynağı çıktı tüketebileceği **veri kaynakları** penceresi. Bu türdeki veri kaynağının aşağıdakilerden biri olabilir:

-   Bir tür veritabanı ile ilişkili bir Entity Framework modelini sınıfta.

-   Bir tür veritabanı ile ilişkili bir veri kümesi.

-   Windows Communication Foundation (WCF) veri hizmeti veya bir REST hizmeti gibi bir ağ hizmeti temsil eden sınıf.

-   Bir SharePoint hizmeti temsil eden sınıf.

-   Bir sınıf veya çözümünüzdeki koleksiyonu.

> [!NOTE]
>  Veri bağlama özellikleri kullanmıyorsanız, veri kümeleri, Entity Framework, LINQ-SQL, WCF veya SharePoint, "veri kaynağı" kavramı geçerli değildir. Yalnızca SQLCommand nesnesi kullanarak doğrudan veritabanına bağlanmak ve veritabanıyla doğrudan iletişim kurar.

 Oluşturma ve veri kaynakları kullanarak düzenleme **veri kaynağı Yapılandırma Sihirbazı** bir Windows Forms ya da Windows Presentation Foundation uygulamasında. Entity Framework için ilk varlık sınıfı oluşturun ve ardından seçerek Sihirbazı'nı başlatmak **proje** > **yeni veri kaynağı Ekle** (Bu makalenin sonraki bölümlerinde daha ayrıntılı açıklanmıştır).

 ![Veri Kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png)

 Bir veri kaynağı oluşturduktan sonra görünür **veri kaynakları** araç penceresi (**Shift**+**Alt**+**D**veya **Görünüm** > **diğer Windows** > **veri kaynağı**). Bir veri kaynağından sürükleyebilirsiniz **veri kaynakları** form Tasarım yüzeyi veya denetimi penceresi. Bu Demirbaş kod oluşturulmasına neden olur — kullanıcı veri deposundaki kaynaklı verileri görüntüler kodu. Aşağıdaki çizimde Windows formunuza bırakılan bir veri kümesini gösterir. Seçtiyseniz **F5** uygulamanın, veritabanından alınan veri formun denetimlerinde görüntülenir.

 ![Veri kaynağı sürükleme işlemi](../data-tools/media/raddata-data-source-drag-operation.png)

## <a name="data-source-for-a-database-or-a-database-file"></a>Bir veritabanı veya veritabanı dosyası için veri kaynağı

### <a name="dataset"></a>Veri kümesi
 Veri kaynağı olarak bir veri kümesi oluşturmak için çalıştırın **veri kaynağı Yapılandırma Sihirbazı** (**proje** > **yeni veri kaynağı Ekle**) ve  **Veritabanı** veri kaynağı türü. Yeni veya var olan veritabanı bağlantısı veya bir veritabanı dosyası belirtmek için istemleri izleyin.

### <a name="entity-classes"></a>Varlık sınıfı
 İlk çalıştırarak bir veri kaynağı olarak bir Entity Framework modelini oluşturma **varlık veri modeli Sihirbazı** varlık sınıfları oluşturmak için (**proje** > **Yeni Öğe Ekle**  >  **ADO.NET varlık veri modeli**).

 ![Yeni Entity Framework modelini proje öğesi](../data-tools/media/raddata-new-entity-framework-model-project-item.png)

 Model oluşturmak istediğiniz yöntemi seçin.

 ![Varlık veri modeli Sihirbazı](../data-tools/media/raddata-entity-data-model-wizard.png)

 Model bir veri kaynağı olarak ekleyin. Oluşturulan sınıflar görünür **veri kaynağı Yapılandırma Sihirbazı** seçtiğinizde **nesneleri** kategorisi.

 ![Sınıflar ile veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/raddata-data-source-configuration-wizard-with-entity-classes.png)

## <a name="data-source-for-a-service"></a>Bir hizmet için veri kaynağı
 Bir veri kaynağı alanından bir hizmet oluşturmak için çalıştırın **veri kaynağı Yapılandırma Sihirbazı** ve **hizmet** veri kaynağı türü. Bu yalnızca bir kısayoludur **hizmet Başvurusu Ekle** projeye sağ tıklayarak da erişebilirsiniz iletişim kutusu, **Çözüm Gezgini** ve seçerek **hizmetBaşvurusuEkle**.

 Bir hizmetinden bir veri kaynağı oluşturduğunuzda, Visual Studio hizmeti başvuru projenize ekler. Visual Studio ayrıca hizmet döndürür nesnelere karşılık proxy nesneleri oluşturur. Örneğin, bir veri kümesini döndüren bir hizmet projenizdeki bir veri kümesi temsil edilir; belirli bir tür projenizdeki türü olarak temsil edilir döndürür döndürülen hizmet.

 Bir veri kaynağı Hizmetleri aşağıdaki türlerden oluşturabilirsiniz:

-   WCF Veri Hizmetleri. Daha fazla bilgi için bkz: [genel bakış](/dotnet/framework/data/wcf/wcf-data-services-overview).

-   WCF hizmetleri. Daha fazla bilgi için bkz: [Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md).

-   Web Hizmetleri.

    > [!NOTE]
    >  İçinde görüntülenen öğeleri **veri kaynakları** penceresi hizmet veren verilere bağımlı. Bazı hizmetler için yeterli bilgi sağlamayabilir **veri kaynağı Yapılandırma Sihirbazı** bağlanabilirse nesneleri oluşturmak için. Hizmet türü belirsiz bir veri kümesini döndürürse, örneğin, hiç öğe görünür **veri kaynakları** Sihirbazı tamamladığınızda penceresi. Yazılmayan veri kümeleri bir şema sağlamaz ve bu nedenle sihirbazın veri kaynağı oluşturmak için yeterli bilgi yok nedeni budur.

## <a name="data-source-for-an-object"></a>Bir nesne için veri kaynağı
 Çalıştırarak bir veya daha fazla ortak özellikleri kullanıma sunan herhangi bir nesneden bir veri kaynağı oluşturabilirsiniz **veri kaynağı Yapılandırma Sihirbazı** seçilerek **nesne** veri kaynağı türü. Bir nesnenin tüm ortak özellikleri görüntülenir **veri kaynakları** penceresi. Entity Framework kullanarak ve bir modeli oluşturulmasını, uygulamanız için veri kaynakları olan varlık sınıfları nerede budur.

 Üzerinde **veri nesneleri seçin** sayfasında, ağaç görünümünde bağlamak istediğiniz nesneleri bulmak için düğümleri genişletin. Ağaç görünümü ve derlemeler ve projeniz tarafından başvurulan diğer projeler projeniz için düğümleri içerir.

 Bir derleme veya ağaç görünümünde görünmez projesindeki bir nesneyi bağlamak istiyorsanız, tıklatın **Başvuru Ekle** ve **başvuru iletişim kutusunu** derleme ya da proje başvuru eklemek için. Başvuru ekledikten sonra derleme veya proje ağaç görünümüne eklenir.

> [!NOTE]
>  Nesnelerinizi nesneleri ağaç görünümünde görüntülenen önce içeren projeyi oluşturmak gerekebilir.

> [!NOTE]
>  Sürükle ve bırak veri bağlama uygulayan nesneler desteklemek için <xref:System.ComponentModel.ITypedList> veya <xref:System.ComponentModel.IListSource> arabirimi varsayılan bir oluşturucu olması gerekir. Aksi takdirde, Visual Studio veri kaynağı nesnesi başlatılamıyor ve öğeyi tasarım yüzeyine sürükleyin olduğunda bir hata görüntüler.

## <a name="data-source-for-a-sharepoint-list"></a>Veri kaynağı bir SharePoint listesi için
 Bir veri kaynağı bir SharePoint listesinden çalıştırarak oluşturabileceğiniz **veri kaynağı Yapılandırma Sihirbazı** ve seçerek **SharePoint** veri kaynağı türü. SharePoint sunan verilerine [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], bir SharePoint veri kaynağı oluşturmadan bir hizmetinden veri kaynağı oluşturma ile aynıdır. Seçme **SharePoint** öğesi **veri kaynağı Yapılandırma Sihirbazı** açılır **hizmet Başvurusu Ekle** SharePoint veri hizmetine eriştikleri iletişim kutusu SharePoint sunucusuna işaret ederek.  Bu SharePoint SDK'sını gerektirir.

## <a name="see-also"></a>Ayrıca bkz.

- [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)