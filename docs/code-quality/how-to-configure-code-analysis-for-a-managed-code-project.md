---
title: Visual Studio'da kod çözümlemesini yapılandırma
ms.date: 04/04/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.csvb
- vs.codeanalysis.propertypages.solution
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 66faf26170e1e102ccbaffcb74334bdd20e4d8ae
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>Nasıl yapılır: Yönetilen Kod Projesi İçin Kod Çözümlemesini Yapılandırma

Visual Studio'da Kod Analizi listesinden seçebilirsiniz *kural kümeleri* yönetilen kod projesi için uygulanacak. Varsayılan kural kümesi *Microsoft Minimum önerilen kurallar*. Başka bir kural bir proje veya bir çözümdeki tüm projeleri kümesi uygulayabilirsiniz.

> [!TIP]
> Bir kural kümesini ASP.NET Web uygulamaları için yapılandırma hakkında daha fazla bilgi için bkz: [nasıl yapılır: ASP.NET Web uygulaması için Kod Analizi yapılandırma](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md).

## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>Bir kural yapılandırmak için .NET Framework projesi için ayarlayın

1. Açık **Kod Analizi** proje özellik sayfalarını sekmesinde. Bunu aşağıdaki yollardan biriyle yapabilirsiniz:

   - İçinde **Çözüm Gezgini**, projeyi seçin. Menü çubuğunda seçin **Çözümle** > **yapılandırma Kod Analizi** > **için \<projectname >**.

   - ' Nde projeye sağ **Çözüm Gezgini** seçip **özellikleri**ve ardından **Kod Analizi** sekmesi.

1. İçinde **yapılandırma** ve **Platform** listeleri, derleme yapılandırmasını ve hedef platformu seçin.

1. Proje seçilen yapılandırma kullanılarak oluşturulmuştur her zaman Kod Analizi çalıştırmak için seçin **etkinleştirmek Kod Analizi derlemede** onay kutusu. Ayrıca Kod Analizi el ile seçerek çalıştırabilirsiniz **Çözümle** > **Kod Analizi çalıştırmak** > **çalıştırmak kod çözümleme \<projectname >**.

1. Varsayılan olarak, Kod Analizi uyarıları dış araçları tarafından otomatik olarak oluşturulan kodundan bildirmiyor. Oluşturulan kodundan uyarıları görüntülemek için temizleyin **bastırmak oluşturulan kod sonuçlarından** onay kutusu.

    > [!NOTE]
    > Hataları ve Uyarıları formlar ve şablonlar görüntülendiğinde bu seçenek kod çözümleme hataları ve Uyarıları oluşturulan kodundan engelleme. Hem görüntülemek ve onu üzerine gerek kalmadan bir form veya şablon için kaynak kodunu sağlayabilirsiniz.

1. İçinde **bu kural kümesini çalıştırmak** listesinde, aşağıdakilerden birini yapın:

    - Kullanmak istediğiniz kural kümesini seçin.

    - Seçin  **\<Gözat... >** var olan bir özel kural kümesi bulmak için listede değil.

    - Tanımlayan bir [özel kural kümesi](../code-quality/how-to-create-a-custom-rule-set.md).

## <a name="specify-rule-sets-for-multiple-projects-in-a-solution"></a>Bir çözümde birden çok proje için kural kümeleri belirtin

Varsayılan olarak, bir çözümün tüm yönetilen projeleri atanan *Microsoft Minimum önerilen kurallar* Kod Analizi kural kümesi. Bir çözümde projelerine atanan kural kümeleri değiştirebileceğiniz **özellikleri** çözüm için iletişim kutusu.

1. Çözümü Visual Studio'da açın.

2. Üzerinde **Çözümle** menüsünde, select **çözüm için Kod Analizi yapılandırma**.

3. Gerekirse, genişletin **ortak özellikleri**ve ardından **kod çözümleme ayarlarını**.

4. Bir kural kümesi için bir veya daha fazla projeleri belirtebilirsiniz:

    - Bir kural için tek bir proje kümesini belirtmek için proje adı seçin.

    - Bir kural için birden çok proje kümesini belirtmek için basılı **Ctrl** ve proje adı seçin.

    - Çözümdeki tüm projeleri belirtmek için basılı **Shift** ve Proje listesinde'ı tıklatın.

5. Seçin **kural kümesi** projenin alan ve ardından uygulamak istediğiniz kuralın adını ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Bir ASP.NET Web Uygulaması İçin Kod Çözümlemesini Yapılandırma](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)