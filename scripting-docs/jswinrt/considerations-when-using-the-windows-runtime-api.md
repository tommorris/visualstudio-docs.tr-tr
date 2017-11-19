---
title: "Windows çalışma zamanı API kullanmayla ilgili konular | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: JavaScript, Windows Runtime API
ms.assetid: 2f56d70c-c80d-4876-8e6a-8ae031d31c22
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 693b3dac9def5533417638c3ec1c0de8db1d5fe3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="considerations-when-using-the-windows-runtime-api"></a>Windows çalışma zamanı API kullanmayla ilgili konular
JavaScript'te Windows çalışma zamanı API neredeyse her öğenin kullanabilirsiniz. Ancak, bazı yönlerini göz önünde bulundurmanız gereken Windows çalışma zamanı öğeleri JavaScript gösterimini vardır.  
  
> [!IMPORTANT]
>  C++'ta Windows çalışma zamanı bileşenleri oluşturma hakkında daha fazla bilgi için C# veya Visual Basic ve JavaScript içinde tüketen bkz [C++'da Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp) ve [C# Windows çalışma zamanı bileşenleri oluşturma ve Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).  
  
## <a name="special-cases-in-the-javascript-representation-of-windows-runtime-types"></a>Windows çalışma zamanı türleri JavaScript gösterimini özel durumlarda  
  
-   Dizeleri: Başlatılmamış bir dize için bir Windows çalışma zamanı yöntemi "undefined" dizesi ve ayarlamak bir dize olarak geçirilen `null` "null" dizesini geçirilir. (Bu doğrudur her bir `null` veya `undefined` değeri dizeye yüklenen.) Windows çalışma zamanı yönteme bir dize geçirmeden önce boş dize olarak başlatması gerekir ("").  
  
-   Arabirimleri: JavaScript'te Windows çalışma zamanı arabirimi uygulanamıyor.  
  
-   Diziler: JavaScript dizilerde yeniden boyutlandırma yöntemler Windows çalışma zamanı dizilerinde işe yaramazsa şekilde Windows çalışma zamanı diziler yeniden boyutlandırılabilir, değildir.  
  
-   Diziler: bir Windows çalışma zamanı yönteme bir JavaScript dize değeri geçirirseniz, dizi kopyalanır. Windows çalışma zamanı yöntemi dizi veya üyelerini değiştirmek ve JavaScript uygulamanızı döndürün mümkün değil. Yazılmış diziler ancak kullanabilirsiniz (örneğin, [ınt32array nesnesi](../javascript/reference/int32array-object.md)), hangi değil kopyalanır.  
  
-   Yapıları: Windows çalışma zamanı yapıları JavaScript'te nesneleridir. Windows çalışma zamanı yöntemi için bir Windows çalışma zamanı yapısı geçirmek istiyorsanız, yapısıyla örneği yok `new` anahtar sözcüğü. Bunun yerine, bir nesne oluşturun ve ilgili üyeleri ve değerlerini ekleyin. Üyelerin adlarını ortası durumda olmalıdır: `SomeStruct.firstMember`.  
  
-   Nesneleri: JavaScript nesneleri yönetilen kod nesneleri ile aynı değildir (`System.Object`). JavaScript nesne gerektiren bir Windows çalışma zamanı yöntemi geçiremezsiniz bir `System.Object`.  
  
-   Nesne Kimliği: Çoğu durumda, nesneleri geçirilen geri ve İleri JavaScript ve Windows çalışma zamanı arasında değiştirmeyin. JavaScript altyapısı bilinen nesne haritasını tutar. Windows Çalışma Zamanı Modülü nesnenin döndürdüğünde karşı harita eşleşen ve yeni bir nesne yoksa, oluşturulur. Windows çalışma zamanı yöntemleri tarafından döndürülen arabirimleri temsil eden nesneler için aynı yordamı izler. Özel durumlar iki tür vardır:  
  
    -   Bir Windows Çalışma Zamanı Modülü döndürülen nesneleri çağrısı ve ardından, eklenen yeni (expando) özellikleri vardır, bu geri Windows çalışma zamanı geçirildiğinde yeni özellikleri korumaz. Ancak, varolan nesne eşleşen çünkü bunlar JavaScript uygulamasını döndürüldüğünde, döndürülen nesne expando özelliklerine sahip.  
  
    -   Yapılar ve Windows çalışma zamanı temsilcileri daha önce kullanılan yapılar veya temsilciler aynı tanımlanamıyor. Bir yapı veya temsilci döndürülen her zaman, yeni bir başvuru alır.  
  
-   Ad çakışmaları: birden çok Windows Çalışma Zamanı Modülü arabirimler üyeleri aynı adlara sahip olabilir. (Olabilen bir çalışma zamanı sınıf veya arabirim gösterimini) tek bir JavaScript nesnesinde birleştirilir, üyeleri tam olarak nitelenmiş adlar ile temsil edilir. Aşağıdaki sözdizimini kullanarak bu üyeleri çağırabilirsiniz: `Class["MemberName"](parameter)`.  
  
     Aşağıdaki kod, iki arabirim çizim yöntemine sahip ve bir çalışma zamanı sınıf hem arabirimlerini uygular.  
  
    ```cpp#  
    namespace CollisionExample {  
        interface InterfaceA  
        {  
            HRESULT Draw([in] Int32 a);  
        }  
        interface InterfaceB  
        {  
            HRESULT Draw([in] HString a);  
        }  
        runtimeclass ExampleObject {  
          interface InterfaceA  
          interface InterfaceB  
        }  
    }  
    ```  
  
     İşte nasıl JavaScript'te Yukarıdaki kod çağırabilir.  
  
    ```JavaScript  
    var example = new ExampleObject();  
    example["CollisionExample.InterfaceA.draw"](12);  
    example["CollisionExample.InterfaceB.draw"]("hello");  
    ```  
  
-   `Out`Parametreler: birden çok Windows çalışma zamanı yöntemi varsa, `out` parametreleri, JavaScript yöntemi bir JavaScript nesne dönüş değeri olarak ve nesne karşılık özellikleri varsa `out` parametresi. Örneğin, aşağıdaki Windows çalışma zamanı imzası c++ göz önünde bulundurun.  
  
    ```cpp#  
    void ExampleMethod(  
      [OutAttribute] char^ first,   
      [OutAttribute] char^ second  
    )  
    ```  
  
     Bu imza JavaScript sürümüdür:  
  
    ```JavaScript  
    var returnValue = exampleMethod();  
  
    ```  
  
     Bu örnekte, `returnValue` iki alanı olan bir JavaScript nesnesi: `first` ve `second`.  
  
-   Statik üyeler: Windows çalışma zamanı statik üyeleri ve örnek üyeleri tanımlar. JavaScript'te, Windows çalışma zamanı sınıf veya arabirim ile ilişkili nesne statik üyeler eklenir.  
  
    ```JavaScript  
    // Static method.   
    var accel = Windows.Devices.Sensors.Accelerometer.getDefault();   
    // Instance method.   
    var reading = accel.getCurrentReading();            
    ```  
  
 Windows çalışma zamanı temel türleri JavaScript gösterimini hakkında daha fazla bilgi için bkz: [JavaScript gösterimi Windows çalışma zamanı tür](../jswinrt/javascript-representation-of-windows-runtime-types.md).