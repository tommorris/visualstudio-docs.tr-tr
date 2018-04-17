---
title: 'CA1304: CultureInfo belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- SpecifyCultureInfo
- CA1304
helpviewer_keywords:
- SpecifyCultureInfo
- CA1304
ms.assetid: b912d76a-54fd-4c93-b25d-16491e0ae319
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee1a90d2499cc0a22f695cdf0840bd1c9b50b941
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1304-specify-cultureinfo"></a>CA1304: CultureInfo belirtme
|||  
|-|-|  
|TypeName|SpecifyCultureInfo|  
|CheckId|CA1304|  
|Kategori|Microsoft.Globalization|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir yöntemi veya oluşturucusu kabul eden bir aşırı sahip bir üye çağıran bir <xref:System.Globalization.CultureInfo?displayProperty=fullName> parametresi yöntemi veya oluşturucusu alan aşırı çağırmaz <xref:System.Globalization.CultureInfo> parametresi. Bu kural aşağıdaki yöntemlerden çağrıları göz ardı eder:  
  
-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>  
  
## <a name="rule-description"></a>Kural Tanımı  
 Zaman bir <xref:System.Globalization.CultureInfo> veya <xref:System.IFormatProvider?displayProperty=fullName> nesne sağlanmadı, aşırı yüklenmiş üyesi tarafından sağlanan varsayılan değeri, tüm yerel ayarlarda istediğiniz etkiye sahip olmayabilir. Ayrıca, [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] üyeleri varsayılan kültürü seçin ve biçimlendirme temel kodunuz için doğru olmayabilir varsayımlar. Kod senaryolarınız için beklendiği gibi çalıştığından emin olmak için aşağıdaki kılavuzlara göre kültüre özgü bilgileri vermeniz gerekir:  
  
-   Değeri kullanıcıya görüntülenir, geçerli kültürü kullanın. Bkz: <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.  
  
-   Diğer bir deyişle, bir dosya ya da veritabanı, kalıcı değeri depolanır ve yazılım tarafından erişilen, sabit kültür kullanın. Bkz: <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
-   Hedef değerinin bilmiyorsanız, veri tüketici sahip veya sağlayıcıyı kültür belirtin.  
  
 Unutmayın <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> yalnızca bir örneğini kullanarak yerelleştirilmiş kaynaklar almak için kullanılan <xref:System.Resources.ResourceManager?displayProperty=fullName> sınıfı.  
  
 Aşırı yüklenmiş üye varsayılan davranışını ihtiyaçlarınız için uygun olsa bile, böylece kodunuzu Self belgelendirme ve daha kolay tutulan kültüre özgü aşırı açıkça çağırmak daha iyidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için alan aşırı yüklemesini kullanın. bir <xref:System.Globalization.CultureInfo> veya <xref:System.IFormatProvider> ve daha önce listelenen yönergelerine göre bağımsız değişken belirtin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan varsayılan kültür/biçim sağlayıcısı doğru seçim olduğunu belirli olduğunda ve kod bakımı önemli geliştirme öncelik olmadığı gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `BadMethod` bu kuralın iki ihlalleri neden olur. `GoodMethod` Sabit kültür için System.String.Compare geçirerek ilk ihlali düzeltir ve geçerli kültür geçirerek ikinci ihlali düzeltir <xref:System.String.ToLower%2A> çünkü `string3` kullanıcıya görüntülenir.  
  
 [!code-csharp[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, varsayılan olarak geçerli kültür etkisini gösterir <xref:System.IFormatProvider> tarafından seçilen <xref:System.DateTime> türü.  
  
 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1304-specify-cultureinfo_2.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **4/6/1900 12:15:12 PM**  
**06/04/1900 12:15:12**   
## <a name="related-rules"></a>İlgili kuralları  
 [CA1305: IFormatProvider belirtin](../code-quality/ca1305-specify-iformatprovider.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[CultureInfo sınıfını kullanma](/dotnet/standard/globalization-localization/globalization#Cultures)  