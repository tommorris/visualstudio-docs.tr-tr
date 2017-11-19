---
title: "Edge ile Eski altyapıların karşılaştırması | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbc7df6c-0bc9-48f5-b9ad-b9ed31c42f92
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50947cbd619f086daecc1e09f88a4b238a36ee41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="targeting-edge-vs-legacy-engines-in-jsrt-apis"></a>Edge ile Eski Altyapıların Karşılaştırması
İki farklı Chakra motorları desteklemek için yeni bir sınır işleme altyapısı destekleyen Windows 10'ın tarayıcı stratejisini ile hizalanır, Chakra için (JavaScript altyapısı) yaptık değişikliklerden biri Windows 10'daki başlangıç şöyledir:  
  
-   Eski Chakra altyapısı (olarak da bilinir *eski altyapısı* veya jscript9.dll aşağıdaki) ile birlikte ve Internet Explorer 11 destekler. Bu altyapı zamanında dondurulmuş ve Win8.1/IE11 sürümünden temelde değişmeden kalır.  
  
-   Yeni Chakra altyapısı (olarak da bilinir *kenar altyapısı* veya chakra.dll aşağıdaki) ile birlikte ve Windows 10'da Microsoft Edge yeni tarayıcı destekler. Bu altyapı sürekli olarak güncelleştirilir ve bir "yaşam" destekleyecek [kenar](http://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) altyapısı. Yaşam kenar altyapısı eski motoru, kenar altyapısı İleri içine kabul etmek için sürüm oluşturma komut dosyası işlevlerin herhangi bir biçimde taşımak değil olduğunu gösterir.  
  
 JavaScript çalışma zamanı barındırma (JsRT) API kullanarak bir uygulama oluştururken, eski veya kenar altyapısı hedeflemeyi seçebilirsiniz.  
  
-   Geriye dönük uyumluluk mevcut uygulamalarınızın vurgulamak gerekiyorsa, eski altyapısı hedefleyin.  
  
-   Uygulamanızı ileriye doğru arama ve Destek yeni JavaScript özellikleri olarak olmasını istiyorsanız (örneğin, ECMAScript 6) kullanıma sunulduklarında, kenar altyapısı hedefleyin.  
  
 Bu konuda farklı altyapıları hedef anlatmaktadır ayrıntıları içerir.  
  
## <a name="target-your-preferred-version"></a>Tercih edilen sürümünüzü hedef  
 Bir uygulama oluştururken, kenar altyapısı veya eski altyapısını destekleyen JsRT sürümü seçebilirsiniz. Yukarıdaki yönergeleri JsRT sürümü seçebilirsiniz. Bu farklılıklar uyum sağlamak için aşağıdaki değişiklikler yapılmıştır `JsCreateRuntime`, `JsCreateContext`, ve `JsStartDebugging`.  
  
 İçin `JsCreateRuntime`:  
  
-   Eski altyapısı hedeflerken `JsRuntimeVersionEdge` numaralandırma değeri kullanım dışı bırakıldı ve bir iletiyi kullanarak önerir `JsRuntimeVersionInternetExplorer11` yerine değer.  
  
-   Kenar altyapısı hedeflerken gelen sürüm parametresi atlanırsa `JsCreateRuntime` işlevi.  
  
    ```cpp  
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
    ```  
  
 İçin `JsCreateContext` ve `JsStartDebugging`:  
  
-   Eski altyapısı hedeflerken `IDebugApplication` arabirimi kendi uzaktan olmayan hata ayıklama yöntemleri sağlamak için kullanılır. Hata ayıklama amacıyla, `JsCreateContext` ve `JsStartDebugging` işlevleri ele `IDebugApplication` parametre olarak.  
  
-   Kenar altyapısı hedeflerken `IDebugApplication` arabirimi kullanım dışıdır. Yetenek Visual Studio hata ayıklayıcısı ile uygulaması gerek kalmadan ayıklamasını ve Chakra altyapısı etkinleştirir yerel `IDebugApplication` kullanıcıdan. Arabirim artık bir parametredir `JsCreateContext` ve `JsStartDebugging` sonucunda.  
  
 Eski altyapısındaki önceki API'leri imzalar aşağıdaki gibidir:  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);  
```  
  
 Kenar altyapısı önceki API'leri imzalar aşağıdaki gibidir:  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging();  
```  
  
## <a name="compile-for-your-preferred-version-using-visual-c"></a>Visual C++ kullanarak tercih edilen sürümünüzün derleme  
 Visual C++ kullanırken, jsrt.h üstbilgi ekleyerek JsRT API'yi içeri aktarma ve o jsrt.lib bağlayıcı giriş dosyaları listenizde bulunduğundan emin olun:  
  
```cpp  
#include <jsrt.h>  
```  
  
 ![Bir bağlayıcı giriş dosyası olarak jsrt.lib ekleme](../chakra-hosting/media/js-chakra.png "JS_Chakra_")  
  
 Makro tanımlamanız gerekecek kenar altyapısı ikili hedeflemek istiyorsanız, `USE_EDGEMODE_JSRT` jsrt.h eklemeden önce ve jsrt.lib karşı bağlama yerine chakrart.lib karşı bağlanması gereken:  
  
```cpp  
#define USE_EDGEMODE_JSRT  
#include <jsrt.h>  
```  
  
 ![Bir bağlayıcı giriş dosyası olarak chakrart.lib ekleme](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting_")  
  
 Yeni bir uygulamayla başlatıyorsanız, artık JsRT API'sine karşı kod yazmaya başlamak hazırsınız.  
  
## <a name="compile-for-your-preferred-version-using-net"></a>.NET kullanarak tercih edilen sürümünüzün derleme  
 .NET ve P/Invoke kullanıyorsanız, jscript9.dll yerine chakra.dll almak için JsRT API [DllImport] bildirimlerinizde değiştirmeniz gerekir. Ayrıca, tanımını değiştirin `JsCreateRuntime` kaldırmak için `JsRuntimeVersion` parametre ve tanımını `JsCreateContext` ve `JsStartDebugging` kaldırmak için `IDebugApplication` parametresi.  
  
 Eski altyapısı için aşağıdaki kodu kullanın.  
  
```c#  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsCreateRuntime(  
    JsRuntimeAttributes attributes,  
    JsRuntimeVersion version,  
    JsThreadServiceCallback callback,  
    out JsRuntimeSafeHandle runtime  
);  
  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsCreateContext(  
    JsRuntimeSafeHandle runtime,  
    IDebugApplication debugApplication,  
    out JsContextRef newContext  
);   
  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsStartDebugging(  
    IDebugApplication debugApplication,  
);  
```  
  
 Kenar altyapısı için aşağıdaki kodu kullanın.  
  
```c#  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsCreateRuntime(  
    JsRuntimeAttributes attributes,  
    JsThreadServiceCallback callback,  
    out JsRuntimeSafeHandle runtime  
);  
  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsCreateContext(  
    JsRuntimeSafeHandle runtime,  
    out JsContextRef newContext  
);   
  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsStartDebugging();  
```  
  
> [!CAUTION]
>  İşlev işaretçisi el ile hazırlama varsa (gibi LoadLibrary/GetProcAddress aracılığıyla), yöntem bildirimlerini karışık kullanmayın, aksi takdirde uygulamanızı neden gibi beklenmeyen davranışlara neden olur yığın unbalance önemlidir çökmesine. İçeri aktarma kodunuzda bir genel arama ve değiştirme jscript9.dll örneklerinin gerçekleştirirseniz kaçırılması çünkü aynı sorun ortaya çıkar `version` bırakılmakta parametresi.  
  
## <a name="summary"></a>Özet  
 Windows 10'da JavaScript çalışma zamanı barındırma API'ları ikiye bölmek. Bu API artık bir "yaşam", dil özellikleri "yaşam" Microsoft Edge kenar altyapısı ile hizalanmış kenar altyapısı destekler. Yeni, şaşırtıcı yolları uygulamanızı genişletmek için ve var olan kod temeliniz modern Web yeteneklerini yararlanacak şekilde oluşturmak için bu özellikleri masaüstü veya mağazası uygulamaları yararlanabilirsiniz. Önceki sürümler arasındaki küçük farklılıklar olduğundan, ancak, kenar veya eski altyapısı hedeflerken şu noktalarını farkında olmanız gerekir.  
  
-   Uygulamanızın işlem başına yalnızca bir sürümü JsRT destekleyebilir.  
  
     Örneğin, bir kenar altyapısı çalışma zamanı ve ardından eski altyapısı çalışma zamanı oluşturmak ve bunları aynı işlem içinde düzgün çalışması için bekler. Bu desteklenmeyen ve ikinci dll dosyası yüklenemiyor gibi belgelenmemiş davranışlara neden.  
  
-   Temel alınan platform otomatik olarak güncelleştirildiğinde kenar altyapısı hedeflerken uygulamanızı beklenmedik bir şekilde yeni özellikler edinmeniz.  
  
     Örneğin, Internet Explorer 11 modu eski çalışma zamanı blok kapsamı değişken bildirimleri gibi destekleyen `let` ve `const`. Kenar altyapısı otomatik sürüm oluşturma davranışı standart daha önce blok kapsamı kuralları sahip değil, Internet Explorer 10 modunda çalışan code olsaydı platform otomatik olarak yükselten zaman başarısız başlatılmamış olabilir. Kullanmak için hangi çalışma zamanı modeli seçerken bu önemli bir unsur olmalıdır. Mümkün olduğunda kenar altyapısı hedeflemelidir inanıyoruz olsa da, gelecekte geçersiz hale gelebilir JavaScript kodu yapıları kullanma konusunda dikkatli olmalıdır.  
  
-   Windows mağazası JsRT yalnızca kenar altyapısı (chakra.dll) destekler. Sertifika uygulamaları jscript9.dll herhangi bir JsRT API'yi karşı bağlantı girişimi başarısız olur.  
  
-   Bildirimi karıştırmayın kritik `JsCreateRuntime`, `JsCreateContext`, ve `JsStartDebugging` jscript9.dll chakra.dll, arasındaki yığın imbalancing sonuçlanır olduğundan.  
  
     Gibi bir arama yaptığınız değil sürece yanlış beyandan kullanmaya çalışırsa, C ve C++ kullanırken, bir bağlayıcı hatası alırsınız `LoadLibrary` ve ardından `GetProcAddress`. .NET geliştiricilerinin değil Bu sorunu kolayca bulmak, böylece kodunuzu bu özelliği kullanırken iki kez kontrol edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript çalışma zamanı barındırma](../chakra-hosting/javascript-runtime-hosting.md)