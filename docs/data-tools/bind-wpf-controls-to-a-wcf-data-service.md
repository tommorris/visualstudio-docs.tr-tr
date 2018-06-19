---
title: Bir WCF veri hizmetine WPF denetimleri bağlama
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 8823537c-82f0-41f7-bf30-705f0e5e59fd
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 8152a02df8f335a92024134dde89b45d2f3e115a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31927366"
---
# <a name="bind-wpf-controls-to-a-wcf-data-service"></a>Bir WCF veri hizmetine WPF denetimleri bağlama

Bu kılavuzda, veri bağlama denetimleri içeren bir WPF uygulaması oluşturacaksınız. Denetimleri içinde kapsüllenmiş Müşteri kayıtlarını bağlı bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)]. Aynı zamanda müşterilerin kayıtları görüntülemek ve güncelleştirmek için kullanabileceğiniz düğmeleri ekler.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Bir varlık veri modeli oluşturma AdventureWorksLT örnek veritabanındaki verilerden oluşturulur.

- Oluşturma bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] veri WPF uygulaması varlık veri modeli sunar.

- Veri bağlama denetimleri kümesini konumundan öğeleri sürükleyerek oluşturma **veri kaynakları** WPF Tasarımcısı penceresine.

- İleri ve geri müşteri kayıtlar arasında gezinme düğmelerini oluşturma.

- Denetimlere veri değişiklikleri kaydeder düğmesi oluşturma [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] ve temel alınan veri kaynağı.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Önkoşullar
Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]

-   SQL Server ya da ekli AdventureWorksLT örnek veritabanı olan SQL Server Express'in çalışan örneğine erişim. AdventureWorksLT veritabanından indirebilirsiniz [CodePlex Web sitesinde](http://go.microsoft.com/fwlink/?linkid=87843).

Aşağıdaki kavramlar önceki bilgi de yararlı, ancak izlenecek yolu tamamlamak için gerekli değildir:

-   WCF Veri Hizmetleri. Daha fazla bilgi için bkz: [genel bakış](/dotnet/framework/data/wcf/wcf-data-services-overview).

-   Veri modelleri [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)].

-   Varlık veri modeli ve ADO.NET Entity Framework. Daha fazla bilgi için bkz: [Entity Framework genel bakış](/dotnet/framework/data/adonet/ef/overview).

-   WPF veri bağlama. Daha fazla bilgi için bkz: [veri bağlama genel bakış](/dotnet/framework/wpf/data/data-binding-overview).

## <a name="create-the-service-project"></a>Hizmet projesi oluşturma
Bu izlenecek yol için bir proje oluşturun bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

### <a name="to-create-the-service-project"></a>Hizmeti projesi oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

3.  Genişletme **Visual C#** veya **Visual Basic**ve ardından **Web**.

4.  Seçin **ASP.NET Web uygulaması** proje şablonu.

5.  İçinde **adı** kutusuna `AdventureWorksService` tıklatıp **Tamam**.

     Visual Studio oluşturur `AdventureWorksService` projesi.

6.  İçinde **Çözüm Gezgini**, sağ **Default.aspx** seçip **silmek**. Bu dosya bu kılavuzda gerekli değildir.

## <a name="create-an-entity-data-model-for-the-service"></a>Hizmeti için bir varlık veri modeli oluşturma
Kullanarak bir uygulamaya veri kullanıma sunmak için bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], hizmet için bir veri modeli tanımlamanız gerekir. [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] Veri modelleri iki türlerini destekler: Varlık veri modeli ve uygulama ortak dil çalışma zamanı (CLR) nesneleri kullanılarak tanımlanmış özel veri modeli <xref:System.Linq.IQueryable%601> arabirimi. Bu kılavuzda, veri modeli için bir varlık veri modeli oluşturun.

### <a name="to-create-an-entity-data-model"></a>Bir varlık veri modeli oluşturmak için

1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.

2.  Yüklü Şablonlar listesinde tıklayın **veri**ve ardından **ADO.NET varlık veri modeli** proje öğesi.

3.  Adına değiştirme `AdventureWorksModel.edmx`, tıklatıp **Ekle**.

     **Varlık veri modeli** Sihirbazı açılır.

4.  Üzerinde **Model içeriği seçin** sayfasında, **veritabanından Oluştur**, tıklatıp **sonraki**.

5.  Üzerinde **veri bağlantınızı** sayfasında, aşağıdaki seçeneklerden birini seçin:

    -   Aşağı açılan listesinde AdventureWorksLT örnek veritabanı veri bağlantısı olup olmadığını seçin.

    -   Tıklatın **yeni bağlantı**ve AdventureWorksLT veritabanına bağlantı oluşturun.

6.  Üzerinde **veri bağlantınızı** sayfasında, olduğundan emin olun **varlık bağlantı ayarlarını App.Config'de şöyle Kaydet** seçeneği seçilir ve ardından **sonraki**.

7.  Üzerinde **veritabanı nesnelerinizi** sayfasında **tabloları**ve ardından **SalesOrderHeader** tablo.

8.  **Son**'a tıklayın.

## <a name="create-the-service"></a>Hizmet oluşturma
Oluşturma bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] varlık veri modeli WPF uygulaması için verileri kullanıma sunmak için.

### <a name="to-create-the-service"></a>Bir hizmet oluşturmak için

1.  Üzerinde **proje** menüsünde, select **Yeni Öğe Ekle**.

2.  Yüklü Şablonlar listesinde tıklayın **Web**ve ardından **WCF veri hizmeti** proje öğesi.

3.  İçinde **adı** kutusuna `AdventureWorksService.svc`, tıklatıp **Ekle**.

     Visual Studio ekler `AdventureWorksService.svc` projeye.

## <a name="configure-the-service"></a>Hizmetini yapılandırma
Oluşturduğunuz varlık veri modeli üzerinde çalışmaya hizmetini yapılandırmanız gerekir.

### <a name="to-configure-the-service"></a>Hizmeti yapılandırmak için

1.  İçinde `AdventureWorks.svc` kod dosyası, yerine `AdventureWorksService` sınıf bildiriminin aşağıdaki kod ile.

     [!code-csharp[Data_WPFWCF#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_1.cs)]
     [!code-vb[Data_WPFWCF#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_1.vb)]

     Bu kod güncelleştirmeleri `AdventureWorksService` den türemesi için sınıf bir <xref:System.Data.Services.DataService%601> , çalışır `AdventureWorksLTEntities` varlık veri modelinizi bağlam sınıfında nesne. Aynı zamanda güncelleştirmeleri `InitializeService` hizmeti tam okuma/yazma erişimi istemcilerin yöntemi `SalesOrderHeader` varlık.

2.  Projeyi derlemek ve hatasız oluşturulduğunu doğrulayın.

## <a name="create-the-wpf-client-application"></a>WPF istemci uygulaması oluşturma
Verileri görüntülemek için [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], hizmetini temel alan bir veri kaynağı ile yeni bir WPF uygulaması oluşturun. Bu kılavuzda daha sonra uygulamaya verilere bağlı denetimler ekleyeceksiniz.

### <a name="to-create-the-wpf-client-application"></a>WPF istemci uygulaması oluşturmak için

1.  İçinde **Çözüm Gezgini**, çözüm düğümüne sağ tıklayın, **Ekle**seçip **yeni proje**.

2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic**ve ardından **Windows**.

3.  Seçin **WPF uygulaması** proje şablonu.

4.  İçinde **adı** kutusuna `AdventureWorksSalesEditor`, tıklatıp **Tamam**.

     Visual Studio ekler `AdventureWorksSalesEditor` çözüme proje.

5.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.

     **Veri kaynakları** penceresi açılır.

6.  İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.

     **Veri kaynağı yapılandırması** Sihirbazı açılır.

7.  İçinde **bir veri kaynağı türü seç** seçin sayfasında **hizmet**ve ardından **sonraki**.

8.  İçinde **hizmet Başvurusu Ekle** iletişim kutusu, tıklatın **bulma**.

     Visual Studio kullanılabilir hizmetler için geçerli çözümü arar ve ekler `AdventureWorksService.svc` içinde kullanılabilir hizmetler listesinde **Hizmetleri** kutusu.

9. İçinde **Namespace** kutusuna `AdventureWorksService`.

10. İçinde **Hizmetleri** kutusunda, **AdventureWorksService.svc**ve ardından **Tamam**.

     Visual Studio hizmet bilgilerini yükler ve ardından döndürür **veri kaynağı yapılandırması** Sihirbazı.

11. İçinde **hizmet Başvurusu Ekle** sayfasında, **son**.

     Visual Studio ekler için hizmet tarafından döndürülen verileri temsil eden düğümleri **veri kaynakları** penceresi.

## <a name="define-the-user-interface-of-the-window"></a>Kullanıcı arabirimi penceresinin tanımlayın
Birkaç düğmeleri WPF Tasarımcısı XAML'de değiştirerek penceresine ekleyin. Bu kılavuzda daha sonra görüntülemek ve bu düğmeleri kullanarak satış kayıtlarını güncelleştirmek kullanıcıların sağlayan kod ekleyeceksiniz.

### <a name="to-create-the-window-layout"></a>Pencere düzenini oluşturmak için

1.  İçinde **Çözüm Gezgini**, çift **MainWindow.xaml**.

     WPF Tasarımcısı'nda penceresi açılır.

2.  İçinde [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] tasarımcısına görüntülemek için aşağıdaki kodu arasında ekleyin `<Grid>` etiketler:

    ```xaml
    <Grid.RowDefinitions>
        <RowDefinition Height="75" />
        <RowDefinition Height="525" />
    </Grid.RowDefinitions>
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>
    ```

3.  Projeyi oluşturun.

## <a name="create-the-data-bound-controls"></a>Verilere bağlı denetimler oluşturma
Müşteri kayıtlarını sürükleyerek görüntüleyen denetimler oluşturma `SalesOrderHeaders` düğümden **veri kaynakları** Tasarımcı penceresine.

### <a name="to-create-the-data-bound-controls"></a>Veri bağlama denetimleri oluşturmak için

1.  İçinde **veri kaynakları** penceresinde, aşağı açılan menüsüne tıklayın **SalesOrderHeaders** düğümü ve select **ayrıntıları**.

2.  Genişletme **SalesOrderHeaders** düğümü.

3.  Bu örnek için bazı alanlar görüntülenmez, bu nedenle aşağıdaki düğümler yanındaki açılır menüsünü tıklatın ve seçin **hiçbiri**:

    -   **CreditCardApprovalCode**

    -   **ModifiedDate**

    -   **OnlineOrderFlag**

    -   **RevisionNumber**

    -   **ROWGUID**

    Bu eylem, Visual Studio sonraki adımda bu düğümler için verilere bağlı denetimler oluşturmasını engeller. Bu kılavuz için son kullanıcı, bu verileri görmek gerekmez varsayalım.

4.  Gelen **veri kaynakları** penceresinde, sürükle **SalesOrderHeaders** düğmeleri içeren satırı altında kılavuz satıra düğümü.

     Visual Studio'nun oluşturduğu XAML ve verilere bağlı denetimler kümesi oluşturan kodunu **ürün** tablo. Oluşturulan XAML ve kod hakkında daha fazla bilgi için bkz: [Visual Studio'da verilere WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

5.  Metin kutusunun yanındaki Tasarımcısı'nda tıklatın **Müşteri Kimliği** etiketi.

6.  İçinde **özellikleri** yanındaki onay kutusunu penceresinde, seçin **IsReadOnly** özelliği.

7.  Ayarlama **IsReadOnly** özelliği her şu metin kutuları için:

    -   **Satınalma siparişi numarası**

    -   **Sipariş Kimliği**

    -   **Sipariş numarası**

## <a name="load-the-data-from-the-service"></a>Verileri hizmetten yükleme
Hizmetinden satış verileri yüklemek için hizmet proxy nesnesi kullanın. Veri kaynağı için döndürülen verileri atamak <xref:System.Windows.Data.CollectionViewSource> WPF penceresinde.

### <a name="to-load-the-data-from-the-service"></a>Verileri hizmetten yükleme için

1.  Tasarımcıda oluşturmak için `Window_Loaded` olay işleyicisi okur metni çift tıklatarak: **MainWindow**.

2.  Olay işleyicisini aşağıdaki kodla değiştirin. Yerini emin olun *localhost* geliştirme bilgisayarınızda yerel ana bilgisayar adresi bu kodda adresiyle.

     [!code-csharp[Data_WPFWCF#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_2.cs)]
     [!code-vb[Data_WPFWCF#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_2.vb)]

## <a name="navigate-sales-records"></a>Satış kayıtları gidin
Kullanıcıların kullanarak satış kayıtlarda kaydırma olanak sağlayan kodu ekleyin **\<** ve **>** düğmeler.

### <a name="to-enable-users-to-navigate-sales-records"></a>Satış kayıtları gitmek kullanıcıların etkinleştirmek için

1.  Tasarımcıda çift **<** penceresini yüzeyinde düğmesi.

     Visual Studio arka plan kod dosyasını açar ve yeni bir `backButton_Click` için olay işleyicisini <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olay.

2.  Aşağıdaki kodu oluşturulan ekleyin `backButton_Click` olay işleyicisi:

     [!code-csharp[Data_WPFWCF#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_3.cs)]
     [!code-vb[Data_WPFWCF#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_3.vb)]

3.  Çift tıklayın ve dönüş Designer'a **>** düğmesi.

     Visual Studio arka plan kod dosyasını açar ve yeni bir `nextButton_Click` için olay işleyicisini <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olay.

4.  Aşağıdaki kodu oluşturulan ekleyin `nextButton_Click` olay işleyicisi:

     [!code-csharp[Data_WPFWCF#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_4.cs)]
     [!code-vb[Data_WPFWCF#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_4.vb)]

## <a name="saving-changes-to-sales-records"></a>Satış kayıtları için değişiklikler kaydediliyor
Hem görüntülemek ve kullanarak satış kayıtları için değişiklikleri kaydetmek kullanıcıların sağlayan kodu ekleyin **değişiklikleri kaydetmek** düğmesi.

### <a name="to-add-the-ability-to-save-changes-to-sales-records"></a>Değişiklikleri kaydetmek için satış kayıtları olanağı eklemek için

1.  Tasarımcıda çift **Değişiklikleri Kaydet** düğmesi.

     Visual Studio arka plan kod dosyasını açar ve yeni bir `saveButton_Click` için olay işleyicisini <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olay.

2.  Aşağıdaki kodu ekleyin `saveButton_Click` olay işleyicisi.

     [!code-csharp[Data_WPFWCF#5](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_5.cs)]
     [!code-vb[Data_WPFWCF#5](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_5.vb)]

## <a name="testing-the-application"></a>Uygulamayı test etme
Oluşturup görüntüleyebilir ve Müşteri kayıtlarını güncelleştirmek doğrulamak için uygulamayı çalıştırın.

### <a name="to-test-the-application"></a>Uygulamayı test etmek için

1.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**. Çözümünüzün hatasız oluşturulduğunu doğrulayın.

2.  Tuşuna **Ctrl + F5**.

     Visual Studio başlatır **AdventureWorksService** , hata ayıklama olmadan projesi.

3.  İçinde **Çözüm Gezgini**, sağ **AdventureWorksSalesEditor** projesi.

4.  Bağlam menüsünde altında **hata ayıklama**, tıklatın **başlangıç yeni örnek**.

     Uygulama çalışır. Aşağıdakileri doğrulayın:

    -   Metin kutuları sipariş Kimliğine sahip ilk satış kayıttan farklı veri alanlarını görüntüler **71774**.

    -   Tıklayabilirsiniz **>** veya **<** diğer satış kayıtlarında gezinmek için düğmeler.

5.  Satış kayıtları her birinde bazı metni yazın **açıklama** kutusuna ve ardından **değişiklikleri kaydetmek**.

6.  Uygulamayı kapatın ve sonra uygulamayı Visual Studio'dan yeniden başlatın.

7.  Değiştirdiğiniz satış kayda gidin ve sonra uygulamayı kapatıp değişikliği devam ettiğini doğrulayın.

8.  Uygulamayı kapatın.

## <a name="next-steps"></a>Sonraki Adımlar

Bu kılavuzu tamamladıktan sonra aşağıdaki görevleri gerçekleştirebilirsiniz:

-   Nasıl kullanacağınızı öğrenin **veri kaynakları** Visual Studio'daki WPF bağlamak için veri kaynakları diğer türleri için denetler. Daha fazla bilgi için bkz: [bir veri kümesine WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-a-dataset.md).

-   Nasıl kullanacağınızı öğrenin **veri kaynakları** Visual Studio'daki WPF denetimleri ilgili veri (yani, bir üst-alt ilişkisinde) görüntülemek için. Daha fazla bilgi için bkz: [izlenecek yol: bir WPF uygulamasında ilgili verileri görüntüleme](../data-tools/display-related-data-in-wpf-applications.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [Bir veri kümesine WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-a-dataset.md)
- [WCF genel bakış (.NET Framework)](/dotnet/framework/data/wcf/wcf-data-services-overview)
- [Entity Framework genel bakış (.NET Framework)](/dotnet/framework/data/adonet/ef/overview)
- [Veri bağlama (.NET Framework) genel bakış](/dotnet/framework/wpf/data/data-binding-overview)