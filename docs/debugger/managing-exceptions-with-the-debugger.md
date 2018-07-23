---
title: Özel durumlar Visual Studio hata ayıklayıcısı ile yönetme | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.exceptions
- vs.debug.exceptions.find
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- run-time errors
- exception handling, during debugging
- errors [debugger]
- debugger, runtime errors
- On Error-style error handlers
- exceptions, Win32
- run-time errors, debugging
- Win32, exceptions
- run time, exceptions
- error handling
- debugging [Visual Studio], exception handling
- common language runtime, exceptions
- native run-time checks
- exceptions, debugging
ms.assetid: 43a77fa8-37d0-4c98-a334-0134dbca4ece
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c514458d6b7e8cfd4837ca907d14055af8a624ce
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39180224"
---
# <a name="manage-exceptions-with-the-debugger-in-visual-studio"></a>Özel durumlar Visual Studio hata ayıklayıcısı ile yönetme

Bir özel durum bir program yürütüldüğü sırada gerçekleşen bir hata durumu göstergesidir. Hata ayıklayıcı kesmek hangi özel durumları (veya özel durumların kümeleri) söyleyebilir ve hangi noktada hata ayıklayıcının istediğiniz (hata ayıklayıcı keserse, size burada özel durumun oluştuğu gösterir). Ayrıca, ekleyin veya özel durumları silebilirsiniz. Çözümünü Visual Studio'da Aç **hata ayıklama > Windows > özel durum ayarları** açmak için **özel durum ayarları** penceresi. 

Olabilir ve yanıt için en önemli özel durum işleyicileri sağlamanız gerekir, ancak her zaman yürütme bazı özel durumlar için hata ayıklayıcının yapılandırma bilmeniz önemlidir.
  
Ne zaman hata ayıklayıcının çıkış penceresinde bir özel durum iletisi yazar. bir özel durum oluşur. Aşağıdaki durumlarda yürütmeyi Kes:  
  
-   Ne zaman bir özel durum oluşturulur ve işlenmezse.  
  
-   Ne zaman hata ayıklayıcı herhangi bir işleyici çağrılmadan önce yürütmeyi kesmek için yapılandırılır.  
  
-   Ayarladıysanız [yalnızca kendi kodum](../debugger/just-my-code.md), ve hata ayıklayıcının kullanıcı kodunda işlenmemiş bir özel durumla kesmek için yapılandırılır.  
  
> [!NOTE]
>  ASP.NET hata sayfalarını bir tarayıcıda gösteren bir üst düzey özel durum işleyicisine sahiptir. Bu yürütme sürece kesmez **yalnızca kendi kodum** açıktır. Bir örnek için bkz. [kullanıcının işlemediği özel durumları devam etmek için hata ayıklayıcı ayarlama](../debugger/managing-exceptions-with-the-debugger.md#BKMK_UserUnhandled) aşağıda.  
  
> [!NOTE]
>  Üzerinde hata stili hata işleyicilerini kullansanız bile, bir Visual Basic uygulamasında hata ayıklayıcı tüm hataları özel durumlar olarak yönetir.    
  
## <a name="tell-the-debugger-to-break-when-an-exception-is-thrown"></a>Bir özel durum oluştuğunda hata ayıklayıcının söyleyin  
Hata ayıklayıcı nerede bir özel durum, bir noktada yürütmeyi kesebilirsiniz bir işleyici çağrılmadan önce özel durumu incelemek için bir fırsat sunar.  
  
İçinde **özel durum ayarları** penceresi (**hata ayıklama > Windows > özel durum ayarları**), özel durumlar kategorisi için düğümü genişletin (örneğin, **ortak dil çalışma zamanı özel durumları**, .NET özel durumları anlamına gelir) ve o kategorideki belirli bir özel durum için onay kutusunu seçin (örneğin **System.AccessViolationException**). Bir tüm özel durumlar kategorisi belirleyebilirsiniz.  
  
![AccessViolationException işaretli](../debugger/media/exceptionsettingscheckaccess.png "ExceptionSettingsCheckAccess")  

> [!TIP]
> Belirli özel durumları kullanarak bulabilirsiniz **arama** penceresinde **özel durum ayarları** araç çubuğunu veya kullanım için belirli ad alanlarını filtrelemek için arayın (örneğin **System.IO**).
  
Bir özel durum seçerseniz **özel durum ayarları** penceresi, hata ayıklayıcı yürütme olup, işlenmiş işlenmemiş veya bağımsız olarak özel durumu atılır her yerde bozar. Bu noktada bir özel durum bir ilk fırsat özel durum olarak adlandırılır. Örneğin, birkaç senaryo şunlardır:  
  
*  Aşağıdaki C# konsol uygulamasında, Main yöntemi oluşturur bir **AccessViolationException** içinde bir `try/catch` engelle:  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        try  
        {  
            throw new AccessViolationException();  
            Console.WriteLine("here");  
        }  
        catch (Exception e)  
        {  
            Console.WriteLine("caught exception");  
        }  
        Console.WriteLine("goodbye");  
    }  
    ```  
  
     Varsa **AccessViolationException** iade **özel durum ayarları**, hata ayıklayıcı yürütme bu kodu çalıştırdığınızda üzerinde bozar `throw` satır. Ardından, yürütme devam edebilirsiniz. Konsol, iki satır görüntülenmesi gerekir:  
  
    ```cmd
    caught exception  
    goodbye  
    ```  
  
     ancak dotnetclıtools'u görüntülemiyor `here` satır.  
  
*  Bir C# konsol uygulaması iki yöntem, bir özel durum oluşturur ve bunu işleyen bir yöntem ve bir ikinci yöntem aynı özel durum oluşturur ve onu işlemiyor sahip bir sınıf ile bir sınıf kitaplığı başvuruyor:  
  
    ```csharp 
    public class Class1  
    {  
        public void ThrowHandledException()  
        {  
            try  
            {  
                throw new AccessViolationException();  
            }  
            catch (AccessViolationException ave)  
            {  
                Console.WriteLine("caught exception" + ave.Message);  
            }  
        }  
  
        public void ThrowUnhandledException()  
        {  
            throw new AccessViolationException();  
        }  
    }  
    ```  
  
     Konsol uygulaması Main() yöntemi aşağıda verilmiştir:  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        Class1 class1 = new Class1();  
        class1.ThrowHandledException();  
        class1.ThrowUnhandledException();  
    }  
    ```  
  
     Varsa **AccessViolationException** iade **özel durum ayarları**, hata ayıklayıcı yürütme bu kodu çalıştırdığınızda üzerinde bozar `throw` hem de satır  **ThrowHandledException()** ve **ThrowUnhandledException()**.  
  
 Özel durum ayarlarını varsayılan ayarlara geri yüklemek istiyorsanız, tıklayabilirsiniz **geri** araç çubuğunda:  
  
 ![Özel durum Ayarları'nda Varsayılanları Geri Yükle](../debugger/media/restoredefaultexceptions.png "RestoreDefaultExceptions")  
  
##  <a name="BKMK_UserUnhandled"></a> Kullanıcı tarafından işlenmeyen özel durumları devam etmek için hata ayıklayıcının işlemi durdurmasını  
 .NET veya JavaScript kodu ile hata ayıklaması yapıyorsanız [yalnızca kendi kodum](../debugger/just-my-code.md), başka bir yere işlenir ancak kullanıcı kodunda işlenmemiş özel durumları değil hata ayıklayıcının işlemi durdurmasını sağlayabilirsiniz.  
  
1.  İçinde **özel durum ayarları** penceresinde penceresinde sağ tıklatıp ardından seçerek, bağlam menüsünü açın **sütunları göster**. (Kapalı durumunda **yalnızca kendi kodum**, bu komut görmezsiniz.)  
  
2.  Adlı ikinci bir sütun görmelisiniz **ek eylemler**. Bu sütunda görüntülenir **kullanıcı kodu tarafından işlenmediğinde devam** belirli özel durumlarda, bu özel durum kullanıcı kodunda işlenmemiş ancak harici kod işlenir, hata ayıklayıcı kesmez anlamına gelir.  
  
3.  Ya da belirli bir özel durum için bu ayarı değiştirebilirsiniz (özel durum, sağ tıklatın ve seçin ve seçimini seçin **kullanıcı kodunda işlenmediğinde devam**) veya özel durumlar (örneğin, tüm ortak bir tüm kategorisi Dil çalışma zamanı özel durumları).  
  
 Örneğin, ASP.NET web uygulamaları için bir HTTP 500 durum kodu dönüştürerek özel durumları işleme ([özel durum işleme ASP.NET API](http://www.asp.net/web-api/overview/error-handling/exception-handling)), hangi değil yardımcı olabilir, özel durumun kaynağı belirlemek için. Aşağıdaki örnekte, kullanıcı kodu çağrıda `String.Format()` oluşturan bir <xref:System.FormatException>. Yürütme aşağıdaki gibi ayırır:  
  
 ![Kullanıcı keser&#45;unhanlded özel durum](../debugger/media/exceptionunhandledbyuser.png "ExceptionUnhandledByUser")  
  
## <a name="add-and-delete-exceptions"></a>Ekleme ve özel durumları silme  
 Ekleme ve özel durumları silebilirsiniz. Herhangi bir türde özel durum özel'i seçip tıklayarak herhangi bir kategoride silebilirsiniz **Sil** düğmesine (eksi işareti) **özel durum ayarları** araç çubuğunu veya özel durum sağ tıklayın ve seçme **Sil** bağlam menüsünden. Bir özel durum siliniyor, bu durum oluştuğunda hata ayıklayıcının kesintiye uğratacağını değil denetlenmeyen, özel durum olarak aynı etkiye sahiptir.  
  
 Bir özel durum eklemek için: içinde **özel durum ayarları** penceresinde özel durum kategorileri birini seçin (örneğin, **ortak dil çalışma zamanı**) tıklayıp **Ekle** düğmesi. Özel durumun bir ad yazın (örneğin. **System.UriTemplateMatchException**). Özel durum listesine (alfabetik sırada) eklenir ve otomatik olarak denetlenir.  
  
 GPU bellek erişimi özel durumlarını, JavaScript çalışma zamanı özel durumları veya Win32 özel durumlar kategorisi için bir özel durum eklemek istiyorsanız, hata kodu ve bunun yanı sıra açıklama eklemeniz gerekir.  
  
> [!TIP]
>  İmlanızı kontrol edin! **Özel durum ayarları** penceresini değil eklenen bir özel durum varlığını denetleyin. Yazarsanız, bu nedenle **Sytem.UriTemplateMatchException**, bir giriş için başka bir özel durum alırsınız (için **System.UriTemplateMatchException**).  
  
 Bunlar için belirli bir çözümü uygulamak için özel durum ayarları çözümün .suo dosyasında kalır. Belirli bir özel durum ayarları çözümlerinde yeniden kullanamazsınız. Bu noktada, eklenen özel durumlar kalıcıdır; Silinen bir özel durum değildir. Diğer bir deyişle, bir özel durum, yakın ekleyin ve çözümü yeniden açın ve özel durum kalmaya devam eder. Ancak, bir özel durum silin ve çözümü Kapat/yeniden, özel durum yeniden görünür.  
  
 **Özel durum ayarları** penceresi, C# ancak Visual Basic'de genel özel durum türlerini destekler. Özel durumlar gibi kesmek `MyNamespace.GenericException<T>`, özel durum olarak eklemelisiniz **MyNamespace.GenericException'1**. Diğer bir deyişle, böyle bir özel durum oluşturduysa:  
  
```csharp  
public class GenericException<T> : Exception  
{  
    public GenericException() : base("This is a generic exception.")  
    {  
    }  
}  
```  
  
 Özel durum ekleyebilirsiniz **özel durum ayarları** şöyle:  
  
 ![Genel özel durumu ekleniyor](../debugger/media/addgenericexception.png "AddGenericException")  

## <a name="add-conditions-to-an-exception"></a>Bir özel durum koşulları ekleme

Özel durumlarda koşulları ayarlayabilirsiniz **özel durum ayarları** iletişim kutusu. Şu anda desteklenen koşullar dahil etmek veya hariç tutmak için bir özel durum için modül adlarını içerir. Modül adlarını koşul olarak ayarlayarak, yalnızca belirli kod modülleri üzerinde özel durum için kesme seçebilir veya belirli modüller hakkında en son önleyebilirsiniz.

> [!NOTE]
> Yeni bir özel durum koşulları ekleme [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Koşullu özel durumlar eklemek için **koşulu Düzenle** simgesi özel durum Ayarları iletişim kutusunda veya özel durum sağ tıklatın ve seçin **koşulları Düzenle**.

![Bir özel durum koşullara](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durumdan sonra yürütmeye devam etme](../debugger/continuing-execution-after-an-exception.md)   
 [Nasıl yapılır: özel durumdan sonra sistem kodunu İnceleme](../debugger/how-to-examine-system-code-after-an-exception.md)   
 [Nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](../debugger/how-to-use-native-run-time-checks.md)   
 [C çalışma zamanı kitaplığını kullanmadan çalışma zamanı kullanarak denetler](../debugger/using-run-time-checks-without-the-c-run-time-library.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/getting-started-with-the-debugger.md)
