---
title: "Kod çözümleme için yönetilen kod genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 5d30f84194ef7a48de106698c9ad4569e947923c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="code-analysis-for-managed-code-overview"></a>Yönetilen kod genel bakış için Kod Analizi

Yönetilen kod için Kod Analizi Yönetilen derlemeler analiz eder ve İleri Microsoft .NET Framework tasarım yönergeleri Tasarım Kuralları ve programlama ihlalleri gibi derlemeler hakkında bilgi raporlar.

Çözümleme aracı bir Çözümleme sırasında uyarı iletileri olarak gerçekleştirdiği denetimleri temsil eder. Uyarı iletilerini programlama ve tasarım ilgili sorunları belirlemek ve sorunun nasıl çözüleceğini olası, sağlar bilgilerini olduğunda.

## <a name="ide-integrated-development-environment-integration"></a>IDE (tümleşik geliştirme ortamı) tümleştirme

Kod çözümleme projenizde el ile veya otomatik olarak çalıştırabilirsiniz.

Kod çözümleme bir projeyi derleme her zaman çalıştırmak için seçin **etkinleştirmek Kod Analizi derlemede** projenin özellik sayfasındaki. Daha fazla bilgi için bkz: [nasıl yapılır: devre dışı otomatik kod analizini etkinleştirme ve](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

Kod çözümleme el ile bir proje üzerinde çalıştırmak için menü çubuğundan seçin **Çözümle** > **Kod Analizi çalıştırmak** > **çalıştırmak kod çözümleme <project>** . Daha fazla bilgi için bkz: [nasıl yapılır: devre dışı otomatik kod analizini etkinleştirme ve](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

## <a name="rule-sets"></a>Kural kümeleri

Yönetilen kod için Kod Analizi kurallarını halinde gruplandırılır *kural kümeleri*. Microsoft Standart kural kümeleri birini kullanabilir veya belirli bir gereksinimi karşılamak için özel bir kural oluşturabilirsiniz. Daha fazla bilgi için bkz: [kod çözümleme kurallarını gruplandırmak için kural kümeleri kullanma](../code-quality/using-rule-sets-to-group-code-analysis-rules.md).

## <a name="suppress-warnings"></a>Uyarıları bastırma

Genellikle, bir uyarı uygulanabilir olmayan olduğunu belirtmek kullanışlıdır. Bu Geliştirici ve daha sonra kodu gözden geçirebilirsiniz diğer kişilerin bir uyarı araştırılan ve sonra da gizlenen veya yoksayıldı olduğunu bildirir.

Kaynak gizleme uyarılar özel özniteliklere uygulanır. Bir uyarıyı gizlemek için öznitelik Ekle `SuppressMessage` aşağıdaki örnekte gösterildiği gibi kaynak koduna:

```csharp
[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

Daha fazla bilgi için bkz: [uyarıları bastırma](../code-quality/in-source-suppression-overview.md).

> [!NOTE]
> Bir proje için Visual Studio 2017 geçirirseniz, aniden zorlamayı bir kod çözümleme uyarıları sayısıyla karşılaştığı. Uyarıları gidermek ve Kod Analizi geçici olarak devre dışı istediğiniz hazır değilseniz, proje özellik sayfalarını açın (**proje** > ***proje* özellikler...** ) ve Git **Kod Analizi** sekmesi. Seçimini **etkinleştirmek Kod Analizi derlemede**ve projenizi yeniden derleyin. Alternatif olarak, farklı, daha küçük kural kodu çalıştırmak için kümesini seçebilirsiniz. Kod çözümleme uyarıları gidermek hazır olduğunuzda geri üzerinde açmayı unutmayın.

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>Kod çözümleme iade ilkesi bir parçası olarak çalıştır

Kuruluş olarak, tüm iadeler belirli ilkeleri karşılamak gerektiren isteyebilirsiniz. Özellikle, bu ilkeler takip ettiğinizden emin olmak istiyoruz:

- İade edildi kod derleme hatalar yoktur.

- Kod çözümleme en son yapı bir parçası olarak çalıştırılır.

Bu iade ilkelerini belirterek gerçekleştirebilirsiniz. Daha fazla bilgi için bkz: [takım projesi iade ilkeleriyle kod kalitesini arttırma](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md).

## <a name="team-build-integration"></a>Team derleme tümleştirmesi

Çözümleme aracı yapılandırma işleminin bir parçası olarak çalıştırmak için tümleşik yapı sistem özelliklerini kullanabilirsiniz. Daha fazla bilgi için bkz: [oluşturmak ve (VSTS) sürüm](/vsts/build-release/index).

## <a name="see-also"></a>Ayrıca bkz.

[Kod çözümleme kurallarını gruplandırmak için kural kullanarak ayarlar](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)   
[Nasıl yapılır: etkinleştirme ve devre dışı otomatik kod çözümleme](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
