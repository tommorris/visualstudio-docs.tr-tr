---
title: Kullanıcı kodu sadece kendi kodumu ile hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 0f0df097-bbaf-46ad-9ad1-ef5f40435079
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b59072f17ecfa810bec422770aeff24e0d8e2d99
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="specify-whether-to-debug-only-user-code-using-just-my-code-in-visual-studio"></a>Hata ayıklama yalnızca sadece kendi kodumu Visual Studio kullanarak kullanıcı kodu belirtin
Otomatik olarak sistem, framework ve diğer kullanıcı olmayan çağrıları adım ve bu çağrıları çağrı yığını penceresinde daraltmak için Visual Studio yapılandırabilirsiniz. Sağlar veya bu davranışı devre dışı bırakır özelliği adlı *sadece kendi kodumu*. Bu konu, sadece kendi kodumu C#, Visual Basic, C++ ve JavaScript projelerinde kullanmayı açıklar.

Çoğu programlama dili için sadece kendi kodumu varsayılan olarak etkindir.
  
##  <a name="BKMK_Enable_or_disable_Just_My_Code"></a> Etkinleştirmek veya sadece kendi kodumu devre dışı bırakma  
 Etkinleştirmek ya da sadece kendi kodumu devre dışı bırakmak için seçin **Araçlar > Seçenekler** Visual Studio menüsünde. İçinde **hata ayıklama** > **genel** düğümü seçin veya temizleyin **sadece kendi kodumu etkinleştir**.
  
 ![Seçenekler iletişim kutusundaki sadece kendi kodumu etkinleştir](../debugger/media/dbg_justmycode_options.png "DBG_JustMyCode_Options")  
  
> [!NOTE]
>  **Sadece kendi kodumu etkinleştir** tüm Visual Studio projeleri tüm dillerde uygulanan genel ayar bir ayardır.  
  
###  <a name="BKMK_Override_call_stack_filtering"></a> Çağrı yığını görünümlerde kullanıcı olmayan kod Göster  
 Çağrı yığını gibi göster görünümlerinde **çağrı yığını** ve **görevleri** windows, sadece kendi kodumu daraltır kullanıcı olmayan kod etiketli bir açıklamalı çerçeveye `[External Code]`. Daraltılmış çerçeveleri görüntülemek için seçin **Göster harici kod** çağrı yığını bağlam menüsünde görüntüler.

 ![Çağrı yığını penceresinde harici kod Göster](../debugger/media/dbg_justmycode_showexternalcode.png "DBG_JustMyCode_ShowExternalCode")
  
> [!NOTE]
>  **Göster harici kod** ayarı için geçerli kullanıcının profil oluşturucu kaydedildi. Kullanıcı tarafından açık olan tüm dillerdeki tüm projelere uygulanır.
  
##  <a name="BKMK__NET_Framework_Just_My_Code"></a> .NET framework yalnızca kendi kodum  
  
###  <a name="BKMK_NET_User_and_non_user_code"></a> Kullanıcı ve kullanıcı olmayan kod  
 Kullanıcı kodu kullanıcı olmayan koddan ayırt etmek için sadece kendi kodumu simge (.pdb) dosyalarını ve program iyileştirmeleri arar. Hata ayıklayıcı kodunun kullanıcı olmayan kodunu ikili en iyi duruma getirilmiş veya .pdb dosyası mevcut olmadığında olmasını göz önünde bulundurur.
  
 Hata ayıklayıcı My kodu dikkate üç öznitelikler de etkiler:  
  
-   <xref:System.Diagnostics.DebuggerNonUserCodeAttribute> hata ayıklayıcı uygulandığı kod kendi kodumu değil söyler.  
  
-   <xref:System.Diagnostics.DebuggerHiddenAttribute> Sadece kendi kodumu kapalı olsa bile hata ayıklayıcı kodundan gizler.  
  
-   <xref:System.Diagnostics.DebuggerStepThroughAttribute> koda adım yerine için uygulandığı kodlarda adım için hata ayıklayıcı söyler.  
  
 Diğer tüm kod kullanıcı kodu olarak kabul edilir.  
  
###  <a name="BKMK_NET_Stepping_behavior"></a> Davranış Adımlama  
 Olduğunda, **Step Into** (klavye kısayolu: F11) kullanıcı olmayan kodu, hata ayıklayıcı adımlarına kod üzerinde ileri kullanıcı bildirimi. Olduğunda, **Step Out** (klavye: Shift + F11), hata ayıklayıcı kodun sonraki satırında, kullanıcı için çalışır. Hiçbir kullanıcı kodu karşılaşıldı sonra yürütülmeye uygulama kadar yinelenir, bir kesme noktası isabet ya da bir özel durum oluşur.  
  
###  <a name="BKMK_NET_Breakpoint_behavior"></a> Kesme noktası davranışı  
 Sadece kendi kodumu etkinleştirildiğinde, seçebileceğiniz **bölün tüm** (klavye: Ctrl + Alt + Break) durdurup yürütme bir konumda söz konusu olduğunda görüntülenecek kullanıcı kodu yok. Bu durumda, Hayır kaynağı penceresi görüntülenir. Hata ayıklayıcı adım komutu ardından seçerseniz, kullanıcı kodu bir sonraki satıra alır.  
  
###  <a name="BKMK_NET_Exception_behavior"></a> Özel durum davranışı  
 Kullanıcı olmayan kodda işlenmeyen bir özel durum oluşursa, hata ayıklayıcı satırında burada özel durum oluşturuldu kullanıcı kodunda keser.  
  
 İlk fırsat özel durumlar için özel durum etkinleştirilirse, kullanıcı kod satırı yeşil vurgulanır. Çağrı yığını etiketli bir açıklamalı çerçeve görüntüler **[dış kodu]**.  
  
##  <a name="BKMK_C___Just_My_Code"></a> C++ yalnızca kendi kodum  
  
###  <a name="BKMK_CPP_User_and_non_user_code"></a> Kullanıcı ve kullanıcı olmayan kod  
 Sürüm davranışı çağrı yığını davranışını bağımsız olduğundan C++ sadece kendi kodumu .NET Framework ve JavaScript sadece kendi kodumu farklı değildir.  
  
 **Çağrı yığınları**  
  
 Varsayılan olarak, hata ayıklayıcı çağrı yığını windows olmayan kullanıcı kodunda olması için bu işlevler göz önünde bulundurur:  
  
-   Kendi simgeleri dosyasındaki kırpılmış kaynak bilgileriyle çalışır.  
  
-   İşlevler, simge dosyaları yığın çerçevesi karşılık gelen hiçbir kaynak dosyası olduğunu gösteriyor.  
  
-   Belirtilen işlevler `*.natjmc` dosyalar `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` klasör.  
  
 **Atlama**  
  
 Varsayılan olarak, yalnızca işlevler belirtilen `*.natstepfilter` dosyalar `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` klasörü kullanıcı olmayan kod olarak kabul edilir.  
  
 Kendi oluşturabilirsiniz `.natstepfilter` ve `.natjmc` atlama özelleştirmek ve çağrı yığını penceresi davranışı için `%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers`.  
  
###  <a name="BKMK_CPP_Stepping_behavior"></a> Davranış Adımlama  
 Olduğunda, **Step Into** (klavye kısayolu: F11) kullanıcı kodundan kullanıcı olmayan kodu, sonraki satırında, kullanıcı kodu için kod üzerinde hata ayıklayıcı adımları. Olduğunda, **Step Out** (klavye: Shift + F11), hata ayıklayıcı kodun sonraki satırında, kullanıcı için çalışır. Hiçbir kullanıcı kodu karşılaşıldı sonra yürütülmeye uygulama kadar yinelenir, bir kesme noktası isabet ya da bir özel durum oluşur.  
  
 Hata ayıklayıcı kullanıcı olmayan kodda bozarsa (örneğin kullanıcı olmayan kodda kesme tüm komut durursa), Adımlama kullanıcı olmayan kodda devam eder.  
  
###  <a name="BKMK_CPP_Exception_behavior"></a> Özel durum davranışı  
 Hata ayıklayıcı bir özel durum geldiğinde, kullanıcı veya kullanıcı olmayan kod olmasından bağımsız olarak özel durumunda durdurur. **Kullanıcı işlenmemiş** içinde seçenekleri **özel durumları** iletişim kutusu yok sayılır.  
  
###  <a name="BKMK_CPP_Customize_stepping_behavior"></a> Sürüm davranışını özelleştirme  
 Bunları kullanıcı olmayan kod olarak listeleniyor tarafından devralınırsa adım işlevleri belirtebilirsiniz `*.natstepfilter` dosyaları.  
  
-   Visual Studio makinenin tüm kullanıcıları için kullanıcı olmayan kodu belirtmek için .natstepfilter dosyasına ekleyin `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` klasör.  
  
-   Tek bir kullanıcı için kullanıcı olmayan kodu belirtmek için .natstepfilter dosyasına ekleyin `%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers` klasör.  
  
 .natstepfilter dosyaları, bu sözdizimi ile xml dosyalarıdır:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<StepFilter xmlns="http://schemas.microsoft.com/vstudio/debugger/natstepfilter/2010">  
    <Function>  
        <Name>FunctionSpec</Name>  
        <Action>StepAction</Action>  
    </Function>  
    <Function>  
        <Name>FunctionSpec</Name>  
        <Module>ModuleSpec</Module>  
        <Action>StepAction</Action>  
    </Function>  
</StepFilter>  
  
```  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|İşlev|Gerekli. Bir veya daha fazla işlevleri kullanıcı olmayan işlevleri olarak belirtir.|  
|`Name`|Gerekli. ECMA-262 eşleşmesi için tam işlevi adı belirterek normal ifade biçimlendirilmiş. Örneğin:<br /><br /> `<Name>MyNS::MyClass.*</Name>`<br /><br /> hata ayıklayıcı bildiren tüm yöntemler `MyNS::MyClass` kullanıcı olmayan kod kabul edilip. Eşleşme büyük/küçük harf duyarlıdır.|  
|`Module`|İsteğe bağlı. ECMA-262 işlevi içeren modülü tam yolunu belirtme normal ifade biçimlendirilmiş. Eşleşme büyük/küçük harf duyarlıdır.|  
|`Action`|Gerekli. Büyük küçük harfe duyarlı şu değerlerden biri:<br /><br /> -   `NoStepInto`  -eşleşen işlevi adım için hata ayıklayıcı söyler.<br />-   `StepInto`  -eşleşen İşlevler, adım için hata ayıklayıcı söyler diğer geçersiz kılma `NoStepInto` eşleşen işlevler için.|  
  
###  <a name="BKMK_CPP_Customize_call_stack_behavior"></a> Çağrı yığını davranışı özelleştirme  
 Modüller, kaynak dosyaları ve bunların belirterek çağrı yığınları kullanıcı olmayan kod olarak işlemek için işlevleri belirtebilirsiniz `*.natjmc` dosyaları.  
  
-   Visual Studio makinenin tüm kullanıcıları için kullanıcı olmayan kodu belirtmek için .natjmc dosyasına ekleyin `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` klasör.  
  
-   Tek bir kullanıcı için kullanıcı olmayan kodu belirtmek için .natjmc dosyasına ekleyin `%USERPROFILE%\My Documents\Visual Studio 2015\Visualizers` klasör.  
  
 .natjmc dosyaları, bu sözdizimi ile xml dosyalarıdır:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<NonUserCode xmlns="http://schemas.microsoft.com/vstudio/debugger/jmc/2015">  
  
  <!-- Modules -->  
  <Module Name="ModuleSpec" />  
  <Module Name="ModuleSpec" Company="CompanyName" />  
  
  <!-- Files -->  
  <File Name="FileSpec"/>  
  
  <!-- Functions -->  
  <Function Name="FunctionSpec" />  
  <Function Name="FunctionSpec" Module ="ModuleSpec" />  
  <Function Name="FunctionSpec" Module ="ModuleSpec" ExceptionImplementation="true" />  
  
</NonUserCode>  
  
```  
  
 **Modül öğesi öznitelikleri**  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Modül veya modülleri tam yolu. Windows joker karakterleri kullanabilirsiniz `?` (sıfır veya bir karakter) ve `*` (sıfır veya daha fazla karakter). Örneğin,<br /><br /> `<Module Name="?:\3rdParty\UtilLibs\*" />`<br /><br /> Tüm modüllerdeki işlemek için hata ayıklayıcı söyler `\3rdParty\UtilLibs` harici kod olarak herhangi bir sürücüdeki.|  
|`Company`|İsteğe bağlı. Yürütülebilir dosyada katıştırılmış modülü yayımlayan şirketin adı. Bu öznitelik modülleri belirsizliğini ortadan kaldırmak için kullanabilirsiniz.|  
  
 **Dosya öğesi öznitelikleri**  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Kaynak dosya veya dosyalar dış kodu olarak işlemek için tam yolu. Windows joker karakterleri kullanabilirsiniz `?` ve `*` yolunu belirtirken.|  
  
 **İşlev öğesi öznitelikleri**  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Dış kodu olarak işlemek için işlevi tam adı.|  
|`Module`|İsteğe bağlı. İşlevi içeren modülü tam yolu ve adı. Bu öznitelik, aynı ada sahip işlevleri belirsizliğini ortadan kaldırmak için kullanabilirsiniz.|  
|`ExceptionImplementation`|Ayarlandığında `true`, bu işlevi yerine bir özel durum belirtti işlevi çağrı yığını görüntüler.|  
  
##  <a name="BKMK_JavaScript_Just_My_Code"></a> JavaScript yalnızca kendi kodum  
  
###  <a name="BKMK_JS_User_and_non_user_code"></a> Kullanıcı ve kullanıcı olmayan kod  
 **Kod sınıflandırmaları**  
  
 JavaScript sadece kendi kodumu atlama ve çağrı yığını görünen kodu bu sınıflandırmalarını birinde sınıflandırarak denetler:  
  
|||  
|-|-|  
|**MyCode**|Sahip olduğunuz ve denetlediğiniz kullanıcı kodu.|  
|**LibraryCode**|Kullanıcı olmayan koddan düzenli olarak kullandığınız kitaplıkları ve uygulamanızın doğru (örneğin WinJS veya jQuery) çalışması için kullanır.|  
|**UnrelatedCode**|Uygulamanız, ancak içinde çalışıyor olabilecek kullanıcı olmayan kod yok sahibi ve uygulamanızı doğrudan düzgün çalışması için kullanmaz. (Örneğin, bu bir reklam reklamlar görüntüler SDK içerebilir.) UWP projelerinde, HTTP veya HTTPS URI uygulamanızdan yüklenen herhangi bir kod da UnrelatedCode olarak kabul edilir.|  
  
 JavaScript hata ayıklayıcı otomatik olarak bu tür kod sınıflandırır:  
  
-   Ana bilgisayar tarafından sağlanan için bir dize aktararak yürütülmeden betik `eval` işlevi sınıflandırılmış olarak **MyCode**.  
  
-   Bir dizeyi aktararak yürütülmeden betik `Function` Oluşturucusu sınıflandırılmış olarak **LibraryCode**.  
  
-   WinJS ya da Azure SDK'sı gibi bir framework Başvurusu'nda yer alan komut dosyası sınıflandırılmış olarak **LibraryCode**.  
  
-   Bir dizeyi aktararak yürütülmeden betik `setTimeout`, `setImmediate`, veya `setInterval` işlevleri sınıflandırılmış olarak **UnrelatedCode**.  
  
-   `%VSInstallDirectory%\JavaScript\JustMyCode\mycode.default.wwa.json` Diğer tüm Visual Studio JavaScript projeleri için kullanıcı ve kullanıcı olmayan kod belirtir.  
  
 Varsayılan sınıflandırmalar değiştirin ve belirli dosyaları sınıflandırabilir ve URL'ler ile adlı bir .json dosyası ekleyin `mycode.json` projenin kök klasöre.  
  
 Diğer tüm kod olarak sınıflandırılan **MyCode**.  
  
###  <a name="BKMK_JS_Stepping_behavior"></a> Davranış Adımlama  
  
-   Bir işlev kullanıcı değilse (**MyCode**) kod, **Step Into** (klavye kısayolu: F11) olarak davranan **Step Over** (klavye: F10).  
  
-   Kullanıcı olmayan bir adımı başlıyorsa (**LibraryCode** veya **UnrelatedCode**) geçici olarak atlama sadece kendi kodumu etkinleştirilmemişse gibi davranır sonra kod. Adım zaman geri kullanıcı kod, sadece kendi kodumu atlama yeniden etkinleştirilmiş.  
  
-   Bir adımı olduğunda (örneğin, olay işleyici son satırının üzerinde bir adımı gerçekleştirmeden) geçerli yürütme bağlamı bırakarak kullanıcı kodu sonuçları hata ayıklayıcı kullanıcı kodu sonraki yürütülen satırına durdurur. Örneğin, bir geri çağırmayı yürütür, **LibraryCode** kod hata ayıklayıcı kodun sonraki satırında, kullanıcı yürütür kadar devam eder.
  
-   **Step Out** (klavye: Shift + F11) kullanıcı kodun sonraki satırında durdurur. Hiçbir kullanıcı kodu karşılaşıldı sonra yürütülmeye uygulama kadar yinelenir, bir kesme noktası isabet ya da bir özel durum oluşur.  
  
###  <a name="BKMK_JS_Breakpoint_behavior"></a> Kesme noktası davranışı  
  
-   Kesme noktaları kodda ayarlama bu kodu sınıflandırma bağımsız olarak her zaman temas eder  
  
-   Varsa `debugger` anahtar sözcüğü karşılaştı:  
  
    -   **LibraryCode** kodu, hata ayıklayıcı her zaman keser.  
  
    -   **UnrelatedCode** kodu değil hata ayıklayıcıyı.  
  
###  <a name="BKMK_JS_Exception_behavior"></a> Özel durum davranışı  
 İşlenmeyen bir özel durum oluşması halinde:  
  
-   **MyCode** veya **LibraryCode** kodu, hata ayıklayıcı her zaman keser.  
  
-   **UnrelatedCode** kodunu ve **MyCode** veya **LibraryCode** çağrı yığını, hata ayıklayıcı sonları kodudur.  
  
 Özel durumlar iletişim kutusu üzerindeki özel durumu için etkin ilk fırsat özel durumlar ve özel durum **LibraryCode** veya **UnrelatedCode** kod:  
  
-   Özel durumun işlenip, hata ayıklayıcı kesme değil.  
  
-   Özel durum işlenmemiş, hata ayıklayıcı keser.  
  
###  <a name="BKMK_JS_Customize_Just_My_Code"></a> Yalnızca kendi kodum özelleştirme  
 Kullanıcı ve kullanıcı olmayan tek bir Visual Studio Proje kodunu sınıflandırmak için adlı bir .json dosyası ekleme `mycode.json` projenin kök klasöre.  
  
 Sınıflandırmaları bu sırayla gerçekleştirilir:  
  
1.  Varsayılan sınıflandırmalar  
  
2.  Sınıflandırmaları `%VSInstallDirectory%\JavaScript\JustMyCode\mycode.default.wwa.json` dosyası  
  
3.  Sınıflandırmaları `mycode. json` geçerli projenin dosya.  
  
 Her sınıflandırma adımdan önceki adımları geçersiz kılar. Bir .json dosyası, tüm anahtar değer çiftleri listesi gerekmez ve **MyCode**, **kitaplıkları**, ve **Unrelated** değerleri boş diziler olabilir.  
  
 Kod .json dosyalarımı şu sözdizimini kullanın:  
  
```json  
{  
    "Eval" : "Classification",  
    "Function" : "Classification",  
    "ScriptBlock" : "Classification",  
    "MyCode" : [  
        "UrlOrFileSpec",  
        . . .  
        "UrlOrFileSpec"  
    ],  
    "Libraries" : [  
        "UrlOrFileSpec",  
        . .  
        "UrlOrFileSpec"  
    ],  
    "Unrelated" : [  
        "UrlOrFileSpec",  
        . . .  
        "UrlOrFileSpec"  
    ]  
}  
  
```  
  
 **Eval, işlev ve ScriptBlock**  
  
 **Eval**, **işlevi**, ve **ScriptBlock** anahtar değer çifti belirlemek nasıl dinamik olarak oluşturulan kod sınıflandırılmış.  
  
|||  
|-|-|  
|**Değerlendirme sürümü**|Ana bilgisayar tarafından sağlanan için bir dize aktararak yürütülmeden betik `eval` işlevi. Varsayılan olarak, Eval komut dosyası olarak sınıflandırılır **MyCode**.|  
|**İşlevi**|Bir dizeyi aktararak yürütülmeden betik `Function` Oluşturucusu. Varsayılan olarak, işlev komut dosyası olarak sınıflandırılır **LibraryCode**.|  
|**ScriptBlock**|Bir dizeyi aktararak yürütülmeden betik `setTimeout`, `setImmediate`, veya `setInterval` işlevleri. Varsayılan olarak, ScriptBlock komut dosyası olarak sınıflandırılır **UnrelatedCode**.|  
  
 Değer şu anahtar sözcüklerden biri olarak değiştirebilirsiniz:  
  
-   `MyCode`  komut dosyası olarak sınıflandırır **MyCode**.  
  
-   `Library`  komut dosyası olarak sınıflandırır **LibraryCode**.  
  
-   `Unrelated`  komut dosyası olarak sınıflandırır **UnrelatedCode**.  
  
 **MyCode, kitaplıklar ve ilgisiz**  
  
 **MyCode**, **kitaplıkları**, ve **Unrelated** anahtar değer çifti URL'leri veya bir sınıflandırma dahil etmek istediğiniz dosyaları belirtin:  
  
|||  
|-|-|  
|**MyCode**|Bir dizi URL'leri veya olarak sınıflandırılan dosyalar **MyCode**.|  
|**Kitaplıkları**|Bir dizi URL'leri veya olarak sınıflandırılan dosyalar **LibraryCode**.|  
|**İlişkisiz**|Bir dizi URL'leri veya olarak sınıflandırılan dosyalar **UnrelatedCode**.|  
  
 Bir veya daha fazla url veya dosya dize içerebilir `*` sıfır veya daha fazla karakteri eşleştirmek karakter. `*` Normal ifade eşdeğerdir `.*`.