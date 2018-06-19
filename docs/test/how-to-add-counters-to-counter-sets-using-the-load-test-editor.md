---
title: Visual Studio'da Test yük sayaçları sayaç kümelerine sayaç ekleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- counters, counter sets
- counter sets
- load tests, counter sets
ms.assetid: e17d0e71-f982-4fc1-a2df-a1065d37473d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 871ba69d088e58ac1d662f254c72c406c79f86fd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31967891"
---
# <a name="how-to-add-counters-to-counter-sets-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini Kullanarak Sayaç Kümelerine Sayaç Ekleme

İle bir yük testi oluşturduğunuzda **Yük Testi Sihirbazı**, başlangıç sayaç kümesini ekleyin. Bu, yük testi için önceden tanımlanmış sayaç kümeleri kümesi sunar. Daha fazla bilgi için bkz: [sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testinde belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

> [!NOTE]
> Yük testleri Uzak makinelerde dağıtılmışsa, denetleyici ve aracı sayaçları denetleyici ve aracı eşlenen sayaç. Yükleme testinizde uzak makineleri kullanma hakkında daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).


 Sayaçlarınızın içinde yönetmek **Yük Testi Düzenleyicisi**. Teste zaten ekli sayaç kümelerini görünür **sayaç kümelerini** yük testi düğümü. Bir yük testi oluşturduğunuzda, varolan sayaç kümelerine yeni sayaçlar ekleyebilirsiniz.

## <a name="to-add-counters-to-a-counter-set"></a>Bir sayaç kümesine sayaç eklemek için

1.  Bir yük testi açın.

2.  Genişletme **sayaç kümelerini** düğümü. Yük testi eklenen tüm sayaç kümeleri görünür.

    > [!NOTE]
    > Yük testi hiyerarşi ağacı de içeren **çalıştırma ayarları** düğümü. Bu düğümü içeren **sayaç kümesi eşlemeleri** tüm bilgisayarlar ve bu bilgisayarlara eşlenen sayaç kümelerini gösterir düğümü.

3.  Var olan bir sayaç kümesini sağ tıklayın ve ardından **Sayaç Ekle**.

     **Performans sayaçlarını Çek** iletişim kutusu görüntülenir.

4.  İçinde **bilgisayar** açılan eşlemek istediğiniz bilgisayarın adını yazın. Alternatif olarak, bilgisayarlardan biri aşağı açılan listeden seçin.

    > [!NOTE]
    > Performans verileri toplanmadan önce sayaç kümelerini bir bilgisayara eşlenmesi gerekir çünkü performans verilerini toplamak bir bilgisayar belirtmeniz gerekir.

5.  Seçin bir **performans kategorisi** performans veri sayacı kategorilerini filtrelemek için. Performans sayaçlarını seçmek verilerden iki sütunu görürsünüz.

    > [!NOTE]
    > Bazı sayaç kategorileri bir örnek de seçmenizi gerektirir. Örneğin, bir SQL sayaç seçerseniz, birden fazla hedef bilgisayarda yüklü SQL örneği olabileceğinden bir SQL örneğini seçmeniz gerekir.

6.  Bir sayacı ve özel sayaç kümenize eklemek için bir örnek seçin.

     \- veya -

     Seçin **tüm sayaçları** radyo düğmesi kullanılabilir tüm sayaçları seçin.

7.  Seçin **Tamam**.

    > [!NOTE]
    > Var olan bir sayacı veya sayaç kategorisini sağ tıklayarak seçip, kopyala'yı seçip ardından onu farklı sayaç kümesi düğümüne yapıştırarak sayaçlar eklemek de mümkündür. Kopyalanan ancak ihtiyaç olmayan fazladan sayaçlar silinebilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)