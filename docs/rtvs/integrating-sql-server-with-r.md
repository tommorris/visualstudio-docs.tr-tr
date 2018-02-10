---
title: "SQL Server, Visual Studio için R araçları ile tümleştirme | Microsoft Docs"
description: "Visual Studio oluşturma ve çalıştırma R gelen SQL sorguları ve saklı yordamlar ile çalışmak R özelliği destekler."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
- SQL
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 65f34339e4c101818cea9b99095d765d5d417cf4
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="working-with-sql-server-and-r"></a>SQL Server ve R ile çalışma

SQL Server için Visual Studio'nun mükemmel desteği veri bilimcilerine R ve SQL veritabanları oluşturmak ve SQL sorguları çalıştırmak için ve saklı yordamlar çalışma olanağı üzerinden çalışmak yardımcı olur.

> [!Note]
> SQL ve R ile birlikte çalışmak için SQL Server veri araçları yüklü olması gerekir:
> - Visual Studio 2017: Visual Studio yükleyicisi çalıştırın ve veri depolama ve SQL Server veri araçları içerir işleme iş yükünü seçin.
> - Visual Studio 2015: yönergelerini izleyin [SQL Server veri araçları indirme](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt).

Aşağıdaki video (3m 03s) SQL Server ve R: kısa bir genel bakış sağlar

<iframe width="560" height="315" src="https://www.youtube.com/embed/n4AYr0QIwdQ" frameborder="0" allowfullscreen></iframe>

## <a name="creating-and-running-sql-queries"></a>Oluşturma ve SQL sorguları çalıştırma

RTVS Aradığınız sonuçları elde edene kadar yinelemeli olarak ayrı bir bağlamda SQL sorguları geliştirmek sağlayarak R projelere ekleme SQL sorguları destekler.

Bir SQL sorgu dosyası eklemek için Çözüm Gezgini'nde, Seç'nde projeye sağ **Ekle > Yeni öğe...** seçip **SQL sorgusu** dosya türü:

![SQL sorgusu öğesi için bir proje ekleyin](media/sql-add-item.png)

Bu komut dosyası ve SQL sorguları çalıştırma yeteneğini için IntelliSense sağlar Visual Studio'nun Transact-SQL Düzenleyicisi'nde açar. Bu özellikleri çalışacak şekilde Düzenleyicisi araç çubuğunda Bağlan düğmesini kullanarak bir veritabanına bağlanmak veya bir sorgu (Ctrl + Shift + ayrıca bir seçimde çalışan E,) çalıştırmayı deneyin gerekir. Her iki durumda da, bağlantı iletişim kutusunu açar:

![SQL Bağlantısı iletişim kutusu](media/sql-connection-dialog.png)

Bağlantı kurulduktan sonra sorguları çalıştırmak ve sonuçları bakın:

![SQL penceresi sorgu sonuçları](media/sql-query-results.png)

Sorgu ve bir sorgu hata ayıklayıcı için yürütme planı görüntüleme gibi diğer özelliklerin çeşitli Transact-SQL Düzenleyicisi'ni destekler.
Daha fazla bilgi için bkz: [Transact-SQL Düzenleyicisi'ni kullanma düzenleme ve komut dosyaları yürütme](https://msdn.microsoft.com/library/hh272706.aspx).

## <a name="working-with-sql-server-stored-procedures"></a>Saklı yordamlar SQL Server ile çalışma

[SQL Server R Hizmetleri](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services) saklı yordamı katıştırmak ve bir T-SQL R kodu çalıştırma (SQL Server 2016 ve üzeri) sağlar. Bir SQL Server bilgisayarında R kodu çalıştırmak, bir SQL sorgusundan döndürülen verileri çalıştırmak ve başka SQL tarafından işlenen veya istemciye döndürülen bir SQL sonuç kümesi oluşturur.

RTVS, aşağıdaki bölümlerde açıklandığı gibi tek bir SQL deyimi içinde SQL ve R kod birleştirmenin aksi yönetilmeleri ve hataya yatkın işlemini basitleştirir:

- [Bir veritabanı bağlantısı Ekle](#add-a-database-connection)
- [Yazma ve SQL saklı yordamı test etme](#write-and-test-a-sql-stored-procedure)
- [SQL saklı yordamı yayımlama](#publish-a-sql-stored-procedure)

Aşağıdaki video (6m 09s) de bu özelliklere genel bakış sağlar:

<iframe width="560" height="315" src="https://www.youtube.com/embed/dFKIT2OitWQ" frameborder="0" allowfullscreen></iframe>

### <a name="add-a-database-connection"></a>Bir veritabanı bağlantısı Ekle

1. Seçin **R Araçlar > veri > Veritabanı Bağlantı Ekle** ortaya çıkarmak için **bağlantı özelliklerini** iletişim. Burada belirttiğiniz (Bu durumda SQL Server) veri kaynağının adını, ad sunucusu, kimlik doğrulama modu ve veritabanının adı. Seçin **Bağlantıyı Sına** iletişim kutusunu kapatmadan önce girişinizi doğrulayın.

    ![SQL bağlantı iletişim kutusu](media/sql-connection-string-dialog.png)

1. Seçtiğinizde, bundan sonra **Tamam** geçerli bir bağlantı ile Visual Studio adlı bir bağlantı dizesi oluşturur `dbConnection` yeni `settings.R` dosya. RTVS (çalışır) otomatik olarak kaynakları R betiklerini bağlantısından hemen kullanabilmek için bu dosyayı:

![SQL Settings.R dosyası](media/sql-settings-dot-r.png)

### <a name="write-and-test-a-sql-stored-procedure"></a>Yazma ve SQL saklı yordamı test etme

Yeni bir SQL saklı yordamı eklemek için projenize sağ tıklayın, seçin **Ekle > Yeni öğe...** seçin **SQL saklı yordamı r** şablonları listesinden bir ad verin (`StoredProcedure.R` Bu örnekte) ve seçin **Tamam**.

RTVS saklı yordamı için üç dosyaları oluşturur: bir `.R` R kodunuz için dosyayı bir `.Query.sql` SQL kod dosyası ve bir `.Template.sql` iki birleştirir dosya. Bunlar alt olarak iki görünür Çözüm Gezgini'nde ikinci `.R` dosyası:

![Çözüm Gezgini SQL saklı yordamı r görünümünü genişletilmiş](media/sql-solution-explorer-expanded.png)

`StoredProcedure.R`(Bu örnekte), burada R kodu yazdığınız şeydir. Varsayılan içeriği şunlardır:

```R
# @InputDataSet: input data frame, result of SQL query execution
# @OutputDataSet: data frame to pass back to SQL

# Test code
# library(RODBC)
# channel <- odbcDriverConnect(dbConnection)
# InputDataSet <- sqlQuery(channel, )
# odbcClose(channel)

OutputDataSet <- InputDataSet
```

Kısaca, kod olarak adlandırılan bir R dataframe alır `InputDataSet` ve onun sonuçları döndürür `OutputDataSet`, yalnızca çıktı girdisi kopyalama şablon koduna sahip.

> [!Note]
> Bu dataframes adlarını denetlediği `@input_data_1_name` ve `@output_data_1_name` çağrısı parametrelerinde `sp_execute_external_script` sistem saklı yordamı. Bu arama kuralı tasarımını hakkında daha fazla ayrıntı ve bazı kullanım örnekleri için bkz: [sp_execute_external_script (Transact-SQL)](https://docs.microsoft.com/sql/relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql).

Diğer oluşturulan kod (açıklamaları) kullanan bir küçük test komut dosyası sağlar [RODBC paket](https://cran.r-project.org/web/packages/RODBC/index.html) SQL Server için bir SQL deyimi iletmek için çalıştırın ve bir R dataframe ayarlamak sonucu almak. SQL Server'dan alma etkileşimli olarak R kodunuzu sonucu karşı yazmak için bu test kod kümesi açıklamadan çıkarın.

`StoredProcedure.Query.sql`Burada yazmak ve sınamak için veri üreten SQL sorgu `InputDataSet`. Bu `.sql` Dosyası Düzenleyicisi tüm olağan Transact-SQL özellikleri sağlar.

İle SQL kodunuzu memnun kaldıysanız sonra R kodunuzda ile tümleştirmenize `StoredProcedure.R` sürükleyerek `.sql` açık Düzenleyicisi üzerine dosya `.R` dosya. Aşağıdaki görüntüde `StoredProcedure.Query.sql` noktasına virgülle sonra sürüklenen `sqlQuery(channel, )`:

![R dize değişkeni SQL dosyaya okuma](media/sql-reference-sql-file-from-r.png)

Gördüğünüz gibi bu basit adımı açmak için R kodu otomatik olarak oluşturur. `.sql` dosya, bir dizeye içeriğini okumak ve SQL sunucusuna göndermek için RODBC paketi iletin.

Etkileşimli olarak işleyen yazma R kodu artık `InputDataSet` dataframe istediğiniz gibi. R Kod düzenleyicisinde seçin yalnızca ve göndermeden unutmayın [etkileşimli pencere](interactive-repl-for-r-in-visual-studio.md) Ctrl + Enter tuşlarına basarak.

`StoredProcedure.Template.sql`, son olarak, SQL saklı yordamı oluşturmak için şablon içerir:

```sql
CREATE PROCEDURE [StoredProcedure]
AS
BEGIN
EXEC sp_execute_external_script @language = N'R'
    , @script = N'_RCODE_'
    , @input_data_1 = N'_INPUT_QUERY_'
--- Edit this line to handle the output data frame.
    WITH RESULT SETS (([MYNEWCOLUMN] NVARCHAR(max)));
END;
```

- `_RCODE_` Yer tutucu içeriğine göre değiştirilir `StoredProcedure.R`.
- `_INPUT_QUERY_` Yer tutucu içeriğine göre değiştirilir `StoredProcedure.Query.sql`.
- Düzen `WITH RESULT SETS` bir saklı yordamdan döndürülen sonuç şeması açıklamak için yan tümcesi. Özellikle sütunlarından tanımlamak `OutputDataSet` saklı yordamı çağırana döndürmek istediğiniz dataframe. 

Örneğin, aşağıdaki sorgu için:

```sql
SELECT TOP 100 medallion, hack_license FROM nyctaxi_sample
```

Aşağıdaki kullanırsınız `WITH RESULT SETS` dönüş değerlerini veri türlerini belirtmek için yan tümcesi:

```sql
WITH RESULT SETS ((medallion NVARCHAR(max), hack_license NVARCHAR(max)));
```

### <a name="publish-a-sql-stored-procedure"></a>SQL saklı yordamı yayımlama

1. Seçin **R Araçlar > veri > seçeneklerle Yayımla...**  menü komutu.
1. Görüntülenen iletişim kutusunda, değiştirmek **Yayımla:** için **veritabanı**, hedef belirtin, seçin **Yayımla**, RTVS oluşturur ve saklı yordam yayımlar ve:

    ![Saklı yordam iletişim yayımlama](media/sql-publish-with-options.png)

1. Bir projedeki tüm depolanmış yordamları yayımlamak için kullanabileceğiniz **R Araçlar > veri > saklı yordamlar yayımlama** aynı zamanda, Çözüm Gezgini'nde projeye sağ tıklattığınızda kullanılabilir olan komutu.

> [!Tip]
> Visual Studio'da açın SQL Server Nesne Gezgini varsa, yayımlanan saklı yordam görünür **programlamasına > saklı yordamlar** veritabanınızın klasör. Ayrıca nesne Gezgini'nden sağ tıklayıp seçerek çalıştırabilirsiniz **yordamı Yürüt**, veya ondan etkileşimli olarak arayarak bir `.sql` sorgu penceresi.
