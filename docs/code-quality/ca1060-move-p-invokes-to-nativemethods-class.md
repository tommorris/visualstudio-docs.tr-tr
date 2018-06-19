---
title: 'CA1060: Taşıma P-çağırır öğesini NativeMethods sınıfına'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
helpviewer_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
ms.assetid: 06686c8c-6ad3-42f7-a355-cbaefa347cfc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d6035553f8d3a4518fe99e7800a61f1b5921d947
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900815"
---
# <a name="ca1060-move-pinvokes-to-nativemethods-class"></a>CA1060: P/Invokes öğesini NativeMethods sınıfına taşıyın
|||
|-|-|
|TypeName|MovePInvokesToNativeMethodsClass|
|CheckId|CA1060|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir yöntem Platform Başlatma Hizmetleri yönetilmeyen kod erişmek için kullanır ve birinin üyesi değil **NativeMethods** sınıfları.

## <a name="rule-description"></a>Kural Tanımı
 Platform Çağırma yöntemlerini kullanarak işaretlenmiş olanlar gibi <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> özniteliği ya da kullanılarak tanımlanan yöntemler `Declare` anahtar sözcük [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], yönetilmeyen kod erişim. Bu yöntemler aşağıdaki sınıflar biri olmalıdır:

-   **NativeMethods** -Bu sınıf yönetilmeyen kod izni yığını yetenekte bastırmak değil. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> bu sınıfa uygulanmamış gerekir.) Yığın ilerlemesi gerçekleştirilecek çünkü herhangi bir kullanılabilir yöntemleri sınıftır.

-   **SafeNativeMethods** -Bu sınıf yönetilmeyen kod izni yığını yetenekte gizler. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> bu sınıfa uygulanır.) Bu sınıf, herkes için aranacak güvenli yöntemleri içindir. Bu yöntemlerin arayanlar yöntemleri için herhangi bir çağırıcı zararsız olduğundan kullanım güvenli olduğundan emin olmak için tam güvenlik incelemesi gerçekleştirmek için gerekli değildir.

-   **UnsafeNativeMethods** -Bu sınıf yönetilmeyen kod izni yığını yetenekte gizler. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> bu sınıfa uygulanır.) Potansiyel olarak tehlikeli olabilecek yöntemleri için sınıftır. Bu yöntemlerin herhangi bir çağırıcı hiçbir yığın ilerlemesi gerçekleştirilecek çünkü kullanım güvenli olduğundan emin olmak için tam güvenlik incelemesi gerçekleştirmeniz gerekir.

 Bu sınıflar olarak bildirilen `internal` (`Friend`, Visual Basic'te) ve yeni örnekleri oluşturulmasını önlemek için özel bir oluşturucuya bildirin. Bu sınıfları yöntemleri olmalıdır `static` ve `internal` (`Shared` ve `Friend` Visual Basic'te).

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için uygun move yöntemi **NativeMethods** sınıfı. Çoğu uygulama için P/Invokes adlı yeni bir sınıf taşıma **NativeMethods** yeterlidir.

 Diğer uygulamalarda kullanmak için kitaplıkları geliştiriyorsanız, Bununla birlikte, denir iki sınıfları tanımlama düşünmelisiniz **SafeNativeMethods** ve **UnsafeNativeMethods**. Bu sınıfların benzer **NativeMethods** sınıf; ancak, bunlar adlı özel bir öznitelik kullanarak işaretlenmiş **SuppressUnmanagedCodeSecurityAttribute**. Bu öznitelik uygulandığında, çalışma zamanı tüm arayanlar sahip olduğunuzdan emin olmak için bir tam yığın ilerlemesi gerçekleştirmez **UnmanagedCode** izni. Çalışma zamanı genellikle başlangıçta bu izni olup olmadığını denetler. Onay değil gerçekleştirildiğinden, yönetilmeyen bu yöntemlere çağrılar için performansı önemli ölçüde artırabilir, sınırlı bu yöntemleri çağırmak için izinleri olan kod ayrıca sağlar.

 Ancak, bu öznitelik ile çok dikkatli kullanmanız gerekir. Yanlış uygulanırsa ciddi güvenlik etkileri olabilir...

 Yöntemleri hakkında daha fazla bilgi için bkz: **NativeMethods** örnek, **SafeNativeMethods** örnek, ve **UnsafeNativeMethods** örnek.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal eden bir yöntem bildirir. İhlali düzeltmek için **RemoveDirectory** P/Invoke yalnızca P/Invokes tutmak için tasarlanmış bir uygun sınıf taşınması.

 [!code-vb[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_1.vb)]
 [!code-csharp[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_1.cs)]

## <a name="nativemethods-example"></a>NativeMethods örneği

### <a name="description"></a>Açıklama
 Çünkü **NativeMethods** sınıf işaretlenmemiş kullanarak **SuppressUnmanagedCodeSecurityAttribute**, kaynakta put P/Invokes gerektirecektir **UnmanagedCode** izni. Yerel bilgisayardan çoğu uygulamayı çalıştırabilir ve tam güven ile birlikte çalıştırın, bu genellikle bir sorun değildir çünkü. Yeniden kullanılabilir kitaplıkları geliştiriyorsanız, ancak tanımlama dikkate almanız bir **SafeNativeMethods** veya **UnsafeNativeMethods** sınıfı.

 Aşağıdaki örnekte gösterildiği bir **Interaction.Beep** sarmalar yöntemi **MessageBeep** user32.dll işlevinden. **MessageBeep** P/Invoke koyun **NativeMethods** sınıfı.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_2.cs)]
 [!code-vb[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_2.vb)]

## <a name="safenativemethods-example"></a>SafeNativeMethods örneği

### <a name="description"></a>Açıklama
 Güvenli bir şekilde ortaya herhangi bir uygulama ve yan etkileri sahip değil P/Invoke yöntemleri adlı bir sınıfta put **SafeNativeMethods**. İsteğe bağlı izinlerine sahip değil ve gelen burada adlı için çok dikkat gerekmez.

 Aşağıdaki örnekte gösterildiği bir **Environment.TickCount** sarmalar özelliği **GetTickCount** kernel32.dll işlevinden.

### <a name="code"></a>Kod
 [!code-vb[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_3.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_3.cs)]

## <a name="unsafenativemethods-example"></a>UnsafeNativeMethods örneği

### <a name="description"></a>Açıklama
 Güvenli bir şekilde çağrılamaz ve yan etkileri neden olabilecek P/Invoke yöntemleri adlı bir sınıfta put **UnsafeNativeMethods**. Bu yöntemler, bunlar kullanıcıya kasıtsız olarak sunulmaz emin olmak için titizlikle denetlenmelidir. Kural [CA2118: gözden geçirme SuppressUnmanagedCodeSecurityAttribute kullanımını](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md) bu ile yardımcı olabilir. Alternatif olarak, yöntemleri yerine talep başka bir iznine sahip olması gereken **UnmanagedCode** kullandığında bunları.

 Aşağıdaki örnekte gösterildiği bir **Cursor.Hide** sarmalar yöntemi **sayı değil geçiş** user32.dll işlevinden.

### <a name="code"></a>Kod
 [!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_4.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_4.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Tasarım Uyarıları](../code-quality/design-warnings.md)