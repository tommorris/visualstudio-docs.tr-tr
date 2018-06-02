---
title: Bir veri kümesine WPF denetimleri bağlama
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 177420b9-568b-4dad-9d16-1b0e98a24d71
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 917bf166057ef304f3d045898838b7074d76c467
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34690724"
---
# <a name="bind-wpf-controls-to-a-dataset"></a>Bir veri kümesine WPF denetimleri bağlama
Bu kılavuzda, veri bağlama denetimleri içeren bir WPF uygulaması oluşturacaksınız. Denetimler için bir veri kümesinde kapsüllenmiş ürün kayıtları bağlıdır. Ayrıca ürünleri üzerinden göz atın ve ürün kayıtları için değişiklikleri kaydetmek için düğmeler ekler.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- WPF uygulaması ve AdventureWorksLT örnek veritabanındaki verilerden oluşturulan bir veri kümesi oluşturma.

- Veri bağlama denetimleri kümesini veri tablosundan sürükleyerek oluşturma **veri kaynakları** WPF Tasarımcısı penceresinde penceresine.

- İleri ve geri ürün kayıtlar arasında gezinme düğmelerini oluşturma.

- Bir düğme oluşturma veri tablosu ve veri kaynağındaki ürün kayıtları kullanıcılar yapmak değişiklikleri kaydeder.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Önkoşullar
Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:

-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]

-   SQL Server ya da ekli AdventureWorksLT örnek veritabanı olan SQL Server Express'in çalışan örneğine erişim. AdventureWorksLT veritabanından indirebilirsiniz [CodePlex Web sitesinde](http://go.microsoft.com/fwlink/?linkid=87843).

Aşağıdaki kavramlar önceki bilgi de yararlı, ancak izlenecek yolu tamamlamak için gerekli değildir:

-   Veri kümeleri ve TableAdapters öğelerini. Daha fazla bilgi için bkz: [Visual Studio'da veri kümesi Araçları](../data-tools/dataset-tools-in-visual-studio.md) ve [TableAdapter](../data-tools/create-and-configure-tableadapters.md).

-   WPF veri bağlama. Daha fazla bilgi için bkz: [veri bağlama genel bakış](/dotnet/framework/wpf/data/data-binding-overview).

## <a name="create-the-project"></a>Projeyi oluşturma
 Yeni bir WPF projesi oluşturun. Proje ürün kayıtları görüntüler.

#### <a name="to-create-the-project"></a>Proje oluşturmak için

1.  Visual Studio'yu başlatın.

2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

3.  Genişletme **Visual Basic** veya **Visual C#** ve ardından **Windows**.

4.  Seçin **WPF uygulaması** proje şablonu.

5.  İçinde **adı** kutusuna `AdventureWorksProductsEditor` tıklatıp **Tamam**.

     Visual Studio oluşturur `AdventureWorksProductsEditor` projesi.

## <a name="create-a-dataset-for-the-application"></a>Uygulama için bir veri kümesi oluşturma
 Verilere bağlı denetimler oluşturmadan önce uygulamanız için bir veri modeli tanımlayın ve ekleyin gerekir **veri kaynakları** penceresi. Bu kılavuzda, veri modeli olarak kullanılacak bir veri kümesi oluşturun.

#### <a name="to-create-a-dataset"></a>Bir veri kümesi oluşturmak için

1.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.

     **Veri kaynakları** penceresi açılır.

2.  İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.

     **Veri kaynağı yapılandırması** Sihirbazı açılır.

3.  Üzerinde **bir veri kaynağı türü seç** sayfasında, **veritabanı**ve ardından **sonraki**.

4.  Üzerinde **bir veritabanı modeli seçin** sayfasında, **Dataset**ve ardından **sonraki**.

5.  Üzerinde **veri bağlantınızı** sayfasında, aşağıdaki seçeneklerden birini seçin:

    -   AdventureWorksLT örnek veritabanı veri bağlantısı aşağı açılan listesinde kullanılabilir ise, onu seçin ve ardından **sonraki**.

    -   Tıklatın **yeni bağlantı**ve AdventureWorksLT veritabanına bağlantı oluşturun.

6.  Üzerinde **bağlantı dizesini uygulama yapılandırma dosyasını Kaydet** sayfasında, **Evet, bağlantı olarak Kaydet** onay kutusunu işaretleyin ve ardından **sonraki**.

7.  Üzerinde **veritabanı nesnelerinizi** sayfasında **tabloları**ve ardından **ürün (SalesLT)** tablo.

8.  **Son**'a tıklayın.

     Visual Studio ekler yeni bir `AdventureWorksLTDataSet.xsd` proje ve bu dosyaya ekler karşılık gelen **AdventureWorksLTDataSet** öğesinin **veri kaynakları** penceresi. `AdventureWorksLTDataSet.xsd` Dosyası tanımlar adlı türü belirtilmiş bir veri kümesi `AdventureWorksLTDataSet` ve adlı bir TableAdapter `ProductTableAdapter`. Bu kılavuzda daha sonra kullanacağınız `ProductTableAdapter` veri kümesini verilerle doldurma ve değişiklikleri veritabanına kaydetmek için.

9. Projeyi oluşturun.

## <a name="edit-the-default-fill-method-of-the-tableadapter"></a>TableAdapter varsayılan dolgu yöntemini Düzenle
 Veri kümesini verilerle doldurmak için kullanmak `Fill` yöntemi `ProductTableAdapter`. Varsayılan olarak, `Fill` yöntemi dolgular `ProductDataTable` içinde `AdventureWorksLTDataSet` veri ürün tablodan tüm satırları ile. Yalnızca satırların alt kümesini döndürmek için bu yöntemi değiştirebilirsiniz. Bu kılavuz için değiştirme `Fill` döndürülecek yöntemi yalnızca Fotoğraf olan ürünler için satırlar.

#### <a name="to-load-product-rows-that-have-photos"></a>Fotoğraf ürün satırları yüklemek için

1.  İçinde **Çözüm Gezgini**, çift `AdventureWorksLTDataSet.xsd` dosya.

     Veri kümesi Tasarımcısı'nı açar.

2.  Tasarımcıda sağ **doldurun, GetData()** sorgulamak ve seçin **yapılandırma**.

     **TableAdapter yapılandırma** Sihirbazı açılır.

3.  İçinde **bir SQL deyimi girin** sayfasında, aşağıdaki WHERE yan tümcesinden sonra eklemek `SELECT` metin kutusuna deyimi.

    ```sql
    WHERE ThumbnailPhotoFileName <> 'no_image_available_small.gif'
    ```

4.  **Son**'a tıklayın.

## <a name="define-the-user-interface"></a>Kullanıcı arabirimi tanımlayın
 Birkaç düğmeleri WPF Tasarımcısı XAML'de değiştirerek penceresine ekleyin. Bu kılavuzda daha sonra bu düğmeleri kullanarak ürünleri kayıtları yapılan değişiklikleri kaydedin ve aracılığıyla kaydırmak kullanıcıların sağlayan kod ekleyeceksiniz.

#### <a name="to-define-the-user-interface-of-the-window"></a>Kullanıcı arabirimi penceresinin tanımlamak için

1.  İçinde **Çözüm Gezgini**, MainWindow.xaml çift tıklayın.

     WPF Tasarımcısı'nda penceresi açılır.

2.  İçinde [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] tasarımcısına görüntülemek için aşağıdaki kodu arasında ekleyin `<Grid>` etiketler:

    ```xaml
    <Grid.RowDefinitions>
        <RowDefinition Height="75" />
        <RowDefinition Height="625" />
    </Grid.RowDefinitions>
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>
    ```

3.  Projeyi oluşturun.

## <a name="create-data-bound-controls"></a>Verilere bağlı denetimler oluşturma
 Müşteri kayıtlarını sürükleyerek görüntüleyen denetimler oluşturma `Product` tablosunda **veri kaynakları** WPF Tasarımcısı penceresine.

#### <a name="to-create-data-bound-controls"></a>Veri bağlama denetimleri oluşturmak için

1.  İçinde **veri kaynakları** penceresinde, aşağı açılan menüsüne tıklayın **ürün** düğümü ve select **ayrıntıları**.

2.  Genişletme **ürün** düğümü.

3.  Bu örnek için bazı alanlar görüntülenmez, bu nedenle aşağıdaki düğümler yanındaki açılır menüsünü tıklatın ve seçin **hiçbiri**:

    -   ProductCategoryID

    -   ProductModelID

    -   ThumbnailPhotoFileName

    -   ROWGUID

    -   ModifiedDate

4.  Aşağı açılır menüsünü tıklatın **ThumbNailPhoto** düğümü ve select **görüntü**.

    > [!NOTE]
    >  Varsayılan olarak, öğeler **veri kaynakları** resimleri temsil penceresi sahip ayarlamak kendi varsayılan denetim **hiçbiri**. Bu resimler bayt dizileri veritabanlarında olarak depolanır ve bayt dizileri herhangi bir şeyin basit bir yürütülebilir dosyasının büyük bir uygulamanın bir bayt dizisi içerebilir kaynaklanır.

5.  Gelen **veri kaynakları** penceresinde, sürükle **ürün** düğmeleri içeren satırı altında kılavuz satıra düğümü.

     Visual Studio'nun verilere bağlı denetimler kümesini tanımlayan XAML oluşturduğu **ürünleri** tablo. Ayrıca, verileri yükler kodu oluşturur. Oluşturulan XAML ve kod hakkında daha fazla bilgi için bkz: [Visual Studio'da verilere WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

6.  Metin kutusunun yanındaki Tasarımcısı'nda tıklatın **ürün kimliği** etiketi.

7.  İçinde **özellikleri** yanındaki onay kutusunu penceresinde, seçin **IsReadOnly** özelliği.

## <a name="navigating-product-records"></a>Ürün kayıt gezinme
 Kullanarak ürün kayıtları arasında kaydırma yapma olanağı sağlayan kodu eklemek **\<** ve **>** düğmeler.

#### <a name="to-enable-users-to-navigate-product-records"></a>Ürün kaydı gitmek kullanıcıların etkinleştirmek için

1.  Tasarımcıda çift **<** penceresini yüzeyinde düğmesi.

     Visual Studio arka plan kod dosyasını açar ve yeni bir `backButton_Click` için olay işleyicisini <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olay.

2.  Değiştirme `Window_Loaded` olay işleyicisi, böylece `ProductViewSource`, `AdventureWorksLTDataSet`, ve `AdventureWorksLTDataSetProductTableAdapter` yöntemi dışında ve tüm form için erişilebilir. Yalnızca bu forma genel olarak bildirme ve bunların içinde atamak `Window_Loaded` olay işleyicisi aşağıdakine benzer:

     [!code-csharp[Data_WPFDATASET#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_1.cs)]
     [!code-vb[Data_WPFDATASET#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_1.vb)]

3.  Aşağıdaki kodu ekleyin `backButton_Click` olay işleyicisi:

     [!code-csharp[Data_WPFDATASET#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_2.cs)]
     [!code-vb[Data_WPFDATASET#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_2.vb)]

4.  Dönüş Tasarımcısı ve çift **>** düğmesi.

5.  Aşağıdaki kodu ekleyin `nextButton_Click` olay işleyicisi:

     [!code-csharp[Data_WPFDATASET#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_3.cs)]
     [!code-vb[Data_WPFDATASET#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_3.vb)]

## <a name="save-changes-to-product-records"></a>Değişiklikleri kaydetmek için ürün kayıtları
Kullanarak ürün kayıtları için değişiklikleri kaydetmek kullanıcıların sağlayan kodu ekleyin **değişiklikleri kaydetmek** düğmesi.

#### <a name="to-add-the-ability-to-save-changes-to-product-records"></a>Ürün kaydı için değişiklikleri kaydetmek için özelliği eklemek için

1.  Tasarımcıda çift **değişiklikleri kaydetmek** düğmesi.

     Visual Studio arka plan kod dosyasını açar ve yeni bir `saveButton_Click` için olay işleyicisini <xref:System.Windows.Controls.Primitives.ButtonBase.Click> olay.

2.  Aşağıdaki kodu ekleyin `saveButton_Click` olay işleyicisi:

     [!code-csharp[Data_WPFDATASET#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_4.cs)]
     [!code-vb[Data_WPFDATASET#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_4.vb)]

    > [!NOTE]
    >  Bu örnekte `Save` yöntemi `TableAdapter` değişiklikleri kaydedin. Yalnızca bir veri tablosu değiştiği için bu kılavuzda, bu uygundur. Birden çok veri tablolarına değişiklikleri kaydetmek gerekiyorsa, bunun yerine kullanabileceğiniz `UpdateAll` yöntemi `TableAdapterManager` , Visual Studio ile Veri kümenizi oluşturur. Daha fazla bilgi için bkz: [TableAdapters](../data-tools/create-and-configure-tableadapters.md).

## <a name="test-the-application"></a>Uygulamayı test etme
 Derleme ve uygulamayı çalıştırın. Görüntülemek ve ürün kayıtları güncelleştirme doğrulayın.

#### <a name="to-test-the-application"></a>Uygulamayı test etmek için

1.  Tuşuna **F5**.

     Uygulamayı oluşturur ve çalıştırır. Aşağıdakileri doğrulayın:

    -   Metin kutuları fotoğraf olan ilk ürün kaydını verileri görüntüler. Bu ürünün ürün kimliği 713 ve adına sahip **uzun manşon logosu bölgesi, S**.

    -   Tıklayabilirsiniz **>** veya **<** diğer ürün kayıtlarında gezinmek için düğmeler.

2.  Ürün kaydı her birinde değiştirme **boyutu** değer ve ardından **değişiklikleri kaydetmek**.

3.  Uygulamayı kapatın ve ardından tuşlarına basarak uygulamayı yeniden **F5** Visual Studio.

4.  Değiştirdiğiniz ürün kaydı gidin ve değişiklik kalıcı olduğunu doğrulayın.

5.  Uygulamayı kapatın.

## <a name="next-steps"></a>Sonraki Adımlar
 Bu kılavuzu tamamladıktan sonra aşağıdaki görevleri gerçekleştirebilirsiniz:

-   Nasıl kullanacağınızı öğrenin **veri kaynakları** Visual Studio'daki WPF bağlamak için veri kaynakları diğer türleri için denetler. Daha fazla bilgi için bkz: [bir WCF veri hizmetine WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md).

-   Nasıl kullanacağınızı öğrenin **veri kaynakları** Visual Studio'daki WPF denetimleri ilgili veri (yani, bir üst-alt ilişkisinde) görüntülemek için. Daha fazla bilgi için bkz: [izlenecek yol: bir WPF uygulamasında ilgili verileri görüntüleme](../data-tools/display-related-data-in-wpf-applications.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [Visual Studio'da veri kümesi araçları](../data-tools/dataset-tools-in-visual-studio.md)
- [Veri Bağlamaya Genel Bakış](/dotnet/framework/wpf/data/data-binding-overview)