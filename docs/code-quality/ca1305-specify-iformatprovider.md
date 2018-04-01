---
title: 'CA1305: Iformatprovider belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8bb3d993cc79ebf683f0a2622628bfc87d7c065a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305: IFormatProvider belirtme
|||  
|-|-|  
|TypeName|SpecifyIFormatProvider|  
|CheckId|CA1305|  
|Kategori|Microsoft.Globalization|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir yöntemi veya oluşturucusu kabul aşırı yüklü bir veya daha fazla üye çağıran bir <xref:System.IFormatProvider?displayProperty=fullName> parametresi yöntemi veya oluşturucusu alan aşırı çağırmaz <xref:System.IFormatProvider> parametresi. Bu kural çağrıları yoksayar [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] yoksayılıyor olarak belgelenen yöntemleri <xref:System.IFormatProvider> parametre ve ayrıca aşağıdaki yöntemleri:  
  
-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>  
  
## <a name="rule-description"></a>Kural Tanımı  
 Zaman bir <xref:System.Globalization.CultureInfo?displayProperty=fullName> veya <xref:System.IFormatProvider> nesne sağlanmadı, aşırı yüklenmiş üyesi tarafından sağlanan varsayılan değeri, tüm yerel ayarlarda istediğiniz etkiye sahip olmayabilir. Ayrıca, [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] üyeleri varsayılan kültürü seçin ve biçimlendirme temel kodunuz için doğru olmayabilir varsayımlar. Kod senaryolarınız için beklendiği gibi çalıştığından emin olmak için aşağıdaki kılavuzlara göre kültüre özgü bilgileri vermeniz gerekir:  
  
-   Değeri kullanıcıya görüntülenir, geçerli kültürü kullanın. Bkz: <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.  
  
-   Değer depolanır ve (bir dosya veya veritabanına kalıcı) yazılım tarafından erişilen, sabit kültür kullanın. Bkz: <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
-   Hedef değerinin bilmiyorsanız, veri tüketici sahip veya sağlayıcıyı kültür belirtin.  
  
 Unutmayın <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> yalnızca bir örneğini kullanarak yerelleştirilmiş kaynaklar almak için kullanılan <xref:System.Resources.ResourceManager?displayProperty=fullName> sınıfı.  
  
 Aşırı yüklenmiş üye varsayılan davranışını ihtiyaçlarınız için uygun olsa bile, böylece kodunuzu Self belgelendirme ve daha kolay tutulan kültüre özgü aşırı açıkça çağırmak daha iyidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için alan aşırı yüklemesini kullanın. bir <xref:System.Globalization.CultureInfo> veya <xref:System.IFormatProvider> ve daha önce listelenen yönergelerine göre bağımsız değişken belirtin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Varsayılan kültür/biçim sağlayıcısı doğru seçim ve kod bakımı önemli geliştirme öncelik olduğu olduğunu belirli olduğunda bir uyarı bu kuraldan gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `BadMethod` bu kuralın iki ihlalleri neden olur. `GoodMethod`Sabit kültür geçirerek ilk ihlali düzeltir <xref:System.String.Compare%2A>ve ikinci ihlali geçerli kültür geçirerek düzeltir <xref:System.String.ToLower%2A> çünkü `string3` kullanıcıya görüntülenir.  
  
 [!code-csharp[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, varsayılan olarak geçerli kültür etkisini gösterir <xref:System.IFormatProvider> tarafından seçilen <xref:System.DateTime> türü.  
  
 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_2.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **4/6/1900 12:15:12 PM**  
**06/04/1900 12:15:12**   
## <a name="related-rules"></a>İlgili kuralları  
 [CA1304: CultureInfo belirtin](../code-quality/ca1304-specify-cultureinfo.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[CultureInfo sınıfını kullanma](/dotnet/standard/globalization-localization/globalization#Cultures)  