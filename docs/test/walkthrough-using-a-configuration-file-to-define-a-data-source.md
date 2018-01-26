---
title: "İzlenecek yol: bir veri kaynağı tanımlamak için bir yapılandırma dosyası kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration files [Visual Studio ALM], defining data sources
- unit tests, walkthrough
- data sources, defining with configuration files
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f36df08f6f750337cdd9c68458aebb92866d0a67
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="walkthrough-using-a-configuration-file-to-define-a-data-source"></a>İzlenecek Yol: Bir Veri Kaynağı Tanımlamak için Yapılandırma Dosyası Kullanma

Bu kılavuzda birim testi için bir app.config dosyasında tanımlanan bir veri kaynağı kullanımını gösterir. Tarafından kullanılan bir veri kaynağı tanımlayan bir app.config dosyasının nasıl oluşturulacağını öğreneceksiniz <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> sınıfı. Bu kılavuzda sunulan görevler aşağıdakileri içerir:  
  
-   Bir app.config dosyası oluşturuluyor.  
  
-   Özel yapılandırma bölümü tanımlama.  
  
-   Bağlantı dizeleri tanımlama.  
  
-   Veri kaynaklarını tanımlama.  
  
-   Verilere erişme kaynakları kullanarak <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> sınıfı.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzu tamamlamak için gerekenler:  
  
-   Visual Studio Enterprise  
  
-   Microsoft Access ya da Microsoft Excel test yöntemleri en az biri için veri sağlamak için.  
  
-   Test projesi içeren bir Visual Studio çözümü.  
  
## <a name="create-the-appconfig-file"></a>App.config dosyasını oluşturma  
  
#### <a name="to-add-an-appconfig-file-to-the-project"></a>Bir app.config dosyası projeye eklemek için  
  
1.  Test projenizin bir app.config dosyası zaten varsa, Git [özel yapılandırma bölümü tanımlamak](#DefineCustomConfigurationSection).  
  
2.  Test projenize sağ tıklayıp **Çözüm Gezgini**, işaret **Ekle**ve ardından **yeni öğe**.  
  
     **Yeni Öğe Ekle** penceresi açılır.  
  
3.  Seçin **uygulama yapılandırma dosyası** şablonu ve tıklatın **Ekle**.  
  
##  <a name="DefineCustomConfigurationSection"></a>Özel yapılandırma bölümü tanımlayın  
 App.config dosyasını inceleyin. En az XML bildirimi ve bir kök öğe içeriyor.  
  
#### <a name="to-add-the-custom-configuration-section-to-the-appconfig-file"></a>Özel yapılandırma bölümü app.config dosyasına eklemek için  
  
1.  App.config kök öğesinin olmalıdır `configuration` öğesi. Oluşturma bir `configSections` öğesi içinde `configuration` öğesi. `configSections` App.config dosyasında ilk öğe olmalıdır.  
  
2.  İçinde `configSections` öğesini oluşturmak bir `section` öğesi.  
  
3.  İçinde `section` öğesi adlı bir öznitelik Ekle `name` ve eşit değerde atama `microsoft.visualstudio.testtools`. Adlı başka bir öznitelik Ekle `type` ve eşit değerde atayın`Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`  
  
 `section` Öğesi şuna benzer görünmelidir:  
  
```  
<section name="microsoft.visualstudio.testtools" type="Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>  
```  
  
> [!NOTE]
>  Derleme adı, kullanmakta olduğunuz Microsoft Visual Studio .NET Framework derleme eşleşmesi gerekir. Visual Studio .NET Framework 3.5 kullanıyorsanız sürüm için 9.0.0.0 ayarlayın. Visual Studio .NET Framework 2.0 kullanıyorsanız, sürüm 8.0.0.0 için ayarlayın.  
  
## <a name="define-connection-strings"></a>Bağlantı dizeleri tanımlayın  
 Bağlantı dizeleri veri kaynaklarına erişim sağlayıcıya özgü bilgileri tanımlar. Bağlantı dizelerini yapılandırma dosyalarında tanımlanan bir uygulama arasında yeniden kullanılabilir veri sağlayıcısı bilgileri sağlar. Bu bölümde, özel yapılandırma bölümünde tanımlanan veri kaynakları tarafından kullanılan iki bağlantı dizeleri oluşturun.  
  
#### <a name="to-define-connection-strings"></a>Bağlantı dizeleri tanımlamak için  
  
1.  Sonra `configSections` öğesini oluşturmak bir `connectionStrings` öğesi.  
  
2.  İçinde `connectionStrings` öğesi, iki oluşturmak `add` öğeleri.  
  
3.  İlk `add` öğesi, aşağıdaki öznitelikleri ve değerleri için bir Microsoft Access veritabanına bağlantı oluşturun:  
  
|Öznitelik|Değerler|  
|---------------|------------|  
|`name`|`"MyJetConn"`|  
|`connectionString`|`"Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;"`|  
|`providerName`|`"System.Data.OleDb"`|  
  
 İkinci `add` öğesi, aşağıdaki öznitelikleri ve değerleri için bir Microsoft Excel elektronik tablosuna bir bağlantı oluşturun:  
  
|||  
|-|-|  
|`name`|`"MyExcelConn"`|  
|`connectionString`|`"Dsn=Excel Files;dbq=data.xlsx;defaultdir=.; driverid=790;maxbuffersize=2048;pagetimeout=5"`|  
|`providerName`|`"System.Data.Odbc"`|  
  
 `connectionStrings` Öğesi şuna benzer görünmelidir:  
  
```  
<connectionStrings>  
    <add name="MyJetConn" connectionString="Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;" providerName="System.Data.OleDb" />  
    <add name="MyExcelConn" connectionString="Dsn=Excel Files;dbq=data.xlsx;defaultdir=.; driverid=790;maxbuffersize=2048;pagetimeout=5" providerName="System.Data.Odbc" />  
</connectionStrings>  
```  
  
## <a name="define-data-sources"></a>Veri kaynakları tanımlayın  
 Veri kaynakları bölümü veri kaynağından veri almak için test altyapısı tarafından kullanılan dört öznitelikleri içerir.  
  
-   `name`tarafından kullanılan kimliği tanımlar <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> kullanmak için hangi veri kaynağı belirtmek için.  
  
-   `connectionString`Önceki bağlantı dizeleri tanımlayın bölümünde oluşturduğunuz bağlantı dizesini tanımlar.  
  
-   `dataTableName`Tablo veya testinde kullanmak için veri tutan sayfasını tanımlar.  
  
-   `dataAccessMethod`veri kaynağındaki veri değerleri erişmek için teknik tanımlar.  
  
 Bu bölümde, bir birim testinde kullanmak için iki veri kaynakları tanımlayacaksınız.  
  
#### <a name="to-define-data-sources"></a>Veri kaynakları tanımlamak için  
  
1.  Sonra `connectionStrings` öğesini oluşturmak bir `microsoft.visualstudio.testtools` öğesi. Bu bölümde tanımla özel yapılandırma bölümü oluşturuldu.  
  
2.  İçinde `microsoft.visualstudio.testtools` öğesini oluşturmak bir `dataSources` öğesi.  
  
3.  İçinde `dataSources` öğesi, iki oluşturmak `add` öğeleri.  
  
4.  İlk `add` öğesi, aşağıdaki öznitelikleri ve değerleri için bir Microsoft Access veri kaynağı oluşturun:  
  
|Öznitelik|Değerler|  
|---------------|------------|  
|`name`|`"MyJetDataSource"`|  
|`connectionString`|`"MyJetConn"`|  
|`dataTableName`|`"MyDataTable"`|  
|`dataAccessMethod`|`"Sequential"`|  
  
 İkinci `add` öğesi, aşağıdaki öznitelikleri ve değerleri için bir Microsoft Excel veri kaynağı oluşturun:  
  
|||  
|-|-|  
|`Name`|`"MyExcelDataSource"`|  
|`connectionString`|`"MyExcelConn"`|  
|`dataTableName`|`"Sheet1$"`|  
|`dataAccessMethod`|`"Sequential"`|  
  
`microsoft.visualstudio.testtools` Öğesi şuna benzer görünmelidir:

```xml
<microsoft.visualstudio.testtools>  
    <dataSources>  
        <add name="MyJetDataSource" connectionString="MyJetConn" dataTableName="MyDataTable" dataAccessMethod="Sequential"/>  
        <add name="MyExcelDataSource" connectionString="MyExcelConn" dataTableName="Sheet1$" dataAccessMethod="Sequential"/>  
    </dataSources>  
</microsoft.visualstudio.testtools>  
```

Son app.config dosyası şuna benzer görünmelidir:

```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <configSections>  
        <section name="microsoft.visualstudio.testtools" type="Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>   
    </configSections>  
    <connectionStrings>  
        <add name="MyJetConn" connectionString="Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;" providerName="System.Data.OleDb" />  
        <add name="MyExcelConn" connectionString="Dsn=Excel Files;dbq=data.xlsx;defaultdir=.; driverid=790;maxbuffersize=2048;pagetimeout=5" providerName="System.Data.Odbc" />  
    </connectionStrings>  
    <microsoft.visualstudio.testtools>  
        <dataSources>  
            <add name="MyJetDataSource" connectionString="MyJetConn" dataTableName="MyDataTable" dataAccessMethod="Sequential"/>  
            <add name="MyExcelDataSource" connectionString="MyExcelConn" dataTableName="Sheet1$" dataAccessMethod="Sequential"/>  
        </dataSources>  
    </microsoft.visualstudio.testtools>  
</configuration>  
```  
  
## <a name="create-a-unit-test-using-data-sources-defined-in-appconfig"></a>App.config dosyasında tanımlanan veri kaynaklarını kullanarak bir birim testi oluşturma  
 Bir app.config dosyası tanımlanmış, app.config dosyasında tanımlanan veri kaynaklarında bulunan verilere kullanan birim testi oluşturur. Bu bölümde, şunları yapacağız:  
  
-   App.config dosyasında bulunan veri kaynakları oluşturun.  
  
-   Her veri kaynağı değerleri Karşılaştır iki test yöntemleri veri kaynaklarında kullanın.  
  
#### <a name="to-create-a-microsoft-access-data-source"></a>Bir Microsoft Access veri kaynağı oluşturmak için  
  
1.  Adlı bir Microsoft Access veritabanı oluşturma `testdatasource.accdb`.  
  
2.  Bir tablo oluşturun ve adlandırın `MyDataTable` içinde `testdatasource.accdb`.  
  
3.  İki alanlarında oluşturun `MyDataTable` adlı `Arg1` ve `Arg2` kullanarak `Number` veri türü.  
  
4.  Beş varlıklara eklemek `MyDataTable` için aşağıdaki değerlerle `Arg1` ve `Arg2`sırasıyla: (10,50), (3,2), (6,0) (0,8) ve (12312,1000).  
  
5.  Kaydedin ve veritabanı kapatın.  
  
6.  Veritabanının konumuna işaret etmek için bağlantı dizesini değiştirin. Değerini değiştirme `Data Source` veritabanı konumunu gösterecek şekilde.  
  
#### <a name="to-create-a-microsoft-excel-data-source"></a>Microsoft Excel veri kaynağı oluşturmak için  
  
1.  Adlı bir Microsoft Excel elektronik tablosu oluşturma `data.xlsx`.  
  
2.  Adlı bir sayfa oluşturma `Sheet1` , zaten içinde mevcut değilse `data.xlsx`.  
  
3.  İki sütun üst bilgileri oluşturmak ve bunları `Val1` ve `Val2` içinde `Sheet1`.  
  
4.  Beş varlıklara eklemek `Sheet1` için aşağıdaki değerlerle `Val1` ve `Val2`sırasıyla: (1,1), (2,2), (3,3) (4,4) ve (5,0).  
  
5.  Kaydedip elektronik kapatın.  
  
6.  Elektronik Tablo konumuna işaret etmek için bağlantı dizesini değiştirin. Değerini değiştirme `dbq` elektronik konumunu gösterecek şekilde.  
  
#### <a name="to-create-a-unit-test-using-the-appconfig-data-sources"></a>App.config veri kaynaklarını kullanma birim testi oluşturmak için  
  
1.  Birim testi için test projesi ekleyin.
  
2.  Birim testi otomatik olarak oluşturulan içeriğini aşağıdaki kodla değiştirin:  
  
    ```csharp
    using System;  
    using Microsoft.VisualStudio.TestTools.UnitTesting;  
  
    namespace TestProject1  
    {  
         [TestClass]  
        public class UnitTest1  
        {  
            private TestContext context;  
  
            public TestContext TestContext  
            {  
                get { return context; }  
                set { context = value; }  
            }  
  
            [TestMethod()]  
            [DeploymentItem("MyTestProject\\testdatasource.accdb")]  
            [DataSource("MyJetDataSource")]  
            public void MyTestMethod()  
            {  
                int a = Int32.Parse(context.DataRow["Arg1"].ToString());  
                int b = Int32.Parse(context.DataRow["Arg2"].ToString());  
                Assert.AreNotEqual(a, b, "A value was equal.");  
            }  
  
            [TestMethod()]  
            [DeploymentItem("MyTestProject\\data.xlsx")]  
            [DataSource("MyExcelDataSource")]  
            public void MyTestMethod2()  
            {  
                Assert.AreEqual(context.DataRow["Val1"], context.DataRow["Val2"]);  
            }  
        }  
    }  
    ```  
  
3.  Veri kaynağı öznitelikleri inceleyin. App.config dosyasını ayarı adlarından dikkat edin.  
  
4.  Çözümünüzü derlemek ve MyTestMethod ve MyTestMethod2 testleri çalıştırın.  

> [!IMPORTANT]
> Böylece dağıtım dizini testinde erişilebilir veri kaynakları gibi öğeleri dağıtın.

## <a name="see-also"></a>Ayrıca Bkz.

[Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)  
[Nasıl Yapılır: Veri Temelli Birim Testi Oluşturma](../test/how-to-create-a-data-driven-unit-test.md)
