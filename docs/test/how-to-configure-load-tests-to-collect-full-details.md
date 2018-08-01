---
title: Yük testi Visual Studio'da için sanal kullanıcı için tüm ayrıntıları toplama
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, virtual user activity chart, configuring
- virtual user activity chart, configuring
ms.assetid: cb22e43b-af4d-4e09-9389-3c3fa00786f7
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 70930a09f01450d59b44678ebd26d7e742af7294
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379631"
---
# <a name="how-to-configure-load-tests-to-collect-full-details-to-enable-virtual-user-activity-in-test-results"></a>Nasıl yapılır: yapılandırma yük testi sonuçlarında sanal kullanıcı etkinliğini etkinleştirmek için tüm ayrıntıları toplamak üzere testleri

Kullanılacak **sanal kullanıcı aktivite grafiği** Yük testiniz için tüm ayrıntıları toplamak üzere yük testinizi yapılandırmanız gerekir. Bunu yapmak için yük testi yapılandırmak için seçin **Tüm Bireysel Ayrıntılar** ayarını **Zamanlama Ayrıntıları Deposu** yük testi ile ilişkili özelliği. Bu modda, yük testinize her test, sayfa ve işlem hakkında ayrıntılı bilgi toplar.

 Bir projeyi Visual Studio Yük testinin önceki bir sürümden yükseltiyorsanız, tam ayrıntılı toplamayı etkinleştirmek için aşağıdaki yordamda adımları kullanın.

 **Tüm Bireysel Ayrıntılar** ayarını **Zamanlama Ayrıntıları Deposu** özelliği aşağıdaki seçeneklerden birine ayarlanabilir:

-   **Tüm Bireysel Ayrıntılar:** toplar ve her test, hareket ve test sırasında verilen sayfa için bireysel zamanlama verilerini depolar.

    > [!NOTE]
    > **Tüm Bireysel Ayrıntılar** seçeneği, yük testi sonuçlarınızda Sanal kullanıcı veri bilgisini etkinleştirmek için seçilmelidir.

-   **Hiçbiri:** herhangi bir zamanlama ayrıntısı toplamaz. Ancak, ortalama değerler hala kullanılabilirdir.

-   **Yalnızca İstatistikler:** bağımsız zamanlama verisini sadece yüzdelik veri depolar. Bu, yer kaynaklarından tasarruf sağlar.

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>Bir yük testi içinde zamanlama ayrıntıları depolama özelliğini yapılandırmak için

1.  Bir yük testi açın **Yük Testi Düzenleyicisi**.

2.  Genişletin **çalıştırma ayarları** düğüm yük testinde.

3.  Örneğin, yapılandırmak istediğiniz çalıştırma ayarlarını seçin **çalıştırma Ayarları1 [etkin]**.

4.  Açık **özellikleri** penceresi. Üzerinde **görünümü** menüsünde **Özellikler penceresi**.

5.  Altında **sonuçları** kategorisi seçin **Zamanlama Ayrıntıları Deposu** özelliğini tıklatın ve **Tüm Bireysel Ayrıntılar**.

     Yapılandırmasını tamamladıktan sonra **Tüm Bireysel Ayrıntılar** ayarını **Zamanlama Ayrıntıları Deposu** özelliğini yükleme çalıştırabilirsiniz görüntülemek ve test **sanal kullanıcı aktivite grafiği**. Daha fazla bilgi için [nasıl yapılır: yük testi sırasında sanal kullanıcıların ne yaptıklarını çözümleme](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [İzlenecek yol: sorunları yalıtmak için sanal kullanıcı aktivite Grafiği'ni kullanma](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)