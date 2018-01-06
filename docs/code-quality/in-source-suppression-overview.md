---
title: "Kaynak gizleme genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
ms.assetid: f1a2dc6a-a9eb-408c-9078-2571e57d207d
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 92babbf3c7a5863d178463b69525bdb722bf28ad
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="in-source-suppression-overview"></a>Kaynak Bastırmaya Genel Bakış
Kaynak gizleme yeteneğidir gizlemek veya Kod Analizi ihlalleri yönetilen kod ekleyerek Yoksay **SuppressMessage** özniteliği ihlali neden kodu kesimleri. **SuppressMessage** yalnızca CODE_ANALYSIS derleme simgenin derleme zamanında tanımlanırsa, yönetilen kod derlemenizi IL meta verilerine dahil bir koşullu özniteliği bir özniteliktir.  
  
 C + +/ CLI, CA_SUPPRESS_MESSAGE veya CA_GLOBAL_SUPPRESS_MESSAGE makroları öznitelik eklemek için üst bilgi dosyasını kullanın.  
  
 Kaynak suppressions sürüm yapıları kaynak gizleme meta verileri yanlışlıkla sevkiyat önlemek için kullanmamanız gerekir. Kaynak gizleme işleme maliyetini nedeniyle, uygulamanızın performansını kaynak gizleme meta veriler ekleyerek da düşebilir.  
  
> [!NOTE]
>  El kod bu öznitelikler kendiniz sahip değilsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: menü öğesini kullanarak uyarıları bastırma](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md). Menü öğesi C++ kodu için kullanılabilir değil.  
  
## <a name="suppressmessage-attribute"></a>SuppressMessage özniteliği  
 Kod çözümleme uyarı olarak sağ **hata listesi** ve ardından **bastırmak iletileri**, **SuppressMessage** özniteliği kodunuzda veya çok eklenir Projenin genel suppressions dosyası.  
  
 **SuppressMessage** özniteliği şu biçime sahiptir:  
  
```vb  
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>  
```  
  
```csharp  
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]  
  
```  
  
 [C++]  
  
```  
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")  
  
```  
  
 Konum:  
  
-   **Kural kategori** -kural tanımlanır kategorisi. Kod çözümleme kural kategorileri hakkında daha fazla bilgi için bkz: [yönetilen kod uyarıları için Kod Analizi](../code-quality/code-analysis-for-managed-code-warnings.md).  
  
-   **Kural Kimliği** -kuralının tanıtıcısı. Hem kısa ve uzun ad kuralı tanımlayıcısı için destek içerir. Kısa ad CAXXXX olur; uzun CAXXXX:FriendlyTypeName adıdır.  
  
-   **Düzeltme** -ileti gizleme nedenini belgelemek için kullanılan metin.  
  
-   **İleti kimliği** -her ileti için sorun benzersiz tanıtıcısı.  
  
-   **Kapsam** -üzerinde uyarı geçersiz kılınır hedef. Hedef belirtilmezse, özniteliğin hedef ayarlanır. Desteklenen kapsamları aşağıdakileri içerir:  
  
    -   Modül  
  
    -   Ad Alanı  
  
    -   Kaynak  
  
    -   Tür  
  
    -   Üye  
  
-   **Hedef** - üzerinde uyarı geçersiz kılınır hedef belirtmek için kullanılan tanımlayıcı bir. Bir tam öğesi adı içermelidir.  
  
## <a name="suppressmessage-usage"></a>SuppressMessage kullanımı  
 Kod çözümleme uyarıları hangi düzeyde gizlenir örneği **SuppressMessage** özniteliği uygulanır. Bunun amacı, sıkı bir şekilde kod gizleme bilgileri eşleştiği için burada ihlali gerçekleşir.  
  
 Gizleme genel biçiminde kural kategorisini ve kural adı isteğe bağlı bir kullanıcı tarafından okunabilen gösterimini içeren bir kural tanımlayıcısını içerir. Örneğin,  
  
 `[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`  
  
 Kaynak gizleme meta verileri en aza indirmek için katı Performans nedeniyle varsa, kural adı bırakılabilir. Kural kategorisini ve kendi kural kimliği birlikte yeterince benzersiz kural tanımlayıcısını oluşturur. Örneğin,  
  
 `[SuppressMessage("Microsoft.Design", "CA1039")]`  
  
 Bu biçim bakım sorunları nedeniyle önerilmez.  
  
## <a name="suppressing-multiple-violations-within-a-method-body"></a>Birden çok ihlalleri bir yöntem gövdesinde gizleme  
 Öznitelikleri yalnızca bir yönteme uygulanabilir ve yöntem gövdesinde katıştırılmış. Ancak, bir ihlali bir yöntem içinde birden çok tekrarı ayırt etmek için ileti kimliği olarak tanımlayıcısını belirtin.  
  
 [!code-cpp[InSourceSuppression#1](../code-quality/codesnippet/CPP/in-source-suppression-overview_1.cpp)]
 [!code-vb[InSourceSuppression#1](../code-quality/codesnippet/VisualBasic/in-source-suppression-overview_1.vb)]
 [!code-csharp[InSourceSuppression#1](../code-quality/codesnippet/CSharp/in-source-suppression-overview_1.cs)]  
  
## <a name="generated-code"></a>Oluşturulan kod  
 Yönetilen kod derleyicileri ve bazı üçüncü taraf araçları hızlı kod geliştirme kolaylaştırmak için kod oluşturur. Kaynak dosyaları görünür derleyici tarafından üretilen kod ile genellikle işaretlenir **GeneratedCodeAttribute** özniteliği.  
  
 Kod çözümleme uyarıları ve hataları üretilen kod için engellenip engellenmeyeceğini seçebilirsiniz. Bu tür uyarılar ve hatalar gizlemek hakkında daha fazla bilgi için bkz: [nasıl yapılır: üretilen kod için uyarıları bastırma](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md).  
  
 Kod çözümleme yoksayar Not **GeneratedCodeAttribute** zaman uygulandığı tüm bütünleştirilmiş veya tek bir parametre. Bu durum nadiren oluşur.  
  
## <a name="global-level-suppressions"></a>Genel düzeyde Suppressions  
 Yönetilen kod çözümleme aracı inceler **SuppressMessage** derleme modül türü üye veya parametre düzeyinde uygulanır öznitelikleri. Ayrıca, kaynakları ve ad alanları karşı ihlalleri ateşlenir. Bu ihlalleri genel düzeyde uygulanmış olması gerekir ve kapsamlı ve hedeflenen. Örneğin, aşağıdaki ileti, bir ad alanı ihlali gizler:  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`  
  
> [!NOTE]
>  Ad alanı kapsamlı bir uyarı bastırma olduğunda uyarı ad karşı gizler. Ad alanı içindeki türleriyle uyarı bastırma değil.  
  
 Tüm gizleme açık bir kapsam belirterek ifade edilebilir. Bu suppressions genel düzeyde bulunmalıdır. Üye düzeyi gizleme türü tasarlayarak belirtemezsiniz.  
  
 Genel düzey suppressions açıkça sağlanan kullanıcı kaynağına eşlemiyor derleyici tarafından üretilen kod başvurmak iletileri bastırmak için tek yoludur. Örneğin, aşağıdaki kod bir ihlali derleyici yayılan Oluşturucusu karşı gizler:  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`  
  
> [!NOTE]
>  Hedef her zaman tam öğe adı içeriyor.  
  
## <a name="global-suppression-file"></a>Genel gizleme dosyası  
 Genel gizleme dosyası genel düzeyde suppressions ya da bir hedef belirtmeyin suppressions suppressions sağlar. Örneğin, suppressions derleme düzeyi ihlalleri için bu dosyada depolanır. Ayrıca, proje düzeyi ayarları form arka plan kod için kullanılabilir olmadığından bazı ASP.NET suppressions bu dosyada depolanır. Genel gizleme oluşturulur ve seçtiğiniz ilk kez projenize eklenir **proje gizleme dosyasını** seçeneği **bastırmak iletileri** hata listesi penceresini komutunu. Daha fazla bilgi için bkz: [nasıl yapılır: menü öğesini kullanarak uyarıları bastırma](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Diagnostics.CodeAnalysis>