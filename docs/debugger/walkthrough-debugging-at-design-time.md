---
title: Tasarım zamanında - Visual Studio hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f1235e6360ccc5f6c0677f7ec9acb1dd85cad226
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39180184"
---
# <a name="debug-at-design-time-in-visual-studio"></a>Visual Studio'da tasarım zamanında hata ayıklama

Tasarım sırasında kod hata ayıklaması yapmak isteyebilirniz bazı senaryolarda, uygulama çalışırken yerine zaman. Bunu kullanarak yapabilirsiniz **hemen** penceresi. Veri bağlama kodunu gibi başka bir kod ile etkileşime giren XAML kod hatası ayıklamak istiyorsanız kullanabileceğiniz **hata ayıklama** > **iliştirme** Bunu yapmak için.
  
### <a name="debug-at-design-time-using-the-immediate-window"></a>Komut penceresi kullanarak tasarım zamanında hata ayıklama  

Visual Studio kullanabileceğiniz **hemen** uygulamanız çalışmıyorken bir işlevi veya alt yordamı yürütmek için penceresi. İşlev veya alt yordam bir kesme noktası içeriyorsa, Visual Studio uygun noktada yürütmeyi keser. Ardından, programınızın durumunu incelemek için hata ayıklayıcı penceresini kullanabilirsiniz. Bu özellik tasarım zamanında hata ayıklama çağrılır.  

Visual Basic'te, aşağıdaki örnek, ancak **hemen** penceresi C# ve C++ uygulamalarında da desteklenir.
  
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
  
2.  Okuma, satırında bir kesme noktası ayarlamak `s="Add BreakPoint Here"`.  
  
3.  Açık **hemen** penceresi (**hata ayıklama** > **Windows** > **hemen**) ve aşağıdakileri yazın penceresi: `?MyFunction<enter>`  
  
4.  Kesme noktalarına isabet ettirilmedi ve çağrı yığını doğru olduğunu doğrulayın.  
  
5.  Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, yine de tasarım modunda olduğunu doğrulayın.  
  
6.  Aşağıdakileri yazın **hemen** penceresi: `?MyFunction<enter>`  
  
7.  Aşağıdakileri yazın **hemen** penceresi: `?MySub<enter>`  
  
8.  Kesme noktasına isabet ve statik değişkenin değerini inceleyin doğrulayın `i` içinde **Yereller** penceresi. Bu değeri 3 olmalıdır.  
  
9. Çağrı yığınını doğru olduğundan emin olun.  
  
10. Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, yine de tasarım modunda olduğunu doğrulayın.  

## <a name="debug-at-design-time-from-the-xaml-designer"></a>XAML Tasarımcısı'ndan tasarım zamanında hata ayıklama

XAML Tasarımcısı'nda bazı bildirim temelli veri bağlama senaryoları arkasındaki kod hatalarını ayıklamak yararlı olabilir.

1. Projenizde, yeni bir XAML sayfası gibi ekleyin *temp.xaml*. Yeni XAML sayfası boş bırakın. 

1. Çözümünüzü derleyin.

1. Açık *temp.xaml*, Tasarımcı yükler (*UwpSurface.exe* bir UWP uygulamasında veya *XDesProc.exe*) için buna sonraki adımlarda ekleyebilirsiniz. 

1. Visual Studio'nun yeni bir örneğini açın. Yeni örnekte, Aç **iliştirme** iletişim kutusu (**hata ayıklama** > **iliştirme**) ayarlayın **ekleme** doğru kod türüne gibi alan **yönetilen kod (CoreCLR)** veya doğru kod türüne göre .NET sürümünüzü. Doğru Tasarımcı işlemi listeden seçip **iliştirme**.

    UWP için 16299 hedefleyen projeler oluşturun veya üstü, Tasarımcı işlemi *UwpSurface.exe*. WPF veya UWP 16299 önceki sürümleri için tasarımcı işlemidir *XDesProc.exe*.

1. İşleme bağlı olsa da, projeye geçiş yapmak, hata ayıklamak istediğiniz arkasındaki kod açın ve bir kesme noktası ayarlayın.

1. Son olarak, veri bağlama içeren XAML kodu içeren sayfasını açın.

    Örneğin, tasarım zamanında bir TextBlock bağlar aşağıdaki XAML için tür dönüştürücüsü kodda bir kesme noktası ayarlayabilirsiniz.

    ```xaml
    <TextBlock Text="{Binding title, ConverterParameter=lower, Converter={StaticResource StringFormatConverter}, Mode=TwoWay}"  />
    ```
   Sayfa yüklendiğinde, kesme noktasına ulaşılır.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/getting-started-with-the-debugger.md)
