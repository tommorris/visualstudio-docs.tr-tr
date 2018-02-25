---
title: "Tasarım zamanında - Visual Studio hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 33e0210023de05047957e7fbf55a8f970fda19d9
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="debug-at-design-time-in-visual-studio"></a>Visual Studio tasarım zamanında hata ayıklama

Bazı senaryolarda, tasarım sırasında kodda hata ayıklama isteyebilirsiniz yerine uygulama çalışırken zaman. Kullanarak bunu yapabilirsiniz **hemen** penceresi. Veri bağlama kod gibi diğer kod ile etkileşime giren XAML kodda hata ayıklama istiyorsanız kullanabileceğiniz **hata ayıklama** > **ekleme işlemi için** Bunu yapmak için.
  
### <a name="debug-at-design-time-using-the-immediate-window"></a>Komut penceresi kullanarak tasarım zamanında hata ayıklama  

Visual Studio'yu kullanabilirsiniz **hemen** uygulamanızı çalışırken bir işlevi veya alt yordama yürütmek için penceresi. İşlev veya alt yordama bir kesme noktası içeriyorsa, Visual Studio uygun noktada yürütme çalışmamasına neden olur. Hata ayıklayıcı windows sonra programın durumunu incelemek için de kullanabilirsiniz. Bu özellik, tasarım zamanında hata ayıklama adı verilir.  

Aşağıdaki örnek Visual Basic'te aynıdır ancak **hemen** penceresi C# ve C++ uygulamalarında da desteklenir.
  
1.  Bir Visual Basic konsol uygulamasına aşağıdaki kodu yapıştırın:  
  
    ```vb  
    Module Module1  
  
        Sub Main()  
            MySub()  
        End Sub  
  
        Function MyFunction() As Decimal  
            Static i As Integer  
            i = i + 1  
            Dim s As String  
  
            s = "Add Breakpoint here"  
            Return 4  
        End Function  
  
        Sub MySub()  
            MyFunction()  
        End Sub  
    End Module  
    ```  
  
2.  Okuma ve satırında bir kesme noktası belirleyerek `s="Add BreakPoint Here"`.  
  
3.  Açık **hemen** penceresi (**hata ayıklama** > **Windows** > **hemen**) ve aşağıdakileri yazın Pencere: `?MyFunction<enter>`  
  
4.  Kesme noktası isabet aldı ve çağrı yığını doğru olduğundan emin olun.  
  
5.  Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, hala Tasarım modunda olup olmadığını ve doğrulayın.  
  
6.  Aşağıdakileri yazın **hemen** penceresi: `?MyFunction<enter>`  
  
7.  Aşağıdakileri yazın **hemen** penceresi: `?MySub<enter>`  
  
8.  Kesme noktası isabet ve statik değişkenin değerini inceleyin doğrulayın `i` içinde **Yereller** penceresi. 3 değeri olmalıdır.  
  
9. Çağrı yığını doğru olduğundan emin olun.  
  
10. Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, hala Tasarım modunda olup olmadığını ve doğrulayın.  

## <a name="debug-at-design-time-from-the-xaml-designer"></a>XAML Tasarımcısı'ndan tasarım zamanında hata ayıklama

XAML Tasarımcısı'nda bazı bildirim temelli veri bağlama senaryoları arkasında kodundan hata ayıklama yararlı olabilir.

1. Projenizde, yeni bir XAML sayfa gibi ekleyin *temp.xaml*. Yeni XAML sayfası boş bırakın. 

1. Çözümünüzü derleyin.

1. Açık *temp.xaml*, Tasarımcı yükler (*UwpSurface.exe* bir UWP uygulamasında veya *XDesProc.exe*), sonraki adımlarda iliştirebilirsiniz şekilde. 

1. Visual Studio yeni bir örneğini açın. Yeni örneği açın **ekleme işlemi için** iletişim kutusu (**hata ayıklama** > **ekleme işlemi için**) ayarlayın **ekleme** doğru kodunu türü gibi alanında **yönetilen kod (CoreCLR)** veya doğru kod türü, .NET sürüm. Doğru Tasarımcı işlemi listeden seçip **Attach**.

    UWP için proje hedefleme 16299 yapı veya üstünü Tasarımcı işlemidir *UwpSurface.exe*. WPF veya UWP sürümleri 16299 Geri'yi için tasarımcı işlemidir *XDesProc.exe*.

1. İşleme bağlı olsa da, projenize geçmek, hata ayıklama istediğiniz arkasındaki kod açın ve bir kesme noktası ayarlayın.

1. Son olarak, veri bağlama içerir XAML kodu içeren sayfasını açın.

    Örneğin, bir TextBlock tasarım zamanında bağlar aşağıdaki XAML için tür dönüştürücüsünü kodda bir kesme noktası ayarlayabilirsiniz.

    ```xaml
    <TextBlock Text="{Binding title, ConverterParameter=lower, Converter={StaticResource StringFormatConverter}, Mode=TwoWay}"  />
    ```
   Sayfa yüklendiğinde kesme noktası isabet.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)
