---
title: "Visual Studio'da veri erişimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: "80025080"
helpviewer_keywords:
- data [Visual Studio]
- data access [Visual Studio]
- data [C#]
- ADO.NET, data access
caps.latest.revision: "100"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: d76ced1c908c832e9fd583eecc3419e57aeb76c7
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2017
---
# <a name="accessing-data-in-visual-studio"></a>Visual Studio'da veri erişimi

Visual Studio'da verilere neredeyse tüm veritabanı ürünü veya hizmetinde herhangi bir biçimde, herhangi bir yerden bağlanma uygulamalar oluşturabilirsiniz — yerel makinede, yerel alan ağı veya genel, özel ve karma bulut.

JavaScript, Python, PHP, Ruby ya da C++ uygulamaları için başka bir şey kitaplıkları edinme ve kod yazma yaptığınız gibi verilere bağlanın. .NET uygulamaları için Visual Studio veri kaynaklarını keşfetmek, depolamak ve bellek verileri işlemek ve verileri kullanıcı arabirimine bağlamak için nesne modeli oluşturmak için kullanabileceğiniz araçlar sağlar. Microsoft Azure SDK'ları .NET, Java, Node.js, PHP, Python, Ruby ve mobil uygulamaları ve Visual Studio Araçları Azure depolama birimine bağlamak için sağlar.

Aşağıdaki listeler, Visual Studio'dan kullanılabilir birçok veritabanı ve depolama sistemlerini birkaçı gösterir. [Microsoft Azure](https://azure.microsoft.com/) teklifleri olan tüm sağlama ve yönetim temel alınan veri deposu içeren veri hizmetleri.  [Visual Studio için Azure Araçları](https://www.visualstudio.com/features/azure-tools-vs.aspx) doğrudan Visual Studio'dan Azure veri depoları ile çalışmanıza olanak sağlayan isteğe bağlı bir bileşenidir. Burada listelenen diğer NoSQL ve SQL veritabanı ürünler çoğunu, yerel makinede, yerel bir ağda veya Microsoft Azure'da bir sanal makine üzerinde barındırılabilir. Bu senaryoda, veritabanının kendisi yönetmekten sorumlu.

**Microsoft Azure**

||||
|-|-|-|
|SQL veritabanı|DocumentDB|Depolama (BLOB'ları, tabloları, kuyrukları, dosyaları)|
|SQL veri ambarı|SQL Server Esnetme veritabanı|StorSimple|

ve daha fazlası...

**SQL**

||||
|-|-|-|
|SQL Server 2005-2016 Express ve yerel veritabanı dahil olmak üzere,|Firebird|MariaDB|
|MySQL|Oracle|PostgreSQL|
|SQLite|||

ve daha fazlası...

**NoSQL**

||||
|-|-|-|
|Apache Cassandra|CouchDB|MongoDB|
|NVeritabanı|OrientDB|RavenDB|
|VelocityDB|||

ve daha fazlası...

Çok sayıda veritabanı satıcılar ve üçüncü tarafların Visual Studio tümleştirmesi tarafından NuGet paketlerini destekler. Nuget.org veya Visual Studio'da NuGet Paket Yöneticisi aracılığıyla teklifleri keşfedebilirsiniz (**Araçları** > **NuGet Paket Yöneticisi** > **Manage NuGet Çözüm için paketlerini**). Diğer veritabanı ürünleri bir uzantısı olarak Visual Studio ile tümleştirin. Visual Studio Market'te bu tekliflerini giderek gözatabilirsiniz **Araçları**, **Uzantılar ve güncelleştirmeler** seçilerek **çevrimiçi** sol bölmesinde iletişim kutusu. Daha fazla bilgi için bkz: [Visual Studio için uyumlu bir veritabanı sistemleri](../data-tools/installing-database-systems-tools-and-samples.md).

> [!NOTE]
> SQL Server 2005 için genişletilmiş destek 12 Nisan 2016 tarihinde sona erdi. Veri araçları Visual Studio 2015 ve daha sonra bu tarihten sonra SQL Server 2005 ile çalışmaya devam edecek garantisi yoktur. Daha fazla bilgi için bkz: [SQL Server 2005 destek bitiş duyuru](https://www.microsoft.com/server-cloud/products/sql-server-2005/).

## <a name="net-languages"></a>.NET dilleri

.NET Core dahil olmak üzere tüm .NET veri erişimi ADO.NET, veri kaynağı, hem ilişkisel hem de ilişkisel olmayan herhangi bir tür erişmek için bir arabirim tanımlayan sınıflar kümesini temel alır. Visual Studio çeşitli araçlar vardır ve veritabanları için bağlanmanıza yardımcı olması için ADO.NET çalışmak tasarımcıları verileri işlemek ve kullanıcıya verileri görüntülemektedir. Bu bölümdeki belgelere bu araçların nasıl kullanılacağını açıklar. Ayrıca, doğrudan ADO.NET komut nesneleri karşı programlama yapabilirsiniz. ADO.NET API'larını doğrudan çağırmak hakkında daha fazla bilgi için bkz: [ADO.NET](https://msdn.microsoft.com/library/e80y5yhx\(v=vs.110\).aspx) MSDN Kitaplığı'nda.

Özellikle ASP.NET ile ilgili veri erişimi belgelerine bakın [verilerle çalışma](http://www.asp.net/web-forms/overview/presenting-and-managing-data) ASP.NET sitesinde. ASP.NET MVC ile Entity Framework kullanarak, bir öğretici için bkz: [Entity Framework 6 kod MVC 5 kullanarak ilk ile çalışmaya başlama](http://www.asp.net/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application).

C# veya Visual Basic Evrensel Windows Platformu (UWP) uygulamaları, Azure Storage ve diğer Azure hizmetlerine erişmek için .NET için Microsoft Azure SDK'sını kullanabilirsiniz. Windows.Web.HttpClient sınıfı herhangi bir RESTful hizmeti ile iletişim sağlar. Daha fazla bilgi için bkz: [Windows.Web.Http kullanarak bir HTTP sunucusuna bağlanmak nasıl](https://msdn.microsoft.com/library/windows/apps/dn469430.aspx).

Yerel makine üzerinde veri depolama için önerilen yaklaşım uygulama ile aynı işlemde çalışan SQLite kullanmaktır. Bir nesne ilişkisel eşleme (ORM) katman gerekiyorsa, Entity Framework kullanabilirsiniz. Daha fazla bilgi için bkz: [veri erişimi](https://msdn.microsoft.com/windows/uwp/data-access/index) Windows Developer Center'da.

Azure hizmetlerine bağlanıyorsanız, en son indirdiğinizden emin olun; [Azure SDK Araçları](https://azure.microsoft.com/downloads/).

### <a name="data-providers"></a>Veri sağlayıcıları

ADO.NET tüketilebilir olması için bir veritabanı için özel bir olmalıdır *ADO.NET veri sağlayıcı* veya başka bir ODBC veya OLE DB arabirimi kullanıma gerekir. Microsoft sağlayan bir [ADO.NET veri sağlayıcıları listesini](https://msdn.microsoft.com/data/dd363565) ODBC ve OLE DB sağlayıcıları yanı sıra, SQL Server ürünleri için.

### <a name="data-modeling"></a>Veri modelleme

.NET içinde modelleme bir veri kaynağından aldıktan sonra verileri ve bellek düzenleme için üç seçeneğiniz vardır:

[Varlık Çerçevesi](../data-tools/entity-data-model-tools-in-visual-studio.md)  
Tercih edilen Microsoft ORM teknolojisi. Bu programı ilişkisel veri karşı birinci sınıf .NET nesneleri kullanabilirsiniz. Yeni uygulamalar için bir model gerekli olduğunda varsayılan ilk seçenek olmalıdır. Temel alınan ADO.NET sağlayıcısının özel desteğini gerektirir.

[LINQ-SQL](../data-tools/linq-to-sql-tools-in-visual-studio2.md)  
Bir önceki nesil nesne ilişkisel Eşleştiricisi. En az karmaşık senaryolar için iyi çalışır ancak artık etkin geliştirme değil.

[Veri kümeleri](../data-tools/dataset-tools-in-visual-studio.md)  
Eski üç modelleme teknolojisi. Öncelikle hangi, değil büyük miktarlarda veri işleme veya karmaşık sorgular veya dönüşümler gerçekleştirme "veriler üzerinde forms" uygulamalarının hızlı geliştirme için tasarlanmıştır. Mantıksal SQL veritabanı nesnelerini .NET nesneleri çok daha benzer DataTable ve DataRow nesneleri bir veri kümesi nesnesi oluşur. SQL veri kaynağını temel alan nispeten basit uygulamalar için veri kümeleri hala iyi bir seçimdir olabilir.

Bu teknolojiler birini kullanmak için gereksinimi yoktur. Özellikle performansı önemli olduğu bazı senaryolarda, yalnızca bir DataReader nesnesi veritabanından okunur ve liste gibi bir koleksiyon nesnesi, gereken değerleri kopyalayın için kullanabileceğiniz\<T >.

## <a name="native-c"></a>Yerel C++

SQL Server'a bağlanmak C++ uygulamaları kullanması gereken [SQL Server için Microsoft® ODBC sürücüsü 13,1](https://www.microsoft.com/download/details.aspx?id=53339) çoğu durumda. Sunucuları bağlıysa, OLE DB gerekli ise ve söz konusu kullandığınız [SQL Server Native Client](https://msdn.microsoft.com/sqlserver/aa937733.aspx). Kullanarak diğer veritabanlarına erişebilirsiniz [ODBC](https://msdn.microsoft.com/library/ms710252\(v=vs.85\).aspx) veya OLE DB sürücüleri doğrudan. ODBC geçerli standart veritabanı arabirimdir, ancak çoğu veritabanı sistemleri ODBC arabirimi aracılığıyla erişilen özel işlevsellik sağlar. OLE DB, hala desteklenir, ancak yeni uygulamalar için önerilmez eski bir COM veri erişimi teknolojisidir. Daha fazla bilgi için bkz: [Visual C++'da veri erişimi](https://docs.microsoft.com/cpp/data/).

REST hizmetlerini kullanma C++ programları kullanabilir [C++ REST SDK](https://github.com/Microsoft/cpprestsdk).

Microsoft Azure Storage ile çalışma C++ programları kullanabilir [Microsoft Azure Storage istemcisi](http://www.nuget.org/packages/wastorage).

Veri modelleme &mdash; Visual Studio için C++ ORM katman sağlamaz. [ODBC](http://www.codesynthesis.com/products/odb/) popüler açık kaynak ORM C++ için değil.

C++ uygulamaları veritabanlarına bağlanma hakkında daha fazla bilgi için bkz: [C++ için Visual Studio veri Araçları](../data-tools/visual-studio-data-tools-for-cpp.md). Eski Visual C++ veri erişim teknolojileri hakkında daha fazla bilgi için bkz: [veri erişimi](http://msdn.microsoft.com/Library/a9455752-39c4-4457-b14e-197772d3df0b).

## <a name="javascript"></a>JavaScript

[Visual Studio'da JavaScript](https://msdn.microsoft.com/library/hh334522.aspx) platformlar arası uygulamalar, UWP uygulamaları, bulut Hizmetleri, Web siteleri ve web uygulamaları oluşturmak için birinci sınıf bir dildir. Sık kullanılan JavaScript kitaplıklarını ve veritabanı ürünleri yüklemek için Bower, Grunt, Gulp, npm ve Visual Studio içinde Nuget'ten kullanabilirsiniz. Sdk'lardan yükleyerek Azure depolama ve hizmetlere bağlanma [Azure Web sitesi](https://azure.microsoft.com/). Edge.js ADO.NET veri kaynakları için sunucu tarafı JavaScript (Node.js) bağlanan bir kitaplıktır.

## <a name="python"></a>Python

Yükleme [Visual Studio için Python Araçları](http://microsoft.github.io/PTVS/) CPython veya IronPython (.NET) uygulamaları oluşturmak için sık kullanılan Python framework yanı sıra. Visual Studio Web sitesi için Python araçları dahil olmak üzere verilere bağlanma birkaç öğreticileri sahip [Django ve Azure SQL veritabanındaki](https://github.com/Microsoft/PTVS/wiki/Django-and-SQL-Database-on-Azure), [Django ve MySQL Azure üzerinde](https://github.com/Microsoft/PTVS/wiki/Django-and-MySQL-on-Azure) ve [Bottle ve MongoDB üzerinde Azure](https://github.com/Microsoft/PTVS/wiki/Bottle-and-MongoDB-on-Azure).

## <a name="related-topics"></a>İlgili konular

[Veri, aygıtları ve analizi](https://msdn.microsoft.com/data-and-devices)  
Cortana Analytics Suite ve nesnelerin interneti için destek dahil olmak üzere Microsoft Akıllı bulut tanıtılmaktadır.

[Microsoft Azure depolama](https://azure.microCsoft.com/documentation/services/storage/)  
Azure Storage ve uygulamalarının Azure BLOB'ları, tabloları, kuyrukları ve dosyaları kullanılarak nasıl oluşturulacağını açıklar.

[Azure SQL veritabanı](https://azure.microsoft.com/documentation/services/sql-database/)  
Azure SQL Database, hizmet olarak ilişkisel bir veritabanına bağlanmak açıklar.

[SQL Server Veri Araçları](https://msdn.microsoft.com/library/hh272686\(v=vs.103\).aspx)  
Tasarım, sınama ve veri bağlı uygulamalar ve veritabanları dağıtma araştırması kolaylaştıran araçlar açıklanmaktadır.

[ADO.NET](/dotnet/framework/data/adonet/index)  
ADO.NET mimarisini, uygulama verilerini yönetmek ve XML ve veri kaynaklarıyla etkileşim kurmak için ADO.NET sınıflarının nasıl kullanılacağını açıklar.

[ADO.NET Entity Framework](https://msdn.microsoft.com/data/ef)  
Geliştiricilere doğrudan ilişkisel veritabanı yerine kavramsal bir modele göre program yazma olanağı tanıyan veri uygulamalarının nasıl oluşturulacağını açıklar.

[WCF Veri Hizmetleri 4.5](/dotnet/framework/data/wcf/index)  
Nasıl kullanılacağını açıklar [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] uygulayan veri Hizmetleri web ya da intranet üzerinde dağıtmak için [açık veri Protokolü (OData)](http://go.microsoft.com/fwlink/?LinkID=182204).

[Office çözümlerindeki veriler](/office-dev/office-dev/data-in-office-solutions)  
Office çözümlerinde verilerin nasıl çalıştığını açıklayan konulara bağlantılar içerir. Burada şema tabanlı programlama, verileri önbelleğe alma ve sunucu tarafında veri erişimi hakkında bilgiler bulunur.

[LINQ (dil ile tümleşik sorgu)](http://msdn.microsoft.com/Library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
C# ve Visual Basic'te yerleşik olarak bulunan sorgu özelliklerinin yanı sıra ilişkisel veritabanlarını, XML belgelerini, veri kümelerini ve bellek içi koleksiyonları sorgulamak için kullanılan ortak modeli açıklar.

[Visual Studio'daki XML araçları](../xml-tools/xml-tools-in-visual-studio.md)  
XML veri, hata ayıklama XSLT, .NET Framework XML özellikleri ile çalışma ve XML sorgusu mimarisini açıklar.

[XML belgeleri ve verileri](/dotnet/standard/data/xml/index)  
.NET Framework'te XML belgeleri ve verileriyle çalışan sınıflardan oluşan kapsamlı ve tümleşik bir gruba genel bir bakış sağlar.