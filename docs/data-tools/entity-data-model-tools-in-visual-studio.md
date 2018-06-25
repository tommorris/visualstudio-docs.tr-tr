---
title: Visual Studio'da Entity Framework Araçları
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1b06b573-84aa-4458-b3f5-e238df47bf45
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 3209a79b0358471977a0e58e8ab5d8d7e5c08e07
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755374"
---
# <a name="entity-framework-tools-in-visual-studio"></a>Visual Studio'da Entity Framework Araçları
Entity Framework, .NET geliştiricilerinin etki alanına özgü nesneleri kullanılarak ilişkisel verilerle çalışmak bir nesne ilişkisel eşleme teknolojisidir. Genellikle geliştiricilerin yazmak zorunda olduğu çoğu veri erişim koduna yönelik gereksinimi ortadan kaldırır. Entity Framework teknolojisi yeni .NET uygulamaları için modelleme önerilen nesne ilişkisel eşleştirme (ORM) yapılır.

Entity Framework Araçları Entity Framework (EF) uygulamalar oluşturmanıza yardımcı olmak için tasarlanmıştır. Entity Framework için kapsamlı belgeler şöyledir: [EF çekirdek ve EF 6](/ef/).

Entity Framework Araçları ile oluşturduğunuz bir *kavramsal model* varolan bir veritabanı grafik görselleştirmek ve kavramsal modeli düzenleyebilirsiniz. Veya, grafik kavramsal model ilk oluşturabilir ve ardından modelinizin destekleyen bir veritabanı oluşturun. Her iki durumda da, temel alınan veritabanı değişikliklerini ve uygulamanız için nesne katmanı kod otomatik olarak oluşturmak modelinizi otomatik olarak güncelleştirebilir. Veritabanı oluşturma ve nesne katmanı kod oluşturma özelleştirilebilir.

Entity Framework Araçları parçası olarak yüklenen **veri depolama ve işleme** Visual Studio yükleyicisi iş yükü. Altında indvidual bileşeni olarak da yükleyebilirsiniz **SDK'ları, kitaplıklarını ve çerçevelerini** kategorisi.

Visual Studio'da Entity Framework Araçları oluşturan belirli araçları şunlardır:

-   Kullanabileceğiniz [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] Tasarımcısı** (**Entity Designer**) görsel olarak oluşturmak ve varlıkları, ilişkileri, eşlemeleri ve devralma ilişkileri değiştirmek için. **Entity Designer** de oluşturur [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nesne katman kodu.

-   Kullanabileceğiniz  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] Sihirbazı** varolan bir veritabanından kavramsal bir model oluşturmak ve veritabanı bağlantısı bilgilerini uygulamanıza eklemek için.

-   Kullanabileceğiniz **Veritabanı Oluşturma Sihirbazı'nı** için kavramsal model önce ve sonra modelini destekleyen bir veritabanı oluşturun.

-   Kullanabileceğiniz **güncelleştirme modeli Sihirbazı** alttaki veritabanına yapılan değişiklikler olduğunda kavramsal model, depolama modelindeki ve eşlemeleri güncelleştirilemedi.

    > [!NOTE]
    >  Visual Studio 2010 ile başlayarak, Entity Framework Araçları desteklemediği [!INCLUDE[ss2k](../data-tools/includes/ss2k_md.md)].

Araçlar oluşturma veya değiştirme bir *.edmx* dosya. Bu *.edmx* dosyası kavramsal model, depolama modelindeki ve bunları arasındaki eşlemeleri açıklayan bilgiler içerir. Daha fazla bilgi için bkz: [EDMX](https://msdn.microsoft.com/data/jj650889.aspx).

[Entity Framework güç araçları](https://marketplace.visualstudio.com/items?itemName=EntityFrameworkTeam.EntityFrameworkPowerToolsBeta4) varlık veri modeli kullanan uygulamalar oluşturmanıza yardımcı olur. Güç Araçları kavramsal bir model oluşturmak, var olan bir model doğrulama, kavramsal modele dayalı nesne sınıfları içeren kaynak kodu dosyaları üretmek ve modeli oluşturur görünümleri içeren kaynak kodu dosyaları üretmek. Ayrıntılı bilgi için bkz: [Pre-Generated eşleme görünümleri](https://msdn.microsoft.com/data/dn469601.aspx).

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[ADO.NET Entity Framework](/dotnet/framework/data/adonet/ef/index)|Nasıl kullanılacağını açıklar [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] araçları, hangi [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)] uygulamaları oluşturmak için sağlar.|
|[Varlık Veri Modeli](/dotnet/framework/data/adonet/entity-data-model)|Üzerinde oluşturulan uygulamalar tarafından kullanılan verilerle çalışmak için bilgi ve bağlantılar sağlanmaktadır [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)].|
|[Entity Framework (EF) belgelerine)](https://msdn.microsoft.com/library/ee712907(v=vs.113).aspx)|Bir dizin videoları, eğitim ve Entity Framework'ün en yapmanıza yardımcı olmak üzere Gelişmiş belgeler sağlar.|
|[ASP.NET 5 uygulaması için yeni veritabanı](https://docs.efproject.net/en/latest/platforms/aspnetcore/new-db.html)|Entity Framework 7'yi kullanarak yeni bir ASP.NET 5 uygulaması oluşturmayı açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

- [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)