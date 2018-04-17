---
title: Yönetilen koddaki onaylar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], assertions in managed code
- Trace.Assert method
- debugging managed code, assertions
- Debug.Assert method
- Debug.Listeners property
- assertions, side effects
- Trace.Listeners property
- assertions, managed code
ms.assetid: 70ab2522-6486-4076-a1a9-e0f11cd0f3a1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: f682768aeb3f3a0f3cc22da8a68f8db4a225b375
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="assertions-in-managed-code"></a>Yönetilen Koddaki Onaylar
Onaylama işlemi, bir ya da `Assert` deyimi, bağımsız değişken olarak belirttiğiniz bir koşulu sınar `Assert` deyimi. Koşul doğru olarak değerlendirilirse, hiçbir eylem oluşur. Koşul false olarak değerlendirilirse, onaylama işlemi başarısız olur. İle hata ayıklama derlemesi çalıştırıyorsanız, programınızı Kesme moduna girer.  
  
##  <a name="BKMK_In_this_topic"></a> Bu konudaki  
 [System.Diagnostics Namespace onaylar](#BKMK_Asserts_in_the_System_Diagnostics_Namespace)  
  
 [Debug.Assert yöntemi](#BKMK_The_Debug_Assert_method)  
  
 [Debug.Assert yan etkileri](#BKMK_Side_effects_of_Debug_Assert)  
  
 [İzleme ve hata ayıklama gereksinimleri](#BKMK_Trace_and_Debug_Requirements)  
  
 [Bağımsız değişkenler onaylama](#BKMK_Assert_arguments)  
  
 [Assert davranışını özelleştirme](#BKMK_Customizing_Assert_behavior)  
  
 [Yapılandırma dosyalarında onayları ayarlama](#BKMK_Setting_assertions_in_configuration_files)  
  
##  <a name="BKMK_Asserts_in_the_System_Diagnostics_Namespace"></a> System.Diagnostics Namespace onaylar  
 Visual Basic ve Visual C#, kullanabileceğiniz `Assert` ya da yönteminden <xref:System.Diagnostics.Debug> veya <xref:System.Diagnostics.Trace>, içinde olduğu <xref:System.Diagnostics> ad alanı. <xref:System.Diagnostics.Debug> Bunlar etmeyin boyutunu artırın veya yayın kodunuzu hızına azaltmak için sınıf yöntemlerini programınızı, bir yayın sürümüne dahil edilmez.  
  
 C++ desteklemiyor <xref:System.Diagnostics.Debug> sınıfı yöntemlerinin. Kullanarak aynı sonucu elde edebilirsiniz <xref:System.Diagnostics.Trace> gibi ile koşullu derleme, sınıf `#ifdef DEBUG`... `#endif`.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_The_Debug_Assert_method"></a> Debug.Assert yöntemi  
 Kullanım <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> serbestçe kodunuzun doğru ise, doğru tutun koşullarda test etmek için yöntem. Örneğin, bir tamsayı bölme işlevi yazmış olduğunuzu varsayın. Matematik kuralları tarafından bölen hiçbir zaman sıfır olamaz. Bu bir onaylama kullanarak test:  
  
```VB  
Function IntegerDivide(ByVal dividend As Integer, ByVal divisor As Integer) As Integer  
    Debug.Assert(divisor <> 0)  
    Return CInt(dividend / divisor)  
End Function  
```  
  
```csharp  
int IntegerDivide ( int dividend , int divisor )  
    { Debug.Assert ( divisor != 0 );  
        return ( dividend / divisor ); }  
```  
  
 Hata ayıklayıcı altında bu kodu çalıştırmak, onaylama işlemi deyimi değerlendirilir, ancak yayın sürümünde karşılaştırma değil yapılır, bu nedenle var. hiçbir ek yükü  
  
 Burada, başka bir örnek verilmiştir. Çek hesabı gibi uygulayan bir sınıf vardır:  
  
```VB  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Debug.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Debug.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 Para hesabından geri önce hesap bakiyesini geri almak için hazırlanırken tutar karşılamak yeterli olduğundan emin olmak istersiniz. Bakiye denetlemek için bir onaylama yazabilirsiniz:  
  
```VB  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Trace.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Trace.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 Çağrılar Not <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> yöntemi kodunuzu sürümünü oluşturduğunuzda kaybolur. Bakiye denetler çağrısı yayın sürümünde kaybolur anlamına gelir. Bu sorunu çözmek için değiştirmelisiniz <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> ile <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, hangi değil kayboluyor yayın sürümünde:  
  
 Çağrılar <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> çağrıları farklı olarak, yayın sürümü yükü eklemek <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Side_effects_of_Debug_Assert"></a> Debug.Assert yan etkileri  
 Kullandığınızda <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, herhangi bir içindeki kod emin olun `Assert` program sonuçlarını değişmez `Assert` kaldırılır. Aksi takdirde, yalnızca programınızın yayın sürümünü görünür bir hatayı yanlışlıkla getirebilir. Özellikle dikkatli olun hakkında işlev veya yordam içeren onaylar çağrısı, aşağıdaki örnek gibi:  
  
```VB  
' unsafe code  
Debug.Assert (meas(i) <> 0 )  
```  
  
```csharp  
// unsafe code  
Debug.Assert (meas(i) != 0 );  
```  
  
 Bu kullanımını <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> ilk bakışta güvenli görünebilir, ancak her zaman bir sayaç işlevi meas güncelleştirmeleri varsayalım adı verilir. Yayın sürümü derlerken sayaç güncelleştirilmemiş için bu çağrıyı meas çıkarıldı. Bu, bir yan etkisi işleviyle örneğidir. Yan etkileri olan bir işlev çağrısı ortadan yalnızca yayın sürümünde görünür bir hataya neden olabilir. Bu tür sorunları önlemek için işlev çağrılarında yerleştirmeyin bir <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> deyimi. Geçici bir değişken kullanın:  
  
```VB  
temp = meas( i )  
Debug.Assert (temp <> 0)  
```  
  
```csharp  
temp = meas( i );  
Debug.Assert ( temp != 0 );  
```  
  
 Kullandığınızda bile <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, yine de işlev çağrıları içinde yerleştirmez isteyebilirsiniz bir `Assert` deyimi. Tür çağrılar güvenli, çünkü <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> deyimleri değil ortadan yayın derlemesi içinde. Böyle yapıları sağlasa da, alýþkanlýk olarak kaçının, ancak, siz kullanırken bir hata yapma olasılığını <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Trace_and_Debug_Requirements"></a> İzleme ve hata ayıklama gereksinimleri  
 Kullanarak projesi oluşturursanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sihirbazlar, izleme simgesi varsayılan sürüm ve hata ayıklama yapılandırmaları olarak tanımlanır. Hata ayıklama simgesi varsayılan yalnızca hata ayıklama derlemesi olarak tanımlanır.  
  
 Aksi takdirde için <xref:System.Diagnostics.Trace> çalışmak için yöntemler programınızı kaynak dosyasının en üstte şunlardan biri olması gerekir:  
  
-   `#Const TRACE = True` Visual Basic'te  
  
-   `#define TRACE` Visual C# ve C++  
  
 Veya programınız izleme seçeneği ile oluşturulmalıdır:  
  
-   `/d:TRACE=True` Visual Basic'te  
  
-   `/d:TRACE` Visual C# ve C++  
  
 Hata ayıklama yöntemleri bir C# veya Visual Basic yayın derleme kullanmanız gerekiyorsa, yayın yapılandırmanızda hata ayıklama simgesi tanımlamanız gerekir.  
  
 C++ desteklemiyor <xref:System.Diagnostics.Debug> sınıfı yöntemlerinin. Kullanarak aynı sonucu elde edebilirsiniz <xref:System.Diagnostics.Trace> gibi ile koşullu derleme, sınıf `#ifdef DEBUG`... `#endif`. Bu simgeleri tanımlayabilirsiniz  **\<Proje > özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [bir Visual Basic hata ayıklama yapılandırması proje ayarları değiştirme](../debugger/project-settings-for-a-visual-basic-debug-configuration.md) veya [C veya C++ hata ayıklama yapılandırması proje ayarları değiştirme](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
##  <a name="BKMK_Assert_arguments"></a> Bağımsız değişkenler onaylama  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> ve <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> en fazla üç bağımsız değişkenleri alır. Zorunludur, ilk bağımsız denetlemek istediğiniz durumdur. Çağırırsanız <xref:System.Diagnostics.Trace.Assert(System.Boolean)?displayProperty=fullName> veya <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=fullName> yalnızca tek bir bağımsız değişken ile `Assert` yöntemi koşulu denetler ve sonucu yanlışsa, çağrı yığını içeriğini çıkarır **çıkış** penceresi. Aşağıdaki örnekte gösterildiği <xref:System.Diagnostics.Trace.Assert(System.Boolean)?displayProperty=fullName> ve <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=fullName>:  
  
```VB  
Debug.Assert(stacksize > 0)  
Trace.Assert(stacksize > 0)  
```  
  
```csharp  
Debug.Assert ( stacksize > 0 );  
Trace.Assert ( stacksize > 0 );   
```  
  
 İkinci ve üçüncü bağımsız değişken varsa, dize olmalıdır. Çağırırsanız <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> veya <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> iki veya üç bağımsız değişkenler, ilk bağımsız değişkeni bir durumdur. Yöntem koşul denetler ve sonuç false ise ikinci dize ve üçüncü dizeleri çıkarır. Aşağıdaki örnekte gösterildiği <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=fullName> ve <xref:System.Diagnostics.Trace.Assert(System.Boolean,System.String)?displayProperty=fullName> iki bağımsız değişkenlerle kullanılır:  
  
```VB  
Debug.Assert(stacksize > 0, "Out of stack space")  
Trace.Assert(stacksize > 0, "Out of stack space")  
```  
  
```csharp  
Debug.Assert ( stacksize > 0, "Out of stack space" );  
Trace.Assert ( stacksize > 0, "Out of stack space" );  
```  
  
 Aşağıdaki örnekte gösterildiği <xref:System.Diagnostics.Debug.Assert%2A> ve <xref:System.Diagnostics.Trace.Assert%2A>:  
  
```VB  
Debug.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:", "inctemp failed on third call" )  
```  
  
```csharp  
Debug.Assert ( stacksize > 100, "Out of stack space" , "Failed in inctemp" );  
Trace.Assert ( stacksize > 0, "Out of stack space", "Failed in inctemp" );   
```  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Customizing_Assert_behavior"></a> Assert davranışını özelleştirme  
 Kullanıcı arabirimi modunda uygulamanızı çalıştırırsanız `Assert` yöntemi görüntüler **onaylama başarısız** koşulu başarısız olduğunda iletişim kutusu. Bir onaylama başarısız olduğunda meydana gelecek eylemleri tarafından denetlenen <xref:System.Diagnostics.Debug.Listeners%2A> veya <xref:System.Diagnostics.Trace.Listeners%2A> özelliği.  
  
 Ekleyerek çıktı davranışını özelleştirebilirsiniz bir <xref:System.Diagnostics.TraceListener> nesnesini `Listeners` kaldırarak koleksiyonu, bir <xref:System.Diagnostics.TraceListener> gelen `Listeners` koleksiyonu veya kılarak <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> varolan yöntemi `TraceListener` yapmak için farklı şekilde davranır.  
  
 Örneğin, kılmanız <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> görüntüleme yerine bir olay günlüğüne yazılacağını yöntemi **onaylama başarısız** iletişim kutusu.  
  
 Çıktı bu şekilde özelleştirmek için program bir dinleyici içermeli ve öğesinden devralmalıdır <xref:System.Diagnostics.TraceListener> ve geçersiz kılma kendi <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> yöntemi.  
  
 Daha fazla bilgi için bkz: [izleme dinleyicileri](/dotnet/framework/debug-trace-profile/trace-listeners).  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Setting_assertions_in_configuration_files"></a> Yapılandırma dosyalarında onayları ayarlama  
 Onaylar kodunuzu olduğu gibi program yapılandırma dosyanızda de ayarlayabilirsiniz. Daha fazla bilgi için bkz. <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> veya <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [İzleme ve uygulamaları](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)   
 [Nasıl yapılır: izleme ve hata ayıklama ile koşullu derleme](/dotnet/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)