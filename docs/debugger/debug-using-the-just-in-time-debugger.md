---
title: Tam zamanında hata ayıklayıcı ile hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 07/06/17
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: ee4d79a5-a1d2-4418-a93f-dd57a53e1836
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa31d9d9b536a614cc1000f7c25ae6fbb5e4d510
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176447"
---
# <a name="debug-using-the-just-in-time-debugger-in-visual-studio"></a>Tam zamanında hata ayıklayıcı, Visual Studio kullanarak hata ayıklama
Visual Studio dışında çalışan bir uygulamada bir özel durum veya kilitlenme oluştuğunda just-In-Time hata ayıklama Visual Studio otomatik olarak başlatır. Bu, Visual Studio çalışmadığı zamanlarda uygulamanızı test edin ve bir sorun ortaya çıktığında, Visual Studio ile hata ayıklamayı başlatmak sağlar.

Just-In-Time hata ayıklama, Windows Masaüstü uygulamaları için çalışır. Evrensel Windows uygulamaları için çalışmaz ve Görselleştiriciler gibi yerel bir uygulama içinde barındırılan yönetilen kod için çalışmaz.

> [!TIP]
> Nasıl Just-ın-Time için yanıt bilmek istiyorsanız, hata ayıklayıcı, iletişim kutusu, bkz: [bu konuda](../debugger/just-in-time-debugging-in-visual-studio.md).

##  <a name="BKMK_Enabling"></a> Etkinleştirme veya devre dışı bırakma, Just-ın-Time hata ayıklama
Etkinleştirebilir veya tam zamanında Visual Studio'dan hata ayıklama devre dışı **Araçlar > Seçenekler** iletişim kutusu.

#### <a name="to-enable-or-disable-just-in-time-debugging"></a>Etkinleştirme veya devre dışı bırakma, Just-ın-Time hata ayıklama

1.  Visual Studio'yu yönetici ayrıcalıklarıyla açın (sağ tıklatın ve seçin **yönetici olarak çalıştır**).

    Etkinleştirme veya devre dışı Just-ın-Time hata ayıklama, bir kayıt defteri anahtarı ayarlar ve yönetici ayrıcalıkları, bu anahtarı değiştirmek için gerekebilir.

2. Üzerinde **Araçları** menüsünü tıklatın **seçenekleri**.

2.  İçinde **seçenekleri** iletişim kutusunda **hata ayıklama** düğümü.

3.  İçinde **hata ayıklama** düğümünü **Just-ın-Time**.

    ![JIT hata ayıklama devre dışı bırakmak veya etkinleştirmek](../debugger/media/dbg-jit-enable-or-disable.png "etkinleştirmek veya devre dışı JIT hata ayıklama")

4.  İçinde **temizleyintypes bu tür kod hata ayıklama** kutusunda seçin veya ilgili program türünü: **yönetilen**, **yerel**, veya **betik**.

5.  **Tamam**'ı tıklatın.

Visual Studio artık bilgisayarınızda yüklü olsa bile just-In-Time hata ayıklamayı hala etkin. Visual Studio yüklü değil, tam zamanında Visual Studio'dan hata ayıklama devre dışı bırakamazsınız **seçenekleri** iletişim kutusu. Bu durumda, tam zamanında hata ayıklama Windows kayıt defterini düzenleyerek devre dışı bırakabilirsiniz.

#### <a name="to-disable-just-in-time-debugging-by-editing-the-registry"></a>Kayıt defterini düzenleyerek devre dışı bırakma, Just-ın-Time hata ayıklama

1.  Üzerinde **Başlat** menü, arayın ve çalıştırın `regedit.exe`

2.  İçinde **Kayıt Defteri Düzenleyicisi'ni** penceresinde bulun ve aşağıdaki kayıt defteri girişleri silin:

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger

    -   HKEY_LOCAL_MACHINE\Software\Microsoft\\. NETFramework\DbgManagedDebugger

    ![JIT kayıt defteri anahtarı](../debugger/media/dbg-jit-registry.png "JIT kayıt defteri anahtarı")

3.  Bilgisayarınızı bir 64-bit işletim sistemi çalıştırıyorsa aşağıdaki kayıt defteri girdilerini de silin:

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\DbgManagedDebugger

4.  Yanlışlıkla silmemek veya herhangi bir kayıt defteri anahtarı değiştirmek için dikkatli olun.

5.  Kapat **Kayıt Defteri Düzenleyicisi'ni** penceresi.

#### <a name="to-enable-just-in-time-debugging-of-a-windows-form"></a>Etkinleştirme Just-ın-Time hata ayıklama için bir Windows formu

1.  Varsayılan olarak, Windows Forms uygulamaları program, kurtarabilirsiniz durumunda çalışmaya devam etmesini sağlar bir üst düzey özel durum işleyicisine sahiptir. Örneğin, Windows Forms uygulaması işlenmeyen bir özel durum oluşturursa, aşağıdakine benzer bir iletişim kutusu görürsünüz:

     ![WindowsFormsUnhandledException](../debugger/media/windowsformsunhandledexception.png "WindowsFormsUnhandledException")

     Bir Windows Forms uygulamasına etkinleştirme Just-ın-Time hata ayıklama için aşağıdaki ek adımları gerçekleştirmeniz gerekir:

2.  Ayarlama `jitDebugging` değerini `true` içinde `system.windows.form` machine.config bölümünde veya  *\<uygulama adı >*. exe.config dosyası:

    ```xml
    <configuration>
        <system.windows.forms jitDebugging="true" />
    </configuration>
    ```

3.  Bir C++ Windows Form uygulamasında de ayarlamalısınız `DebuggableAttribute` .config dosyasında ya da kodunuzda. Derleme yaparsanız [/zi](/cpp/build/reference/z7-zi-zi-debug-information-format) ve olmadan [/Og](/cpp/build/reference/og-global-optimizations), derleyici bu özniteliği sizin için ayarlar. Ancak, bir yayın olmayan yapılandırmada yapı hata ayıklamak istiyorsanız, bu kendiniz ayarlamanız gerekir. Bunu, aşağıdaki satırı uygulamanızın AssemblyInfo.cpp dosyasına olduğunuz ekleyerek yapabilirsiniz:

    ```cpp
    [assembly:System::Diagnostics::DebuggableAttribute(true, true)];
    ```

     Daha fazla bilgi için bkz. <xref:System.Diagnostics.DebuggableAttribute>.

## <a name="a-namebkmkusingjituse-just-in-time-debugging"></a><a name="BKMK_Using_JIT">Just-ın-Time hata ayıklamasını kullanın
 Bu bölüm, yürütülebilir bir özel durum oluşturduğunda ne olacağını gösterir.

 Visual Studio bu adımları izlemek için yüklü olması gerekir. Visual Studio yoksa, ücretsiz indirebileceğiniz [Visual Studio Community Edition](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15).

 Just-ın-Time emin olun. hata ayıklama [etkin](#BKMK_Enabling).

 Bu bölümün amacı doğrultusunda, C# konsol uygulaması Visual Studio'da oluşturur oluşturacağız bir [NullReferenceException](/dotnet/api/system.nullreferenceexception).

 Visual Studio'da C# konsol uygulaması oluşturma (**Dosya > Yeni > Proje > Visual C# > konsol uygulaması**) adlı **ThrowsNullException**. Visual Studio'da proje oluşturma hakkında daha fazla bilgi için bkz. [izlenecek yol: basit bir uygulama oluşturma](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md).

 Projeyi Visual Studio'da açıldığında, Program.cs dosyasını açın. Ana() yöntemi, bir çizgi konsola yazdırır ve ardından bir NullReferenceException oluşturur aşağıdaki kodla değiştirin:

```csharp
static void Main(string[] args)
{
    Console.WriteLine("we will now throw a NullReferenceException");
    throw new NullReferenceException("this is the exception thrown by the console app");
}
```

> [!IMPORTANT]
>  Çalışmak için bu yordamı sırayla bir [yayın Yapılandırması](../debugger/how-to-set-debug-and-release-configurations.md), devre dışı bırakmak gereksinim [yalnızca kendi kodum](../debugger/just-my-code.md). Visual Studio'da **Araçlar > Seçenekler**. İçinde **seçenekleri** iletişim kutusunda **hata ayıklama**. Denetimden Kaldır **yalnızca benim kodumu etkinleştir**.

 Çözümü derleyin (Visual Studio'da **Yapı > çözümü yeniden derle**). Hata ayıklama veya sürüm yapılandırmasını seçebilirsiniz (seçin **hata ayıklama** tam hata ayıklama deneyimi için). Derleme yapılandırmaları hakkında daha fazla bilgi için bkz. [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).

 Derleme işlemi, bir yürütülebilir ThrowsNullException.exe oluşturur. C# projesini oluşturduğunuz klasörü altında bulabilirsiniz: **...\ThrowsNullException\ThrowsNullException\bin\Debug** veya **...\ThrowsNullException\ThrowsNullException\bin\Release**.

 ThrowsNullException.exe çift tıklayın. Böyle bir komut penceresi görmeniz gerekir:

 ![ThrowsNullExceptionConsole](../debugger/media/throwsnullexceptionconsole.png "ThrowsNullExceptionConsole")

 Birkaç saniye sonra bir hata penceresinde görüntülenir:

 ![ThrowsNullExceptionError](../debugger/media/throwsnullexceptionerror.png "ThrowsNullExceptionError")

 Tıklamayın **iptal**! Birkaç saniye sonra iki düğme görmelisiniz **hata ayıklama** ve **Programı Kapat**. Tıklayın **hata ayıklama**.

> [!CAUTION]
>  Uygulamanızda güvenilmeyen kod varsa, bir güvenlik uyarısı iletişim kutusu görünür. Bu iletişim kutusu, hata ayıklamaya devam edip etmemeyi karar vermenize olanak sağlar. Hata ayıklamaya devam etmeden önce kodun güvenilir olup olmadığına karar verin. Size kodu kendiniz mi yazdınız? Kodlayıcıya güveniyor musunuz? Uygulama uzak makinede çalışıyorsa, işlemin adını hatırlar mısınız? Uygulamayı yerel olarak çalışıyor olsa bile, mutlaka güvenilir olabildiği anlamına gelmez. Bilgisayarınızda kötü amaçlı kod olasılığını göz önünde bulundurun. Kod üzeresiniz, karar verirseniz, güvenilir hata ayıklama, tıklayın **hata ayıklama**. ' A tıklayıp **hata ayıklama**.

 **Visual Studio anlık hata ayıklayıcısı** penceresi görüntülenir:

 ![JustInTimeDialog](../debugger/media/justintimedialog.png "JustInTimeDialog")

 Altında **olası hata ayıklayıcıları**, durumunda olduklarını görmüş olmalısınız **yeni Microsoft Visual Studio örneğini <available version>**  satır seçili. Zaten seçili değilse, şimdi seçin.

 Pencerenin en altında **seçili hata ayıklayıcısını kullanarak hata ayıklamak istiyor musunuz?**, tıklayın **Evet**.

 ThrowsNullException projeyi Visual Studio'nun yeni bir örneğinde yürütme özel durum oluşturan satırında durduruldu ile açar:

 ![NullReferenceSecondInstance](../debugger/media/nullreferencesecondinstance.png "NullReferenceSecondInstance")

 Bu noktada hata ayıklama başlayabilirsiniz. Bu gerçek bir uygulama varsa, kodu özel neden durum bulmak gerekir.

## <a name="just-in-time-debugging-errors"></a>Just-In-Time hata ayıklama hataları
 program çöktüğünde iletişim görmüyorsanız Bu bilgisayarınızdaki Windows hata bildirimi ayarları nedeniyle olabilir. Daha fazla bilgi için [. WER ayarları](/windows-hardware/drivers/dashboard/windows-error-reporting-getting-started).

 Just-ın-Time ile ilişkili aşağıdaki hata iletilerinden görebileceğiniz hata ayıklama.

-   **Kilitlenen işleme iliştirilemiyor. Belirtilen program Windows veya bir MS-DOS programı değil.**

     Başka bir kullanıcı olarak çalışan bir işleme eklemeyi denediğinizde, bu hata oluşur.

     Bu soruna geçici bir çözüm, Visual Studio, başlangıç açmak **iliştirme** iletişim kutusundan **hata ayıklama** menü ve hata ayıklamak istediğiniz bulma işlemi **kullanılabilir işlemler**listesi. İşlemin adını bilmiyorsanız, bakmak **Visual Studio anlık hata ayıklayıcısı** iletişim ve Not işlem kimliği İşlemi seçin **kullanılabilir işlemler** listelemek ve tıklayın **iliştirme**. İçinde **Visual Studio anlık hata ayıklayıcısı** iletişim kutusunda, tıklayın **Hayır** iletişim kutusunu kapatın.

-   **Hiçbir kullanıcı giriş yapmadığından hata ayıklayıcı başlatılamadı.**

     Just-ın-Time olduğunda bu hata oluşur çalışır bir makinede Visual Studio'yu başlatmak hata ayıklama konsolda oturum açmış hiçbir kullanıcı olduğu. Hiçbir kullanıcı oturum açmadığından, Just-ın-Time görüntülemek için bir kullanıcı oturumu var. hata ayıklama iletişim kutusu.

     Bu sorunu gidermek için makinede oturum açın.

-   **Sınıf kayıtlı değil.**

     Bu hata, hata ayıklayıcının, büyük olasılıkla bir yükleme sorunu nedeniyle kayıtlı olmayan bir COM sınıfı oluşturmayı denediğini gösterir.

     Bu sorunu gidermek için Visual Studio yüklemenizi onarın veya yeniden yüklemek için kurulum diskini kullanın.

## <a name="see-also"></a>Ayrıca Bkz.
 [Hata ayıklayıcı, güvenlik](../debugger/debugger-security.md) [hata ayıklayıcı temel bilgileri](../debugger/getting-started-with-the-debugger.md) [Just-ın-hata ayıklama, Time, Seçenekler iletişim kutusu](../debugger/just-in-time-debugging-options-dialog-box.md) [güvenlik uyarısı: güvenilmeyen bir kullanıcının sahip olduğu işleme ekleme olabilir tehlikeli. Aşağıdaki bilgiler kuşkulu görünüyorsa ya da emin değilseniz, bu işleme eklemeyin.](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)
