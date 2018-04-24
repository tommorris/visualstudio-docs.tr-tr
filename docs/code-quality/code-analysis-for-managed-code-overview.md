---
title: Visual Studio'da yönetilen kod için Kod Analizi
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 727a63d122871ff452365eea66e9a6e63a7c67b0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="overview-of-code-analysis-for-managed-code"></a>Yönetilen kod için Kod Analizine genel bakış

Visual Studio 2017 iki yolla yönetilen kodu analiz eder: eski ile *FxCop* statik çözümleme Yönetilen derlemeler ve .NET derleyici platformuyla *çözümleyiciler*. Bu konu FxCop statik kod analizi kapsar. .NET derleme platformu Çözümleyicileri kullanarak kod çözümleme hakkında daha fazla bilgi için bkz: [genel bakış, Roslyn çözümleyiciler](../code-quality/roslyn-analyzers-overview.md).

Yönetilen kod için Kod Analizi Yönetilen derlemeler analiz eder ve İleri Microsoft .NET Framework tasarım yönergeleri Tasarım Kuralları ve programlama ihlalleri gibi derlemeler hakkında bilgi raporlar.

Çözümleme aracı bir Çözümleme sırasında uyarı iletileri olarak gerçekleştirdiği denetimleri temsil eder. Uyarı iletilerini programlama ve tasarım ilgili sorunları belirlemek ve sorunun nasıl çözüleceğini olası, sağlar bilgilerini olduğunda.

## <a name="ide-integrated-development-environment-integration"></a>IDE (tümleşik geliştirme ortamı) tümleştirme

Kod çözümleme projenizde el ile veya otomatik olarak çalıştırabilirsiniz.

Kod çözümleme bir projeyi derleme her zaman çalıştırmak için seçin **etkinleştirmek Kod Analizi derlemede** projenin özellik sayfasındaki. Daha fazla bilgi için bkz: [nasıl yapılır: devre dışı otomatik kod analizini etkinleştirme ve](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

Kod çözümleme el ile bir proje üzerinde çalıştırmak için menü çubuğundan seçin **Çözümle** > **Kod Analizi çalıştırmak** > **çalıştırmak kod çözümleme \<proje >**.

## <a name="rule-sets"></a>Kural kümeleri

Yönetilen kod için Kod Analizi kurallarını halinde gruplandırılır [kural kümeleri](../code-quality/using-rule-sets-to-group-code-analysis-rules.md). Microsoft Standart kural kümeleri birini kullanabilir ya da yapabilecekleriniz [bir özel kural kümesi oluşturma](../code-quality/how-to-create-a-custom-rule-set.md) belirli bir gereksinimi karşılamak için.

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
> Bir proje için Visual Studio 2017 geçirirseniz, aniden çok sayıda kod analizi uyarıları karşılaştığı. Uyarıları gidermek ve hemen üretken olmak hazır değilseniz yapabilecekleriniz *temel* projenizin çözümleme durumu. Gelen **Çözümle** menüsünde, select **Kod Analizi çalıştırmak ve bastırmak etkin sorunlar**.

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>Kod çözümleme iade ilkesi bir parçası olarak çalıştır

Kuruluş olarak, tüm iadeler belirli ilkeleri karşılamak gerektiren isteyebilirsiniz. Özellikle, bu ilkeler takip ettiğinizden emin olmak istiyoruz:

- İade edildi kod derleme hatalar yoktur.

- Kod çözümleme en son yapı bir parçası olarak çalıştırılır.

Bu iade ilkelerini belirterek gerçekleştirebilirsiniz. Daha fazla bilgi için bkz: [takım projesi iade ilkeleriyle kod kalitesini arttırma](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md).

## <a name="team-build-integration"></a>Team derleme tümleştirmesi

Çözümleme aracı yapılandırma işleminin bir parçası olarak çalıştırmak için tümleşik yapı sistem özelliklerini kullanabilirsiniz. Daha fazla bilgi için bkz: [oluşturmak ve (VSTS) sürüm](/vsts/build-release/index).

## <a name="see-also"></a>Ayrıca bkz.

- [Roslyn çözümleyiciler genel bakış](../code-quality/roslyn-analyzers-overview.md)
- [Kod Analizi Kurallarını Gruplandırmak için Kural Kümeleri Kullanma](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [Nasıl yapılır: etkinleştirme ve devre dışı otomatik kod çözümleme](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
