---
title: 'CA1812: Örneklendirilmemiş iç sınıflardan kaçının'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf39d775c5602aaddf5b9487d175ddbbdd70d52e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: Örneklendirilmemiş iç sınıflardan kaçının
|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir derleme düzeyi türünün örneği, derleme içindeki kod tarafından oluşturulmaz.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural türü oluşturuculardan birine çağrısına bulmaya çalışır ve hiçbir çağrı bulunursa, bir ihlali raporlar.

 Bu kural tarafından aşağıdaki türlerden incelenmesi değil:

-   Değer türleri

-   Soyut türler

-   Numaralandırmalar

-   Temsilciler

-   Derleyici yayılan dizi türleri

-   Olamaz başlatılamaz ve tanımlayan türleri `static` (`Shared` Visual Basic'te) yalnızca yöntemleri.

 Uygularsanız <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> analiz ediliyor. derlemeye olarak işaretlenmiş oluşturucular üzerinde bu kural gerçekleşmez `internal` bir alan bir başkası tarafından kullanılıp kullanılmadığını bildiremez çünkü `friend` derleme.

 Bu sınırlamaya geçici çalışamaz olsa bile [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kod analizi, dış tek başına FxCop gerçekleşeceği iç oluşturucularda her varsa `friend` derlemedir analiz mevcut.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için türünü kaldırmak veya onu kullanan kodu ekleyin. Türü yalnızca statik yöntemler içeriyorsa, varsayılan bir ortak örnek oluşturucu yayma derleyici önlemek için türü için aşağıdakilerden birini ekleyin:

-   İçin özel bir oluşturucu türleri hedefleyen [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 1.0 ve 1.1 sürümleri.

-   `static` (`Shared` Visual Basic'te) değiştiricisi için türleri hedefleyen [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan gizlemek güvenlidir. Bu uyarı aşağıdaki durumlarda bastırmak öneririz:

-   Sınıfı gibi geç bağlama yansıma yöntemleri ile oluşturulan <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>.

-   Sınıfı çalışma zamanı tarafından otomatik olarak oluşturulur veya [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]. Örneğin, uygulayan sınıflar <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> veya <xref:System.Web.IHttpHandler?displayProperty=fullName>.

-   Sınıfının yeni bir kısıtlamaya sahip bir genel tür parametresi olarak geçirilir. Örneğin, aşağıdaki örnekte, bu kural ortaya koyar.

    ```csharp
    internal class MyClass
    {
        public DoSomething()
        {
        }
    }
    public class MyGeneric<T> where T : new()
    {
        public T Create()
        {
            return new T();
        }
    }
    // [...]
    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
    mc.Create();
    ```

 Bu durumda, bu uyarıyı gizlemek önerilir.

## <a name="related-rules"></a>İlgili kuralları
 [CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1801: Kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)