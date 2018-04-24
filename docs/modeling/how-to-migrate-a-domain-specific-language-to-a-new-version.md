---
title: 'Nasıl yapılır: Etki Alanına Özgü Dili Yeni Sürüme Geçirme'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 83f80e9fe0bf68f5d10d8f3b76840b55de025f33
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="how-to-migrate-a-domain-specific-language-to-a-new-version"></a>Nasıl yapılır: Etki Alanına Özgü Dili Yeni Sürüme Geçirme
Tanımlamak ve etki alanına özgü dil kullanan projeleri geçirebilirsiniz [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] sürümünden [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] , ile dağıtılan [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)].

 Geçiş Aracı parçası olarak sağlanan [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)]. Aracı dönüştürür [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projeler ve çözümler, kullanın veya DSL araçları tanımlayın.

 Geçiş Aracı açıkça çalıştırmanız gerekir: bir çözümde açtığınızda otomatik olarak başlatılmaz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Aracı ve ayrıntılı kılavuz belge bu yolda bulunabilir:

 **% Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**

## <a name="before-you-migrate-your-dsl-projects"></a>Önce DSL projelerinizi geçirme
 Geçiş Aracı değiştirir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje dosyalarını (**.csproj**) ve çözüm dosyalarını (**.sln**).

#### <a name="to-prepare-projects-for-migration"></a>Projeleri geçişe hazırlamak için.

-   Emin olun **.csproj** ve **.sln** dosyaları kullanılarak yazılabilir. Kaynak denetimi altında olmaları durumunda, bunlar kullanıma olduğundan emin olun.

-   Geçirmek istediğiniz klasörleri bir kopyasını oluşturun.

## <a name="migrating-a-collection-of-projects"></a>Projeleri koleksiyonu geçirme

#### <a name="to-migrate-dsl-projects-and-solutions-to-visual-studio-2010"></a>Visual Studio 2010 DSL projeler ve çözümler geçirmek için

1.  DSL geçiş aracı başlatın.

    -   Windows Gezgini'nde (veya dosya Gezgini'ni) aracı çift tıklatın veya bir komut isteminden Aracı'nı başlatın. Bu konumda bir araçtır:

         **%ProgramFiles%\Microsoft visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**

2.  Çözüm ve dönüştürmek istediğiniz projeleri içeren bir klasör seçin.

    -   Aracı üstündeki kutusunda yolunu girin veya tıklatın **Gözat**.

     Geçiş Aracı tanımlayın veya DSL'ler kullanan projeleri ağacı görüntüler. Ağaç kullanan her proje içeriyor **Microsoft.VisualStudio.Modeling.Sdk** veya **TextTemplating** derlemeler.

3.  Projeleri ağacının gözden geçirin ve dönüştürmek istiyor musunuz projeleri seçeneğinin işaretini kaldırın.

    -   Bir proje veya aracı yaptığınız değişiklikler listesini görmek için çözümü seçin.

        > [!NOTE]
        >  Klasör adları yanındaki görünür onay kutularını hiçbir etkisi yoktur. Projeler ve çözümler incelemek için klasörleri genişletmeniz gerekir.

4.  Projeleri dönüştürün.

    1.  Tıklatın **dönüştürme**.

         Her proje dosyası dönüştürülür önce bir kopyasını *proje *** .csproj** olarak kaydedilen *proje ***.vs2008.csproj**

         Her bir kopyasını *çözüm *** .sln** olarak kaydedilen *çözüm ***.vs2008.sln**

    2.  Bildirilen tüm başarısız dönüştürme araştırın.

         Hataları metin penceresinde raporlanır. Ayrıca, ağaç görünümü kırmızı bayrak dönüştürmek için başarısız oldu her düğümde gösterir. Bu hata hakkında daha fazla bilgi almak için düğüm tıklatabilirsiniz.

5.  **Tüm Şablonları dönüştürme** çözümlerinde başarıyla içeren projeler dönüştürülür.

    1.  Çözümü açın.

    2.  Tıklatın **tüm şablonları dönüştürme** Çözüm Gezgini üstbilgisindeki düğmesini.

        > [!NOTE]
        >  Bu adım, gereksiz yapabilirsiniz. Daha fazla bilgi için bkz: [otomatikleştirmek tüm şablonları dönüştürme nasıl](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).

6.  Dönüştürülen projelerinde özel kodunuzu güncelleştirin.

    -   Projeleri derlemek ve olan hataları araştırmak çalışır.

    -   Tasarımcısı sınayın.


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Ayrıca Bkz.

- [İlgili blog gönderileri](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)