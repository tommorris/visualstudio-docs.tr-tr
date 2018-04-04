---
title: 'Nasıl yapılır: yönetilen kod projesi için kod analizini yapılandırma | Microsoft Docs'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 46d41b09f0f6639195613c8a4d9a08f952c79525
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
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

    - Özel bir kural kümesini tanımlar. Daha fazla bilgi için bkz: [özel kural kümeleri oluşturma](../code-quality/creating-custom-code-analysis-rule-sets.md).

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek Yol: Özel bir Kural Kümesini Yapılandırma ve Kullanma](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)
- [Nasıl yapılır: Bir ASP.NET Web Uygulaması İçin Kod Çözümlemesini Yapılandırma](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)