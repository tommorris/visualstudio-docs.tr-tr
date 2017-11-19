---
title: "Veri bilimi ve analitik uygulamaları iş yükü Visual Studio'da | Microsoft Docs"
ms.custom: 
ms.date: 9/5/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
- devlang-python
- devlang-fsharp
ms.tgt_pltfrm: 
ms.topic: landing-page
ms.assetid: 018069f3-6d1a-4143-a851-d86d2ff5fbfc
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 86f97beae9405003e123ad05893c7e49486f5661
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="data-science-and-analytical-applications-workload"></a>Veri bilimi ve analitik uygulamaları iş yükü

Visual Studio'da veri bilimi ve analitik uygulamaları iş yükü üç dilleri ve bunların ilgili çalışma zamanı dağıtımları bir araya getirir:

- [R ve Microsoft R istemci](../rtvs/index.md)
- [Python ve Anaconda](../python/python-in-visual-studio.md)
- [F # .NET framework ile](https://docs.microsoft.com/dotnet/fsharp/)

![Visual Studio yükleyicisi veri bilimi ve analizi uygulamaları iş yükü](media/data-science-workload.png)

R ve Python veri bilimi için kullanılan birincil betik dosyası oluşturma dillerini ikisidir. Her iki dilde bilgi edinmek kolay ve zengin ekosistemi paketleri tarafından desteklenmektedir. Bu paketleri, çok çeşitli veri alım, temizleme, model eğitim, dağıtım ve çizme gibi senaryoları adres. Ve F #, çok çeşitli veri işleme görevlerini için uygun bir güçlü ilk .NET dilidir.

<!--Note link on the image because this one is large -->
[![Visual Studio R, Python ve F # ile ekran görüntüleri](media/data-science-workload-screens.png)](media/data-science-workload-screens.png)

## <a name="workload-options"></a>İş yükü seçenekleri

Varsayılan olarak, Visual Studio yükleyicisi iş yükü için Özet bölümündeki değiştirebileceğiniz aşağıdaki seçenekleri iş yükü yükler:

- F # dil desteği
- Python:
  - Python dil desteği
  - Python web desteği
  - [Anaconda3 64-bit](https://www.continuum.io) (kapsamlı veri bilimi kitaplıkları ve bir Python yorumlayıcısı içerir A Python distro)
  - Cookiecutter şablon desteği
- R:
  - R dil desteği
  - [Microsoft R istemci](/machine-learning-server/r-client/what-is-microsoft-r-client) (Microsoft'un tümüyle uyumlu, topluluk tarafından desteklenen R yorumlayıcı daha hızlı hesaplama tek düğümler veya kümeleri için ScaleR kitaplıkları ile. Gelen tüm R de kullanabilirsiniz [CRAN](https://cran.r-project.org/).)
  - R geliştirme araçları çalışma zamanı desteği

Üç R bileşenleri de F # diğer iş yükleri bir dizi dahil edilir ve Python kendi, veri bilimi iş yüküne sahiptir ve analitik uygulamaları yalnızca iş yükü r bağımsız iş yükü içeren şu anda olduğu, ancak üzerinde seçilebilir. **Bileşenleri tek tek** yükleyici sekmesindedir. Seçenekleri seçin **geliştirme etkinlikleri > R dil desteği**, **geliştirme etkinlikleri > Microsoft R istemci**, ve **derleyicileri, yapı araçları ve çalışma zamanları > çalışma zamanı desteği R geliştirme araçları için**.

## <a name="sql-server-integration"></a>SQL Server Integration

R ve Python doğrudan SQL Server içinde gelişmiş analizler yapmak için SQL Server kullanılmasını destekler. R desteği SQL Server 2016 ve sonraki sürümlerinde; Python desteği ve sonrasında SQL Server 2017 CTP 2. 0'ın kullanılabilir değil.

Kodunuz nerede verilerinizi zaten yaşıyor çalıştırarak, çok sayıda avantaj keyfini çıkarın:

- **Veri taşıma ortadan kaldırılması**: verileri veritabanından uygulamanızı veya model için taşıma yerine, veritabanındaki R ve Python uygulamalar oluşturabilir. Bu özellik, güvenlik, uyumluluk, idare, bütünlük ve çok büyük miktarda veri taşıma için ilgili benzer sorunlar ana bilgisayarını engelleri ortadan kaldırır. Ayrıca, bir istemci makine belleğe sığması uygulanamadı veri kümeleri kullanmasına olanak sağlar.

- **Kolay dağıtım**: bilgisayarınızda R veya Python model hazır, üretime dağıtma yalnızca bir T-SQL betiği katıştırma anlamına gelir. Herhangi bir dilde yazılmış herhangi bir SQL istemcisi uygulama modelleri ve saklı yordam çağrısı aracılığıyla Intelligence yararlanabilir. Belirli bir R veya Python tümleştirmeler gereklidir.

- **Kurumsal düzeyde performans ve ölçek**: bellek içi tablo ve sütun dizinleri yüksek performanslı ölçeklenebilir API'leri ile RevoScaleR ve RevoScalePy paketler depolamak gibi SQL Server'ın gelişmiş özelliklerini kullanabilirsiniz. Veri taşıma eleme verilerinizi büyüyor veya uygulamanın performansını artırmak istediğiniz gibi istemci bellek kısıtlamaları önlemek anlamına gelir.

- **Zengin genişletilebilirlik**: yükleyin ve herhangi bir son açık kaynak büyük miktarlardaki verileri SQL Server üzerinde derin öğrenme ve AI uygulamaları oluşturmak için SQL Server'daki R veya Python paketlerini çalıştırın. Bir paketi SQL Server yükleme yerel makinenizde bir paketi yüklemek kadar basittir.

- **Hiçbir ek ücret ödemeden uluslararası kullanılabilirlik**: R ve Python tümleştirmeler SQL Server 2017 ve daha sonra tüm sürümlerinde kullanılabilir Express edition dahil. (R desteği SQL Server 2016 kullanılabilir ve üzeri içindir.)

SQL Server Integration tam olarak yararlanmak için de yüklemeniz gerekir **veri depolama ve işleme** yüküyle **SQL Server veri Araçları** seçeneği. Bu seçenek, SQL IntelliSense, sözdizimi vurgulama ve dağıtımını sağlar.

![Veri depolama ve işlem iş yükü](media/data-storage-workload.png) &nbsp;&nbsp; &nbsp;&nbsp; ![Veri depolama ve işleme iş yükü seçenekleri](media/data-storage-workload-options.png)

Daha fazla bilgi için:

- [SQL Server ve R ile çalışma](../rtvs/sql-server.md)
- [Veritabanı-r ile SQL Server 2016 Gelişmiş analizi](https://blogs.technet.microsoft.com/dataplatforminsider/2016/03/29/in-database-advanced-analytics-with-r-in-sql-server-2016/)
- [SQL Server 2017 Python'da: veritabanı machine learning Gelişmiş](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)

## <a name="additional-services-and-sdks"></a>Ek hizmetler ve SDK'ları

Veri bilimi ve analizi uygulamaları iş yükü doğrudan nedir yanı sıra, Azure not defterlerini hizmeti ve Python için Azure SDK'sı da veri bilimi için yararlıdır.

Python için Azure SDK'sını kullanabilir ve Windows, Mac OSX ve Linux üzerinde çalışan uygulamalardan Microsoft Azure hizmetlerini yönetmek kolaylaştırır. Daha fazla bilgi için bkz: [Python için Azure SDK'sı](../python/azure-sdk-for-python.md)

(Şu anda önizlemede) Azure not defterlerini bulutta Microsoft Azure üzerinde çalışan Jupyter not defterleri için ücretsiz çevrimiçi erişim sağlar. Hizmet, Python, R ve F # başlamanıza yardımcı olmak için örnek not defterlerini içerir. Ziyaret[notebooks.azure.com](https://notebooks.azure.com/).

<!--Note link on the image because this one is large -->
[![R örnek giriş ile Azure Not ekran görüntüleri](media/data-science-workload-notebooks.png)](media/data-science-workload-notebooks.png)