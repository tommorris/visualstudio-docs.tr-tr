---
title: Visual Studio'da ADO.NET kullanarak basit veri uygulaması oluşturma
ms.date: 08/23/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 2222841f-e443-4a3d-8c70-4506aa905193
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0c4e985231f8e74095add3e8a3a3e412814bed0d
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745808"
---
# <a name="create-a-simple-data-application-by-using-adonet"></a>ADO.NET kullanarak basit veri uygulaması oluşturma

Veritabanındaki verileri işleyen bir uygulama oluşturduğunuzda, bağlantı dizeleri tanımlama, veri ekleme ve saklı yordamları çalıştırmak gibi temel görevleri gerçekleştirin. Bu konuda izleyerek Visual C# veya Visual Basic ve ADO.NET kullanarak basit bir Windows Forms "veriler üzerinde forms" uygulaması aynı veritabanıyla etkileşim kurmayı bulabilir.  Tüm .NET veri teknolojileri — veri kümeleri, LINQ to SQL ve Entity Framework dahil olmak üzere — sonuçta çok bu makalede gösterilen benzerdir adımları gerçekleştirin.

 Bu makalede çok hızlı bir şekilde bir veritabanından veri almak için basit bir yol gösterilmektedir. Uygulamanızın veri Önemsiz olmayan yollarla değiştirin ve veritabanını güncelleştirmek gerekirse, Entity Framework kullanarak ve kullanıcı arabirimi denetimlerini temel alınan verilerde yapılan değişiklikler için otomatik olarak senkronize için veri bağlamayı kullanarak düşünmelisiniz.

> [!IMPORTANT]
> Kod basit tutmak için üretime hazır özel durum işleme içermez.

## <a name="prerequisites"></a>Önkoşullar

Uygulama oluşturmak için ihtiyacınız vardır:

-   Visual Studio.

-   SQL Server Express LocalDB. SQL Server Express LocalDB yoksa, buradan yükleyebilirsiniz [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express).

Bu konu, Visual Studio IDE temel işlevlerle tanıdık ve bir Windows Forms uygulaması oluşturma, forms düğmelerin ve diğer denetimlerin formlarında put projeye özelliklerini denetimler ve kod basit olayları kümesi ekleme olduğunu varsayar. Bu görevleri memnun değilseniz, tamamlamanızı öneririz [Visual C# ve Visual Basic ile çalışmaya başlama](../ide/getting-started-with-visual-csharp-and-visual-basic.md) bu kılavuza başlamadan önce konu.

## <a name="set-up-the-sample-database"></a>Örnek veritabanı ayarlama

Örnek veritabanını aşağıdaki adımları izleyerek oluşturun:

1. Visual Studio'da açın **Sunucu Gezgini** penceresi.

2. Sağ tıklayın **veri bağlantıları** ve ** oluşturmak yeni SQL Server veritabanı... ".

3. İçinde **sunucu adı** metin kutusuna **(localdb) \mssqllocaldb**.

4. İçinde **yeni bir veritabanı adı** metin kutusuna **satış**, ardından **Tamam**.

     Boş **satış** veritabanı oluşturulur ve Sunucu Gezgininde veri bağlantıları eklenir.

5. Sağ **satış** veri bağlantısı ve select **yeni sorgu**.

     Sorgu Düzenleyicisi penceresini açar.

6. Kopya [satış Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/raw/master/docs/data-tools/samples/sales.sql) panonuza.

7. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.

     Kısa bir süre sonra sorgu yürütme tamamlandıktan ve veritabanı nesnelerini oluşturulur. Veritabanı iki tablolarını içerir: Müşteri ve siparişler. Bu tablo hiçbir veri başlangıçta içerir, ancak oluşturacağınız uygulamayı çalıştırdığınızda verileri ekleyebilirsiniz. Veritabanı, dört basit saklı yordamları da içerir.

## <a name="create-the-forms-and-add-controls"></a>Formları oluşturma ve denetimleri ekleme

1.  Windows Forms uygulaması için bir proje oluşturun ve SimpleDataApp olarak adlandırın.

     Visual Studio Proje ve Form1 adlı boş bir Windows formu dahil olmak üzere çeşitli dosyaları oluşturur.

2.  Üç forms sahip olması iki Windows forms projenize ekleyin ve bunları aşağıdaki adlar verin:

    -   Gezinme

    -   NewCustomer

    -   FillOrCancel

3.  Her form için aşağıdaki örneklerde kullanılan metin kutuları, düğmeler ve görüntülenen diğer denetimleri ekleyin. Her denetim için aşağıdaki tablolarda açıklanmıştır özellikleri ayarlayın.

    > [!NOTE]
    >  Grup kutusu ve etiket denetimleri netlik eklemek, ancak kodda kullanılmaz.

 **Gezinti formu**

 ![Gezinti iletişim kutusu](../data-tools/media/simpleappnav.png)

|Gezinti formu denetimleri|Özellikler|
|--------------------------------------|----------------|
|Düğme|Adı btnGoToAdd =|
|Düğme|Adı btnGoToFillOrCancel =|
|Düğme|Adı btnExit =|

 **NewCustomer formu**

 ![Yeni bir müşteri ekleyin ve bir sipariş verin](../data-tools/media/simpleappnewcust.png)

|NewCustomer form için denetimleri|Özellikler|
|---------------------------------------|----------------|
|TextBox|Adı txtCustomerName =|
|TextBox|Adı txtCustomerID =<br /><br /> ReadOnly = True|
|Düğme|Adı btnCreateAccount =|
|NumericUpdown|Ondalık basamaklar = 0<br /><br /> En fazla 5000 =<br /><br /> Adı numOrderAmount =|
|DateTimePicker|Biçim kısa =<br /><br /> Adı dtpOrderDate =|
|Düğme|Adı btnPlaceOrder =|
|Düğme|Adı btnAddAnotherAccount =|
|Düğme|Adı btnAddFinish =|

 **FillOrCancel formu**

 ![doldurun veya sipariş iptal etme](../data-tools/media/simpleappcancelfill.png)

|FillOrCancel form için denetimleri|Özellikler|
|----------------------------------------|----------------|
|TextBox|Adı txtOrderID =|
|Düğme|Adı btnFindByOrderID =|
|DateTimePicker|Biçim kısa =<br /><br /> Adı dtpFillDate =|
|DataGridView|Adı dgvCustomerOrders =<br /><br /> ReadOnly = True<br /><br /> RowHeadersVisible = False|
|Düğme|Adı btnCancelOrder =|
|Düğme|Adı btnFillOrder =|
|Düğme|Adı btnFinishUpdates =|

## <a name="store-the-connection-string"></a>Depolama bağlantı dizesi
 Veritabanına bir bağlantı açmak, uygulama çalıştığında, uygulamanızı bağlantı dizesi erişiminiz olmalıdır. Dize her form üzerinde el ile girmeyi önlemek için dize projenizin App.config dosyasında depolamak ve uygulamanızda herhangi bir formdan yöntemi çağrıldığında dizesi döndüren bir yöntem oluşturun.

 Üzerinde sağ tıklayarak bağlantı dizesini bulabilirsiniz **satış** veri bağlantısında **Sunucu Gezgini** ve seçme **özellikleri**. Bulun **ConnectionString** özelliği, sonra kullanım Ctrl + A, seçmek ve dizesini panoya kopyalamak için Ctrl + C.

1.  C# içinde kullanıyorsanız, **Çözüm Gezgini**, genişletin **özellikleri** düğümü altında proje ve ardından açık **Settings.settings** dosya.
    Visual Basic içinde kullanıyorsanız, **Çözüm Gezgini**, tıklatın **tüm dosyaları göster**, genişletin **My proje** düğümünü ve ardından açın **Settings.settings** dosya.

2.  İçinde **adı** sütun girin `connString`.

3.  İçinde **türü** listesinde **(bağlantı dizesi)**.

4.  İçinde **kapsam** listesinde **uygulama**.

5.  İçinde **değeri** sütun, bağlantı dizenizi (olmadan herhangi bir teklif dış) girin ve değişikliklerinizi kaydedin.

> [!NOTE]
> Gerçek bir uygulamada, bağlantı dizesi açıklandığı gibi güvenli şekilde saklamalısınız [bağlantı dizeleri ve yapılandırma dosyalarını](/dotnet/framework/data/adonet/connection-strings-and-configuration-files).

##  <a name="write-the-code-for-the-forms"></a>Formları için kod yazma

Bu bölümde her form yaptığı, kısa genel bakış bilgileri içerir. Ayrıca, formdaki bir düğme tıklatıldığında temel mantığını tanımlayan kodu sağlar.

### <a name="navigation-form"></a>Gezinti formu

Uygulamayı çalıştırdığınızda Gezinti formu açılır. **Hesap Ekle** düğmesi NewCustomer form açar. **Dolgu veya iptal siparişleri** düğmesi FillOrCancel form açar. **Çıkış** düğmesi uygulama kapatır.

#### <a name="make-the-navigation-form-the-startup-form"></a>Başlangıç formu form Gezinti yapın

C# içinde kullanıyorsanız, **Çözüm Gezgini**, Program.cs açın ve sonra değiştirmek `Application.Run` bu satırı: `Application.Run(new Navigation());`

Visual Basic içinde kullanıyorsanız, **Çözüm Gezgini**, açık **özellikleri** penceresinde, seçin **uygulama** sekmesini tıklatın ve ardından  **SimpleDataApp.Navigation** içinde **başlangıç formu** listesi.

#### <a name="create-auto-generated-event-handlers"></a>Otomatik olarak oluşturulan olay işleyicileri oluşturma

Boş olay işleyicisi yöntemleri oluşturmak için Gezinti form üzerindeki üç düğmeleri çift tıklayın. Düğmeleri çift de otomatik olarak oluşturulan kod bir olayı için düğmeyi tıklatın sağlayan Tasarımcısı kod dosyasını ekler.

#### <a name="add-code-for-the-navigation-form-logic"></a>Gezinti form mantığı için kodu ekleyin

Gezinti formu kod sayfasında tam yöntem gövdeleri üç düğme için olay işleyicileri aşağıdaki kodda gösterildiği gibi tıklayın.

[!code-csharp[Navigation#1](../data-tools/codesnippet/CSharp/SimpleDataApp/Navigation.cs#1)]
[!code-vb[Navigation#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/Navigation.vb#1)]

### <a name="newcustomer-form"></a>NewCustomer formu

Ne zaman bir müşteri adı girin ve ardından **hesap oluştur** düğmesi NewCustomer formun bir müşteri hesabı oluşturur ve SQL Server yeni müşteri kimliği olarak bir kimlik değeri döndürür Tutar ve bir sipariş tarihi belirtme ve seçtikten sonra yeni hesap için bir sıra yerleştirebilirsiniz **sipariş** düğmesi.

#### <a name="create-auto-generated-event-handlers"></a>Otomatik olarak oluşturulan olay işleyicileri oluşturma

Boş bir tıklatma oluşturmak için her dört düğmeleri çift tıklatarak NewCustomer formundaki her düğmesi olay işleyicisi. Düğmeleri çift de otomatik olarak oluşturulan kod bir olayı için düğmeyi tıklatın sağlayan Tasarımcısı kod dosyasını ekler.

#### <a name="add-code-for-the-newcustomer-form-logic"></a>Kodu NewCustomer form mantığı ekleyin

NewCustomer form mantığı tamamlamak için aşağıdaki adımları izleyin.

1. Getir `System.Data.SqlClient` kapsam içine ad alanı, tam olarak gerekmez böylece üyeleri adlarını nitelemek.

     ```csharp
     using System.Data.SqlClient;
     ```
     ```vb
     Imports System.Data.SqlClient
     ```

2. Bazı değişkenler ve yardımcı yöntemler aşağıdaki kodda gösterildiği gibi sınıfına ekleyin.

     [!code-csharp[NewCustomer#1](../data-tools/codesnippet/CSharp/SimpleDataApp/NewCustomer.cs#1)]
     [!code-vb[NewCustomer#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/NewCustomer.vb#1)]

3. Tam yöntem gövdeleri dört düğmesi için olay işleyicileri aşağıdaki kodda gösterildiği gibi tıklayın.

     [!code-csharp[NewCustomer#2](../data-tools/codesnippet/CSharp/SimpleDataApp/NewCustomer.cs#2)]
     [!code-vb[NewCustomer#2](../data-tools/codesnippet/VisualBasic/SimpleDataApp/NewCustomer.vb#2)]

### <a name="fillorcancel-form"></a>FillOrCancel formu

Bir sipariş kimliği girin ve ardından bir sipariş döndürülecek sorgu FillOrCancel formun çalıştıran **Bul sipariş** düğmesi. Döndürülen satır salt okunur veri kılavuzunda bulunur. Seçerseniz siparişi iptal edildi (X) olarak işaretleyebilirsiniz **siparişi iptal et** düğmesini veya işaretleyebilirsiniz sırası dolu (F) seçerseniz **doldurun sipariş** düğmesi. Seçerseniz **Bul sipariş** yeniden güncelleştirilmiş satır görünür düğmesi.

#### <a name="create-auto-generated-event-handlers"></a>Otomatik olarak oluşturulan olay işleyicileri oluşturma

Boş oluşturmak düğmeleri çift tıklatarak olay işleyicileri FillOrCancel form üzerindeki dört düğmeleri için tıklatın. Düğmeleri çift de otomatik olarak oluşturulan kod bir olayı için düğmeyi tıklatın sağlayan Tasarımcısı kod dosyasını ekler.

#### <a name="add-code-for-the-fillorcancel-form-logic"></a>Kodu FillOrCancel form mantığı ekleyin

FillOrCancel form mantığı tamamlamak için aşağıdaki adımları izleyin.

1. Böylece üyeleri adlarını tam olarak nitelemek yok aşağıdaki iki ad alanı kapsam içine alın.

     ```csharp
     using System.Data.SqlClient;
     using System.Text.RegularExpressions;
     ```
     ```vb
     Imports System.Data.SqlClient
     Imports System.Text.RegularExpressions
     ```

2. Aşağıdaki kodda gösterildiği gibi bir değişken ve yardımcı yöntem sınıfına ekleyin.

     [!code-csharp[FillOrCancel#1](../data-tools/codesnippet/CSharp/SimpleDataApp/FillOrCancel.cs#1)]
     [!code-vb[FillOrCancel#1](../data-tools/codesnippet/VisualBasic/SimpleDataApp/FillOrCancel.vb#1)]

3. Tam yöntem gövdeleri dört düğmesi için olay işleyicileri aşağıdaki kodda gösterildiği gibi tıklayın.

     [!code-csharp[FillOrCancel#2](../data-tools/codesnippet/CSharp/SimpleDataApp/FillOrCancel.cs#2)]
     [!code-vb[FillOrCancel#2](../data-tools/codesnippet/VisualBasic/SimpleDataApp/FillOrCancel.vb#2)]

## <a name="test-your-application"></a>Uygulamanızı test edin

Seçin **F5** oluşturmak ve her Click olay işleyicisi kod sonra uygulamanızı test etmek için anahtar ve kodlama tamamladıktan sonra sonra.

## <a name="see-also"></a>Ayrıca bkz.

- [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)
