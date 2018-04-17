---
title: Veri bilimi ve analitik uygulamaları iş yükü
description: "Visual Studio'da veri bilimi ve analitik uygulamaları iş yükü Python, R, F # ve Anaconda dahil olmak üzere kendi ilgili çalışma zamanı dağıtımları bir araya getirir."
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- devlang-r
- devlang-python
ms.topic: overview
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 5b2a1eccfbf90784d19ded18667e8b336d920892
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="data-science-and-analytical-applications-workload"></a>Veri bilimi ve analitik uygulamaları iş yükü

Seçin ve Visual Studio yükleyicisi yüklemek, veri bilimi ve analitik uygulamaları iş yükünün üç dilleri ve bunların ilgili çalışma zamanı dağıtımları bir araya getirir:

- [R ve Microsoft R istemci](../rtvs/index.md)
- [Python ve Anaconda](../python/overview-of-python-tools-for-visual-studio.md)
- [F # .NET framework ile](/dotnet/fsharp/)

![Visual Studio yükleyicisi veri bilimi ve analizi uygulamaları iş yükü](media/data-science-workload.png)

R ve Python veri bilimi için kullanılan birincil betik dosyası oluşturma dillerini ikisidir. Her iki dilde bilgi edinmek kolay ve zengin ekosistemi paketleri tarafından desteklenmektedir. Bu paketleri, çok çeşitli veri alım, temizleme, model eğitim, dağıtım ve çizme gibi senaryoları adres. F # Ayrıca, çok çeşitli veri işleme görevlerini için uygun bir güçlü ilk .NET dildir.

<!--Note link on the image because this one is large -->
[![Visual Studio R, Python ve F # ile ekran görüntüleri](media/data-science-workload-screens.png)](media/data-science-workload-screens.png)

## <a name="workload-options"></a>İş yükü seçenekleri

Varsayılan olarak, Visual Studio yükleyicisi iş yükü için Özet bölümündeki değiştirebileceğiniz aşağıdaki seçenekleri iş yükü yükler:

- F # dil desteği
- Python:
  - Python dil desteği
  - [Anaconda3 64-bit](https://www.continuum.io) (kapsamlı veri bilimi kitaplıkları ve bir Python yorumlayıcısı içerir A Python distro)
  - Python web desteği
  - Cookiecutter şablon desteği
- R:
  - R dil desteği
  - R geliştirme araçları çalışma zamanı desteği
  - [Microsoft R istemci](/machine-learning-server/r-client/what-is-microsoft-r-client) (Microsoft'un tümüyle uyumlu, topluluk tarafından desteklenen R yorumlayıcı daha hızlı hesaplama tek düğümler veya kümeleri için ScaleR kitaplıkları ile. Gelen tüm R de kullanabilirsiniz [CRAN](https://cran.r-project.org/).)

F # diğer iş yükleri bir dizi dahil edilir ve kendi iş yükü Python sahip veri bilimi ve analitik uygulamaları olsa da yalnızca iş yükü şu anda r içerir Ancak, iş yükünü bağımsız R yükleyebilirsiniz. Üzerinde **bileşenleri tek tek** sekmesinde Yükleyicisi'nde, aşağıdaki R seçenekleri seçin:

- **Geliştirme etkinlikleri > R dil desteği**
- **Geliştirme etkinlikleri > Microsoft R istemcisi**
- **Derleyicileri, yapı araçları ve çalışma zamanları > R geliştirme araçları çalışma zamanı desteği**

## <a name="sql-server-integration"></a>SQL Server Integration

R ve Python doğrudan SQL Server içinde gelişmiş analizler yapmak için SQL Server kullanılmasını destekler. R desteği SQL Server 2016 ve sonraki sürümlerinde; Python desteği ve sonrasında SQL Server 2017 CTP 2. 0'ın kullanılabilir değil.

Aşağıdaki avantajları nerede verilerinizi zaten yaşıyor kodunuzu çalıştırarak keyfini çıkarın:

- **Veri taşıma ortadan kaldırılması**: verileri veritabanından uygulamanızı veya model için taşıma yerine, veritabanındaki R ve Python uygulamalar oluşturabilir. Bu özellik, güvenlik, uyumluluk, idare, bütünlük ve çok büyük miktarda veri taşıma için ilgili benzer sorunlar ana bilgisayarını engelleri ortadan kaldırır. Bir istemci makine belleğe sığması uygulanamadı veri kümeleri de kullanabilir.

- **Kolay dağıtım**: sahip olduğunuz bir R veya Python model hazır sonra üretime dağıtma bir T-SQL betiği katıştırma bir basit konudur. Herhangi bir dilde yazılmış herhangi bir SQL istemcisi uygulama modelleri ve saklı yordam çağrısı aracılığıyla Intelligence yararlanabilir. Belirli bir R veya Python tümleştirmeler gereklidir.

- **Kurumsal düzeyde performans ve ölçek**: bellek içi tablo ve sütun dizinleri yüksek performanslı ölçeklenebilir API'leri ile RevoScaleR ve RevoScalePy paketler depolamak gibi SQL Server'ın gelişmiş özelliklerini kullanabilirsiniz. Veri taşıma eleme verilerinizi büyüyor veya uygulamanın performansını artırmak istediğiniz gibi istemci bellek kısıtlamaları önlemek anlamına gelir.

- **Zengin genişletilebilirlik**: yükleyin ve herhangi bir son açık kaynak büyük miktarlardaki verileri SQL Server üzerinde derin öğrenme ve AI uygulamaları oluşturmak için SQL Server'daki R veya Python paketlerini çalıştırın. Bir paketi SQL Server yükleme yerel makinenizde bir paketi yüklemek kadar basittir.

- **Hiçbir ek ücret ödemeden uluslararası kullanılabilirlik**: R ve Python tümleştirmeler SQL Server 2017 ve daha sonra tüm sürümlerinde kullanılabilir Express edition dahil. (R desteği SQL Server 2016 kullanılabilir ve üzeri içindir.)

SQL Server Integration tam anlamıyla yararlanabilmek için yüklemek için Visual Studio yükleyicisi kullanın **veri depolama ve işleme** yüküyle **SQL Server veri Araçları** seçeneği. İkinci seçeneği SQL IntelliSense, sözdizimi vurgulama ve dağıtım sağlar.

![Veri depolama ve işlem iş yükü](media/data-storage-workload.png) &nbsp;&nbsp;&nbsp;&nbsp; ![Veri depolama ve işleme iş yükü seçenekleri](media/data-storage-workload-options.png)

Daha fazla bilgi için:

- [SQL Server ve R ile çalışma](../rtvs/sql-server.md)
- [Veritabanı Advanced Analytics r ile SQL Server 2016 (blog)](https://blogs.technet.microsoft.com/dataplatforminsider/2016/03/29/in-database-advanced-analytics-with-r-in-sql-server-2016/)
- [SQL Server 2017 Python'da: Gelişmiş veritabanı machine learning (blog)](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)

## <a name="additional-services-and-sdks"></a>Ek hizmetler ve SDK'ları

Veri bilimi ve analizi uygulamaları iş yükü doğrudan nedir yanı sıra, Azure not defterlerini hizmeti ve Python için Azure SDK'sı da veri bilimi için yararlıdır.

Python için Azure SDK'sını kullanabilir ve Windows, Mac ve Linux üzerinde çalışan uygulamalardan Microsoft Azure hizmetlerini yönetmek kolaylaştırır. Daha fazla bilgi için bkz: [Python için Azure SDK'sı](../python/azure-sdk-for-python.md)

(Şu anda önizlemede) Azure not defterlerini bulutta Microsoft Azure üzerinde çalışan Jupyter not defterleri için ücretsiz çevrimiçi erişim sağlar. Hizmet, Python, R ve F # başlamanıza yardımcı olmak için örnek not defterlerini içerir. Ziyaret[notebooks.azure.com](https://notebooks.azure.com/).

<!--Note link on the image because this one is large -->
[![R örnek giriş ile Azure Not ekran görüntüleri](media/data-science-workload-notebooks.png)](media/data-science-workload-notebooks.png)