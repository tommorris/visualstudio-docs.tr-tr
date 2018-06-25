---
title: TableAdapter’lar oluşturma ve yapılandırma
ms.date: 09/01/2017
ms.topic: conceptual
helpviewer_keywords:
- table adapters, creating
- creating TableAdapters
- data [Visual Studio], creating data components
- data [Visual Studio], TableAdapters
- data [Visual Studio], creating table adapters
ms.assetid: 08630d69-0d6c-4e8f-b42d-2922f45f8415
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d3a5cebc3cb04872ff9266a2fa404b261a32c2d6
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757103"
---
# <a name="create-and-configure-tableadapters"></a>TableAdapter’lar oluşturma ve yapılandırma
TableAdapter, uygulamanızla veritabanı arasındaki iletişimi sağlar. Veritabanı, çalışma sorgular veya saklı yordamlar bağlanmak ve ya da yeni bir veri dönüş tablo veya varolan bir dolgu <xref:System.Data.DataTable> döndürülen verilerle. TableAdapters veritabanına uygulamanızdan güncelleştirilen verileri de gönderebilirsiniz.

Aşağıdaki eylemlerden birini gerçekleştirdiğinizde TableAdapters sizin için oluşturulur:

-   Çalıştırma [veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png) seçin **veritabanı** veya **Web hizmeti** veri kaynağı türü.

-   Sürükleme veritabanı nesnelerini **Sunucu Gezgini** içine **veri kümesi Tasarımcısı**.

Ayrıca yeni bir TableAdapter oluşturma ve gelen bir TableAdapter sürükleyerek ile bir veri kaynağı yapılandırma **araç** için boş bir bölgede **veri kümesi Tasarımcısı** yüzeyini.

TableAdapters giriş için bkz: [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="use-the-tableadapter-configuration-wizard"></a>TableAdapter Yapılandırma Sihirbazı'nı kullanın
Çalıştırma **TableAdapter Yapılandırma Sihirbazı'nı** oluşturmak veya TableAdapters ve bunların ilişkili DataTables düzenlemek için. Varolan bir TableAdapter içinde üzerinde sağ tıklayarak yapılandırabileceğiniz **veri kümesi Tasarımcısı**.

![raddata tablo bağdaştırıcısı Yapılandırma Sihirbazı](../data-tools/media/raddata-table-adapter-configuration-wizard.png)

Yeni bir TableAdapter Araç Kutusu'ndan sürükleyin durumunda olduğunda **veri kümesi Tasarımcısı** odak Sihirbazı başlatılır ve istemleri, hangi verileri belirtmek için kaynak TableAdapter bağlanmak için kullanılıyor. Sonraki sayfada, ne tür bir komutları ile saklı yordamları veya SQL deyimlerini veritabanıyla iletişim kurmak üzere kullanmalısınız sihirbaz sorar. (Zaten bir veri kaynağı ile ilişkili bir TableAdapter yapılandırıyorsanız, bu görmezsiniz.)

-   Veritabanı için doğru izinlere sahip yeni bir saklı yordam temel veritabanında oluşturma seçeneğiniz vardır. Bu izinlere sahip değilseniz, bu bir seçenek olmayacaktır.

-   İçin var olan saklı yordamları çalıştırmak de seçebilirsiniz **seçin**, **Ekle**, **güncelleştirme**, ve **silmek** komutları TableAdapter. Atandığı saklı yordam **güncelleştirme** komutu, örneğin, çalıştırıldığında ne zaman `TableAdapter.Update()` yöntemi çağrılır.

Seçili saklı yordamdan veri tablosunda karşılık gelen sütunlara parametreleriyle eşleyin. Örneğin, saklı yordam adlı bir parametre kabul ederse `@CompanyName` için aktardığı `CompanyName` tablosundaki sütun kümesi **kaynak sütunu** , `@CompanyName` parametresi `CompanyName`.

> [!NOTE]
>  SELECT komutu atanan saklı yordamın adını sihirbazın sonraki adımda TableAdapter yöntemi çağrılarak çalıştırılır. Varsayılan yöntemdir `Fill`, böylece genellikle SELECT yordamını çalıştırmak için kullanılan kod `TableAdapter.Fill(tableName)`. Varsayılan adından değiştirirseniz `Fill`, yerine `Fill` adıyla atayın ve "TableAdapter" TableAdapter gerçek adıyla değiştirin (örneğin, `CustomersTableAdapter`).

-   Seçme **veritabanına doğrudan güncelleştirmeleri göndermek için yöntemleri oluşturma** seçeneği ayarına eşdeğerdir `GenerateDBDirectMethods` özelliğinin true. Özgün SQL deyimi yeterli bilgi sağlamaz veya sorgu güncelleştirilebilir bir sorgu olmadığında seçeneği kullanılamaz. Bu durum, örneğin, içinde oluşabilir **katılma** sorgular ve tek bir (sayı) değerini döndüren sorgular.

**Gelişmiş Seçenekler** Sihirbazı'nda sağlar:
- Üzerinde tanımlanan SELECT deyimi göre INSERT, UPDATE ve DELETE deyimlerini Oluştur **oluştur SQL deyimlerini** sayfası
- İyimser eşzamanlılık kullanın
- Veri tablosu ekleme sonrasında Yenile belirtin ve güncelleştirme deyimleri çalıştırın

## <a name="configure-a-tableadapters-fill-method"></a>TableAdapter'ın dolgu yöntemini yapılandırma
Bazen TableAdapter'ın tablonun şeması değiştirmek isteyebilirsiniz. Bunu yapmak için TableAdapter'ın birincil değiştirmeniz `Fill` yöntemi. TableAdapters birincil ile oluşturulan `Fill` ilişkili veriler tablo şemasını tanımlayan yöntemi. Birincil `Fill` yöntemi sorgu veya saklı yordam TableAdapter ilk olarak yapılandırıldığında girdiğiniz dayanır. Bu ilk (en üstteki) veri tablosu veri kümesi Tasarımcısı'nda altında yöntemdir.

![TableAdapter ile birden çok sorgu](../data-tools/media/tableadapter.gif)

TableAdapter yaptığınız tüm değişiklikler ana `Fill` yöntemi ilişkili veri tablosu şemada yansıtılır. Örneğin, ana sorgudan bir sütun kaldırma `Fill` yöntemi de ilişkili veriler tablodan sütun kaldırır. Ayrıca, sütun ana kaldırma `Fill` yöntemi bu TableAdapter için hiçbir ek sorgularından sütun kaldırır.

TableAdapter sorgu Yapılandırma Sihirbazı'nı oluşturmak ve ek sorgular için TableAdapter düzenlemek için kullanabilirsiniz. Bir skaler değere döndürmeleri sürece bu ek sorgular tablo şemaya uygun olmalıdır.  Her ek sorgu belirttiğiniz bir adı vardır.

Aşağıdaki örnek adlı ek bir sorguyu çağırmak nasıl gösterir `FillByCity`:

`CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, "Seattle")`

#### <a name="to-start-the-tableadapter-query-configuration-wizard-with-a-new-query"></a>Yeni bir sorgu ile TableAdapter sorgu Yapılandırma Sihirbazı'nı başlatmak için

1.  Bir veri kümesini açma **veri kümesi Tasarımcısı**.

2.  Yeni bir sorgu oluşturuyorsanız, sürükleyin bir **sorgu** nesnesinin **DataSet** sekmesinde **araç** üzerine bir <xref:System.Data.DataTable>, ya da seçin **sorguEkle**TableAdapter'ın kısayol menüsünden. Ayrıca sürükleyebilirsiniz bir **sorgu** boş bir alanı nesneye **veri kümesi Tasarımcısı**, ilişkili bir olmadan bir TableAdapter oluşturan <xref:System.Data.DataTable>. Bu sorgular yalnızca tek (skaler) değerler ya da çalışma güncelleştirme, ekleme, dönüş veya komutları veritabanında SİLEBİLİRSİNİZ.

3.  Üzerinde **veri bağlantınızı** ekranında, seçin veya sorguyu kullanacağı bir bağlantı oluşturun.

    > [!NOTE]
    >  Bu ekran yalnızca Tasarımcısı'nı kullanmak için doğru bağlantı belirleyemediğinde veya bağlantı kullanılabilir olduğunda görüntülenir.

4.  Üzerinde **komut türü seçin** ekran, veritabanından veri getirme, aşağıdaki yöntemler arasından seçin:

    -   **SQL deyimleri kullanmak** veritabanınızdan verileri seçmek için bir SQL deyimi yazmanızı sağlar.

    -   **Yeni bir saklı yordam oluşturma** etkinleştirir sihirbazın sağlamak için oluşturduğunuz yeni bir saklı yordamı belirtilen SELECT deyimine dayalı (veritabanındaki ek olarak).

    -   **Var olan saklı yordamları kullanma** , varolan bir saklı yordamı sorgu çalıştırırken çalıştırmanızı sağlar.

#### <a name="to-start-the-tableadapter-query-configuration-wizard-on-an-existing-query"></a>Varolan bir sorguyu TableAdapter sorgu Yapılandırma Sihirbazı'nı başlatmak için

-   Varolan bir TableAdapter sorgu düzenliyorsanız, sorguyu sağ tıklayın ve ardından **yapılandırma** kısayol menüsünden.

    > [!NOTE]
    >  Bir TableAdapter ana sorgu sağ TableAdapter yeniden yapılandırır ve <xref:System.Data.DataTable> şema. Ek bir sorgu bir TableAdapter üzerinde sağ tıklayarak, ancak yalnızca seçili sorgu yapılandırır. **TableAdapter Yapılandırma Sihirbazı'nı** TableAdapter tanımı yeniden yapılandırır ancak **TableAdapter sorgu Yapılandırma Sihirbazı'nı** yalnızca seçili sorguyu yeniden yapılandırır.

#### <a name="to-add-a-global--query-to-a-tableadapter"></a>Bir TableAdapter genel sorgu eklemek için

-   Genel sorgular tek bir (sayı) değerini veya herhangi bir değer döndüren bir SQL sorguları gerçekleşiyor. Genellikle, genel işlevler ekler, güncelleştirmeleri ve silme gibi veritabanı işlemlerini gerçekleştirir. Bunlar ayrıca bir tablo ya da belirli bir sırada tüm öğeler için toplam ücretleri müşteri sayısı gibi bilgiler toplama.

     Sürükleyerek genel sorgular ekleme bir **sorgu** nesnesinin **DataSet** sekmesinde **araç** boş bir alanı üzerine **veri kümesi Tasarımcısı**.

-   Örneğin, istenen görevi gerçekleştiren bir sorgu sağlamak `SELECT COUNT(*) AS CustomerCount FROM Customers`.

    > [!NOTE]
    >  Sürükleme bir **sorgu** doğrudan üzerine nesne **veri kümesi Tasarımcısı** (yalnızca skaler tek) bir değer döndüren bir yöntem oluşturur. Sorgu veya seçtiğiniz saklı yordam birden çok tek bir değer döndürebilir olsa da, sihirbaz tarafından oluşturulan yöntemi yalnızca tek bir değer döndürür. Örneğin, sorgu döndürülen verileri ilk satırının ilk sütununu döndürebilir.

## <a name="see-also"></a>Ayrıca bkz.

- [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md)