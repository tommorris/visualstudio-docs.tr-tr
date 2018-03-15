---
title: "Nasıl yapılır: bir kod çözümleme iade ilkesi ile Bakımı yapılabilir kodu zorlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7b1a6d953128317e89672d5d9b175ce7acc1b63f
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Nasıl yapılır: bir kod çözümleme iade ilkesi ile Bakımı yapılabilir kodu zorlama

Geliştiriciler karmaşıklığı ve bakımı kendi kodunun ölçmek için kod ölçümleri aracını kullanabilirsiniz, ancak bir iade ilkesi bir parçası olarak kod ölçümleri çağrılamıyor. Ancak, kodunuzun kod ölçümleri standartlar ile uyumluluğun doğrulayın kod çözümleme kurallarını etkinleştirin ve iade ilkeleri aracılığıyla kuralları zorlayın. Kod ölçümleri hakkında daha fazla bilgi için bkz: [kod ölçüm değerleri](../code-quality/code-metrics-values.md).

Derinlik, devralma, sınıf Kuplaj, bakım dizin ve karmaşıklık kurallarını bir kod çözümleme iade ilkesi ile Bakımı yapılabilir kodu zorlama etkinleştirebilirsiniz. Bu kurallar dört kod çözümleme İlkesi Düzenleyicisi'nde "Bakım kuralları" kategorisi altında bulunur.

Team Foundation sürüm denetimi yöneticileri kod analizi Bakımı kurallarını iade ilkesi gereksinimleri ekleyebilirsiniz. Bu kod analizi iade başlatmadan önce bu kural değişikliklere dayalı çalıştırmak geliştiricilere ilkeleri gerektiren iade.

## <a name="to-open-the-code-analysis-policy-editor"></a>Kod çözümleme İlkesi Düzenleyicisi'ni açmak için

1. İçinde **Takım Gezgini**, takım projesine sağ tıklayın, **takım projesi ayarları**ve ardından **kaynak denetimi**.

     **Kaynak denetimi** iletişim kutusu görüntülenir.

2. Üzerinde **iade ilkesi** sekmesine ve tıklayın **Ekle**.

     **İade İlkesi Ekle** iletişim kutusu görüntülenir.

3. İçinde **iade ilkesi** listesinde **Kod Analizi** onay kutusunu işaretleyin ve ardından **Tamam**.

     **Kod analiz İlkesi Düzenleyicisi'ni** iletişim kutusu görüntülenir.

## <a name="to-enable-code-analysis-maintainability-rules"></a>Kod çözümleme Bakımı kurallarını etkinleştirmek için

1. İçinde **kod analiz İlkesi Düzenleyicisi'ni** iletişim kutusunda **kural ayarları**, genişletin **Bakımı kuralları** düğümü.

2. Aşağıdaki kuralları için onay kutularını seçin:

    -   Devralma derinliği: **CA1501 AvoidExcessiveInheritance** -eşiği: fazla 5 düzey derinliğinde uyarı

    -   Karmaşıklık: **CA1502 AvoidExcessiveComplexity** -eşiği: birden fazla 25 uyarı

    -   Bakım dizini: **CA1505 AvoidUnmaintainableCode** -eşiği: az 20 uyarı

    -   Sınıf bağ: **CA1506 AvoidExcessiveClassCoupling** -eşiği: birden fazla sınıf için 80 ve birden fazla 30 bir yöntem için uyarı

    Ayrıca, başarılı bir derlemede önlemek için bir kuralı ihlali istiyorsanız seçin **uyarı bir hata olarak kabul** kural açıklaması yanındaki onay kutusunu.

3. **Tamam**'ı tıklatın. Yeni iade ilkesi şimdi gelecekteki onay bileşenleri için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod ölçüm değerleri](../code-quality/code-metrics-values.md)
- [Oluşturma ve kod çözümleme iade ilkelerini kullanma](../code-quality/creating-and-using-code-analysis-check-in-policies.md)