---
title: Visual Studio veritabanı uyumluluk | Microsoft Docs
ms.custom: ''
ms.date: 09/06/2017
ms.topic: conceptual
helpviewer_keywords:
- database systems
- database compatibility
- databases for Visual Studio
ms.assetid: 821de34b-eaa9-40af-b9aa-b8305de16899
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 3c8cffef6144c188fd5f53e504f6065c4e7d0c1d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="compatible-database-systems-for-visual-studio"></a>Visual Studio için uyumlu bir veritabanı sistemleri

Visual Studio'da veri bağlantılı bir uygulama geliştirmek için genellikle yerel geliştirme makinenizde veritabanı sistemini yüklemek ve hazır olduğunuzda uygulama ve veritabanı üretim ortamına dağıtırsınız. Visual Studio makinenizde SQL Server Express LocalDB parçası olarak yükler **veri depolama ve işleme** iş yükü. Bu yerel veritabanı örneği, hızlı ve kolay bir şekilde veri bağlı uygulamaları geliştirmek için yararlıdır.

Bir veritabanı sistemi için .NET uygulamaları erişilebilir olmasını ve Visual Studio veri Araçlar windows görünür olması için bir ADO.NET veri sağlayıcı olmalıdır. Varlık veri modeli .NET uygulamanızda kullanmayı planlıyorsanız, sağlayıcı özellikle Entity Framework desteklemesi gerekir. Birçok sağlayıcısı aracılığıyla NuGet Paket Yöneticisi veya Visual Studio Market'te aracılığıyla sunulur.

Azure depolama API'leri kullanıyorsanız, Azure storage öykünücüsünü üretime dağıtmaya hazır olana kadar ücretlerden kaçınmak için geliştirme sırasında yerel makinenize yükleyin. Daha fazla bilgi için bkz: [geliştirme ve sınama için Azure Storage öykünücüsünü kullanma](/azure/storage/common/storage-use-emulator).

Aşağıdaki listede, kullanılabilir daha yaygın veritabanı sistemleri bazıları Visual Studio projelerinde içerir. Liste geniş kapsamlı değildir. Visual Studio Araçları ile derin tümleştirme sağlamak ADO.NET veri sağlayıcıları sunan üçüncü taraf satıcılar listesi için bkz: [ADO.NET Data Provider](/dotnet/framework/data/adonet/data-providers).

## <a name="microsoft-sql-server"></a>Microsoft SQL Server

SQL Server, Microsoft flagship veritabanı sunar. SQL Server 2016 performansından, Gelişmiş Güvenlik ve zengin, tümleşik raporlama ve analiz sunar. Farklı kullanımlar için tasarlanmış çeşitli sürümlerinde gelir: tek bir bilgisayardan kullanmak için yüksek düzeyde ölçeklenebilir, yüksek performanslı İş analizi, gelen. SQL Server Express'in tam özellikli, bir yeniden dağıtımı ve katıştırma için tasarlanmış SQL Server sürümüdür.  Yerel veritabanı, SQL Server yapılandırma gerektirir ve uygulamanızın işleminde çalışır, Express, Basitleştirilmiş bir sürümüdür. Her ikisi de ürünlerinden indirebilirsiniz [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express). Bu bölümdeki SQL örnekleri birçoğu, SQL Server yerel veritabanı kullanın. SQL Server Management Studio (SSMS) Visual Studio SQL Server nesne Gezgini'nde sağlanan değerinden daha fazla işlevsellik olan bir tek başına veritabanı yönetim uygulamasıdır. Önceki bağlantıdan SSMS elde edebilirsiniz.

## <a name="oracle"></a>Oracle

Oracle veritabanından ücretli veya ücretsiz sürümünü indirebilirsiniz [Oracle teknolojisi ağ](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index-092322.html) sayfası. Entity Framework ve TableAdapters öğelerini tasarım zamanı desteği ihtiyacınız olacak [Oracle geliştirici araçları Visual Studio için](http://www.oracle.com/technetwork/developer-tools/visual-studio/overview/index.html). Oracle anlık istemci gibi diğer resmi Oracle ürünleri NuGet Paket Yöneticisi aracılığıyla kullanılabilir.  Yönergeleri izleyerek Oracle örnek şemaları indirebilirsiniz [Oracle çevrimiçi belgeleri](http://docs.oracle.com/cd/E11882_01/server.112/e10831/toc.htm).

## <a name="mysql"></a>MySQL

MySQL şirketler ve Web sitelerine yaygın olarak kullanılan bir popüler açık kaynak veritabanı sistemidir. Visual Studio ve ilgili ürünler için MySQL yüklemeleri MySQL için olan adresindeki [MySQL Windows](http://www.mysql.com/why-mysql/windows/).  Üçüncü tarafların çeşitli Visual Studio uzantıları ve MySQL için tek başına Yönetim uygulamaları sunar. NuGet Paket Yöneticisi'nde teklifleri göz atabilirsiniz (**Araçları** > **NuGet Paket Yöneticisi** > **çözüm için NuGet paketlerini Yönet**) .

## <a name="postgresql"></a>PostgreSQL

PostgreSQL, ücretsiz, açık kaynak nesne ilişkisel veritabanı sistemidir. Windows yüklemek için buradan indirebilirsiniz [PostgreSQL indirme sayfası](http://www.postgresql.org/download/windows/).  Kaynak kodundan PostgreSQL de oluşturabilirsiniz.  PostgreSQL çekirdek sistem C dil arabirimi içerir. Çok sayıda üçüncü tarafların PostgreSQL .NET uygulamalarından kullanımı için NuGet paketleri sağlar.  NuGet Paket Yöneticisi'nde teklifleri göz atabilirsiniz (**Araçları** > **NuGet Paket Yöneticisi** > **çözüm için NuGet paketlerini Yönet**) . En popüler paketi tarafından sağlanan belki [npgsql.org](http://www.npgsql.org).

## <a name="sqlite"></a>SQLite

SQLite, uygulamanın kendi işleminde çalışır, katıştırılmış bir SQL veritabanı altyapısıdır. Buradan indirebilirsiniz [SQLite indirme sayfası](http://www.sqlite.org/download.html). Çok sayıda üçüncü taraf NuGet paketlerini SQLite için de kullanılabilir. NuGet Paket Yöneticisi'nde teklifleri göz atabilirsiniz (**Araçları** > **NuGet Paket Yöneticisi** > **çözüm için NuGet paketlerini Yönet**) .

## <a name="firebird"></a>Firebird

Firebird bir açık kaynak SQL veritabanı sistemidir. Buradan indirebilirsiniz [Firebird indirme sayfası](http://firebirdsql.org/en/downloads/). Bir ADO.NET veri sağlayıcı NuGet Paket Yöneticisi aracılığıyla kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)  
[Sürümüne ve SQL Server ve bileşenlerini belirleme](http://support.microsoft.com/kb/321185)