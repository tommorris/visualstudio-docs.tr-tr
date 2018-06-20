---
title: Visual Studio'da web performans testine veri kaynağı ekleme
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, walkthroughs
- Web performance tests, data binding (database)
ms.assetid: 2ada376d-f168-455d-9643-6acb535360c1
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 0f50e8a2f9381b4fd248b044772f5c2bdbf95a41
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234770"
---
# <a name="add-a-data-source-to-a-web-performance-test"></a>Web performans testine veri kaynağı ekleme

Örneğin aynı test için farklı değerler sağlamak için parametreleri formunuz için farklı değerler sonrası sağlamak için veri bağlayın.

 ![Web performans testine veri bağlama](../test/media/web_test_databinding_conceptual.png)

 Örnek bir ASP.NET uygulaması kullanılacak yapacağız. Üç *.aspx* sayfaları – varsayılan sayfası, kırmızı bir sayfa ve mavi sayfası. Varsayılan sayfa kırmızı veya mavi ve bir gönderme düğmesi seçmek için bir radyo denetleyebilir. Diğer iki *.aspx* sayfalarıdır çok basit. Bir kırmızı adlı bir etiket yoktur ve diğer mavi adlı bir etiket sahiptir. Gönderme varsayılan sayfasında biz görüntülemek diğer sayfalardan birini seçtiğinizde. İndirebilirsiniz [ColorWebApp](http://code.msdn.microsoft.com/Sample-ColorWebApp-76ff7506) örnek ya da kendi web uygulaması ile birlikte izlemeniz yeterlidir.

 ![Sınanacak web uygulaması çalıştıran](../test/media/web_test_databinding_runwebapp.png)

 Çözümünüzü Ayrıca web uygulaması sayfalarıyla gözatar web performans testine içermesi gerekir.

 ![Web performans testi Çözümle](../test/media/web_test_databinding_solution.png)

## <a name="create-a-sql-database"></a>SQL veritabanı oluşturma

1. Visual Studio Enterprise yoksa, buradan indirebilirsiniz [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) sayfası.

2. Bir SQL veritabanı oluşturun.

     ![Yeni bir SQL veritabanı Ekle](../test/media/web_test_databinding_sql_addnewdb.png)

3. Bir veritabanı projesi oluşturun.

     ![Veritabanından yeni proje oluşturma](../test/media/web_test_databinding_sql_addnewdbproject.png)

4. Bir tablo veritabanı projeye ekleyin.

     ![Yeni bir tablo için veritabanı projesi ekleme](../test/media/web_test_databinding_sql_addnewdbtablename.png)

5. Alanları tabloya ekleyin.

     ![Tabloya alanlar ekleme](../test/media/web_test_databinding_sql_addnewdbaddfields.png)

6. Veritabanı projesi yayımlayın.

     ![Çözüm Gezgini'nden veritabanı projesi Yayımla](../test/media/web_test_databinding_sql_addnewdbpublish.png)

7. Veri alanları ekleyin.

     ![Veri alanları ekleyin](../test/media/web_test_databinding_sql_addnewfieldsadddata.png)

## <a name="add-the-data-source"></a>Veri kaynağı ekleme

1. Bir veri kaynağı ekleyin.

     ![Web performans testine veri kaynağı ekleme](../test/media/web_test_databinding_sql_adddatasource.png)

2. Veri kaynağı türünü seçin ve adlandırın.

     ![Veritabanı kaynağı adı](../test/media/web_test_databinding_sql_adddatasourcedialog.png)

3. Bir bağlantı oluşturun.

     ![Yeni bir bağlantı seçin](../test/media/web_test_databinding_sql_adddatasourcedialogconnectionnew.png)

     Bağlantı ayrıntılarını girin.

     ![SQL veritabanı bağlantı özelliklerini girin](../test/media/web_test_databinding_sql_adddatasourcedialogconnection.png)

4. Test için kullanmak istediğiniz tabloyu seçin.

     ![Renk tablosu veri kaynağı olarak Ekle](../test/media/web_test_databinding_sql_adddatasourcedialogaddtable.png)

     Tablo test bağlıdır.

     ![Veri kaynakları düğümü web performans testine ekleme](../test/media/web_test_databinding_requestnodeadded_mdb.png)

5. Test kaydedin.

## <a name="bind-the-data"></a>Veri bağlama

1. Bağlama **ColorName** alan.

     ![RadioButtonList1 değerine ColorName alana bağlayın](../test/media/web_test_databinding_sql_binddatasource.png)

2. Açık *Local.testsettings* dosyasını **Çözüm Gezgini** seçip **her veri kaynağı satırı için tek çalıştırma** seçeneği.

     ![Test ayarları dosyasını düzenleme](../test/media/web_test_databinding_sql_testsettings.png)

3. Web performans testi kaydedin.

## <a name="run-the-test-with-the-data"></a>Veri ile test çalıştırma

1. Testi çalıştırın.

     ![Bağlama doğrulamak için web performans testini çalıştırma](../test/media/web_test_databinding_sql_runtest.png)

     İki çalışması için her veri satırı görüntülenir. Çalışma 1 sayfa için bir istek gönderir *Red.aspx*, ve çalışma 2 sayfa için bir istek gönderir *Blue.aspx*.

     ![Test çalıştırma sonuçları](../test/media/web_test_databinding_sql_runresults.png)

     Bir veri kaynağına bağladığınızda varsayılan yanıt URL kuralı ihlal edebilir. Bu durumda, çalışma 2 hata bekleyen kural tarafından kaynaklanır *Red.aspx* özgün testi kaydı, ancak veri şimdi bağlama sayfasından kendisine yönlendirir *Blue.aspx* sayfa.

2. Doğrulama hatasını silerek düzeltmek **yanıt URL'si** doğrulama kuralı ve test yeniden çalıştırma.

     ![Yanıt URL'si doğrulama kuralı Sil](../test/media/web_test_databinding_sql_deleteresponseurl.png)

     Web performans testine veri bağlama işlemini kullanma şimdi geçirir.

     ![Veri bağlama işlemini kullanma test başarılı](../test/media/web_test_databinding_sql_deleteresponseurlrunresults.png)

## <a name="q--a"></a>Soru - Yanıt

### <a name="q-what-databases-can-i-use-as-a-data-source"></a>S: Hangi veritabanlarının bir veri kaynağı olarak kullanabilir miyim?

**Y:** aşağıdakileri kullanabilirsiniz:

- Microsoft SQL Azure.

- Herhangi bir sürüm olduğu Microsoft SQL Server 2005 veya üzeri.

- Microsoft SQL Server veritabanı dosyası (SQL Express dahil).

- Microsoft ODBC.

- OLE DB için .NET Framework sağlayıcısı kullanarak Microsoft Access dosyası.

- Oracle 7.3, 8i, 9i veya 10g '.

### <a name="q-how-do-i-use-a-comma-separated-value-csv-text-file-as-a-data-source"></a>S: bir veri kaynağı olarak nasıl bir virgülle ayrılmış değer (CSV) metin dosyasına kullanıyor?

**Y:** burada nasıl:

1. Projeleri veritabanı yapıtları düzenlemek ve bir öğe eklemek için bir klasör oluşturun.

     ![Veri klasörüne yeni öğe Ekle](../test/media/web_test_databinding_foldernewitem.png)

2. Bir metin dosyası oluşturun.

     ![Yeni metin dosyası ColorData.csv adı](../test/media/web_test_databinding_foldernewitemtextfile.png)

3. Metin dosyasını düzenleyin ve aşağıdakileri ekleyin:

    ```text
    ColorId, ColorName
    0,Red
    1,Blue
    ```

4. İçindeki adımları kullanın [veri kaynağı ekleme](#add-the-data-source), ancak veri kaynağınız CSV dosyası seçin.

     ![Bir ad girin ve CSV dosyası seçin](../test/media/web_test_databinding_adddatasourcedialog.png)

### <a name="q-what-if-my-existing-csv-file-does-not-contain-column-headers"></a>S: Peki my mevcut bir CSV dosyasını sütun üst bilgileri içermiyor?

**Y:** sütun başlığı eklenemiyor, CSV dosyasında bir veritabanı olarak işlemek için bir şema tanımı dosyası kullanabilirsiniz.

1. Adlı yeni bir metin dosyasına eklemek *schema.ini*.

     ![Bir schema.ini dosyası ekleme](../test/media/web_test_databinding_schemafile.png)

2. Düzen *schema.ini* verilerinizin yapısını açıklayan bilgileri eklemek için dosya. Örneğin, CSV dosyasını tanımlayan bir şema dosyası şuna benzeyebilir:

    ```text
    [testdata.csv]
    ColNameHeader=False
    ```

3. Bir veri kaynağı test ekleyin.

     ![Web performans testine veri kaynağı ekleme](../test/media/web_test_databinding_sql_adddatasource.png)

4. Kullanıyorsanız, bir *schema.ini* dosya, seçin **veritabanı** (CSV dosyası değil) veri kaynağı ve adlandırın.

     ![Veritabanı veri kaynağı ekleme](../test/media/web_test_databinding_adddatasourcecolortext.png)

5. Yeni bir bağlantı oluşturun.

     ![Yeni bir bağlantı seçin](../test/media/web_test_databinding_sql_adddatasourcedialogconnectionnew.png)

6. OLE DB için .NET Framework veri sağlayıcısı seçin.

     ![.NET framework OLE DB veri sağlayıcısı seçin](../test/media/web_test_databinding_adddatasourcecolortext2.png)

7. Seçin **Gelişmiş**.

     ![Gelişmiş seçin](../test/media/web_test_databinding_advanced.png)

8. Sağlayıcı özelliği için Microsoft.Jet.OLEDB.4.0 seçin ve ardından **genişletilmiş özellikler** metne; HDR = HAYIR.

     ![Gelişmiş Özellikler Uygula](../test/media/web_test_databinding_advancedproperties.png)

9. Şema dosyasını içeren klasörün adını yazın ve bağlantınızı sınayın.

     ![Veri klasörün yolunu girin](../test/media/web_test_databinding_adddatasourcecolortext5.png)

10. Kullanmak istediğiniz CSV dosyasını seçin.

     ![Metin dosyasını seçin](../test/media/web_test_databinding_adddatasourcecolortext6.png)

     Bitirdikten sonra CSV dosyası bir tablo görünür.

     ![Test etmek için eklenen veri kaynağı](../test/media/web_test_databinding_adddatasourcecolortext7.png)

### <a name="q-how-do-i-use-an-xml-file-as-a-data-source"></a>S: bir veri kaynağı olarak nasıl bir XML dosyası kullanıyor?

**Y:** Evet.

1. Projeleri veritabanı yapıtları düzenlemek ve bir öğe eklemek için bir klasör oluşturun.

     ![Veri klasörüne yeni öğe Ekle](../test/media/web_test_databinding_foldernewitem.png)

2. Bir XML dosyası oluşturun.

     ![ColorData.xml dosyası ekleme](../test/media/web_test_databinding_additemxmlfile.png)

3. XML dosyasını düzenleyin ve verilerinizi ekleyin:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <ColorData>
        <Color>
            <ColorId>0</ColorId>
            <ColorName>Red</ColorName>
        </Color>
        <Color>
            <ColorId>1</ColorId>
            <ColorName>Blue</ColorName>
        </Color>
    </ColorData>
    ```

4. İçindeki adımları kullanın [veri kaynağı ekleme](#add-the-data-source), ancak veri kaynağınız XML dosyası seçin.

     ![Bir ad girin ve XML dosyası seçin](../test/media/web_test_databinding_adddatasourcedialogxml.png)

### <a name="q-can-i-add-data-binding-to-a-web-service-request-that-uses-soap"></a>S: SOAP kullanan web hizmeti isteğine veri bağlama ekleyebilir miyim?

**Y:** Evet, SOAP XML el ile değiştirmeniz gerekir.

1. Web hizmeti isteğine istek ağacında Özellikleri penceresinde seçip, dize gövde özelliğinde üç nokta (...) seçin.

     ![Web hizmeti dize gövde Düzenle](../test/media/web_test_databinding_webservicerequest.png)

2. SOAP gövdesi değerleri, aşağıdaki sözdizimini kullanarak veri bağlama değerleriyle değiştirin:

    ```xml
    {{DataSourceName.TableName.ColumnName}}
    ```

    Örneğin, aşağıdaki kodu varsa:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <CheckStatus xmlns="http://tempuri.org/">
                <userName>string</userName> <password>string</password> <orderID>int</orderID>
            </CheckStatus>
        </soap:Body>
    </soap:Envelope>
    ```

    Bunun için bunu değiştirebilirsiniz:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <CheckStatus xmlns="http://tempuri.org/">
                <userName>{{DataSourceName.Users.Name}}</userName> <password>{{DataSourceName.Users.Password}}</password> <orderID>{{DataSourceName.Orders.OrderID}}</orderID>
            </CheckStatus>
        </soap:Body>
    </soap:Envelope>
    ```

3. Test kaydedin.