---
title: 'Nasıl yapılır: Standart Kod Çözümleme İade İlkeleri Oluşturma veya Güncelleme'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.policyeditor
helpviewer_keywords:
- code analysis, migrating check-in policy
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eb0642828daa96d7904d4e4bb967afc5f1c563d9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-or-update-standard-code-analysis-check-in-policies"></a>Nasıl yapılır: Standart Kod Çözümleme İade İlkeleri Oluşturma veya Güncelleme

Kod çözümleme İade İlkesi kullanarak kod analizi takım projesinde tüm kod projelerde çalıştırılması gerektirebilir. Kod çözümleme gerektiren kod temeli denetlenir kod kalitesini iyileştirebilir.

> [!NOTE]
> Bu özellik yalnızca Team Foundation Server kullanıyorsanız kullanılabilir.

Kod çözümleme iade ilkeleri takım projesi ayarlarında belirlenir ve her takım projesi kod projesinde uygulanır. Kod çözümleme çalıştırır ve kod projesi için proje (.xxproj) dosyasında kodu projeleri için yapılandırılır. Kod çözümleme çalıştırır yerel bilgisayarda gerçekleştirilir. Takım projesi ayarlarını kurallarında bir kod çözümleme iade ilkesi etkinleştirdiğinizde, son kullanıcıların düzenlemeden sonra iade edilmesi için bir kod proje dosyalarında derlenmiş ve çalıştıran bir kod analizi, en azından içeren bilgisayarda gerçekleştirilmelidir burada c değişiklikleri yapıldı.

- Yönetilen kod için iade ilkesi belirterek ayarladığınız bir *kural kümesi* , bir alt kümesini kod çözümleme kurallarını içerir.

- C/C++ kodu için iade ilkesi tüm kod çözümleme kurallarını çalıştırmasını gerektirir. Takım projenizin kod projeler için belirli kurallar devre dışı bırakmak için ön işlemci yönergeleri ekleyebilirsiniz.

Yönetilen kod için bir ilke belirttikten sonra takım üyeleri kod projeleri takım projesi ilke ayarları için kod çözümleme ayarlarını eşitleyebilirsiniz.

### <a name="to-open-the-check-in-policy-editor"></a>İade İlkesi Düzenleyicisi'ni açmak için

1. Takım Gezgini'nde Takım Proje adına sağ tıklayın, fareyle **takım projesi ayarları**ve ardından **kaynak denetimi**.

1. İçinde **kaynak denetimi** iletişim kutusunda **iade ilkesi** sekmesi.

1. Aşağıdakilerden birini yapın:

    - Tıklatın **Ekle** yeni bir iade ilkesi oluşturmak için.

    - Varolan çift **Kod Analizi** öğesi **ilke türü** ilkeyi değiştirmek için liste.

### <a name="to-set-policy-options"></a>İlke seçeneklerini ayarlamak için

Seçin veya aşağıdaki seçenekleri temizleyin:

    |Seçenek|Açıklama|
    |------------|-----------------|
    |**Yalnızca geçerli çözümün bir parçası olan dosyaları içerecek şekilde iade uygulayın.**|Kod çözümleme yalnızca çözüm ve proje yapılandırma dosyalarında belirtilen dosyaları çalıştırabilirsiniz. Bu ilke bir çözümün bir parçası olan tüm kod analiz edilir güvence altına alır.|
    |**C/C++ Kod Analizi zorla (/ analyze)**|Tüm C veya C++ projeleri ile oluşturulması gerekir / analyze derleyici seçeneği Kod Analizi iade edilmeden önce çalıştırın.|
    |**Yönetilen kod için Kod Analizi zorla**|Tüm yönetilen projeleri Kod Analizi çalıştırmak ve iade edilmeden önce yapı gerektirir.|

### <a name="to-specify-a-managed-rule-set"></a>Yönetilen kural kümesini belirtmek için

- Gelen **bu kural kümesini çalıştırmak** listesinde, aşağıdaki yöntemlerden birini kullanın:

    - Bir Microsoft standart bir kural kümesi seçin.

    - Özel bir kural kümesini seçmek için tıklatın  **\<... kaynak denetiminden kural kümesi seçin >** ve kural kaynak denetimi tarayıcıda kümesi sürüm denetim yolunu yazın. Sürüm denetimi yolu sözdizimi şöyledir:

    - **$/** `TeamProjectName` **/** `VersionControlPath`

    - Oluşturma ve iade özel ilke kuralı uygulama hakkında daha fazla bilgi için bkz: [yönetilen kod için uygulamaya özel iade ilkelerini](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kod Çözümleme İade İlkeleri Oluşturma ve Kullanma](../code-quality/creating-and-using-code-analysis-check-in-policies.md)