---
title: Derleme ve oluşturma
description: Bu makalede derlemek ve Mac için projeler ve çözümler Visual Studio'da derleme hakkında
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: 29c6baaa4da4eae4a2302ec3916a156b59a49272
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34453889"
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>Derleme ve Mac için Visual Studio'da derleme

Mac için Visual Studio, uygulamaları geliştirmek ve projenizi geliştirme sırasında derlemeleri oluşturmak için kullanılabilir. Derleme ve Tür uyuşmazlıkları ve diğer derleme zamanı hataları belirleyebilir kodunuzu erken ve genellikle oluşturmak önemlidir.

## <a name="building-from-the-ide"></a>IDE içinden derleme

Mac sağlar oluşturmak ve çalıştırmak için Visual Studio kullanarak hemen hala yapı işlevselliği denetleyen verilirken oluşturur. Mac için Visual Studio MSBuild temel yapı sistem olarak kullanır.

Tüm projeler ve çözümler IDE içinde oluşturulan varsayılan bir yapı yapılandırma derlemeleri bağlamının tanımlayan sahip olur. Bu yapılandırmalar düzenlenip düzenlenemeyeceğini veya kendi oluşturabilirsiniz. Otomatik olarak oluşturmak veya bu yapılandırmalar ardından projenizi oluşturmak için MSBuild tarafından kullanılan proje dosyasını güncelleştirir.  

Projeler ve çözümler IDE'de oluşturma hakkında daha fazla bilgi için bkz: [yapı ve projeler ve çözümler Temizleme](building-and-cleaning-projects-and-solutions.md) Kılavuzu.

Mac için Visual Studio, aşağıdakileri yapmak için de kullanılabilir:

* Çıkış yolu değiştirin. Bu, projenizin seçeneklerinde düzenlenmesi:

    ![Çıkış yolu Değiştir](media/compiling-and-building-image4.png)

* Derleme çıktı ayrıntı değiştirin:

    ![Değişiklik yapı ayrıntı](media/compiling-and-building-image5.png)

* Özel komutlar önce sırasında veya sonrasında oluşturma veya temizleme ekleyin:

    ![özel komutlar ekleme](media/compiling-and-building-image6.png)

## <a name="building-from-command-line"></a>Komut satırından oluşturma

Komut satırı aracılığıyla uygulamaları oluşturmak için MSBuild Build Engine kullanabilirsiniz.

Bkz: [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild) MSBuild kullanma hakkında daha fazla bilgi için içerik.

## <a name="building-from-visual-studio-team-services"></a>Visual Studio Team Services oluşturma

* [Xamarin uygulamanızı derleyin](https://www.visualstudio.com/docs/build/apps/mobile/xamarin)
* [Xamarin ile sürekli tümleştirme](https://developer.xamarin.com/guides/cross-platform/ci/)