---
title: "Performans uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.performancerules
helpviewer_keywords:
- warnings, performance
- performance warnings
- performance, warnings
- managed code analysis warnings, performance warnings
ms.assetid: e014ac3a-02e6-46d9-942c-3491dd63782f
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: baf04adf4589f0809db6a2de2bedcc0efd0f6fcb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="performance-warnings"></a>Performans Uyarıları
Performans uyarıları, yüksek performanslı kitaplıkları ve uygulamaları destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1800: Gereksiz atamalar yapmayın](../code-quality/ca1800-do-not-cast-unnecessarily.md)|Özellikle yayınlar sıkıştırılmış yineleme deyiminde gerçekleştirildiğinde yinelenen yayınların performansını azaltır.|  
|[CA1801: Kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)|Yöntem imzası, yöntemin gövdesinde kullanılmayan bir parametre içerir.|  
|[CA1802: Uygun Yerlerde Değişmez Değerler Kullanın](../code-quality/ca1802-use-literals-where-appropriate.md)|Bir alan statik ve salt okunur bildirilmiş (paylaşılan ve salt okunur olarak [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ve derleme zamanında computable olan bir değer ile başlatıldı. Hedeflenen alanına atanan değer derleme zamanında computable olduğundan, bir const bildirimi değiştirme (içinde Const [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) derleme zamanında yerine çalışma zamanında hesaplanan değer böylece alan.|  
|[CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)|Kullanılmayan yerel değişkenler ve gereksiz atamaların derleme boyutunu artırır ve performansı düşürür.|  
|[CA1806: Yöntem sonuçlarını yoksaymayın](../code-quality/ca1806-do-not-ignore-method-results.md)|Yeni bir nesne oluşturulur, ancak hiç kullanılmamış veya oluşturur ve yeni bir dize döndüren bir yöntem olarak adlandırılır ve yeni bir dize hiç kullanılmamış veya hiç kullanılmamış bir HRESULT ya da hata kodu Bileşen Nesne Modeli (COM) ya da P/Invoke yöntemi döndürür.|  
|[CA1809: Aşırı yerel öğelerden kaçın](../code-quality/ca1809-avoid-excessive-locals.md)|Bir değeri bellek yerine işlemci yazmacında tutmak yaygın bir performans iyileştirmesidir ve buna "değeri kaydetmek denir".  Tüm yerel değişkenler işlemiyor olduğunu olasılığını artırmak için yerel değişkenleri 64 sayısını sınırlayın.|  
|[CA1810: Başvuru türü statik alanları satır içi başlatın](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)|Bir tür açık statik yapıcı bildirdiğinde, JIT derleyici her bir statik yöntemi kontrol ekler ve türün yapıcı örneği statik yapıcının daha önceden çağrıldığından emin olur. Statik oluşturucu denetimleri performansı düşürebilir.|  
|[CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)|Özel veya dahili (derleme düzeyi) üyesi derlemede arayanlar yok, ortak dil çalışma zamanı tarafından çağrılan değil ve temsilci tarafından çağrılan değil.|  
|[CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)|Bir derleme düzeyi türünün örneği, derleme içindeki kod tarafından oluşturulmaz.|  
|[CA1813: Korumasız özniteliklerden kaçının](../code-quality/ca1813-avoid-unsealed-attributes.md)|[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Sınıf kitaplığı özel öznitelikleri alma için yöntemler sağlar. Varsayılan olarak, bu yöntemleri öznitelik devralma hiyerarşisinde arar. Öznitelik mühürleme kalıtım hiyerarşisi aracılığıyla aramayı ortadan kaldırır ve performansı artırabilir.|  
|[CA1814: Basit dizileri çok boyutlu dizilere tercih edin](../code-quality/ca1814-prefer-jagged-arrays-over-multidimensional.md)|Basit bir dizi, öğeleri dizi olan bir dizidir. Öğeleri olun diziler bazı veri kümeleri için daha az harcanan alan sonuçlanabilir farklı boyutlarda olabilir.|  
|[CA1815: Değer türlerinde eşittir ve işleç eşitliklerinin üzerine yazın](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)|Değer türleri için, Equals'ın devralınmış uygulaması Reflection kitaplığını kullanır ve türdeki tüm alanların içeriğini karşılaştırır. Yansıma hesaplama açısından pahalıdır ve her alan için eşitlik karşılaştırma gereksiz olabilir. Kullanıcıları karşılaştırmak veya örneklerini sıralamak ya da tablo anahtarlarını karma olarak kullanmayı bekliyorsanız, değer türünüz Equals'ı uygulamalıdır.|  
|[CA1816: GC.SuppressFinalize öğesini doğru çağırın](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Dispose uygulamasıdır bir yöntem GC çağırmaz. GC SuppressFinalize veya Dispose uygulaması olmayan bir yöntem çağırır. GC SuppressFinalize ya da bir yöntemi çağırır. SuppressFinalize ve bunun dışında bir şey geçirir (Oturumumu [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).|  
|[CA1819: Özellikler diziler döndürmemelidir](../code-quality/ca1819-properties-should-not-return-arrays.md)|Salt okunur özelliği olsa bile, özellik tarafından döndürülen dizi yazma korumalı değildir. Dizi değiştirilmeye kanıt tutulacak özellik dizisinin bir kopyasını döndürmelidir. Tipik olarak, kullanıcılar bu tür bir özellik aramanın performans üzerindeki olumsuz etkilerini anlamayacaktır.|  
|[CA1820: Dize uzunluğunu kullanarak boş dizeler için sınayın](../code-quality/ca1820-test-for-empty-strings-using-string-length.md)|String.Length özelliği veya String.IsNullOrEmpty yöntemi, Equals kullanılmasından önemli ölçüde daha hızlıdır.|  
|[CA1821: Boş sonlandırıcıları kaldırın](../code-quality/ca1821-remove-empty-finalizers.md)|Güncelleştirirken, nesne kullanım süresini izleme söz konusu olduğunda ek performans yükü nedeniyle sonlandırıcılardan kaçının. Boş bir Sonlandırıcısı uygulanan bir fayda olmaksızın yükünü eklendi.|  
|[CA1822: Üyeleri statik olarak işaretleyin](../code-quality/ca1822-mark-members-as-static.md)|Örnek verileri veya çağrı örneği yöntemleri erişmemesi üyeleri işaretlenir olarak statik (paylaşılan [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). Yöntemleri statik olarak işaretledikten sonra, derleyici sanal olmayan arama sitelerini bu üyelere yayar. Bu, ölçülebilir kazanç performansını performans duyarlı kodunuz için verebilir.|  
|[CA1823: Kullanılmayan özel alanlardan kaçının](../code-quality/ca1823-avoid-unused-private-fields.md)|Derlemede erişimi görülmeyen özel alanlar algılandı.|  
|[CA1824: Derlemeleri NeutralResourcesLanguageAttribute ile işaretleme](../code-quality/ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md)|NeutralResourcesLanguage özniteliği bir derlemenin bağımsız kültürünün kaynağını görüntüleyen dilin Kaynak Yöneticisi'ni bilgilendirir. Bu ilk yüklediğiniz kaynak için arama performansını artırır ve çalışma kümenizi azaltabilir.|