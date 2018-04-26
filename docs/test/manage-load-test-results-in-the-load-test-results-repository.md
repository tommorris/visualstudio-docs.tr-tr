---
title: Visual Studio Yük testi sonuçlarını yönetme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, results repository
- results, load test
- load test results, repository
- Load Test Results Repository
ms.assetid: 1cd63c4b-4f74-4133-b675-5e8fbeab25f3
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e1eb6a5218f9d9ea7c853733690922846443ed4c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="manage-load-test-results-in-the-load-test-results-repository"></a>Yük testi sonuçları havuzu yük testi sonuçlarını yönetme

Yük testleri çalıştırdığınızda, bir yük testi sırasında toplanan herhangi bir bilgi depolanabilir *Yük Testi Sonuçları Deposu*, bir SQL veritabanı olduğundan. Yük testi sonuçları havuzu performans sayacı verilerini ve kaydedilmiş hatalar hakkındaki tüm bilgileri içerir. Sonuçlar deposu veritabanı denetleyiciler için kurulum tarafından oluşturulan veya bir yük testi ilk yerel çalıştırılmasında otomatik olarak oluşturulur. Yerel çalıştırma için yük testi şeması mevcut değilse veritabanını otomatik olarak oluşturulur.

 Farklı bir sunucu kullanmak için denetleyicinin sonuç depo bağlantı dizesini değiştirirseniz, yeni sunucunun loadtestresultsrepository.sql betik şema oluşturmak için çalıştırması olması gerekir.

 Visual Studio Enterprise teknolojiye dayalı ortak performans sayaçlarını toplayan adlandırılmış sayaç kümesi sağlar. Bu ayarlar, bir IIS sunucusunu, ASP.NET sunucusu veya bir SQL server incelerken yararlıdır. Sayaç kümeleri ile toplanan verilerin tümünü yük testi sonuçları deposunda saklanır.

> [!IMPORTANT]
> Bir sayaç kümesi ve performans sayacı verilerini arasında bir fark yoktur. Bir sayaç kümesi meta verilerdir. IIS veya SQL Server gibi belirli bir rol gerçekleştiren bir bilgisayardan toplanması gereken performans sayaçları grubu tanımlar. Sayaç kümesi yük testi tanımının bir parçasıdır. Performans sayacı verilerini temel sayaç kümelerine toplanan, belirli bir bilgisayar ve örnek hızı sayaç eşleme ayarlayın.

## <a name="sql-server-versions"></a>SQL Server sürümleri

 Yük testleri kullanmak için SQL Server Express Visual Studio ile yüklenen LocalDB, kullanabilirsiniz. Bu yük testleri (Microsoft Excel tümleştirme dahil) için varsayılan veritabanı sunucusudur. SQL Server Express LocalDB bir program geliştiriciler için hedeflenen SQL Server Express, yürütme modudur. SQL Server Express LocalDB yükleme en az bir SQL Server Veritabanı Altyapısı'nı başlatmak için gerekli dosyaları kopyalar.

 Yoğun veritabanı gereksinimlerini ekibinizin bekliyor ya da SQL Server Express LocalDB projelerinizi outgrow, SQL Express ya da tam SQL Server için daha fazla ölçeklendirme olası sağlamak için yükseltme düşünmelisiniz. SQL Server yükseltirseniz, SQL Server Express LocalDB MDF ve LDF dosyalarını kullanıcı profili klasöründe depolanır. Bu dosyalar, SQL Server Express veya SQL Server için yük testi veritabanını almak için kullanılabilir.

## <a name="load-test-results-store-considerations"></a>Yük testi sonuçları deposunu dikkat edilecek noktalar

 Visual Studio Enterprise yüklü olduğunda bilgisayarda yüklü olan SQL Express örneği kullanmak için yük testi sonuçları deposu ayarlanır. SQL Express en fazla 4 GB disk alanı kullanmaya sınırlıdır. Uzun bir süre boyunca birçok yük testi çalıştıracaksanız yük testi sonuçları deposunu varsa tam SQL Server ürün örneğini kullanmak için yapılandırma düşünmelisiniz.

## <a name="load-test-analyzer-tasks"></a>Yük Testi Çözümleyicisi görevleri

|Görevler|İlgili Konular|
|-----------|-----------------------|
|**Bir yük testi ayarlama sonuçları deposu:** bir SQL veritabanı bir yük testi sonuçları deposunu ayarlayabilirsiniz. **Not:** bir test denetleyicisi yüklediğinizde yük testi deposu de oluşturulabilir. Daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).||
|**Seçme ve sonuç deposu görüntüleme:** belirli bir sonuç havuzunu seçebilirsiniz. Bir yerel sonuçları deposu sınırlı değildir. Genellikle, yük testleri Aracı bilgisayarların uzaktan kümesine göre çalıştırılır. Test sonuçlarından aracılarınızı veya yerel bilgisayarınıza bir yük testi sonuçları deposu oluşturmuş olduğunuz herhangi bir SQL sunucusuna kaydedilebilir. Her iki durumda da kullanarak yük testi sonuçlarını depolanacağı tanımlamalıdır **Test denetleyicilerini yönetme** penceresi.|-   [Nasıl yapılır: yük testi sonuçları deposunu seçme](../test/how-to-select-a-load-test-results-repository.md)<br />-   [Nasıl yapılır: yük testi sonuçlarını çözümleme için erişim](../test/how-to-access-load-test-results-for-analysis.md)|
|**Bir yük testi sonuç depodan silme:** bir yük testi sonucundan kaldırabilirsiniz **Yük Testi Düzenleyicisi** kullanarak **yük testi sonuçlarını yönetme ve Aç** iletişim kutusu.|-   [Nasıl yapılır: yük testi sonuçlarını bir depodan silme](../test/how-to-delete-load-test-results-from-a-repository.md)|
|**İçeri ve sonuçları bir depoya dışarı aktarma:** içeri aktarabilir ve yük testi sonuçlarını dışarı aktarın **Yük Testi Düzenleyicisi**.|-   [Nasıl yapılır: yük testi sonuçlarını bir depoya içeri aktarma](../test/how-to-import-load-test-results-into-a-repository.md)<br />-   [Nasıl yapılır: yük testi sonuçlarını bir depodan dışarı aktarma](../test/how-to-export-load-test-results-from-a-repository.md)|

## <a name="related-tasks"></a>İlişkili görevler

 [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)

 Yük Testi Çözümleyicisi kullanarak çalışan bir yük testi ve tamamlanmış bir yük testi sonuçlarını görüntüleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Nasıl yapılır: yük testi sonuçlarını çözümleme için erişim](../test/how-to-access-load-test-results-for-analysis.md)