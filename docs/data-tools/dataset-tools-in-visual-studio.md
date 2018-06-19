---
title: Visual Studio'da veri kümesi araçları
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.data.DataSet
helpviewer_keywords:
- untyped datasets
- datasets [Visual Basic], extended properties
- typed datasets
- current record in dataset
- XML [Visual Basic], datasets
- DataSet class, about datasets
- unique constraints (datasets)
- data relationships
- parent records in datasets
- extended properties, in typed datasets
- datasets [Visual Basic]
- schemas [Visual Basic], datasets
- datasets [Visual Basic], msprop
- master-detail tables, datasets
- databases [Visual Basic], updating
- msprop
- foreign keys, datasets
- DataSet class
- datasets [Visual Basic], filling
- case sensitivity, datasets
- constraints [Visual Basic], datasets
- child records
- related tables, datasets
- updating datasets, about dataset updates
- data caching, datasets
- DataRelation object, datasets
- untyped datasets, compared to typed datasets
- cache [Visual Studio], datasets
- datasets [Visual Basic], relationships
- related tables
- XML schemas, about XML schemas and datasets
- relationships, datasets
- typed datasets, compared to untyped datasets
- datasets [Visual Basic], populating
- datasets [Visual Basic], namespace
- data adapters, populating datasets
ms.assetid: ee57f4f6-9fe1-4e0a-be9a-955c486ff427
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9dc41702d9af7a604569c72f64c869f34a2e1b3b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31927158"
---
# <a name="dataset-tools-in-visual-studio"></a>Visual Studio'da veri kümesi araçları
> [!NOTE]
>  Veri kümeleri ve ilgili sınıfların eski .NET uygulamaları veritabanından değilken bellekte verilerle çalışmak uygulamalar sağlayan 2000'lerin başına gelen teknolojilerdir. Bunlar veri değiştirmek ve veritabanına değişiklikleri kalıcı hale getirmek kullanıcıların uygulamaları için özellikle yararlıdır. Veri kümeleri çok başarılı bir teknoloji olarak kanıtlanmış olsa da, yeni .NET uygulamaları Entity Framework kullanmanızı öneririz. Entity Framework tablo verileri nesne modelleri olarak çalışmak için daha doğal bir yol sağlar ve daha basit bir programlama arabirimine sahiptir.

 Bir veri kümesi nesnesi temelde kısa bir veritabanı olan bir bellek içi nesnesidir. Depolamak ve açık bir bağlantıyı sürdürmek zorunda kalmadan bir veya daha fazla veritabanlarındaki verileri değiştirme DataTable, DataColumn ve DataRow nesneleri içerir. Güncelleştirmeleri izlenen ve uygulamanızı bağlandığınızda hale veritabanına geri gönderilen veri kümesi verilerini yapılan değişikliklerle ilgili bilgileri tutar.

 Veri kümeleri ve ilgili sınıfların System.Data ad alanı .NET Framework Sınıf Kitaplığı'nda tanımlanır. Oluşturun ve kod kümelerinde dinamik olarak değiştirin. ADO.NET nasıl hakkında daha fazla bilgi için bkz. Bu bölümdeki belgelere, Visual Studio tasarımcıları kullanarak veri kümeleriyle çalışmak üzere gösterilmiştir. Bildiğiniz bir şey: tasarımcıları yapılan veri kümelerini kullanan TableAdapter nesneleri veritabanı ile etkileşim kurmak için program aracılığıyla yapılan veri kümeleri DataAdapter nesneleri kullanmasa. Veri kümeleri program aracılığıyla oluşturma hakkında daha fazla bilgi için bkz: [DataAdapters ve DataReader](/dotnet/framework/data/adonet/dataadapters-and-datareaders).

 Uygulamanızı yalnızca bir veritabanından veri okumak ve güncelleştirmeleri yapmayacak gerekir, ekler veya siler, genel bir liste nesnesi veya başka bir koleksiyon nesnesi veri almak için bir DataReader nesnesi kullanarak, genellikle daha iyi performans alabilirsiniz. Verileri görüntülüyorsanız, veri kullanıcı arabirimi koleksiyona bağlama.

## <a name="dataset-workflow"></a>Veri kümesi iş akışı
 Visual Studio çok miktarda veri kümeleri ile çalışma basitleştirmek için araç sağlar. Temel uçtan uca iş akışı şöyledir:

-   Kullanım **veri kaynağı** bir veya daha fazla veri kaynaklarından yeni bir veri kümesi oluşturmak için pencere. Kullanım **veri kümesi Tasarımcısı** dataset yapılandırmak ve özelliklerini ayarlayın. Örneğin, hangi dahil etmek için veri kaynağından tablolar ve her tablodaki hangi sütunların belirtmeniz gerekir. Veri kümesi gerektiren bellek miktarını korumak dikkatle seçin. Daha fazla bilgi için bkz: [oluşturma ve veri kümelerini yapılandırma](../data-tools/create-and-configure-datasets-in-visual-studio.md).

-   Yabancı anahtarlar doğru şekilde işlenir tablolar arasındaki ilişkileri belirtin. Daha fazla bilgi için bkz: [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md).

-   Kullanım **TableAdapter Yapılandırma Sihirbazı'nı** sorgu veya veri kümesi dolduracaktır saklı yordam belirtmek için ve uygulamak için hangi veritabanı işlemleri (güncelleştirme, silme vb.). Daha fazla bilgi için şu konulara bakın:

    -   [TableAdapters kullanarak veri kümelerini doldurma](../data-tools/fill-datasets-by-using-tableadapters.md)

    -   [Veri kümelerindeki verileri düzenleme](../data-tools/edit-data-in-datasets.md)

    -   [Veri kümelerindeki verileri doğrulama](../data-tools/validate-data-in-datasets.md)

    -   [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)

-   Sorgu ve veri kümesinde arayın. Daha fazla bilgi için bkz: [sorgu veri kümeleri](../data-tools/query-datasets.md). [!INCLUDE[linq_dataset](../data-tools/includes/linq_dataset_md.md)] etkinleştirir [LINQ (dil ile tümleşik sorgu)](/dotnet/csharp/linq/) verileri üzerinden bir <xref:System.Data.DataSet> nesnesi. Daha fazla bilgi için bkz: [LINQ-DataSet](/dotnet/framework/data/adonet/linq-to-dataset).

-   Kullanım **veri kaynakları** penceresi kullanıcı arabirimi denetimlerini dataset veya bireysel sütunlarını bağlamak ve hangi sütunların kullanıcı düzenlenebilir belirtmek için. Daha fazla bilgi için bkz: [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md).

## <a name="datasets-and-n-tier-architecture"></a>Veri kümeleri ve N katmanlı mimarisi
 N katmanlı uygulamalarda veri kümelerine hakkında daha fazla bilgi için bkz: [n katmanlı uygulamalarda veri kümeleriyle çalışmak](../data-tools/work-with-datasets-in-n-tier-applications.md).

## <a name="datasets-and-xml"></a>Veri kümeleri ve XML
 Veri kümeleri için ve XML dönüştürme hakkında daha fazla bilgi için bkz: [bir veri kümesini okuma XML verilerini](../data-tools/read-xml-data-into-a-dataset.md) ve [bir veri kümesini XML olarak kaydetme](../data-tools/save-a-dataset-as-xml.md).

## <a name="see-also"></a>Ayrıca bkz.

- [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)