---
title: Visual Studio'da Test yük için düşünme sürelerini | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, think times
- load tests, adding delays
- load tests, changing think times
ms.assetid: 8e03bee5-ab7b-4b40-9497-9dbe91ccb90e
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: e67e514b3b977e50be553704ec1997ce7476f045
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="edit-think-times-to-simulate-website-human-interaction-delays-in-load-tests-scenarios"></a>Yük testleri senaryolarında Web sitesi insan etkileşimi gecikmelerini benzetmek için Düşünme zamanlarını düzenleme

Düşünme süreleri, insanların bir Web sitesi ile etkileşim arasında beklemesine neden olan insan davranışını benzetmek için kullanılır. Web performans testinde istekleri arasında ve bir yük testi senaryosunda test yinelemeleri arasındaki düşünme sürelerini oluşur. Bir yük testinde düşünme sürelerini kullanarak daha kesin yükleme benzetimleri oluşturmada faydalı olabilir. Düşünme sürelerini kullanıldığını ya yükleme testlerinde kullanılıp değiştirebilirsiniz. Yük Testi Düzenleyicisi'nde testlerinde düşünme süreleri Yükleme kullanılır olup olmadığını, değiştirin.

 *Düşünme profili* bir yük testi senaryosunda uygulandığı bir ayardır. Düşünme sürelerinin kaydedilip kaydedilmediğini tek tek Web performans testleri yük testi sırasında kullanılan ayar belirler. Kullanmak istiyorsanız, düşünme sürelerini bazı Web performans testlerinde ancak bazı durumlarda, bunları farklı senaryolarda yerleştirmelisiniz. Senaryolar hakkında daha fazla bilgi için bkz: [yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md).

 Başlangıçta, Yeni Yük Testi Sihirbazı'nı kullanarak yük testi oluşturduğunuzda, yük testlerinde düşünme sürelerini kullanıp kullanmayacağınızı ayarlarsınız. Daha fazla bilgi için bkz: [yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md).

 Düşünme profili seçenekleri aşağıdaki listede açıklanmaktadır:

**Kapalı**

Düşünme sürelerini göz ardı edilir. Yoğun bir şekilde Web sunucunuz stres testi uygulamak için en fazla yük oluşturmak istediğinizde bu ayarı kullanın. Bir Web sunucusu ile daha gerçekçi kullanıcı etkileşimleri oluşturulmaya çalışılırken kullanmayın.

**üzerinde**

Web performans testinde tam olarak kaydedilmiş gibi Düşünme süreleri kullanılır. Tam olarak kaydedildiği gibi Web performans testleri çalıştıran birden çok kullanıcıyı taklit eder. Bir yük testi benzetim çünkü aynı kullanarak birden çok kullanıcı zaman eşitlenmiş sanal kullanıcıların doğal olmayan yük düzeni oluşturabilirsiniz düşünün.

**Normal dağıtım**

Düşünme süreleri kullanılır, ancak normal eğri üzerinde değişir. İstekler arasında düşünme sürelerini biraz değiştirerek sanal kullanıcıların daha gerçekçi benzetimini sağlar.

> [!NOTE]
> Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

## <a name="changing-the-think-profile"></a>Düşünme profilini değiştirme

### <a name="to-change-a-think-profile-in-a-load-test-scenario"></a>Yük testi senaryosunda bir Düşünme profilini değiştirmek için

1.  Web performans ve yük projeyi test, bir yük testi açın.

2.  İçinde **Yük Testi Düzenleyicisi**, değiştirmek istediğiniz senaryo düğümünü seçin **Düşünme profili**. **Düşünme profili** Özellikler penceresinde görüntülenir. Özellikler penceresini görüntülemek için F4 tuşuna basın.

3.  Değişiklik **Düşünme profili** Özellikleri penceresinde özelliği.

4.  Özellikleri değiştirme bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni Düşünme profili ile yük testlerini çalıştırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)