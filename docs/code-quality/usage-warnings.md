---
title: "Kullanım uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.usagerules
helpviewer_keywords:
- warnings, usage
- managed code analysis warnings, usage warnings
- usage warnings
ms.assetid: fe7dc2a3-289d-4bf7-a1e4-0947a81287c4
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 57068ae8c3d6bb8f86b8a9b052f4d1e2f5fec2d4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="usage-warnings"></a>Kullanım Uyarıları
Kullanım uyarıları .NET Framework'ün uygun kullanımını destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1801: kullanılmayan parametreleri gözden geçir](../code-quality/ca1801-review-unused-parameters.md)|Yöntem imzası, yöntemin gövdesinde kullanılmayan bir parametre içerir.|  
|[CA1806: yöntem sonuçlarını yoksaymayın](../code-quality/ca1806-do-not-ignore-method-results.md)|Yeni bir nesne oluşturulur, ancak hiç kullanılmaz veya çağrılan yeni dizeyi oluşturur ve döndürür ve yeni dize hiç kullanılmaz ya da COM veya P/Invoke yöntemi, bir HRESULT ya da hiç kullanılmayan hata kodu döndürür.|  
|[CA1816: GC çağırın. SuppressFinalize doğru](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Dispose uygulamasıdır bir yöntem GC çağırmaz. SuppressFinalize; veya GC Dispose uygulaması olmayan bir yöntem çağırır. SuppressFinalize; veya GC bir yöntemi çağırır. SuppressFinalize ve bu (Me Visual Basic'te) dışında bir şey geçirir.|  
|[CA2200: yığın ayrıntılarını korumak için yeniden fırlatma](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|Bir özel durum yeniden oluşturulur ve özel durum throw deyimi içinde açıkça belirtilir. Bir özel durum throw deyimi içinde özel durum belirterek yeniden oluşturulursa, özel durum oluşturdu özgün yöntemi ve geçerli yöntemi arasındaki yöntem çağrılarını listesi kaybolur.|  
|[CA2201: ayrılmış özel durum türleri yükseltmeyin](../code-quality/ca2201-do-not-raise-reserved-exception-types.md)|Bu özgün hata algılamak ve hata ayıklama zor hale getirir.|  
|[CA2202: nesneleri birden çok kez atmayın](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|Yöntem uygulaması, aynı nesne üzerinde System.IDisposable.Dispose veya bir Dispose eşdeğer (örneğin, bazı türleri üzerinde Close() yöntemi) için birden fazla çağrı kodu yolları içerir.|  
|[CA2204: Değişmez değerler doğru yazılmalıdır](../code-quality/ca2204-literals-should-be-spelled-correctly.md)|Bir yöntemin gövdesi içinde hazır bilgi dizesi Microsoft yazım denetimi kitaplığı tarafından tanınmayan bir veya birkaç sözcük içerir.|  
|[CA2205: yönetilen eşdeğerlerini kullanın Win32 API](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|Bir platform çağırma yöntemi tanımlanır ve .NET Framework Sınıf Kitaplığı'nda eşdeğer işlevselliğe sahip bir yöntem bulunmaktadır.|  
|[CA2207: değer türü statik alanları satır içi başlatın](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|Bir değer türü açık bir statik oluşturucu bildirir. Bu kural ihlalini düzeltmek için bildirildiğinde, tüm statik veriyi başlatın ve statik oluşturucuyu kaldırın.|  
|[CA2208: bağımsız değişken özel durumlarını doğru örnekleyin](../code-quality/ca2208-instantiate-argument-exceptions-correctly.md)|Varsayılan (parametresiz) kurucu veya ArgumentException türeyen özel bir durum türü için çağrı yapılır veya hatalı dize bağımsız değişkeni parametreli bir kurucu veya ArgumentException türeyen bir özel durum türü iletilir.|  
|[CA2211: Sabit olmayan alanlar görünür olmamalıdır](../code-quality/ca2211-non-constant-fields-should-not-be-visible.md)|Ne sabitler, ne de salt okunur olan statik alanlar güvenli iş parçacığı değildir. Böyle bir alan erişimi dikkatli bir şekilde denetlenmesi gerekir ve sınıf nesneye erişimi eşitlemek için Gelişmiş programlama tekniklerinin gerektirir.|  
|[CA2212: servis verilen bileşenleri WebMethod ile işaretlemeyin](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|System.EnterpriseServices.ServicedComponent devralan bir tür yönteminde System.Web.Services.WebMethodAttribute ile işaretlenir. WebMethodAttribute ve bir ServicedComponent yönteminin çakışan davranışları ve bağlam ve işlem akışı için gereksinimleri olduğu için, bazı senaryolarda yöntemin davranışı yanlış olacaktır.|  
|[CA2213: Atılabilen alanlar atılmalıdır](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|IDisposable uygulayan türlerin alanları System.IDisposable uygulayan bir türle bildirilir. Bir Dispose yöntemi alanının tanıtıcısının bildirim türü Dispose yöntemi tarafından çağrılmaz.|  
|[CA2214: geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|Bir oluşturucu sanal bir yöntem çağırdığında yöntemi çağırır örnek oluşturucusu değil yürüttüğünü mümkündür.|  
|[CA2215: Atma yöntemleri taban sınıf atmayı çağırmalıdır](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|Tür atılabilen bir türden devralınırsa, kendi Dispose yönteminden basit tür olan Dispose yöntemini çağırmalıdır.|  
|[CA2216: Atılabilir türler sonlandırıcıyı bildirmelidir](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|System.IDisposable uygulayan ve yönetilmeyen kaynakları kullanımını önermek alanları olan bir türü tarafından Object.Finalize açıklandığı gibi bir sonlandırıcı uygulamıyor.|  
|[CA2217: numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)|Dışarıdan görünür numaralandırma FlagsAttribute ile işaretlenir ve iki ya da diğer tanımlanan değerlerin numaralandırma üzerinde bir birleşimini tabanların olmayan bir veya daha fazla değerlere sahip.|  
|[CA2218: gethashcode'u eşittir'i geçersiz kılarak geçersiz kılın](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)|GetHashCode, karma algoritmalar ve karma tablolar gibi veri yapıları için uygun olan geçerli örneği temel alan bir değer döndürür. Aynı türdeki ve eşit olan iki nesnenin aynı karma kodu döndürmesi gerekir.|  
|[CA2219: özel durumları durum yan tümceleri içinde yükseltmeyin](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)|Bir istisna sonlandırıcı ya da arıza yan tümcesine neden olduğunda, yeni istisna aktif istisnayı saklar. Filtre yan tümcesinde bir özel durum ortaya çıktığında, çalışma zamanı özel durumu sessizce yakalar. Bu özgün hata algılamak ve hata ayıklama zor hale getirir.|  
|[CA2220: Sonlandırıcılar taban sınıf Sonlandırıcıları çağırmalıdır](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|Sonlandırılma, devralma hiyerarşisi aracılığıyla gönderilmelidir. Bunu güvence altına almak için, türler basit sınıflarının kendi Finalize yönteminde Finalize yöntemini çağırmalıdır.|  
|[CA2221: Sonlandırıcılar korunmalıdır](../code-quality/ca2221-finalizers-should-be-protected.md)|Sonlandırıcılar aile erişim değiştiricisi kullanmalıdır.|  
|[CA2222: devralınan üye görünürlüğünü azaltmayın](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|Devralınan üyeler için erişim değiştiricisini değiştirmemelisiniz. Devralınmış bir üyeyi özel olarak değiştirme, arayanların yöntemin temel sınıf uygulamasına erişmesini engellemez.|  
|[: Ca2223 üyeler dönüş türünden daha fazla farklı](../code-quality/ca2223-members-should-differ-by-more-than-return-type.md)|Ortak dil çalışma zamanı, aynı üyeler arasında ayrım yapmak için dönüş türleri kullanımına izin verir, ancak bu özelliği ne ortak dil belirtimi ne de .NET programlama dillerinin ortak özelliğidir.|  
|[CA2224: eşittir işlecini aşırı yüklemesi üzerinde geçersiz kılma eşittir](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|Bir ortak türü eşitlik işleci uygular, ancak Object.Equals kılmaz.|  
|[CA2225: İşleç aşırı yüklemeleri adlandırılmış Alternatiflere sahiptir](../code-quality/ca2225-operator-overloads-have-named-alternates.md)|Operatör aşırı yüklemesi bulundu ve beklenen adlandırılmış alternatif yöntem bulunamadı. Adlandırılmış alternatif üye işleci aynı işlevselliğe erişim sağlar ve aşırı yüklenmiş işleçler desteklemeyen dillerde program geliştiriciler için sağlanır.|  
|[CA2226: İşleçler simetrik aşırı olması gerekir](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|Bir türü eşitlik veya eşitsizlik işleci uygular ve ters işleci uygulamıyor.|  
|[CA2227: Koleksiyon Özellikleri salt okunur](../code-quality/ca2227-collection-properties-should-be-read-only.md)|Yazılabilir koleksiyon özelliği kullanıcının koleksiyonun tamamını farklı bir koleksiyonla değiştirmesine izin verir. Salt okunur özelliği değiştirilmesini durdurur ancak yine de tekil üyelerin ayarlamasına izin verir.|  
|[CA2228: yayımlanmamış kaynak biçimlerini yollamayın](../code-quality/ca2228-do-not-ship-unreleased-resource-formats.md)|.NET Framework'ün yayın öncesi sürümleri kullanılarak oluşturulan kaynak dosyaları .NET Framework'ün desteklenen sürümleri tarafından kullanılamayabilir.|  
|[CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)|Bu kural ihlalini düzeltmek için seri hale getirme yapıcısını uygular. Kapalı bir sınıf için kurucusunu özel yapın; aksi takdirde korunmuş yapın.|  
|[CA2230: değişken bağımsız değişkenler için params kullanın](../code-quality/ca2230-use-params-for-variable-arguments.md)|Ortak veya korumalı tür VarArgs çağırma kuralı params anahtar sözcüğünü kullanan bir ortak veya korumalı yöntem içerir.|  
|[CA2231: ValueType.Equals geçersiz kılma üzerinde aşırı işleci eşittir.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Bir değer türü Object.Equals'ı geçersiz kılar, ama eşitlik işlecini uygulamaz.|  
|[CA2232: İşareti Windows Forms giriş noktalarını STAThread ile](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|STAThreadAttribute, COM uygulama modelinin tek bir iş parçacıklı grup olduğunu gösterir. Bu öznitelik Windows Forms kullanan herhangi bir uygulamanın girişinde sunulur; atlanırsa, Windows bileşenleri doğru çalışmayabilir.|  
|[CA2233: İşlemler taşmamalıdır](../code-quality/ca2233-operations-should-not-overflow.md)|Aritmetik işlemler işleminin sonucu dahil edilen veri türleri için olası değerler aralığının dışında olduğundan emin olmak için işlenen doğrulamadan gerçekleştirilmemelidir.|  
|[CA2234: Dizeler yerine System.Uri nesneleri](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)|Adında "URI", "URI", "urn", "urn", "url" veya "url" içeren bir dize parametresi olan yöntem çağrısı yapıldı.  Bildirim türü yöntemi, System.Uri parametresini aşırı yüklemeye uyan yöntemi içerir.|  
|[CA2235: tüm serileştirilebilir olmayan alanları işaretleyin](../code-quality/ca2235-mark-all-non-serializable-fields.md)|Seri hale getirilemeyen bir örnek alan türü seri hale getirilebilir bir tür içinde bildirilir.|  
|[CA2236: ISerializable türler üzerinde taban sınıf yöntemlerini çağırın](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|Bu kural ihlalini düzeltmek için, taban türü GetObjectData yöntemini veya karşılık gelen türetilmiş yöntemden ya da oluşturucudan serileştirme oluşturucusunu çağırın.|  
|[CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|Özel seri hale getirme yordamı ISerializable arabirimini uygulaması aracılığıyla bir tür kullanıyor olsa bile ortak dil çalışma zamanı tarafından seri hale getirilebilir olarak tanınması için türleri SerializableAttribute özniteliğiyle işaretlenmesi gerekir.|  
|[CA2238: Serileştirme yöntemlerini doğru uygulama](../code-quality/ca2238-implement-serialization-methods-correctly.md)|Seri hale getirme olayı tanıtan yöntem türü, doğru imzaya, dönüş türüne veya görünürlüğe sahip değil.|  
|[CA2239: Sağlayan yöntemler için isteğe bağlı alanları](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|System.Runtime.Serialization.OptionalFieldAttribute özniteliğiyle işaretlenmiş bir alan türüne sahip ve türü serinin olay işleme yöntemleri sağlamaz.|  
|[CA2240: ISerializable doğru](../code-quality/ca2240-implement-iserializable-correctly.md)|Bu kural ihlal düzeltmek için görünür ve geçersiz kılınabilir GetObjectData yöntemi olun ve tüm örneği alanları seri hale getirme işlemine dahil veya açıkça NonSerializedAttribute özniteliğiyle işaretlenmiş olduğundan emin olun.|  
|[CA2241: biçimlendirme yöntemlerine doğru bağımsız değişkenleri sağlayın](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|System.String.Format için geçirilen biçimi bağımsız değişken her nesne bağımsız değişkeni için veya tersi karşılık gelen bir biçim öğesi içermiyor.|  
|[CA2242: NaN için doğru sınayın](../code-quality/ca2242-test-for-nan-correctly.md)|Bu ifade, değeri Single.Nan veya Double.Nan'a karşı test eder. Single.IsNan(Single) ya da Double.IsNan(Double) değerini test etmek için kullanın.|  
|[CA2243: Öznitelik dize harfleri doğru ayrıştırma](../code-quality/ca2243-attribute-string-literals-should-parse-correctly.md)|Bir özniteliğin dize değişmez değer parametresi doğru bir URL, bir GUID veya bir sürüm için ayrıştırma değil.|