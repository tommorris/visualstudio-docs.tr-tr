---
title: Performans uyarıları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.performancerules
helpviewer_keywords:
- warnings, performance
- performance warnings
- performance, warnings
- managed code analysis warnings, performance warnings
ms.assetid: e014ac3a-02e6-46d9-942c-3491dd63782f
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c0f43cd713c5f87530455411a5915f5e357d69ab
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629406"
---
# <a name="performance-warnings"></a>Performans Uyarıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [performans uyarıları](https://docs.microsoft.com/visualstudio/code-quality/performance-warnings).  
  
Performans uyarıları, yüksek performanslı kitaplıkları ve uygulamaları destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1800: Gereksiz atamalar yapmayın](../code-quality/ca1800-do-not-cast-unnecessarily.md)|Özellikle yayınlar sıkıştırılmış yineleme deyiminde gerçekleştirildiğinde yinelenen yayınların performansını azaltır.|  
|[CA1801: Kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)|Yöntem imzası, yöntemin gövdesinde kullanılmayan bir parametre içerir.|  
|[CA1802: Uygun Yerlerde Değişmez Değerler Kullanın](../code-quality/ca1802-use-literals-where-appropriate.md)|Statik ve salt okunur bir alana bildirilen (paylaşılan ve salt okunur [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) ve derleme zamanında hesaplanabilen bir değer ile başlatılır. Hedeflenen alana atanan değer derleme zamanında hesaplanabilir olduğundan, bildirimi hesaplanmasını değiştirme (içinde sabit [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) ve böylece, çalışma zamanında derleme zamanından yerine değeri hesaplanan alan.|  
|[CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)|Kullanılmayan yerel değişkenler ve gereksiz atamaların derleme boyutunu artırır ve performansı düşürür.|  
|[CA1806: Yöntem sonuçlarını yoksaymayın](../code-quality/ca1806-do-not-ignore-method-results.md)|Yeni bir nesne oluşturulur, ancak hiç kullanılmadı, oluşturur ve yeni bir dize döndüren bir yöntem çağrılır ve yeni bir dize hiçbir zaman kullanılmaz veya bir Bileşen Nesne Modeli (COM) veya P/Invoke yöntemi hiçbir zaman kullanılmaz bir HRESULT ya da hata kodu döndürür.|  
|[CA1809: Aşırı yerel öğelerden kaçın](../code-quality/ca1809-avoid-excessive-locals.md)|Bir değeri bellek yerine işlemci yazmacında tutmak yaygın bir performans iyileştirmesidir ve buna "değeri kaydetmek denir".  Tüm yerel değişkenlerin kaydedilme imkanına sahip olabilmesi şansını artırmak için 64 yerel değişken sayısını sınırlayın.|  
|[CA1810: Başvuru türü statik alanları satır içi başlatın](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)|Bir tür açık statik yapıcı bildirdiğinde, JIT derleyici her bir statik yöntemi kontrol ekler ve türün yapıcı örneği statik yapıcının daha önceden çağrıldığından emin olur. Statik oluşturucu denetimleri performansı düşürebilir.|  
|[CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)|Özel veya iç (derleme düzeyi) üye Arayanların derlemede yok, ortak dil çalışma zamanı tarafından çağrılan değildir ve temsilci tarafından çağrılan değildir.|  
|[CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)|Bir derleme düzeyi türünün örneği, derleme içindeki kod tarafından oluşturulmaz.|  
|[CA1813: Korumasız özniteliklerden kaçının](../code-quality/ca1813-avoid-unsealed-attributes.md)|[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Sınıf kitaplığı özel öznitelikleri almak için yöntemler sağlar. Varsayılan olarak, bu yöntemleri öznitelik devralma hiyerarşisinde arar. Öznitelik mühürleme kalıtım hiyerarşisi aracılığıyla aramayı ortadan kaldırır ve performansı artırabilir.|  
|[CA1814: Basit dizileri çok boyutlu dizilere tercih edin](../code-quality/ca1814-prefer-jagged-arrays-over-multidimensional.md)|Basit bir dizi, öğeleri dizi olan bir dizidir. Öğeleri olan diziler bazı veri kümeleri için daha az harcanmış sonuçlanabilir farklı boyutlarda olabilir.|  
|[CA1815: Değer türlerinde eşittir ve işleç eşitliklerinin üzerine yazın](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)|Değer türleri için, Equals'ın devralınmış uygulaması Reflection kitaplığını kullanır ve türdeki tüm alanların içeriğini karşılaştırır. Yansıma hesaplama açısından pahalıdır ve her alan için eşitlik karşılaştırma gereksiz olabilir. Kullanıcıları karşılaştırmak veya örneklerini sıralamak ya da tablo anahtarlarını karma olarak kullanmayı bekliyorsanız, değer türünüz Equals'ı uygulamalıdır.|  
|[CA1816: GC.SuppressFinalize öğesini doğru çağırın](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Dispose uygulamasını bir yöntemi, GC çağırmaz. GC IDisposable.Dispose ya da Dispose uygulamasını olmayan bir yöntem çağırır. GC IDisposable.Dispose ya da bir yöntemi çağırır. IDisposable.Dispose ve bunun dışında bir şey geçirir (Oturumumu [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).|  
|[CA1819: Özellikler diziler döndürmemelidir](../code-quality/ca1819-properties-should-not-return-arrays.md)|Özellik salt okunur olsa bile özellikleri tarafından döndürülen dizi yazma korumalı değildir. Dizi değiştirilmeye kanıt tutulacak özellik dizisinin bir kopyasını döndürmelidir. Tipik olarak, kullanıcılar bu tür bir özellik aramanın performans üzerindeki olumsuz etkilerini anlamayacaktır.|  
|[CA1820: Dize uzunluğunu kullanarak boş dizeler için sınayın](../code-quality/ca1820-test-for-empty-strings-using-string-length.md)|String.Length özelliği veya String.IsNullOrEmpty yöntemi, Equals kullanılmasından önemli ölçüde daha hızlıdır.|  
|[CA1821: Boş sonlandırıcıları kaldırın](../code-quality/ca1821-remove-empty-finalizers.md)|Güncelleştirirken, nesne kullanım süresini izleme söz konusu olduğunda ek performans yükü nedeniyle sonlandırıcılardan kaçının. Doğurur boş Sonlandırıcı eklenen yükü hiçbir avantajı olmadan.|  
|[CA1822: Üyeleri statik olarak işaretleyin](../code-quality/ca1822-mark-members-as-static.md)|Örnek veri veya çağrı örnek yöntemlerinin erişmez üyeleri işaretlenebilir olarak statik (paylaşılan [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]). Yöntemleri statik olarak işaretledikten sonra, derleyici sanal olmayan arama sitelerini bu üyelere yayar. Bu, ölçülebilir kazanç performansını performans duyarlı kodunuz için verebilir.|  
|[CA1823: Kullanılmayan özel alanlardan kaçının](../code-quality/ca1823-avoid-unused-private-fields.md)|Derlemede erişimi görülmeyen özel alanlar algılandı.|  
|[CA1824: Derlemeleri NeutralResourcesLanguageAttribute ile işaretleme](../code-quality/ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md)|NeutralResourcesLanguage özniteliği bir derlemenin bağımsız kültürünün kaynağını görüntüleyen dilin Kaynak Yöneticisi'ni bilgilendirir. Bu ilk yüklediğiniz kaynak için arama performansını artırır ve çalışma kümenizi azaltabilir.|



