---
title: Hızlı Eylemler | Microsoft Docs
ms.date: 03/28/2018
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
ms.openlocfilehash: 941980eff8fc2474df9555b326278abdb9b26dac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="quick-actions"></a>Hızlı Eylemler

Hızlı Eylemler kolayca düzenleme olanak tanır, oluşturmak veya aksi halde tek bir eylemle kodunu değiştirin. Hızlı Eylemler C# ' ta kullanılabilir [C++](/cpp/ide/writing-and-refactoring-code-cpp)ve Visual Basic kod dosyaları. Bazı eylemler için bir dil özeldir ve diğer tüm diller için geçerlidir.

Hızlı eylemler için kullanılabilir:

- bir kod düzeltme için geçerli bir [Çözümleyicisi kod](../code-quality/roslyn-analyzers-overview.md) kural ihlali
- [gizlemek](../code-quality/use-roslyn-analyzers.md) bir kod Çözümleyicisi Kuralı ihlali
- bir yeniden düzenleme uygulamak (örneğin, [satır içi geçici bir değişken](../ide/reference/inline-temporary-variable.md))
- kod oluşturma (örneğin, [yerel bir değişken tanıtmak](../ide/reference/introduce-local-variable.md))

Ampul simgesini kullanarak hızlı Eylemler uygulanabilir ![küçük ampul simge](media/vs2015_lightbulbsmall.png), basarak veya **Ctrl**+**.** imlecinizi bir eylem kullanılabilir kod satırında olduğunda. Bir kırmızı dalgalı ve Visual Studio ise ampul sorunu gidermeye yönelik bir öneri sahip görürsünüz. Örneği için kırmızı dalgalı tarafından belirtilen bir hata varsa, düzeltmeleri bu hata için kullanılabilir durumda olduğunda bir ampul görünür.

Herhangi bir dil için üçüncü tarafların özel tanılama ve öneriler, örneğin bir SDK'ın bir parçası olarak sağlayabilir ve bu kurallara göre Visual Studio ampuller hafif.

## <a name="to-see-a-light-bulb"></a>Bir ampul görmek için

1. Çoğu durumda, bir hata içeren satırları şapka taşıdığınızda, fare bir hata noktasında veya düzenleyicinin sol kenar boşluğunda geldiğinizde ampuller kendiliğinden görünür. Kırmızı dalgalı gördüğünüzde, bunun üzerine ampul görüntülenecek gelebilirsiniz. Ayrıca, herhangi bir yere satırda sorunun nerede oluştuğunu gitmek için klavye ve fare kullandığınızda görüntülemek bir ampul neden olabilir.

1. Tuşuna **Ctrl**+**.** Ampul çağırma ve olası listesine doğrudan gitmek için bir satır üzerinde herhangi bir yere giderir.

   ![Ampul fare bekleyerek ile](../ide/media/vs2015_lightbulb_hover.png)

## <a name="to-see-potential-fixes"></a>Olası düzeltmeleri görmek için

Ya da aşağı oka veya olası ampul için uygulayabileceğiniz hızlı eylemlerin bir listesini görüntülemek için bağlantıyı düzeltmeleri Göster'i tıklatın.

![Genişletilmiş ampul](../ide/media/vs2015_lightbulb_hover_expanded.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da kod oluşturma](../ide/code-generation-in-visual-studio.md)
- [Yaygın Hızlı Eylemler](../ide/common-quick-actions.md)
- [Kod stilleri ve hızlı Eylemler](../ide/code-styles-and-quick-actions.md)
- [Kod yazma ve yeniden düzenleme (C++)](/cpp/ide/writing-and-refactoring-code-cpp)