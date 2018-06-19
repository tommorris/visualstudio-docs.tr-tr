---
title: Hızlı Eylemler, ampuller ve tornavidalar
ms.date: 03/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d413d5b440c39c3603e1e909fb0c4645719f188b
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34064856"
---
# <a name="quick-actions"></a>Hızlı Eylemler

Hızlı Eylemler kolayca düzenleme olanak tanır, oluşturmak veya aksi halde tek bir eylemle kodunu değiştirin. Hızlı Eylemler C# ' ta kullanılabilir [C++](/cpp/ide/writing-and-refactoring-code-cpp)ve Visual Basic kod dosyaları. Bazı eylemler için bir dil özeldir ve diğer tüm diller için geçerlidir.

Hızlı eylemler için kullanılabilir:

- bir kod düzeltme için geçerli bir [Çözümleyicisi kod](../code-quality/roslyn-analyzers-overview.md) kural ihlali
- [gizlemek](../code-quality/use-roslyn-analyzers.md) bir kod Çözümleyicisi Kuralı ihlali
- bir yeniden düzenleme uygulamak (örneğin, [satır içi geçici bir değişken](../ide/reference/inline-temporary-variable.md))
- kod oluşturma (örneğin, [yerel bir değişken tanıtmak](../ide/reference/introduce-local-variable.md))

Ampul kullanarak hızlı Eylemler uygulanabilir ![ampul simgesi](media/light-bulb-icon.png) veya tornavida ![tornavida simgesi](media/screwdriver-icon.png) simgeleri basarak veya **Ctrl** + **.** imlecinizi bir eylem kullanılabilir kod satırında olduğunda. Bir hata ampul görürsünüz ![hata ampul simgesi](media/error-light-bulb-icon.png) belirten bir hata bir kırmızı dalgalı yoktur ve Visual Studio olan bir düzeltme bu hata için kullanılabilir.

Herhangi bir dil için üçüncü tarafların özel tanılama ve öneriler, örneğin bir SDK'ın bir parçası olarak sağlayabilir ve bu kurallara göre Visual Studio ampuller hafif.

## <a name="icons"></a>Simgeler

Hızlı bir eylem kullanılabilir olduğunda görüntülenen simgesini kullanılabilir düzeltme veya yeniden düzenleme türünün bir gösterge sağlar. *Tornavida* ![tornavida simgesi](media/screwdriver-icon.png) gösterir. Bu simgeyi yalnızca kodunu değiştirmek kullanılabilir eylemler vardır, ancak bunları mutlaka kullanmamalısınız. *Sarı ampul* ![ampul simgesi](media/light-bulb-icon.png) simgesi gösterir kullanılabilir eylemler, *gereken* yapmak kodunuzu geliştirmek için. *Hata ampul* ![hata ampul simgesi](media/error-light-bulb-icon.png) simgesi gösterir, kodunuzda hata düzeltmeleri bir eylem yoktur.

## <a name="to-see-a-light-bulb-or-screwdriver"></a>Ampul veya tornavida görmek için

- Bir düzeltme varsa, fare bir hata konumda geldiğinizde ampuller kendiliğinden görünür.

   ![Ampul fare bekleyerek ile](../ide/media/vs2015_lightbulb_hover.png)

- Hızlı bir eylem kullanılabilir kod satırına şapka taşıdığınızda ampuller ve tornavidalar düzenleyicinin sol kenar boşluğunda görünür.

- Tuşuna **Ctrl**+**.** kullanılabilir hızlı Eylemler ve yapan yeniden düzenlemeler listesini görmek için herhangi bir satıra.

## <a name="to-see-potential-fixes"></a>Olası düzeltmeleri görmek için

Her iki yanındaki aşağı oka ampul seçin veya **olası düzeltmeleri göster** kullanılabilir hızlı eylemlerin bir listesini görüntülemek için bağlantı.

![Genişletilmiş ampul](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da kod oluşturma](../ide/code-generation-in-visual-studio.md)
- [Yaygın Hızlı Eylemler](../ide/common-quick-actions.md)
- [Kod stilleri ve hızlı Eylemler](../ide/code-styles-and-quick-actions.md)
- [Yazma ve düzenleme kod (C++)](/cpp/ide/writing-and-refactoring-code-cpp)