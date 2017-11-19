---
title: "Derleme ve Mac için Visual Studio'da derleme | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: 9005cf64f4b72f39923d6525e78de745d79c3953
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>Derleme ve Mac için Visual Studio'da derleme

Mac için Visual Studio, uygulamaları geliştirmek ve projenizi geliştirme sırasında derlemeleri oluşturmak için kullanılabilir. Derleme ve Tür uyuşmazlıkları ve diğer derleme zamanı hataları belirleyebilir kodunuzu erken ve genellikle oluşturmak önemlidir.

## <a name="choosing-a-build-method"></a>Bir yapı yöntemi seçme:

### <a name="using-the-ide"></a>IDE kullanma

Mac için Visual Studio kullanarak oluşturmak ve derlemeleri hemen çalıştırmak için sağlar, hala verilirken yapı işlevselliği üzerinde denetim. Mac için Visual Studio MSBuild temel yapı sistem olarak kullanır.

Tüm projeler ve çözümler IDE içinde oluşturulan varsayılan bir yapı yapılandırma derlemeleri bağlamının tanımlayan sahip olur. Bu yapılandırmalar düzenlenip düzenlenemeyeceğini veya kendi oluşturabilirsiniz. Otomatik olarak oluşturmak veya bu yapılandırmalar ardından projenizi oluşturmak için MSBuild tarafından kullanılan proje dosyasını güncelleştirir.  

Projeler ve çözümler IDE'de oluşturma hakkında daha fazla bilgi için bkz: [yapı ve projeler ve çözümler Temizleme](~/building-and-cleaning-projects-and-solutions.md) Kılavuzu.

Mac için Visual Studio, aşağıdakileri yapmak için de kullanılabilir:

* Çıkış yolu değiştirin. Bu, projenizin seçeneklerinde düzenlenmesi:

    ![Çıkış yolu Değiştir](media/compiling-and-building-image4.png)

* Derleme çıktı ayrıntı değiştirin:

    ![Değişiklik yapı ayrıntı](media/compiling-and-building-image5.png)

* Özel komutlar önce sırasında veya sonrasında oluşturma veya temizleme ekleyin:

    ![özel komutlar ekleme](media/compiling-and-building-image6.png)

### <a name="building-from-command-line"></a>Komut satırından oluşturma

Komut satırı aracılığıyla uygulamaları oluşturmak için MSBuild Build Engine kullanabilirsiniz.

Bkz: [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild) MSBuild kullanma hakkında daha fazla bilgi için içerik.

### <a name="using-visual-studio-team-services"></a>Visual Studio Team Services kullanma

* [Xamarin uygulamanızı derleyin](https://www.visualstudio.com/docs/build/apps/mobile/xamarin)
* [Xamarin ile sürekli tümleştirme](https://developer.xamarin.com/guides/cross-platform/ci/)