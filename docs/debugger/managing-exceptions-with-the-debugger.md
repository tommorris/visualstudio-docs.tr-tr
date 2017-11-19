---
title: "Özel durumlar Visual Studio hata ayıklayıcısı ile yönetme | Microsoft Docs"
ms.custom: 
ms.date: 04/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "35"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0504ba8229e67284d4f54032dbbce3cef42d6e8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="manage-exceptions-with-the-debugger-in-visual-studio"></a>Özel durumlar Visual Studio hata ayıklayıcısı ile yönetme

Bir özel durum bir program yürütüldüğü sırada oluşan bir hata durumu bir göstergesidir. Bu noktada istediğiniz ayırmak için hata ayıklayıcı ve hangi özel durumları (veya özel durumları kümesi) üzerinde ayırmak hata ayıklayıcı anlayabilirsiniz (hata ayıklayıcı böldüğünde size burada özel durum oluştu gösterir). Ayrıca, ekleyebilir veya özel durumlarını silin. Çözümü Visual Studio'da Aç kullanmak **hata ayıklama > Windows > özel ayarları** açmak için **Exception ayarlarını** penceresi. 

Yanıt için en önemli özel durum işleyicileri sağlaması gerekir ve kullanabilirsiniz, ancak yürütme bazı özel durumlar için her zaman ayırmak için hata ayıklayıcı yapılandırma bilmeniz önemlidir.
  
Ne zaman hata ayıklayıcı çıktı penceresinde bir özel durum iletisi Yazar bir özel durum oluşur. Aşağıdaki durumlarda, yürütme kesilebilir:  
  
-   Ne zaman bir özel durum oluşur ve değil gerçekleştirilir.  
  
-   Ne zaman hata ayıklayıcı herhangi bir işleyicisini çağrılmadan önce yürütme ayırmak için yapılandırılır.  
  
-   Ayarlamış olmanız durumunda [sadece kendi kodumu](../debugger/just-my-code.md), ve hata ayıklayıcısı kullanıcı kodunda işlenmemiş bir özel durumla ayırmak için yapılandırılır.  
  
> [!NOTE]
>  ASP.NET hata sayfaları bir tarayıcıda gösteren üst düzey özel durum işleyicisi vardır. Bu yürütme sürece bozmadığından **sadece kendi kodumu** açıktır. Bir örnek için bkz: [kullanıcının işlemediği özel durumları devam etmek için hata ayıklayıcı ayarı](../debugger/managing-exceptions-with-the-debugger.md#BKMK_UserUnhandled) aşağıda.  
  
> [!NOTE]
>  Hata stili hata işleyicilerinde kullansanız bile, bir Visual Basic uygulamasında hata ayıklayıcı tüm hataları özel durumlar olarak yönetir.    
  
## <a name="tell-the-debugger-to-break-when-an-exception-is-thrown"></a>Bir özel durum yakalandığında ayırmak için hata ayıklayıcı söyleyin  
Hata ayıklayıcı yürütme yeri bir özel durum, bir noktada bozabilir, özel durum işleyici çağrılmadan önce incelemek için bir fırsat vermiş.  
  
İçinde **Exception ayarlarını** penceresi (**hata ayıklama > Windows > özel ayarları**), özel durumların bir kategori düğümünü genişletin (örneğin, **ortak dil çalışma zamanı özel durumları**, .NET özel durumlarını anlamına gelir) ve belirli bir özel durum Bu kategoride onay kutusunu seçin (örneğin **System.AccessViolationException**). Özel durumların tüm bir kategorisini de seçebilirsiniz.  
  
![AccessViolationException işaretli](../debugger/media/exceptionsettingscheckaccess.png "ExceptionSettingsCheckAccess")  

> [!TIP]
> Kullanarak belirli özel durumların bulabilirsiniz **arama** penceresinde **Exception ayarlarını** araç veya belirli ad alanları için filtrelemek için Ara kullanın (örneğin **System.IO**).
  
Bir özel durum seçerseniz **Exception ayarlarını** penceresi, hata ayıklayıcı yürütme olup, işlenen işlenmemiş veya bağımsız olarak özel durum atılır her yerde bozar. Bu noktada özel bir ilk fırsat özel durum adı verilir. Örneğin, birkaç senaryo şunlardır:  
  
*  Main yöntemi aşağıdaki C# konsol uygulamasındaki oluşturur bir **AccessViolationException** içinde bir `try/catch` engelle:  
  
    ```CSharp  
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
  
     Varsa **AccessViolationException** iade **Exception ayarlarını**, bu kod hata ayıklayıcı yürütmede çalıştırdığınızda üzerinde bozar `throw` satır. Ardından, yürütme devam edebilirsiniz. Konsol iki satır görüntülenmelidir:  
  
    ```  
    caught exception  
    goodbye  
    ```  
  
     Ancak, görüntülenmez `here` satır.  
  
*  Bir C# konsol uygulaması bir sınıf kitaplığı iki yöntem, bir özel durum oluşturur ve bunu işleyen bir yöntem ve aynı özel durum oluşturur ve bunu işlemiyor ikinci bir yöntemi olan bir sınıfı ile başvuruyor:  
  
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
  
     Konsol uygulaması Main() yöntemi şöyledir:  
  
    ```CSharp  
    static void Main(string[] args)  
    {  
        Class1 class1 = new Class1();  
        class1.ThrowHandledException();  
        class1.ThrowUnhandledException();  
    }  
    ```  
  
     Varsa **AccessViolationException** iade **Exception ayarlarını**, bu kod hata ayıklayıcı yürütmede çalıştırdığınızda üzerinde bozar `throw` hem de satır  **ThrowHandledException()** ve **ThrowUnhandledException()**.  
  
 Özel durum ayarlarına ayarlarına geri yüklemek istiyorsanız, tıklayabilirsiniz **geri** araç çubuğunda:  
  
 ![Özel durum ayarlarında Varsayılanları Geri Yükle](../debugger/media/restoredefaultexceptions.png "RestoreDefaultExceptions")  
  
##  <a name="BKMK_UserUnhandled"></a>Kullanıcının işlemediği özel durumları devam etmek için hata ayıklayıcı söyleyin  
 Hata ayıklama ile .NET veya JavaScript kodu varsa [sadece kendi kodumu](../debugger/just-my-code.md), içinde kullanıcı kodu işlenmez ancak başka bir yere işlenir kesilecek değil için hata ayıklayıcı anlayabilirsiniz.  
  
1.  İçinde **Exception ayarlarını** penceresinde penceresinde sağ tıklayıp ardından seçerek bağlam menüsünü açmak **sütunları göster**. (Kapalı durumunda **sadece kendi kodumu**, bu komut görmezsiniz.)  
  
2.  Adlı ikinci bir sütun görmelisiniz **ek eylemleri**. Bu sütun görüntüler **devam kullanıcı kodu tarafından işlenmemiş zaman** üzerinde özel durum, bu özel durum kullanıcı kodunda işlenmemiş ancak dış kodda ele hata ayıklayıcı bozmadığından anlamına gelir.  
  
3.  Belirli bir özel durum için bu ayarı değiştirebilirsiniz (özel durum, sağ tıklatın ve seçin ve seçimini seçin **devam kullanıcı kodunda işlenemeyen zaman**) veya bir özel durum (örneğin, tüm ortak kategorisinin tamamını için Dil çalışma zamanı özel durumları).  
  
 Örneğin, ASP.NET web uygulamaları için bir HTTP 500 durum kodu dönüştürerek özel durumları işleme ([özel durum işleme ASP.NET API'sindeki](http://www.asp.net/web-api/overview/error-handling/exception-handling)), hangi değil yardımcı olabilir, özel durumun kaynağı belirlemek için. Aşağıdaki örnekte, kullanıcı kodu çağrıda bulunur `String.Format()` oluşturur, bir <xref:System.FormatException>. Yürütme aşağıdaki gibi ayırır:  
  
 ![Kullanıcı &#45;sonları; unhanlded özel durum](../debugger/media/exceptionunhandledbyuser.png "ExceptionUnhandledByUser")  
  
## <a name="add-and-delete-exceptions"></a>Ekleme ve özel durumları silme  
 Ekleme ve özel durumlarını silin. Herhangi bir özel durum türü özel seçerek ve tıklayarak herhangi bir kategoride silebilirsiniz **silmek** düğmesine (eksi işareti) **Exception ayarlarını** araç veya özel durum sağ tıklayarak ve seçme **silmek** ve bağlam menüsünden. Bir özel durum silinmesi bu oluştuğunda hata ayıklayıcı kesintiye uğrar değil, olan denetlenmeyen, özel durum olarak aynı etkiye sahiptir.  
  
 Bir özel durum ekleyin: içinde **Exception ayarlarını** penceresinde, özel durum kategorileri birini seçin (örneğin, **ortak dil çalışma zamanı**) tıklatıp **Ekle** düğmesi. Özel durum adını (örneğin, yazın **System.UriTemplateMatchException**). Özel durum (alfabetik sırada) listesine eklenir ve otomatik olarak denetlenir.  
  
 Bir özel durum GPU bellek erişimi özel durumları, JavaScript çalışma zamanı özel durumları veya Win32 özel durum kategorileri eklemek istiyorsanız, açıklama yanı sıra, hata kodu eklemeniz gerekir.  
  
> [!TIP]
>  Yazım denetimi yapın! **Exception ayarlarını** penceresinden eklenen bir özel durum varlığını denetlemek değil. Yazarsanız, bunu **Sytem.UriTemplateMatchException**, bu özel durum için bir giriş elde edersiniz (değil **System.UriTemplateMatchException**).  
  
 Belirli bir çözümü uygulamak için özel ayarları çözümün .suo dosyasında kalıcıdır. Bir özel durum ayarları çözümleri arasında yeniden kullanamazsınız. Bu noktada, yalnızca eklenen özel durumlar kalıcı; Silinen özel durumlar değildir. Diğer bir deyişle, bir özel durum, Kapat ekleyin ve çözümü kapatıp yeniden açın ve özel durum var olmaya devam edecektir. Ancak, bir özel durum silin ve çözüm Kapat/yeniden açın, özel durum görünecektir.  
  
 **Exception ayarlarını** penceresi, C# ancak Visual Basic'de genel özel durum türlerini destekler. Özel durumlar gibi ayırmak için `MyNamespace.GenericException<T>`, özel durum olarak eklemelisiniz **MyNamespace.GenericException'1**. Diğer bir deyişle, böyle bir özel durum oluşturduysa:  
  
```CSharp  
public class GenericException<T> : Exception  
{  
    public GenericException() : base("This is a generic exception.")  
    {  
    }  
}  
```  
  
 Özel durum ekleyebilirsiniz **Exception ayarlarını** şöyle:  
  
 ![Genel özel durum ekleme](../debugger/media/addgenericexception.png "AddGenericException")  

## <a name="add-conditions-to-an-exception"></a>Bir özel durum koşulları ekleme

Özel durumları üzerinde koşulları ayarlayabilirsiniz **Exception ayarlarını** iletişim kutusu. Şu anda desteklenen koşullar dahil etmek veya hariç özel durumuna modül adlarını içerir. Modül adlarını koşul olarak ayarlayarak, özel durum yalnızca belirli kod modülleri için bölüneceği seçebilir veya belirli modüller hakkında en son önleyebilirsiniz.

> [!NOTE]
> Yeni bir özel durum koşulları ekleme[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Koşullu özel durumlar eklemek için **koşulu Düzenle** özel ayarlar iletişim kutusu simgesine kutusuna veya özel durum sağ tıklatın ve seçin **koşulları Düzenle**.

![Bir özel durum koşullara](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durumdan sonra yürütmeye devam](../debugger/continuing-execution-after-an-exception.md)   
 [Nasıl yapılır: özel durumdan sonra sistem kodunu İnceleme](../debugger/how-to-examine-system-code-after-an-exception.md)   
 [Nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](../debugger/how-to-use-native-run-time-checks.md)   
 [C çalışma zamanı kitaplığını kullanmadan çalışma zamanı kullanarak denetler](../debugger/using-run-time-checks-without-the-c-run-time-library.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)