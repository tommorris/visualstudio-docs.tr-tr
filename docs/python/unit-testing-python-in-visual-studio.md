---
title: "Birim testi Visual Studio'da Python için | Microsoft Docs"
description: "Visual Studio'da Python kodu için test etme birimi bulmak için Test Gezgini özelliklerden tam olarak yararlanmak için ayarlama, çalıştırın ve testlerin hata ayıklama."
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 55b99e2f572b075c1e9ab1658c8a02b3fdd5ea88
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="setting-up-unit-testing-for-python-code"></a>Birim testi için Python kodu ayarlama

Birim testleri, bir uygulama, genellikle yalıtılmış işlevleri, sınıflar ve benzeri diğer kod birimleri test kod parçalarıdır. Bir uygulamanın tüm birim testleri geçtiğinde, alt düzey işlevselliğini doğru olduğunu en az güvenebilirsiniz.

Python birim testleri bir program tasarlarken senaryoları doğrulamak için yaygın olarak kullanır. Visual Studio'da Python desteği, keşfetme, yürütme ve birim testleri geliştirme sürecinizi bağlamında testleri ayrı olarak çalıştırmaya gerek kalmadan hata ayıklama içerir.

Bu makalede, Visual Studio'da Python ile test etme özelliklerini birim kısa bir özeti sağlanmaktadır. Birim testi genel hakkında daha fazla bilgi için bkz: [birim testi kodunuzu](../test/unit-test-your-code.md).

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Testing-Python-hb46k6LWE_405918567) Python (2 m 31s) sınama birim üzerinde. |

## <a name="discovering-and-viewing-tests"></a>Keşfetmek ve testleri görüntüleme

Kurala göre Visual Studio testleri tanımlayan olan adları başlayan ile yöntemleri olarak `test`. Bu davranış görmek için aşağıdakileri yapın:

1. Açık bir [Python proje](managing-python-projects-in-visual-studio.md) Visual Studio'da yüklenen, projenize sağ tıklayın, **Ekle > Yeni öğe...** seçeneğini belirleyip **Python birim testi** arkasından **Ekle**.

1. Bu eylem oluşturur bir `test1.py` standart alır kod dosyasıyla `unittest` modülü, bir test sınıfından türetilen `unittest.TestCase`ve çağırır `unittest.main()` betik doğrudan çalıştırırsanız:

    ```python
    import unittest

    class Test_test1(unittest.TestCase):
        def test_A(self):
            self.fail("Not implemented")

    if __name__ == '__main__':
        unittest.main()
    ```

1. Gerekirse, dosyayı kaydedin ve ardından Test Gezgini ile açmak **Test > Windows > Test Gezgini** menü komutu.

1. Test Gezgini projeniz testleri için arar ve aşağıda gösterildiği gibi görüntüler. Bir test çift kendi kaynak dosyasını açar.

    ![Test Gezgini gösteren varsayılan test_A](media/unit-test-A.png)

1. Daha fazla test projenize eklemek gibi araç çubuğundaki menüsü grubunu kullanarak Test Gezgini görünümünde düzenleyebilirsiniz:

    ![Araç çubuğu menü testleri Explorer grupla](media/unit-test-group-menu.png)

1. Ayrıca, testleri ada göre filtrelemek için arama alanı metin de girebilirsiniz.

Daha fazla bilgi için `unittest` modülü ve testleri, yazma bkz [Python 2.7 belgelerine](https://docs.python.org/2/library/unittest.html) veya [Python 3.4 belgelerine](https://docs.python.org/3/library/unittest.html) (python.org).

## <a name="running-tests"></a>Testleri çalıştırma

Test Gezgini içinde çeşitli şekillerde testlerinde çalıştırabilirsiniz:

- **Tümünü Çalıştır** açıkça (tabi filtreleri) gösterilen tüm testleri çalıştırır.
- **Çalıştır...**  menü komutları başarısız, geçirilen veya çalışmadı testler, bir grup olarak sağlar.
- Bir veya daha fazla sınama seçebileceğiniz sağ tıklayın ve ardından seçin **seçili Testleri Çalıştır**.

Arka planda testleri çalıştırın ve tamamladıkça Test Gezgini güncelleştirmeleri her testin durumu:

- Geçirme testler yeşil rick ve testi çalıştırmak için geçen süre gösterilmektedir:

    ![Durum geçirilen test_A](media/unit-test-A-pass.png)

- Başarısız testleri Göster kırmızı çarpı ile bir **çıkış** konsol çıktısı gösterilmektedir bağlantı ve `unittest` test çalışması çıktı:

    ![test_A durumu başarısız oldu](media/unit-test-A-fail.png)

    ![test_A şu nedenle başarısız oldu](media/unit-test-A-fail-reason.png)

## <a name="debugging-tests"></a>Hata ayıklama testleri

Birim testleri kod parçalarını olduğundan, başka bir kod gibi hatalar tabidir ve bazen bir hata ayıklayıcıda çalıştırılması gerekir. Hata ayıklayıcıda kesme noktalarını ayarlayın, değişkenleri inceleyin ve kod üzerinden adım. Visual Studio tanılama araçları için birim testleri de sağlar.

Hata ayıklamayı başlatma, kodunuzda ilk bir kesme noktası belirleyerek sonra test (veya bir seçim) Test Explorer'da sağ tıklatın ve seçin **seçili Testlerde Hata Ayıkla**. Uygulama kodu için olduğu gibi visual Studio Python hata ayıklayıcı başlatır.

![Bir test hata ayıklama](media/unit-test-debugging.png)

De kullanabilirsiniz **Seçili testler için kod kapsamı analiz** ve **profil Test** Visual Studio sürümünüze bağlı komutları (bkz [özellikleri matris](overview-of-python-tools-for-visual-studio.md#features-matrix)).

### <a name="known-issues"></a>Bilinen Sorunlar

- Hata ayıklama başlatılırken, Visual Studio hata ayıklamayı durdurmak ve başlatmak için görünür ve yeniden başlatın. Bu davranış beklenir.
- Birden çok sınama hata ayıklarken, her biri bağımsız olarak, hangi hata ayıklama oturumu keser çalıştırılır.
- Visual Studio hata ayıklama sırasında bir test başlatmak zaman zaman başarısız olur. Normalde, test yeniden hata ayıklama girişiminde başarılı olur.
- Hata ayıklama sırasında bir testine dışında adıma mümkündür `unittest` uygulaması. Normalde, sonraki adım programı ve hata ayıklamayı Durdur sonuna kadar çalışır.