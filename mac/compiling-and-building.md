---
title: Derleme ve oluşturma
description: Bu makalede, derlemek ve Mac için projeleri ve Visual Studio çözümleri oluşturmak açıklanır
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: a66cc250b0d019b3efa4873b89eef252af44b8a6
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283710"
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>Derleme ve Mac için Visual Studio'da oluşturma

Mac için Visual Studio, uygulamaları oluşturun ve projenizi geliştirilmesi sırasında derlemeleri oluşturmak için kullanılabilir. Derlemek ve tür uyumsuzluklarına ve diğer derleme zamanı hataları belirleyebilir erken ve sıkça kodunuzu oluşturmak önemlidir.

## <a name="building-from-the-ide"></a>IDE içinden derleme

Mac sağlar oluşturmak ve çalıştırmak için Visual Studio kullanarak hemen hala yapı işlevselliğinde kontrol sağlarken oluşturur. Mac için Visual Studio MSBuild, temel alınan derleme sisteminin kullanır.

Tüm projeler ve çözümler IDE içinde oluşturulan yapılar için bağlam tanımlayan bir varsayılan yapı yapılandırması gerekir. Bu yapılandırmalar düzenlenebilir veya kendi oluşturabilirsiniz. Oluştururken veya değiştirirken Bu yapılandırmalar ardından projenizi oluşturmak için MSBuild tarafından kullanılan proje dosyası otomatik olarak güncelleştirecektir.

Projeler ve çözümler IDE'de oluşturma hakkında daha fazla bilgi için bkz. [oluşturma ve projeler ve çözümler Temizleme](building-and-cleaning-projects-and-solutions.md) Kılavuzu.

Mac için Visual Studio, aşağıdakileri yapmak için de kullanılabilir:

* Çıkış yolunu değiştirin. Bu proje seçeneklerinde düzenlenmesi:

    ![Çıkış yolu Değiştir](media/compiling-and-building-image4.png)

* Yapı çıkış ayrıntı değiştirin:

    ![Değişiklik derleme ayrıntısı](media/compiling-and-building-image5.png)

* Özel komutlar öncesinde, sırasında veya sonrasında oluşturma veya temizleme ekleyin:

    ![özel komutlar ekleme](media/compiling-and-building-image6.png)

## <a name="building-from-command-line"></a>Komut satırından derleme

MSBuild derleme altyapısı, komut satırı aracılığıyla uygulamaları oluşturmak için kullanabilirsiniz.

Bkz: [MSBuild](/visualstudio/msbuild/msbuild) MSBuild kullanma hakkında daha fazla bilgi için içerik.

## <a name="building-from-azure-pipelines"></a>Azure işlem hatları oluşturma

* [Xamarin uygulamanızı derleyin](/vsts/pipelines/apps/mobile/xamarin?view=vsts&tabs=vsts)
* [Xamarin ile sürekli tümleştirme](https://developer.xamarin.com/guides/cross-platform/ci/)