---
title: 'Öğretici: hata ayıklama yönetilen ve yerel kodu (karma mod)'
description: Yerel bir .NET Core veya .NET Framework uygulamasına karışık modda hata ayıklama kullanarak DLL'den hata ayıklama öğrenin
ms.custom: ''
ms.date: 04/27/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- mixed mode debugging
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: 1f34f6af0a98e71f5feb910f84e8d67ada051ae9
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057043"
---
# <a name="tutorial-debug-managed-and-native-code-in-visual-studio"></a>Öğretici: Visual Studio yönetilen ve yerel kodda hata ayıklama

Visual Studio karışık modda hata ayıklama denir hata ayıklama sırasında birden fazla hata ayıklayıcı türü etkinleştirmenize olanak sağlar. Bu öğreticide, tek bir hata ayıklama oturumunda hem yönetilen hem de yerel kodda hata ayıklamak için seçenekleri ayarlayın. Bu öğretici, yönetilen bir uygulamadan yerel kod hata ayıklamak gösterilmektedir, ancak ters da yapabilirsiniz ve [yönetilen koddan yerel uygulama hata ayıklama](../debugger/how-to-debug-in-mixed-mode.md). Hata ayıklayıcı ayrıca diğer tür karma mod, hata ayıklama gibi hata ayıklama destekler [Python ve yerel kodu](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md) ve komut dosyası hata ayıklayıcısı gibi ASP.NET uygulama türleri kullanma.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Basit bir yerel DLL oluşturma
> * DLL çağırmak için basit bir .NET Core veya .NET Framework uygulaması oluşturma
> * Hata ayıklayıcı Başlat
> * Yönetilen bir uygulama içinde kesme noktası isabet
> * Yerel kod içine adım

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio yüklü olmalıdır ve **C++ ile masaüstü geliştirme** iş yükü.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

    İş yükü yüklenir ancak tıklatın Visual Studio zaten gerektiğinde **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **Node.js geliştirme** iş yükü, ardından **Değiştir**.

* Ya da olmalıdır **.NET masaüstü geliştirme** iş yükü veya **.NET Core platformlar arası** yüklü iş yükü, oluşturmak istediğiniz hangi uygulamanın türü üzerinde bağlı olarak.

## <a name="create-a-simple-native-dll"></a>Basit bir yerel DLL oluşturma

1. Visual Studio'da, **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunda, seçin **Visual C++**, **genel** yüklenmiş şablonlar bölümünden ve Orta bölmede seçin **boş proje** .

1. İçinde **adı** alanında, yazın **karma mod Debugging** tıklatıp **Tamam**.

    Visual Studio Çözüm Gezgini'nde sağ bölmede görünür boş proje oluşturur.

1. Çözüm Gezgini'nde sağ **kaynak dosyaları** C++ düğümünde proje ve ardından **Ekle** > **yeni öğe**ve ardından **C++ dosya (.cpp)**. Dosyaya ad verin **karma Mode.cpp**ve seçin **Ekle**.

    Visual Studio yeni C++ dosyasına ekler.

1. Aşağıdaki kodu kopyalayın *karma Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. Çözüm Gezgini'nde sağ **üstbilgi dosyaları** C++ düğümünde proje ve ardından **Ekle** > **yeni öğe**ve ardından  **Üstbilgi dosyası (.h)**. Dosyaya ad verin **karma Mode.h**ve seçin **Ekle**.

    Visual Studio yeni üstbilgi dosyası ekler.

1. Aşağıdaki kodu kopyalayın *karma Mode.h*:

    ```cpp
    #ifndef MIXED_MODE_MULTIPLY_HPP
    #define MIXED_MODE_MULTIPLY_HPP

    extern "C"
    {
        __declspec(dllexport) int __stdcall mixed_mode_multiply(int a, int b) {
            return a * b;
        }
    }
    #endif
    ```

1. Hata ayıklama araç çubuğundan seçin bir **hata ayıklama** yapılandırma ve **herhangi bir CPU** platform olarak mı, yoksa .NET Core, seçin **x64** platform olarak.

    > [!NOTE]
    > .NET Core üzerinde seçin **x64** platform olarak. .NET core her zaman 64-bit modunda çalışır, böylece bu gereklidir.

1. Çözüm Gezgini'nde, proje düğümüne sağ tıklayın (**karma mod Debugging**) ve **özellikleri**.

1. İçinde **özellikleri** sayfasında, **yapılandırma özellikleri** > **bağlayıcı** > **Gelişmiş**, ve ardından **No giriş noktası** aşağı açılan listesinden, **Hayır**. Daha sonra ayarlarını uygulayın.

1. İçinde **özellikleri** sayfasında, **yapılandırma özellikleri** > **genel**ve ardından **dinamik kitaplığı (.dll)** gelen **yapılandırma türü** alan. Daha sonra ayarlarını uygulayın.

    ![Yerel bir DLL'e geçiş](../debugger/media/mixed-mode-set-as-native-dll.png)

1. Projeye sağ tıklayın ve seçin **hata ayıklama** > **yapı**.

    Projenin hatasız oluşturması gerekir.

## <a name="create-a-simple-net-framework-or-net-core-app-to-call-the-dll"></a>DLL çağırmak için basit bir .NET Framework veya .NET Core uygulaması oluşturma

1. Visual Studio'da, **dosya** > **yeni** > **proje**.

1. Uygulama kodunuz için bir şablon seçin.

    .NET Framework içinde **yeni proje** iletişim kutusunda, seçin **Visual C#**, **Windows Masaüstü** yüklenmiş şablonlar bölümünden, ardından Ortabölmesindeseçin **Konsol uygulaması (.NET Framework)**.

    .NET Core için de **yeni proje** iletişim kutusunda, seçin **Visual C#**, **.NET Core** yüklenmiş şablonlar bölümünden ve Orta bölmede seçin  **Konsol uygulaması (.NET Core)**.

1. İçinde **adı** alanında, yazın **Mixed_Mode_Calling_App** tıklatıp **Tamam**.

    Visual Studio Çözüm Gezgini'nde sağ bölmede görünür konsol projesi oluşturur.

1. İçinde *Program.cs*, varsayılan kodu aşağıdaki kodla değiştirin:

    ```csharp
    using System;
    using System.Runtime.InteropServices;

    namespace Mixed_Mode_Calling_App
    {
        public class Program
        {
            // Replace the file path shown here with the
            // file path on your computer. For .NET Core, the typical (default) path
            // for a 64-bit DLL might look like this:
            // C:\Users\username\source\repos\Mixed-Mode-Debugging\x64\Debug\Mixed-Mode-Debugging.dll
            // Here, we show a typical path for a DLL targeting the **Any CPU** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed-Mode-Debugging\Debug\Mixed-Mode-Debugging.dll", EntryPoint =
            "mixed_mode_multiply", CallingConvention = CallingConvention.StdCall)]
            public static extern int Multiply(int x, int y);
            public static void Main(string[] args)
            {
                int result = Multiply(7, 7);
                Console.WriteLine("The answer is {0}", result);
                Console.ReadKey();
            }
        }
    }
    ```

## <a name="configure-mixed-mode-debugging-net-framework"></a>Karışık mod hata ayıklaması (.NET Framework) yapılandırma

1. Çözüm Gezgini'nde yönetilen sağ **Mixed_Mode_Calling_App** proje ve seçin **başlangıç projesi olarak ayarla**.

1. Yönetilen sağ **Mixed_Mode_Calling_App** proje ve ardından **özellikleri**ve ardından **hata ayıklama** sol bölmede. Seçin **yerel kod hata ayıklamayı etkinleştir**ve ardından değişiklikleri kaydetmek için Özellikler sayfasını kapatın.

    ![Karışık mod hata ayıklamayı etkinleştir](../debugger/media/mixed-mode-enable-native-code-debugging.png)

## <a name="configure-mixed-mode-debugging-net-core"></a>Karışık mod hata ayıklaması (.NET Core) yapılandırma

Visual Studio 2017 çoğu sürümlerini .NET Core kullanarak uygulama yerel kod için karışık modda hata ayıklama etkinleştirmelisiniz *launchSettings.json* yerine dosya **özellikleri** sayfası. Bu özellik için kullanıcı Arabirimi güncelleştirmeleri izlemek için bu bkz [GitHub sorunu](https://github.com/dotnet/project-system/issues/1125).

1. Açık *launchSettings.json* dosyasını *özellikleri* klasör. Varsayılan olarak, dosyanın bu konumda bulabilirsiniz.

    *C:\Users\<kullanıcı adı > \source\repos\Mixed_Mode_Calling_App\Properties*

    Dosya mevcut değilse proje özelliklerini açın (yönetilen sağ **Mixed_Mode_Calling_App** Çözüm Gezgini'nde proje ve seçin **özellikleri**). Bir geçici değişiklik **hata ayıklama** sekmesinde ve projenizi yapılandırın. Yaptığınız değişikliği geri alın.

1. İçinde *lauchsettings.json* dosya, aşağıdaki özellik Ekle:

    ```csharp
    "nativeDebugging": true
    ```

    Bu nedenle, örneğin, dosyanız aşağıdakine benzeyebilir:

    ```csharp
    {
      "profiles": {
        "Mixed_Mode_Calling_App": {
          "commandName": "Project",
          "nativeDebugging": true
        }
      }
    }
    ```

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Bir kesme noktası ayarlayın ve hata ayıklayıcısı başlatın

1. C# projesinde, açık *Program.cs* ve sol kenar boşluğunda tıklayarak aşağıdaki kod satırında bir kesme noktası ayarlayın:

    ```csharp
    int result = Multiply(7, 7);
    ```

    Kırmızı bir daire kesme noktası ayarlama belirtmek için sol kenar boşluğunda görünür.

1. Tuşuna **F5** (**hata ayıklama** > **hata ayıklamayı Başlat**) hata ayıklayıcısını başlatın.

    Hata ayıklayıcı ayarladığınız kesme noktası duraklatır. Sarı bir ok nerede Hata Ayıklayıcı duraklatılmış durumda gösterir.

## <a name="step-into-native-code"></a>Yerel kod içine adım

1. Yönetilen uygulama duraklatıldı olsa da, basın **F11** (**hata ayıklama** > **Step Into**).

    Yerel kod ile üst bilgi dosyasını açar ve burada hata ayıklayıcı duraklatıldı sarı ok bakın.

    ![Yerel kod içine adım](../debugger/media/mixed-mode-step-into-native-code.png)

    Artık, kümesi gibi şeyler ve kesme noktası isabet ve değişkenleri inceleyin.

1. Kendi değeri görmek için değişkenlerinden gelin.

1. Bakmak **otomobiller** ve **Yereller** değişken ve değerlerinin görmek için windows.

    Hata ayıklayıcıda duraklatıldı olsa da, diğer hata ayıklayıcı özellikleri gibi kullanabilir **izleme** penceresi ve **çağrı yığını** penceresi.

1. Tuşuna **F11** yeniden hata ayıklayıcı bir satır ilerlemek için.

1. Tuşuna **SHIFT + F11** (**hata ayıklama** > **Step Out**) uygulama yürütme devam etmek ve yeniden yönetilen uygulamada duraklatmak için.

1. Tuşuna **F5** uygulamaya devam etmek için.

    Tebrikler! Karışık mod hata ayıklaması üzerinde öğreticisini tamamladınız.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, yönetilen bir uygulamadan yerel kod hata ayıklama karışık modda hata ayıklama etkinleştirme öğrendiniz. Diğer hata ayıklayıcı özelliklerine genel bakış için aşağıdaki makaleye bakın:

> [!div class="nextstepaction"]
> [Hata ayıklayıcıya ilk bakış](../debugger/debugger-feature-tour.md)
