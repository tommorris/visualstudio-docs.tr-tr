---
title: "Nasıl yapılır: oluştur veya güncelleştir standart kod çözümleme iade ilkeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.policyeditor
helpviewer_keywords: code analysis, migrating check-in policy
ms.assetid: 458eb3b8-bb5e-4056-82b7-7079ce9c4089
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6396b698a5f4d2602c9969d6cab0422832b3e6dc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-or-update-standard-code-analysis-check-in-policies"></a>Nasıl yapılır: Standart Kod Çözümleme İade İlkeleri Oluşturma veya Güncelleme
Kod çözümleme İade İlkesi kullanarak kod analizi takım projesinde tüm kod projelerde çalıştırılması gerektirebilir. Kod çözümleme gerektiren kod temeli denetlenir kod kalitesini iyileştirebilir.  
  
> [!NOTE]
>  Bu özellik yalnızca Team Foundation Server kullanıyorsanız kullanılabilir.  
  
 Kod çözümleme iade ilkeleri takım projesi ayarlarında belirlenir ve her takım projesi kod projesinde uygulanır. Kod çözümleme çalıştırır ve kod projesi için proje (.xxproj) dosyasında kodu projeleri için yapılandırılır. Kod çözümleme çalıştırır yerel bilgisayarda gerçekleştirilir. Takım projesi ayarlarını kurallarında bir kod çözümleme iade ilkesi etkinleştirdiğinizde, son kullanıcıların düzenlemeden sonra iade edilmesi için bir kod proje dosyalarında derlenmiş ve çalıştıran bir kod analizi, en azından içeren bilgisayarda gerçekleştirilmelidir burada c değişiklikleri yapıldı.  
  
-   Yönetilen kod için iade ilkesi belirterek ayarladığınız bir *kural kümesi* , bir alt kümesini kod çözümleme kurallarını içerir.  
  
-   C/C++ kodu için iade ilkesi tüm kod çözümleme kurallarını çalıştırmasını gerektirir. Takım projenizin kod projeler için belirli kurallar devre dışı bırakmak için ön işlemci yönergeleri ekleyebilirsiniz.  
  
 Yönetilen kod için bir ilke belirttikten sonra takım üyeleri kod projeleri takım projesi ilke ayarları için kod çözümleme ayarlarını eşitleyebilirsiniz.  
  
### <a name="to-open-the-check-in-policy-editor"></a>İade İlkesi Düzenleyicisi'ni açmak için  
  
1.  Takım Gezgini'nde Takım Proje adına sağ tıklayın, fareyle **takım projesi ayarları**ve ardından **kaynak denetimi**.  
  
2.  İçinde **kaynak denetimi** iletişim kutusunda **iade ilkesi** sekmesi.  
  
3.  Aşağıdakilerden birini yapın:  
  
    -   Tıklatın **Ekle** yeni bir iade ilkesi oluşturmak için.  
  
    -   Varolan çift **Kod Analizi** öğesi **ilke türü** ilkeyi değiştirmek için liste.  
  
### <a name="to-set-policy-options"></a>İlke seçeneklerini ayarlamak için  
  
-   Seçin veya aşağıdaki seçenekleri temizleyin:  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |**Yalnızca geçerli çözümün bir parçası olan dosyaları içerecek şekilde iade uygulayın.**|Kod çözümleme yalnızca çözüm ve proje yapılandırma dosyalarında belirtilen dosyaları çalıştırabilirsiniz. Bu ilke bir çözümün bir parçası olan tüm kod analiz edilir güvence altına alır.|  
    |**C/C++ Kod Analizi zorla (/ analyze)**|Tüm C veya C++ projeleri ile oluşturulması gerekir / analyze derleyici seçeneği Kod Analizi iade edilmeden önce çalıştırın.|  
    |**Yönetilen kod için Kod Analizi zorla**|Tüm yönetilen projeleri Kod Analizi çalıştırmak ve iade edilmeden önce yapı gerektirir.|  
  
-  
  
### <a name="to-specify-a-managed-rule-set"></a>Yönetilen kural kümesini belirtmek için  
  
-   Gelen **bu kural kümesini çalıştırmak** listesinde, aşağıdaki yöntemlerden birini kullanın:  
  
    -   Bir Microsoft standart bir kural kümesi seçin.  
  
    -   Özel bir kural kümesini seçmek için tıklatın  **\<... kaynak denetiminden kural kümesi seçin >**ve kural kaynak denetimi tarayıcıda kümesi sürüm denetim yolunu yazın. Sürüm denetimi yolu sözdizimi şöyledir:  
  
    -   **$/** `TeamProjectName` **/** `VersionControlPath`  
  
    -   Oluşturma ve iade özel ilke kuralı uygulama hakkında daha fazla bilgi için bkz: [yönetilen kod için uygulamaya özel iade ilkelerini](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Oluşturma ve kod çözümleme iade ilkelerini kullanma](../code-quality/creating-and-using-code-analysis-check-in-policies.md)