---
title: 'CA2105: Dizi alanları salt okunur olmalıdır değil | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2105
- ArrayFieldsShouldNotBeReadOnly
helpviewer_keywords:
- ArrayFieldsShouldNotBeReadOnly
- CA2105
ms.assetid: 0bdc3421-3ceb-4182-b30c-a992fbfcc35d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4091586091fd5a71d7bba09617d851642fe3f9e2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2105-array-fields-should-not-be-read-only"></a>CA2105: Dizi alanları salt okunur olmamalıdır
|||  
|-|-|  
|TypeName|ArrayFieldsShouldNotBeReadOnly|  
|CheckId|CA2105|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir dizi tutan bir genel veya korumalı alan salt okunur bildirildi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Uyguladığınızda `readonly` (`ReadOnly` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) için farklı bir dizi başvurmak için bir dizi alan içeren bir alan değiştiricisi değiştirilemez. Bir dizinin öğeleri salt okunur bir alanda depolanmış olsa bile değiştirilebilir. Kararları veya genel olarak erişilebilir bir salt okunur dizi öğelerde temel işlemleri gerçekleştiren kod yararlanma güvenlik açığı içerebilir.  
  
 Genel alan sahip de tasarım kuralını ihlal ediyor olduğunu Not [CA1051: görünür örnek alanlarını bildirme](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural tarafından belirlenen güvenlik açığı düzeltmek için ortak olarak erişilebilen bir salt okunur dizi içeriğine kullanmayın. Aşağıdaki yordamlardan birini kullanmanız önerilir:  
  
-   Dizi değiştirilemez kesin türü belirtilmiş bir koleksiyonu ile değiştirin. Daha fazla bilgi için bkz. <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>.  
  
-   Genel alan özel bir dizi kopyasını döndüren bir yöntem ile değiştirin. Kodunuzu kopyada bağlı değildir çünkü olup olmadığını tehlike öğeleri değiştirdi.  
  
 İkinci yaklaşımı seçerseniz, alanın bir özelliğiyle değiştirmeyin; diziler olumsuz döndüren özellikleri performansını etkiler. Daha fazla bilgi için bkz: [CA1819: özellikler diziler döndürmemelidir](../code-quality/ca1819-properties-should-not-return-arrays.md).  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan hariç kesinlikle önerilmez. Salt okunur bir alanın içeriği önemli olduğu neredeyse hiçbir senaryoları oluşur. Senaryonuz Durum buysa, kaldırma `readonly` ileti hariç yerine değiştiricisi.  
  
## <a name="example"></a>Örnek  
 Bu örnek, bu kural ihlal tehlikeleri gösterir. Bir türe sahip bir örnek kitaplığı ilk bölümü gösterir `MyClassWithReadOnlyArrayField`, iki alan içeriyor (`grades` ve `privateGrades`) güvenli değildir. Alan `grades` ortak ve bu nedenle herhangi bir çağırıcı karşı savunmasız. Alan `privateGrades` özel ancak çağıranlar tarafından döndürdüğünden korumasız `GetPrivateGrades` yöntemi. `securePrivateGrades` Alanı tarafından güvenli bir şekilde kullanıma sunulan `GetSecurePrivateGrades` yöntemi. İyi tasarım uygulamaları izlemek için özel olarak bildirilir. İkinci bölümü depolanan değerleri değiştirir kod gösterir `grades` ve `privateGrades` üyeleri.  
  
 Örnek sınıf kitaplığı aşağıdaki örnekte görünür.  
  
 [!code-csharp[FxCop.Security.ArrayFieldsNotReadOnly#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği sınıf kitaplığı salt okunur dizi güvenlik sorunlarını göstermek için kullanır.  
  
 [!code-csharp[FxCop.Security.TestArrayFieldsRead#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_2.cs)]  
  
 Bu örnek çıktısı şöyledir:  
  
 **İzinsiz önce: dereceleri: 90, 90, 90 özel dereceleri: 90, 90, 90 güvenli dereceleri, 90, 90, 90**  
**İzinsiz sonra: dereceleri: 90, 555, 90 özel dereceleri: 90, 555, 90 güvenli dereceleri, 90, 90, 90**   
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Array?displayProperty=fullName>   
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>