---
title: "Alt sürüme ile çalışma | Microsoft Docs"
description: "Alt sürüme Mac için Visual Studio kullanarak"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 2400ED9C-6236-4C0A-A3AB-9D7CBE1F0CF4
ms.openlocfilehash: 39f7407854b2ff74552209762565236adb403d84
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="working-with-subversion"></a>Alt sürüme ile çalışma

Alt sürüme tek ana verilerin bir kopyasını merkezi denetlemenize olanak sağlayan merkezi sürüm denetim sistemidir. Git, aksine bir alt sürüme deposu denetimi tüm depoyu kopyalayın değil, yalnızca zamandaki o noktada bir anlık görüntüsünü alır.

Alt sürüme, kullanıcının aynı Havuzda eşzamanlı olarak çalışmasına izin vermek için bir kopya değiştirme birleştirme modeli kullanır. Başka bir deyişle, her kullanıcı üzerinde bağımsız olarak çalışırlar merkezi veri yerel ya da çalışma, bir kopyasını oluşturur. Kopya çalışan kullanıcılar değişiklikleri kronolojik bir biçimde birleştirilir.

Örneğin, bir kullanıcı hem de kullanıcı B uzak depo ve bir kopyasından her Değiştir dosyaları kullanıma olduğunu düşünün. Kullanıcı A değişiklikler tamamlandıktan ve Uzaktan kaydeder. İşlerini kullanıcı B tamamlar önce kullanıcı A'ın değişiklikleri birleştirme uzaktan değişikliklerle kendi çalışma kopyası güncelleştirmelisiniz.

Aşağıdaki bölümlerde nasıl alt sürüme Visual Studio'daki sürüm denetimi için Mac için kullanılabileceğini keşfedin

Aşağıdaki resimde, Visual Studio tarafından Mac için sürüm denetimi menü öğesi tarafından sağlanan seçenekleri gösterilmektedir:

![Sürüm denetimi menü öğeleri](media/version-control-svnVersionControlMenu.png)

## <a name="checkout"></a>Checkout...

Uzak bir alt sürüme depo kullanmaya başlamadan önce depoyu yerel makinenize bu dizine çalışan bir kopyasını oluşturmak için göz atın.

Kullanma hakkında bilgi almak için **Checkout** Mac için Visual Studio'da özelliği, adımları [bir alt sürüme depoyu ayarı](~/set-up-subversion-repository.md) bölümü.

## <a name="update-solution"></a>Güncelleştirme çözümü

Uzak bir depo kullanırken, diğer kullanıcıların dosyaları, eski çalışma kopyanızı yapmadan değiştiriliyor olabilir olduğunu unutmamak önemlidir. İçinde kapatıldığını çakışmalarını depodan çözümünüze çalışmaya başlamadan önce ve gerçekleştirmeden önce herhangi bir değişiklik çıkarmak için her zaman önermiştir. Değişiklikleri isteyecek şekilde seçin **sürüm denetimi > güncelleştirme çözümü** menü öğesi.

## <a name="review-solution-and-commit"></a>Gözden geçirme çözüm ve yürütme

Dosyalardaki değişiklikler gözden geçirmek için değişiklikleri, nedenlerle, günlük kullanın ve aşağıdaki görüntüde gösterildiği gibi her bir belgenin sekmelerinde birleştirme:

![Sürüm denetimi sekmeleri](media/version-control-vcTabs.png)

Göz atarak bir projedeki tüm değişiklikleri gözden **sürüm denetimi > gözden geçirme çözüm ve yürütme** menü öğesi:

![Review Solution](media/version-control-vcStatus.png)

Bu geri alın, düzeltme eki, oluşturma seçeneğini projenin her bir dosyadaki tüm değişiklikleri görüntüleme izin verir veya uygulayın.

Uzak depoya bir dosyayı Yürüt, yürütme basın..., bir tamamlama iletisi girin ve yürütme düğmesi ile onaylamak için:


![Bir dosya teslim etme](media/version-control-svnCommit.png)

Bu değişiklikler, tüm değişikliklerinizi yeni sürümünü burada oluşturdukları depoya gönderir.
