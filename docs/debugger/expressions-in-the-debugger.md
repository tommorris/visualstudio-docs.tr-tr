---
title: Hata ayıklayıcıdaki ifadeler | Microsoft Docs
ms.custom: ''
ms.date: 02/07/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.expressions
helpviewer_keywords:
- expressions [debugger]
- debugging [Visual Studio], expressions
- expression evaluation, debugger evaluator
- native expression evaluation
- expression evaluators
- debugger, evaluating expressions
- debugging [Visual Studio], expression evaluation
- debugging [Visual Studio], variable evaluation
ms.assetid: 70f9b531-44c7-4d77-980d-5eddbf2bff41
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 063fe4f61e6e3d8e8ed9e54b990029f2cf408e24
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="expressions-in-the-visual-studio-debugger"></a>Visual Studio Hata ayıklayıcıdaki ifadeler
Visual Studio hata ayıklayıcısı bir ifadede girdiğinizde, çalışan ifade değerlendiricisi içerir **QuickWatch** iletişim kutusu, **izleme** penceresinde veya **hemen** penceresi. İfade değerlendiricileri iş ayrıca altındadır **kesme noktaları** penceresi ve hata ayıklayıcısı diğer birçok yerde.
  
 Aşağıdaki bölümlerde farklı dillerde ifadeler hakkında ayrıntılar sağlar.  
  
## <a name="f-expressions-are-not-supported"></a>F # ifadeleri desteklenmez.  
 F # ifadeler tanımaz. F # kodunda hata ayıklama, bir hata ayıklayıcı penceresini veya iletişim kutusuna ifadeleri girmeden önce C# sözdizimi ifadelere Çevir gerekir. C# gelen F # ifadeleri Çevir, C# kullandığını unutmayın emin olun `==` kullanırken F # tek eşitlik için test etmek için işleci `=`.  
  
## <a name="c-expressions"></a>C++ ifadeleri  
 C++'ta ifadelerle bağlam işleçlerini kullanma hakkında daha fazla bilgi için bkz: [bağlamı işleci (C++)](../debugger/context-operator-cpp.md).  
  
### <a name="unsupported-expressions-in-c"></a>C++'ta desteklenmeyen ifadeler  
  
#### <a name="constructors-destructors-and-conversions"></a>Oluşturucular, yok ediciler ve dönüştürmeler  
 Açık veya örtülü olarak, bir nesne için Oluşturucusu veya yıkıcı çağrılamaz. Örneğin aşağıdaki deyim açıkça bir oluşturucuyu çağırır ve bir hata iletisi ile sonuçlanır:  
  
```C++  
my_date( 2, 3, 1985 )  
```  
  
 Dönüştürme hedefi bir sınıf ise dönüştürme işlevi çağrılamaz. Bu tür dönüştürme nesneyi yapımı içerir. Örneğin, varsa `myFraction` örneği `CFraction`, dönüştürme işlevi işleci tanımlayan `FixedPoint`, aşağıdaki deyim hatayla sonuçlanır:  
  
```C++  
(FixedPoint)myFraction  
```  
  
 Yeni çağrı veya işleçleri silin. Örneğin, aşağıdaki ifadesi desteklenmiyor:  
  
```C++  
new Date(2,3,1985)  
```  
  
#### <a name="preprocessor-macros"></a>Önişlemci makroları  
 Önişlemci makroları Hata Ayıklayıcısı'ndaki desteklenmez. Örneği için bir sabit olmadığını `VALUE` olarak bildirilen: `#define VALUE 3`, kullanamazsınız `VALUE` içinde **izleme** penceresi. Bu sınırlama önlemek için değiştirmelisiniz `#define`numaralandırmaları ile adı ve mümkün olduğunda çalışır.  
  
### <a name="using-namespace-declarations"></a>ad alanı bildirimleri kullanma  
 Kullanamazsınız `using namespace` bildirimleri.  Bir tür adı veya değişken geçerli ad alanı dışında erişmek için tam adı kullanmanız gerekir.  
  
### <a name="anonymous-namespaces"></a>Anonim ad alanları  
 Anonim ad alanları desteklenmiyor. Aşağıdaki kodu varsa, ekleyemezsiniz `test` Gözcü penceresi için:  
  
```C++  
namespace mars   
{   
    namespace  
    {  
        int test = 0;   
    }   
}   
int main()   
{   
    // Adding a watch on test does not work.   
    mars::test++;   
    return 0;   
}  
  
```  
  
###  <a name="BKMK_Using_debugger_intrinisic_functions_to_maintain_state"></a> Hata ayıklayıcı iç işlevler durumunu korumak için kullanma  
 Hata ayıklayıcı iç işlevler uygulama durumunu değiştirmeden ifadelerinde belirli C/C++ işlevleri çağırmak için bir yol sağlar.  
  
 Hata ayıklayıcı iç işlevler:  
  
-   Güvenli olması garanti: hata ayıklayıcı iç işlev yürütülürken bozuk olmadıklarından ayıklanacak işlem.  
  
-   Hatta nerede yan etkiler ve işlev değerlendirmesi izin verilmeyen senaryolarda tüm ifadelerde izin verilir.  
  
-   Burada normal işlev çağrılarını bir mini döküm hata ayıklama gibi mümkün olmayan senaryolarında çalışır.  
  
 Hata ayıklayıcı iç işlevler da değerlendirilirken ifadeleri daha kullanışlı hale getirebilirsiniz. Örneğin, `strncmp(str, "asd")` bir kesme noktası koşulunda yazma çok daha kolaydır `str[0] == 'a' && str[1] == 's' && str[2] == 'd'`. )  
  
|Alan|İç işlevler|  
|----------|-------------------------|  
|**Dize uzunluğu**|strlen, wcslen, strnlen, wcsnlen|  
|**Dize karşılaştırması**|strcmp, wcscmp, stricmp, _stricmp, _strcmpi, wcsicmp, _wcscmpi, _wcsnicmp, strncmp, wcsncmp, strnicmp, wcsnicmp|  
|**Dize arama**|strchr, wcschr, strstr, wcsstr|  
|**Win32**|GetLastError(), TlsGetValue()|  
|**Windows 8**|WindowsGetStringLen(), WindowsGetStringRawBuffer()<br /><br /> Bu işlevler, Windows 8'de çalışıyor olması gerektiğini ayıklanacak işlem gerektirir. Hata ayıklama dökümü dosyaları bir Windows 8 aygıttan oluşturulan de Visual Studio bilgisayar olmasını gerektirir Windows 8 çalıştıran. Ancak, Windows 8 aygıtı uzaktan hata ayıklama yaptığınız, Visual Studio bilgisayarın da Windows 7 çalıştıran.|  
|**Çeşitli**|__log2<br /><br /> Günlük taban 2 düşük en yakın tamsayıya yuvarlanan belirtilen bir tamsayı döndürür.|  
  
## <a name="ccli---unsupported-expressions"></a>C + +/ CLI - desteklenmeyen ifadeler  
  
-   İşaretçileri içeren atamaları veya kullanıcı tanımlı atamaları desteklenmez.  
  
-   Nesne karşılaştırma ve atama desteklenmez.  
  
-   Aşırı yüklenmiş işleçler ve Aşırı yüklenen işlevler desteklenmez.  
  
-   Kutulama ve kutudan çıkarma desteklenmiyor.  
  
-   `Sizeof` işleci desteklenmiyor.  
  
## <a name="c---unsupported-expressions"></a>C# - desteklenmeyen ifadeler  
  
### <a name="dynamic-objects"></a>Dinamik nesneler  
 Statik olarak dinamik olarak yazılan hata ayıklayıcı ifadelerinde değişkenleri kullanabilirsiniz. Ne zaman, uygulayan nesneler <xref:System.Dynamic.IDynamicMetaObjectProvider> Gözcü penceresi, dinamik bir düğüm eklenir görünüm değerlendirilir. Dinamik görünüm düğümü nesne üyeleri gösterir, ancak üyelerinin değerlerini düzenlenmesine izin vermiyor.  
  
 Dinamik nesneler aşağıdaki özellikleri desteklenmez:  
  
-   Bileşik işleçleri `+=`, `-=`, `%=`, `/=`, ve `*=`  
  
-   Sayısal atamalar ve tür bağımsız değişkeni atamalar da dahil olmak üzere birçok atamaları  
  
-   Yöntem çağrıları ikiden fazla bağımsız değişken  
  
-   Özellik alıcıları ikiden fazla bağımsız değişken  
  
-   Özellik ayarlayıcıları bağımsız değişkenlerle  
  
-   Bir dizin oluşturucu atama  
  
-   Boole işleçleri `&&` ve `||`  
  
### <a name="anonymous-methods"></a>Anonim Yöntemler  
 Yeni anonim yöntemler oluşturulması desteklenmiyor.  
  
## <a name="visual-basic---unsupported-expressions"></a>Visual Basic - desteklenmeyen ifadeler  
  
### <a name="dynamic-objects"></a>Dinamik nesneler  
 Statik olarak dinamik olarak yazılan hata ayıklayıcı ifadelerinde değişkenleri kullanabilirsiniz. Ne zaman, uygulayan nesneler [IDynamicMetaObjectProvider arabirimi](http://msdn.microsoft.com/Library/e887a72d-ebe2-4253-a7e8-3d8d05154647) Gözcü penceresi, dinamik bir düğüm eklenir görünüm değerlendirilir. Dinamik görünüm düğümü nesne üyeleri gösterir, ancak üyelerinin değerlerini düzenlenmesine izin vermiyor.  
  
 Dinamik nesneler aşağıdaki özellikleri desteklenmez:  
  
-   Bileşik işleçleri `+=`, `-=`, `%=`, `/=`, ve `*=`  
  
-   Sayısal atamalar ve tür bağımsız değişkeni atamalar da dahil olmak üzere birçok atamaları  
  
-   Yöntem çağrıları ikiden fazla bağımsız değişken  
  
-   Özellik alıcıları ikiden fazla bağımsız değişken  
  
-   Özellik ayarlayıcıları bağımsız değişkenlerle  
  
-   Bir dizin oluşturucu atama  
  
-   Boole işleçleri `&&` ve `||`  
  
### <a name="local-constants"></a>Yerel sabitleri  
 Yerel sabitleri desteklenmez.  
  
### <a name="import-aliases"></a>İçeri aktarma diğer adları  
 İçeri aktarma diğer adları desteklenmez.  
  
### <a name="variable-declarations"></a>Değişken bildirimleri  
 Windows hata ayıklayıcısında açık yeni değişkenleri bildiremezsiniz. Bununla birlikte, içinde yeni örtük değişkenleri atayabilirsiniz **hemen** penceresi. Örtük bu değişkenleri hata ayıklama oturumu için kapsamlı ve hata ayıklayıcı dışında erişilebilir değildir. Örneğin, deyim `o = 5` örtük olarak yeni bir değişken oluşturur `o` ve 5 değerini atayın. Türü örtük böyle değişkenlerdir **nesne** türü hata ayıklayıcı tarafından çıkarsanabileceği sürece.  
  
### <a name="unsupported-keywords"></a>Desteklenmeyen anahtar sözcükler  
  
-   `AddressOf`  
  
-   `End`  
  
-   `Error`  
  
-   `Exit`  
  
-   `Goto`  
  
-   `On Error`  
  
-   `Resume`  
  
-   `Return`  
  
-   `Select/Case`  
  
-   `Stop`  
  
-   `SyncLock`  
  
-   `Throw`  
  
-   `Try/Catch/Finally`  
  
-   `With`  
  
-   Namespace veya modülü düzey anahtar sözcükler gibi `End Sub` veya `Module`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ içindeki Biçim belirticileri](../debugger/format-specifiers-in-cpp.md)   
 [Context işleci (C++)](../debugger/context-operator-cpp.md)   
 [C# içindeki Biçim belirticileri](../debugger/format-specifiers-in-csharp.md)   
 [Sözde değişkenler](../debugger/pseudovariables.md)