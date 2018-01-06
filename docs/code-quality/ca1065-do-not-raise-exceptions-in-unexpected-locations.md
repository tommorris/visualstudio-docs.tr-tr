---
title: "CA1065: beklenmedik konumlarda özel durumlar yükseltmeyin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1065
- DoNotRaiseExceptionsInUnexpectedLocations
helpviewer_keywords:
- DoNotRaiseExceptionsInUnexpectedLocations
- CA1065
ms.assetid: 4e1bade4-4ca2-4219-abc3-c7b2d741e157
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6d34a92c1e71df0c355a9c8a3b5290146dce7240
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1065-do-not-raise-exceptions-in-unexpected-locations"></a>CA1065: Beklenmedik konumlarda özel durumlar harekete geçirmeyin
|||  
|-|-|  
|TypeName|DoNotRaiseExceptionsInUnexpectedLocations|  
|CheckId|CA1065|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 İstisna atılmasını beklemeyen yöntem bir istisna atar.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Özel durumlar oluşturma beklenmez yöntemler aşağıdaki gibi kategorilere ayrılabilir:  
  
-   Özellik Get yöntemleri  
  
-   Olay erişimci yöntemleri  
  
-   Eşittir yöntemleri  
  
-   GetHashCode yöntemleri  
  
-   ToString yöntemleri  
  
-   Statik Oluşturucular  
  
-   Sonlandırıcılar  
  
-   Dispose yöntemleri  
  
-   Eşitlik İşleçleri  
  
-   Örtük atama işleçleri  
  
 Aşağıdaki bölümlerde bu yöntem türleri açıklanmaktadır.  
  
### <a name="property-get-methods"></a>Özellik Get yöntemleri  
 Özellikler temelde akıllı alanlardır. Bu nedenle, bir alan mümkün olduğunca gibi davranırlar. Alanları özel durumlar oluşturmayın ve özellikler, gerekir. Aykırı bir özellik varsa, bir yöntem kolaylaştırarak göz önünde bulundurun.  
  
 Aşağıdaki özel durumlar bir özellik alma yönteminden durum oluşturulmasına izin verilir:  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName>ve tüm türevleri (de dahil olmak üzere <xref:System.ObjectDisposedException?displayProperty=fullName>)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName>ve tüm türevleri  
  
-   <xref:System.ArgumentException?displayProperty=fullName>(yalnızca get dizinlenmiş)  
  
-   <xref:System.Collections.Generic.KeyNotFoundException>(yalnızca get dizinlenmiş)  
  
### <a name="event-accessor-methods"></a>Olay erişimci yöntemleri  
 Olay erişimcileri özel durumlar oluşturmayın basit işlemler olmalıdır. Olay işleyici ekleyip çalıştığınızda bir olay bir özel durum oluşturmamalıdır.  
  
 Aşağıdaki özel durumlar, bir olay accesor durum izin verilir:  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName>ve tüm türevleri (de dahil olmak üzere <xref:System.ObjectDisposedException?displayProperty=fullName>)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName>ve tüm türevleri  
  
-   <xref:System.ArgumentException>ve türevleri  
  
### <a name="equals-methods"></a>Eşittir yöntemleri  
 Aşağıdaki **eşittir** yöntemleri özel durumları olmayan throw:  
  
-   <xref:System.Object.Equals%2A?displayProperty=fullName>  
  
-   [M:IEquatable.Equals](http://go.microsoft.com/fwlink/?LinkId=113472)  
  
 Bir **eşittir** yöntemi döndürmelidir `true` veya `false` bir özel durum atma yerine. Örneğin, eşittir geçirilir, iki türleri, yalnızca döndürmelidir `false` atma yerine bir <xref:System.ArgumentException>.  
  
### <a name="gethashcode-methods"></a>GetHashCode yöntemleri  
 Aşağıdaki **GetHashCode** yöntemleri genellikle değil throw özel durumlar:  
  
-   <xref:System.Object.GetHashCode%2A>  
  
-   [M:IEqualityComparer.GetHashCode(T)](http://go.microsoft.com/fwlink/?LinkId=113477)  
  
 **GetHashCode** her zaman bir değer döndürmelidir. Aksi takdirde, karma tablosundaki öğelerin kaybedebilir.  
  
 Sürümleri **GetHashCode** bağımsız değişken throw süren bir <xref:System.ArgumentException>. Ancak, **Object.GetHashCode** hiçbir zaman bir özel durum oluşturması gerekir.  
  
### <a name="tostring-methods"></a>ToString yöntemleri  
 Hata ayıklayıcı kullanan <xref:System.Object.ToString%2A?displayProperty=fullName> dize biçiminde nesneler hakkındaki bilgileri görüntülemek amacıyla. Bu nedenle, **ToString** bir nesnenin durumu değiştirmemeniz gerektiğini ve özel durumlar oluşturmamalıdır.  
  
### <a name="static-constructors"></a>Statik Oluşturucular  
 Statik oluşturucusundan özel durumları atma türün geçerli uygulama etki alanında kullanılamaz hale gelmesine neden olur. Statik oluşturucusundan bir özel durum atma için çok iyi bir nedenle (örneğin, bir güvenlik sorunu) olmalıdır.  
  
### <a name="finalizers"></a>Sonlandırıcılar  
 Sonlandırıcı bir özel durum atma hangi işlem çıkarır CLR hızlı, başarısız olmasına neden olur. Bu nedenle, bir sonlandırıcı özel durumları atma her zaman kaçınılmalıdır.  
  
### <a name="dispose-methods"></a>Dispose yöntemleri  
 A <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> yöntemi bir özel durum değil throw. Dispose temizleme mantığının parçası olarak adlandırılan genellikle bir `finally` yan tümcesi. Bu nedenle, özel durum işleme içine eklenecek kullanıcının açıkça Dispose bir özel durum atma zorlar `finally` yan tümcesi.  
  
 **Dispose(false)** kod yolu hiçbir zaman throw özel durumlar, bu neredeyse her zaman bir sonlandırıcı çağrıldığı için.  
  
### <a name="equality-operators--"></a>Eşitlik işleçleri (==,! =)  
 Eşittir yöntemler gibi eşitlik işleçleri ya da döndürmelidir `true` veya `false` ve özel durumlar oluşturmamalıdır.  
  
### <a name="implicit-cast-operators"></a>Örtük atama işleçleri  
 Kullanıcı genellikle bir örtük atama işleci çağrıldı farkında olduğundan örtük atama işleci tarafından oluşturulan bir özel tamamen beklenmeyen bir durumdur. Bu nedenle, hiçbir özel durum örtük atama işleçleri durum.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Özellik alıcıları da mantığı artık bir özel durum ya da bir yönteme özelliği değiştirmek sahip şekilde değiştirin.  
  
 Daha önce listelenen tüm diğer yöntemi türleri için mantığı artık bir özel durum gereken şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Tarafından oluşturulan özel durum yerine bir özel durum bildirimi ihlali neden oldu, bu kural bir uyarıdan gizlemek güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2219: Özel durum yan tümceleri içinde özel durum harekete geçirmeyin](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım Uyarıları](../code-quality/design-warnings.md)