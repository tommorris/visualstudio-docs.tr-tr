---
title: Visual Studio'da veri erişimi
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- "80025080"
helpviewer_keywords:
- data [Visual Studio]
- data access [Visual Studio]
- data [C#]
- ADO.NET, data access
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a7c7e031eb3fbe0330ab752882c8ac89eb7617bf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="accessing-data-in-visual-studio"></a>Visual Studio'da veri erişimi

Visual Studio'da verilere neredeyse tüm veritabanı ürünü veya hizmetinde herhangi bir biçimde, herhangi bir yerden bağlanma uygulamalar oluşturabilirsiniz — yerel makinede, yerel alan ağı veya genel, özel ve karma bulut.

JavaScript, Python, PHP, Ruby ya da C++ uygulamaları için başka bir şey kitaplıkları edinme ve kod yazma yaptığınız gibi verilere bağlanın. .NET uygulamaları için Visual Studio veri kaynaklarını keşfetmek, depolamak ve bellek verileri işlemek ve verileri kullanıcı arabirimine bağlamak için nesne modeli oluşturmak için kullanabileceğiniz araçlar sağlar. Microsoft Azure SDK'ları .NET, Java, Node.js, PHP, Python, Ruby ve mobil uygulamaları ve Visual Studio Araçları Azure depolama birimine bağlamak için sağlar.

Aşağıdaki listeler, Visual Studio'dan kullanılabilir birçok veritabanı ve depolama sistemlerini birkaçı gösterir. [Microsoft Azure](https://azure.microsoft.com/) teklifleri olan tüm sağlama ve yönetim temel alınan veri deposu içeren veri hizmetleri.  [Visual Studio için Azure Araçları](https://www.visualstudio.com/features/azure-tools-vs.aspx) doğrudan Visual Studio'dan Azure veri depoları ile çalışmanıza olanak sağlayan isteğe bağlı bir bileşenidir. Burada listelenen diğer NoSQL ve SQL veritabanı ürünler çoğunu, yerel makinede, yerel bir ağda veya Microsoft Azure'da bir sanal makine üzerinde barındırılabilir. Bu senaryoda, veritabanının kendisi yönetmekten sorumlu.

**Microsoft Azure**

||||
|-|-|-|
|SQL veritabanı|Azure Cosmos DB|Depolama (BLOB'ları, tabloları, kuyrukları, dosyaları)|
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
> SQL Server 2005 için genişletilmiş destek 12 Nisan 2016 tarihinde sona erdi. Veri araçları Visual Studio 2015 ve daha sonra bu tarihten sonra SQL Server 2005 ile çalışmaya devam edecek garantisi yoktur. Daha fazla bilgi için bkz: [SQL Server 2005 destek bitiş duyuru](https://www.microsoft.com/sql-server/sql-server-2005).

## <a name="net-languages"></a>.NET dilleri

.NET Core dahil olmak üzere tüm .NET veri erişimi ADO.NET, veri kaynağı, hem ilişkisel hem de ilişkisel olmayan herhangi bir tür erişmek için bir arabirim tanımlayan sınıflar kümesini temel alır. Visual Studio çeşitli araçlar vardır ve veritabanları için bağlanmanıza yardımcı olması için ADO.NET çalışmak tasarımcıları verileri işlemek ve kullanıcıya verileri görüntülemektedir. Bu bölümdeki belgelere bu araçların nasıl kullanılacağını açıklar. Ayrıca, doğrudan ADO.NET komut nesneleri karşı programlama yapabilirsiniz. ADO.NET API'larını doğrudan çağırmak hakkında daha fazla bilgi için bkz: [ADO.NET](/dotnet/framework/data/adonet/index).

Özellikle ASP.NET ile ilgili veri erişimi belgelerine bakın [verilerle çalışma](http://www.asp.net/web-forms/overview/presenting-and-managing-data) ASP.NET sitesinde. ASP.NET MVC ile Entity Framework kullanarak, bir öğretici için bkz: [Entity Framework 6 kod MVC 5 kullanarak ilk ile çalışmaya başlama](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application).

C# veya Visual Basic Evrensel Windows Platformu (UWP) uygulamaları, Azure Storage ve diğer Azure hizmetlerine erişmek için .NET için Microsoft Azure SDK'sını kullanabilirsiniz. Windows.Web.HttpClient sınıfı herhangi bir RESTful hizmeti ile iletişim sağlar. Daha fazla bilgi için bkz: [Windows.Web.Http kullanarak bir HTTP sunucusuna bağlanmak nasıl](https://msdn.microsoft.com/library/windows/apps/dn469430.aspx).

Yerel makine üzerinde veri depolama için önerilen yaklaşım uygulama ile aynı işlemde çalışan SQLite kullanmaktır. Bir nesne ilişkisel eşleme (ORM) katman gerekiyorsa, Entity Framework kullanabilirsiniz. Daha fazla bilgi için bkz: [veri erişimi](/windows/uwp/data-access/index) Windows Developer Center'da.

Azure hizmetlerine bağlanıyorsanız, en son indirdiğinizden emin olun; [Azure SDK Araçları](https://azure.microsoft.com/downloads/).

### <a name="data-providers"></a>Veri sağlayıcıları

ADO.NET tüketilebilir olması için bir veritabanı için özel bir olmalıdır *ADO.NET veri sağlayıcı* veya başka bir ODBC veya OLE DB arabirimi kullanıma gerekir. Microsoft sağlayan bir [ADO.NET veri sağlayıcıları listesini](https://msdn.microsoft.com/data/dd363565) ODBC ve OLE DB sağlayıcıları yanı sıra, SQL Server ürünleri için.

### <a name="data-modeling"></a>Veri modelleme

.NET içinde modelleme bir veri kaynağından aldıktan sonra verileri ve bellek düzenleme için üç seçeneğiniz vardır:

[Entity Framework](../data-tools/entity-data-model-tools-in-visual-studio.md) tercih edilen Microsoft ORM teknolojisi. Bu programı ilişkisel veri karşı birinci sınıf .NET nesneleri kullanabilirsiniz. Yeni uygulamalar için bir model gerekli olduğunda varsayılan ilk seçenek olmalıdır. Temel alınan ADO.NET sağlayıcısının özel desteğini gerektirir.

[LINQ-SQL](../data-tools/linq-to-sql-tools-in-visual-studio2.md) eski kuşak nesne ilişkisel Eşleştiricisi. En az karmaşık senaryolar için iyi çalışır ancak artık etkin geliştirme değil.

[Veri kümeleri](../data-tools/dataset-tools-in-visual-studio.md) üç modelleme teknolojileri en eski. Öncelikle hangi, değil büyük miktarlarda veri işleme veya karmaşık sorgular veya dönüşümler gerçekleştirme "veriler üzerinde forms" uygulamalarının hızlı geliştirme için tasarlanmıştır. Mantıksal SQL veritabanı nesnelerini .NET nesneleri çok daha benzer DataTable ve DataRow nesneleri bir veri kümesi nesnesi oluşur. SQL veri kaynağını temel alan nispeten basit uygulamalar için veri kümeleri hala iyi bir seçimdir olabilir.

Bu teknolojiler birini kullanmak için gereksinimi yoktur. Özellikle performansı önemli olduğu bazı senaryolarda, yalnızca bir DataReader nesnesi veritabanından okunur ve liste gibi bir koleksiyon nesnesi, gereken değerleri kopyalayın için kullanabileceğiniz\<T >.

## <a name="native-c"></a>Yerel C++

SQL Server'a bağlanmak C++ uygulamaları kullanması gereken [SQL Server için Microsoft® ODBC sürücüsü 13,1](https://www.microsoft.com/download/details.aspx?id=53339) çoğu durumda. Sunucuları bağlıysa, OLE DB gerekli ise ve söz konusu kullandığınız [SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client). Kullanarak diğer veritabanlarına erişebilirsiniz [ODBC](https://msdn.microsoft.com/library/ms710252\(v=vs.85\).aspx) veya OLE DB sürücüleri doğrudan. ODBC geçerli standart veritabanı arabirimdir, ancak çoğu veritabanı sistemleri ODBC arabirimi aracılığıyla erişilen özel işlevsellik sağlar. OLE DB, hala desteklenir, ancak yeni uygulamalar için önerilmez eski bir COM veri erişimi teknolojisidir. Daha fazla bilgi için bkz: [Visual C++'da veri erişimi](/cpp/data/data-access-in-cpp).

REST hizmetlerini kullanma C++ programları kullanabilir [C++ REST SDK](https://github.com/Microsoft/cpprestsdk).

Microsoft Azure Storage ile çalışma C++ programları kullanabilir [Microsoft Azure Storage istemcisi](http://www.nuget.org/packages/wastorage).

Veri modelleme&mdash;Visual Studio için C++ ORM katman sağlamaz. [ODBC](http://www.codesynthesis.com/products/odb/) popüler açık kaynak ORM C++ için değil.

C++ uygulamaları veritabanlarına bağlanma hakkında daha fazla bilgi için bkz: [C++ için Visual Studio veri Araçları](../data-tools/visual-studio-data-tools-for-cpp.md). Eski Visual C++ veri erişim teknolojileri hakkında daha fazla bilgi için bkz: [veri erişimi](/cpp/data/data-access-in-cpp).

## <a name="javascript"></a>JavaScript

[Visual Studio'da JavaScript](/scripting/javascript/javascript-language-reference) platformlar arası uygulamalar, UWP uygulamaları, bulut Hizmetleri, Web siteleri ve web uygulamaları oluşturmak için birinci sınıf bir dildir. Sık kullanılan JavaScript kitaplıklarını ve veritabanı ürünleri yüklemek için Bower, Grunt, Gulp, npm ve Visual Studio içinde Nuget'ten kullanabilirsiniz. Sdk'lardan yükleyerek Azure depolama ve hizmetlere bağlanma [Azure Web sitesi](https://azure.microsoft.com/). Edge.js ADO.NET veri kaynakları için sunucu tarafı JavaScript (Node.js) bağlanan bir kitaplıktır.

## <a name="python"></a>Python

Yükleme [Python desteği Visual Studio'da](../python/overview-of-python-tools-for-visual-studio.md) Python uygulamaları oluşturmak için. Azure belgelerine aşağıdakiler de dahil olmak üzere verilere bağlanma birkaç öğreticileri sahiptir:

- [Django ve Azure üzerinde SQL veritabanı](/azure/app-service/app-service-web-get-started-python)
- [Django ve Azure üzerinde MySQL](/azure/app-service-web/web-sites-python-ptvs-django-mysql)
- Çalışmak [BLOB'lar](/azure/storage/blobs/storage-quickstart-blobs-python), [dosyaları](/azure/storage/files/storage-python-how-to-use-file-storage), [sıraları](/azure/storage/queues/storage-python-how-to-use-queue-storage), ve [tabloları (Cosmo DB)](/azure/cosmos-db/table-storage-how-to-use-python).

## <a name="related-topics"></a>İlgili konular

[Microsoft AI platform](https://azure.microsoft.com/overview/ai-platform/?v=17.42w)&mdash;Cortana Analytics Suite ve nesnelerin interneti için destek dahil olmak üzere Microsoft Akıllı bulut tanıtılmaktadır.

[Microsoft Azure depolama](/azure/storage/)&mdash;Azure Storage açıklar ve Azure BLOB'ları, tabloları, kuyrukları ve dosya kullanarak uygulama oluşturma.

[Azure SQL veritabanı](/azure/sql-database/)&mdash;Azure SQL Database, hizmet olarak ilişkisel bir veritabanına bağlanmak açıklar.

[SQL Server veri Araçları](/sql/ssdt/download-sql-server-data-tools-ssdt)&mdash;tasarım, sınama ve veri bağlı uygulamalar ve veritabanları dağıtma araştırması kolaylaştıran araçlar açıklanmaktadır.

[ADO.NET](/dotnet/framework/data/adonet/index)&mdash;ADO.NET mimarisi ve ADO.NET sınıflarını uygulama verilerini yönetmek ve veri kaynakları ve XML ile etkileşim kurmak için nasıl kullanılacağını açıklar.

[ADO.NET Entity Framework](https://msdn.microsoft.com/data/ef)&mdash;yerine kavramsal model ilişkisel bir veritabanına karşı doğrudan karşı geliştiricilerin izin veri uygulamalarının nasıl oluşturulacağını açıklar.

[WCF Veri Hizmetleri 4.5](/dotnet/framework/data/wcf/index)&mdash;nasıl kullanılacağını açıklar [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] uygulayan veri Hizmetleri web ya da intranet üzerinde dağıtmak için [açık veri Protokolü (OData)](http://go.microsoft.com/fwlink/?LinkID=182204).

[Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)&mdash;Office çözümlerinde verileri nasıl çalıştığını açıklayan konulara bağlantılar içerir. Burada şema tabanlı programlama, verileri önbelleğe alma ve sunucu tarafında veri erişimi hakkında bilgiler bulunur.

[LINQ (dil ile tümleşik sorgu)](/dotnet/csharp/linq/)&mdash;C# ve Visual Basic ve ilişkisel veritabanları, XML belgeleri, veri kümeleri ve bellek içi koleksiyonları sorgulamak için ortak modeli yerleşik sorgu özellikleri açıklanmaktadır.

[Visual Studio'daki XML araçları](../xml-tools/xml-tools-in-visual-studio.md)&mdash;XML veri, hata ayıklama XSLT, .NET Framework XML özellikleri ile çalışma ve XML sorgusu mimarisini açıklar.

[XML belgeleri ve verileri](/dotnet/standard/data/xml/index)&mdash;XML belgelerini ve .NET Framework Veri çalışmak sınıfları kapsamlı ve tümleşik bir dizi genel bir bakış sağlar.
