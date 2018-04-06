---
title: 'İzlenecek yol: Yapılandırma ve kullanma özel bir kural kümesi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-code-analysis
ms.topic: article
helpviewer_keywords:
- code analysis, walkthroughs
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b72a86f10c6e864406929fdccfb59bdd9393752e
ms.sourcegitcommit: a0a49cceb0fdc1465ddf76d131c6575018b628b8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2018
---
# <a name="walkthrough-configuring-and-using-a-custom-rule-set"></a>İzlenecek Yol: Özel bir Kural Kümesini Yapılandırma ve Kullanma

Bu kılavuz bir özelleştirilmiş kullanmak üzere yapılandırılmış kod çözümleme araçları nasıl kullanacağınızı gösterir *kural kümesi* üzerinde bir sınıf kitaplığı. Eski kod bölünemez şekilde sabit sorunları için tarama gibi belirli bir gereksinimi karşılamak için alternatif bir kural kümesi, çözümünüz için belirtilen ya da seçebilirsiniz proje türü ilişkili bir kural kümesini seçebilirsiniz. Her iki durumda da, kural kümeleri de yapılandırarak proje gereksinimlerinizi ince ayar için özelleştirilebilir.  
  
Bu kılavuzda, bu işlemler adım:  
  
-   Bir sınıf kitaplığı oluşturun.  
  
-   Seçin **Microsoft temel tasarım yönerge kuralları** Kod Analizi kural kümesi.  
  
-   Kendi kodunuzu sınıfına ekleyin.  
  
-   Kod çözümleme çalıştırın.  
  
-   Kural kümesi özelleştirin.  
  
-   Kod çözümleme çalıştırın ve nasıl özelleştirme davranışı works kural kümesi bakın.  
  
## <a name="using-rule-sets-with-code-analysis"></a>Kural Kod Analizi ile kümeleri kullanma

İlk olarak, bir basit sınıf kitaplığı oluşturun.  
  
### <a name="create-a-class-library"></a>Bir sınıf kitaplığı oluşturun  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **proje türleri**, tıklatın **Visual C#**.  
  
3.  Altında **Visual C#**seçin **sınıf kitaplığı**.  
  
4.  İçinde **adı** metin kutusunda, **RuleSetSample** ve ardından **Tamam**.  
  
 Ardından, seçecektir **Microsoft temel tasarım yönerge kuralları** kural kümesini ve projenizi ile kaydedin.  
  
### <a name="select-a-code-analysis-rule-set"></a>Kod çözümleme kural kümesi seçin  
  
1.  Üzerinde **Çözümle** menüsünde tıklatın **RuleSetSample için Kod Analizi yapılandırma**.  
  
     Kod çözümleme için yapılandırma ayarları görüntülenir.  
  
2.  İçinde **bu kural kümesini çalıştırmak** aşağı açılan listesinden, **Microsoft tüm kuralları**.  
  
     Kullanılabilir kural kümeleri hakkında daha fazla bilgi için bkz: [Kod Analizi kural kümesi başvurusu](../code-quality/code-analysis-rule-set-reference.md).  
  
     Dosya menüsünde **seçili öğeleri Kaydet** proje dosyası seçtiğiniz kural kümesi hakkında bilgi ve ayarları güncelleştirmek için.  
  
    > [!TIP]
    >  Kod Analizi ile hedeflemek istediğiniz hangi sorunların önceliğini belirleme için kullanmak üzere iyi bir uygulama başlamak gerçek durumda olur **Minimum önerilen kurallar** kural kümesini ve istenen sorunları düzeltin ve artımlı olarak ekleyin Daha fazla kural ya da kural bulmak ve ek sorunları düzeltmek için ayarlar.  
  
 Ardından, CA1704 ihlalleri göstermek için kullanılan sınıf kitaplığı için bazı kod ekleyeceksiniz "Tanımlayıcıları yazıldığından" Kod Analizi kural. Daha fazla bilgi için bkz: [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
### <a name="add-your-own-code"></a>Kendi kodunuzu ekleyin  
  
-   Çözüm Gezgini'nde, Class1.cs dosyasını açın ve var olan kodu aşağıdakiyle değiştirin:  
  
    ```csharp
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace RuleSetSample  
    {  
        public class Class1  
        {  
            //The variable parameter names "a" and "b" will cause  
            //the warning CA 1704 Microsoft.Naming "Consider   
            //providing a more meaningful name" to fire  
            public int AddIntegers(int a, int b)  
            {  
  
                int sum = a + b;  
  
                return (sum);  
            }  
        }  
    }
    ```
  
Şimdi RuleSetSample projede Kod Analizi çalıştırın ve hataları ve uyarıları hata Listesi penceresindeki oluşturulan arayın.  
  
### <a name="run-code-analysis-on-the-rulesetsample-project"></a>Kod çözümleme RuleSetSample projede çalıştırın  
  
1.  Üzerinde **Çözümle** menüsünde tıklatın **RuleSetSample kod çözümleme çalıştırmak**.  
  
2.  Hata Listesi penceresini tıklatın **uyarıları** ve ardından **açıklama** uyarılar sıralamak için sütun başlığını alfasayısal olarak.  
  
     Gerçek dünya uygulamada, bu noktada, düzeltme değerinde herhangi kuralı ihlallerini düzeltmek veya isteğe bağlı olarak kapatmak veya onu düzelttikten değerinde olmadığını belirlediyseniz, bir kural bastır. Daha fazla bilgi için bkz: [uyarıları bastırma](../code-quality/in-source-suppression-overview.md).
  
3.  CA1704 uyarılar dikkat edin. Bu kural üzerinde bu ihlalleri, "parametreleri için daha anlamlı bir ad sağlama düşünmelisiniz olduğunu." belirtin Kodunuzda sorunu düzeltin veya, kural bir sonraki yordamda açıklandığı gibi devre dışı bırakabilirsiniz.  
  
 Ardından, kural CA1704 uyarı dışlanacak kümesi özelleştireceğiniz, "Tanımlayıcılar doğru yazılmalıdır".  
  
### <a name="customize-the-rule-set-for-your-project-to-disable-a-specific-rule"></a>Kural belirli bir kuralın devre dışı bırakmak projeniz için kümesi özelleştirme  
  
1.  Üzerinde **Çözümle** menüsünde tıklatın **RuleSetSample için Kod Analizi yapılandırma**.  
  
2.  İçinde **bu kural kümesini çalıştırmak** aşağı açılan listesinde, doğrulayın **Microsoft tüm kuralları** kümesi hala vurgulanmış kural ve ardından **açık**. Kural kümesi sayfası görüntülenir.  
  
3.  Microsoft.Naming kategorisi düğümünü genişletin ve ardından CA1704 uyarı seçin.  
  
4.  Altında **eylem** sütun, select **yok.** Bu, bir uyarı veya hata listesi penceresini hata olarak görüntüleme CA1704 önler.  
  
     Şimdi çeşitli araç çubuğu düğmeleri ile denemek için iyi bir zamandır ve bunlarla aşina seçenekleri filtreleme. Örneğin, kullanabileceğiniz **Group By** belirli bir kural veya kategori kurallarının bulmasına yardımcı olmak için aşağı açılan liste. Kullanabileceğiniz başka bir örnektir **Gizle devre dışı kurallarını** sahip tüm kurallar göstermek veya gizlemek için kural kümesi sayfaları araç çubuğu düğmesini **eylem** sütun kümesine **hiçbiri**. Bu, hala bunları devre dışı olmasını istediğiniz doğrulamak için kapatmış herhangi bir kuralın için taramak istiyorsanız yararlı olabilir.  
  
5.  Görünüm menüsünde Özellikler penceresini'ı tıklatın. Tür **My özel kural kümesi** aracı penceresinin Ad kutusuna. Bu yeni kural kümesi görünen adını değiştirir [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] IDE.  
  
6.  Üzerinde **dosya** menüsünde tıklatın **Microsoft tüm Rules.ruleset kaydetmek** özelleştirilmiş kuralınız kaydetmek üzere ayarlama. Projenizin kök klasöre gidin. İçinde **FileName** metin kutusunda, **MyCustomRuleSet**. Özel kural kümesini şimdi projenizi ile kullanmak için seçilebilir.  
  
Oluşturulan, yeni kural kümesi ile artık, yeni kuralınıza ile ayarlamak kullanmak istediğinizi belirtmek için proje ayarlarınızı yapılandırmanız gerekir.  
  
### <a name="specify-the-new-rule-set-for-use-with-your-project"></a>Yeni Kural projenizi ile kullanılmak üzere kümesi belirtin  
  
1.  Çözüm Gezgini'nde projeye sağ tıklayın ve ardından **özellikleri**.  
  
2.  İçinde **özellikleri** sekmesini tıklatın, **Kod Analizi**.  
  
     İçinde **bu kural kümesini çalıştırmak** aşağı açılan listesinde, tıklatın  **\<Gözat... >**. Kod projenizi kök klasörüne gidin ve ardından **MyCustomRuleSet.ruleset**. Önceki yordamda oluşturduğunuz yeni bir kural kümesi budur.  
  
3.  Üzerinde **dosya** menüsünde tıklatın **kaydetmek** proje yapılandırmanızı kaydetmek için. Özel kural kümesini şimdi projenizi ile kullanılabilir.  
  
 Son olarak, Kod Analizi MyCustomRuleSet kural kümesini kullanarak yeniden çalışır. Hata Listesi penceresini CA1704 performans kuralı ihlali görüntülemez dikkat edin.  
  
### <a name="run-code-analysis-on-the-rulesetsample-project-for-the-second-time"></a>Kod çözümleme RuleSetSample projede ikinci kez çalıştırın.  
  
1.  Üzerinde **Çözümle** menüsünde tıklatın **RuleSetSample kod çözümleme çalıştırmak**.  
  
2.  ' I tıklattığınızda hata Listesi penceresinde dikkat **uyarıları**, artık CA1704 uyarı ihlalleri "Tanımlayıcılar doğru yazılmalıdır" kuralı için bkz.  
  
## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: yönetilen kod projesi için kod çözümlemesini yapılandırma](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)   
[Kod çözümleme kural kümesi başvurusu](../code-quality/code-analysis-rule-set-reference.md)