---
title: "Örnek projeler için R araçları Visual Studio için | Microsoft Docs"
description: "R ve Visual Studio ile çalışmaya başlamak için örnekleri koleksiyonunu dizini."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: get-started-article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: f8bf96d4fcfdb29fdaf79fa5adba9b99375aaddd
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="r-tools-for-visual-studio-sample-projects"></a>Visual Studio örnek projeler için R araçları

Bu koleksiyon örnekleri R, R araçları için Visual Studio (RTVS) ve Microsoft R Server başlamanızı sağlar:

1. Karşıdan [samples ZIP dosyası](https://github.com/Microsoft/RTVS-docs/archive/master.zip) ve tercih ettiğiniz bir klasöre ayıklayın.
1. Açık `examples/Examples.sln` projeyi de iki klasör görmek için:

    - *Bir ilk bakabilir R* r için yeni gelenlere için size bir giriş sağlar
    - *MRS ve makine öğrenme* R ve Microsoft R Server machine learning için nasıl kullanılacağı örnekleri verir.

## <a name="a-first-look-at-r"></a>R ilk bakma

Bu örnek kapsamlı bir R giriş kapsamlı iki kaynak dosyalardaki açıklamalar aracılığıyla sağlar. En iyi deneyimi, dosyanın üst kısmında imleci yerleştirin ve kod satırı-tarafından-kalan için göndermek için Ctrl + Enter tuşlarına **R etkileşimli** penceresi. (Paketleri yüklemek satırları veya iki tamamlamak için bir dakika sürebilir.)

- `1-Getting Started with R.R`paketleri kullanma, yükleme ve veri analizi ve Çizdirmek dahil olmak üzere birçok R temelleri kapsar.

    ![1-Başlarken R.R örnek örnek çıkışı](media/samples-getting-started-output.png)

- `2-Introduction to ggplot2.R`Basit sözdizimi ve görsel olarak çekici çizimleri için bilinen ggplot2 grafik paket tanıtır. Bu örnek Fiji deprem verilerden visualizes.

    ![Örnek 2 giriş ggplot2 için çıktı. R örnek](media/samples-ggplot-output.png)

## <a name="microsoft-r-server-and-machine-learning"></a>Microsoft R Server ve makine öğrenme

Bu koleksiyonda örneklerin R makine öğrenimi modellerini oluşturmak için ve yararlanmak için nasıl kullanılacağını gösterir [Microsoft R Server (MRS)](http://aka.ms/rtvs-msft-r). Komut dosyaları çalıştırmak için MRS yüklemek `MRS` başlık ve aksi belirtilmedikçe.

Tüm örnekler, dosyayı açma gibi en üstte imleci yerleştirin ve satır Ctrl + Enter ile kodlarda adım. Her klasör markdown dosyalarında da ek ayrıntıları içerir.

- `Benchmarks`yoğun, paralel Lineer Cebir hesaplamalar performansı göstermek için bir dizi kazanır çalıştırır Microsoft R açık ve Intel matematik çekirdek kitaplığı (MKL) kullanımı ile mümkün olabilir. Benzetimli verilerle değerlendirmeler özellikle iki karşı bir iş parçacığı matris hesaplamaları karşılaştırın.

    ![Örnek Kıyaslama çizim](media/samples-mro-benchmark-plot.png)

- `Bike_Rental_Estimation_with_MRS`Geçmiş verileri Microsoft R Server kullanarak kümesinde, temel bisiklet kiralama olanağı için isteğe bağlı bir tahmin modeli oluşturur. 

- `Data_Exploration`üç komut dosyaları içerir:

  - `Import Data from URL.R`bir URL tanımlanan veri dosyası r yüklemek nasıl gösterir
  - `Import Data from URL to xdf.R`Microsoft R Sunucusu'na bir xdf olarak bir URL tanımlanan veri dosyasını yükleme gösterilmektedir. (MRS gerektirir.)
  - `Using ggplot2.R`bir uzantısıdır `A First Look at R/2-Introduction to ggplot2.R` ggplot2'ın işlevselliği etkileşimli 3B Çizdirmek dahil olmak üzere daha geniş bir turu vermiş örnek.

      ![Ggplot2 kullanarak çıktı. R örneği](media/samples-3d-interactive.png)

- `Datasets`üç içeren `.csv` diğer örnekleri tarafından kullanılan dosyaları
- `Flight_Delays_Prediction_with_R`ve `Flight_Delays_Prediction_with_MRS` R, machine learning ve geçmiş zamanında performans ve hava durumu verilerini kullanarak uçuş gecikmeler tahmin gösterilmektedir. 
- `Machine learning`Uçuş gecikmeler, muhafazası fiyatları ve bisiklet kiralamaları tahmin etmek öğrenme için üç örnekleri içerir. Birlikte, bu örnekleri uygulamaya R ve MRS gerçek dünyadaki sorunları gösterir. Ayrıca, birçok popüler makine öğrenimi modellerini kullanın ve bir Azure Web hizmetini kullanarak olarak dağıtma olarka bir [Azure Machine Learning](https://azure.microsoft.com/services/machine-learning/) çalışma.

- `R_MRO_MRS_Comparison`benzerlikler ve komutlar, sözdizimi, yapılar ve performans ile R, Microsoft R açın ve Microsoft R Server farklar gösterilmektedir altı bölümü karşılaştırması bulunur.

## <a name="whats-special-about-microsoft-r-open-and-microsoft-r-server"></a>Microsoft R açın ve Microsoft R Server hakkında özel nedir?

[Microsoft R açık](http://aka.ms/rtvs-r-open), R, Microsoft'un dağıtımını farklı [CRAN R](https://cran.r-project.org/) iki önemli şekilde:

1. [Daha iyi hesaplama performans](https://mran.revolutionanalytics.com/rro/#intelmkl1) ile kullanıldığında [Intel matematik çekirdek kitaplıkları](https://software.intel.com/intel-mkl). Kitaplıklar, ücretsiz olarak Microsoft Microsoft R açık ile kullanmak için kullanılabilir.

1. [Yeniden üretilebilir R Araç Seti](https://mran.revolutionanalytics.com/rro/#reproducibility) R programınızı oluşturmak için kullanılan kitaplıklar her zaman çalışmanızı yeniden istediğiniz başkaları için kullanılabilir olmasını sağlar.

[Microsoft R Server](http://aka.ms/rtvs-msft-r) daha fazla veri işleme ve daha hızlı işlemek izin veren R uzantısıdır. R iki güçlü özellikleri sağlar:

1. Büyük veri kümeleri RAM kısıtlama olmadan. MRS bellek yetersiz veri kaynakları Hadoop kümeleri, veritabanları ve veri ambarlarında dahil olmak üzere çeşitli işleyebilir.

1. Paralel, çok çekirdekli işleme. MRS verimli hesaplama dağıtmak hesaplama tüm kaynaklar arasında kullanılabilir sahiptir. Kişisel iş istasyonunuzu veya uzak bir küme, MRS daha hızlı bir yanıt alır.

Aşağıdaki karşılaştırmaya MRS ve MKL ile MRO belirli matris hesaplamasından R ve MKL olmadan MRO ilgili önemli ölçüde daha iyi hesaplama performans olduğunu gösterir. Sanal veri Bu hesaplamada kullanılır:

![MRS ve MKL r ile MRO ve MKL olmadan MRO karşılaştırma](media/samples-speed-comparison.png)

R MRO ve MRS teknik karşılaştırması için kullanıma [Lixun Zhang'in ayrıntılı tartışma](http://htmlpreview.github.io/?https://github.com/lixzhang/R-MRO-MRS/blob/master/Introduction_to_MRO_and_MRS.html) konusunda.

Aşağıdaki şekilde geçen süre içinde Lojistik regresyon modeli oluşturma uçuş gecikmeler 15 dakikadan fazla tahmin etmek için kullanılan saniye sonra karşılaştırır.  Geçen süre içinde CRAN R kullanılan MRS yalnızca yaklaşık iki kez artırır ancak az sayıda satırı artan zaman önemli ölçüde artırır. Bu kıyaslama ayrıntılarını kullanıma `Benchmarks/rxGlm_benchmark.R` örnek.

![rxGlm Kıyaslama](media/samples-rxGLM-benchmark.png)
