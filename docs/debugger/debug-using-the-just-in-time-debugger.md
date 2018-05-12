---
title: Just-In-Time hata ayıklayıcısı ile hata ayıklama | Microsoft Docs
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
ms.openlocfilehash: 17dc34cd030bf2eab430872a191424fb657d6cd0
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="debug-using-the-just-in-time-debugger-in-visual-studio"></a>Visual Studio'da Just-In-Time hata ayıklayıcısı ile hata ayıklama
Bir özel durum ya da kilitlenme dış Visual Studio çalıştıran bir uygulamada oluştuğunda tam zamanı hata ayıklama Visual Studio otomatik olarak başlatır. Bu, Visual Studio çalışmadığı zaman uygulamanızı test etmek ve bir sorun ortaya çıktığında Visual Studio ile hata ayıklama başlamak sağlar.

Tam zamanında hata ayıklama Windows Masaüstü uygulamaları için çalışır. Evrensel Windows uygulamaları için çalışmaz ve Görselleştiriciler gibi yerel bir uygulamada, barındırılan yönetilen kod için çalışmaz.

> [!TIP] 
> Nasıl sadece zaman için yanıt bilmek istiyorsanız, hata ayıklayıcı, iletişim kutusu, bkz: [bu konuda](../debugger/just-in-time-debugging-in-visual-studio.md).

##  <a name="BKMK_Enabling"></a> Etkinleştirme veya devre dışı bırak sadece zamanında hata ayıklama  
Etkinleştirmek veya zaman hemen Visual Studio'dan hata ayıklama devre dışı **Araçlar > Seçenekler** iletişim kutusu.
  
#### <a name="to-enable-or-disable-just-in-time-debugging"></a>Etkinleştirme veya devre dışı bırak sadece zamanında hata ayıklama  
  
1.  Visual Studio'yu yönetici ayrıcalıklarıyla açın (sağ tıklatın ve seçin **yönetici olarak çalıştır**).

    Etkinleştirerek veya devre dışı sadece zamanında hata ayıklama ayarlar bir kayıt defteri anahtarı ve yönetici ayrıcalıkları gereken bu anahtarı değiştirmek için.
    
2. Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.
  
2.  İçinde **seçenekleri** iletişim kutusunda, genişletin **hata ayıklama** düğümü.  
  
3.  İçinde **hata ayıklama** düğümü, select **zaman içinde hemen**.

    ![Etkinleştirmek veya JIT hata ayıklama devre dışı](../debugger/media/dbg-jit-enable-or-disable.png "etkinleştirmek veya devre dışı JIT hata ayıklama") 
  
4.  İçinde **Just-In-Time etkinleştirme kodu bu tür hata ayıklama** kutusunda seçin veya ilgili program türlerini Temizle: **yönetilen**, **yerel**, veya **betik**.    
  
5.  **Tamam**'ı tıklatın.  
  
Visual Studio artık bilgisayarınızda yüklü olsa bile tam zamanı hata ayıklama hala etkin. Visual Studio yüklenmediğinde zaman hemen Visual Studio'dan hata ayıklama devre dışı bırakamazsınız **seçenekleri** iletişim kutusu. Bu durumda, sadece zaman Windows kayıt defterini düzenleyerek hata ayıklama devre dışı bırakabilirsiniz.  
  
#### <a name="to-disable-just-in-time-debugging-by-editing-the-registry"></a>Sadece zaman kayıt defterini düzenleyerek hata ayıklama devre dışı bırakmak için  
  
1.  Üzerinde **Başlat** menüsü, arama ve çalıştırma `regedit.exe`  
  
2.  İçinde **Kayıt Defteri Düzenleyicisi'ni** penceresinde bulun ve aşağıdaki kayıt defteri girdilerini silin:  
  
    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger  
  
    -   HKEY_LOCAL_MACHINE\Software\Microsoft\.NETFramework\DbgManagedDebugger  

    ![JIT kayıt defteri anahtarı](../debugger/media/dbg-jit-registry.png "JIT kayıt defteri anahtarı") 
  
3.  Bilgisayarınızı bir 64-bit işletim sisteminde çalışıyorsa, aşağıdaki kayıt defteri girdilerini de Sil:  
  
    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger  
  
    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\DbgManagedDebugger  
  
4.  Yanlışlıkla silmeyin veya herhangi bir kayıt defteri anahtarı değiştirmek için dikkat edin.  
  
5.  Kapat **Kayıt Defteri Düzenleyicisi'ni** penceresi.   
  
#### <a name="to-enable-just-in-time-debugging-of-a-windows-form"></a>Etkinleştir sadece zaman bir Windows formunda hata ayıklama için  
  
1.  Varsayılan olarak, Windows Forms uygulamaları programın kurtarma yapabilirsiniz, çalışmaya devam etmesini sağlayan bir üst düzey özel durum işleyici sahiptir. Örneğin, Windows Forms uygulaması işlenmeyen bir özel durum oluşturursa, aşağıdaki gibi bir iletişim kutusu görürsünüz:  
  
     ![WindowsFormsUnhandledException](../debugger/media/windowsformsunhandledexception.png "WindowsFormsUnhandledException")  
  
     Etkinleştirme zaman sadece bir Windows Forms uygulaması, hata ayıklama için aşağıdaki ek adımları gerçekleştirmeniz gerekir:  
  
2.  Ayarlama `jitDebugging` değeri `true` içinde `system.windows.form` machine.config bölümünü veya  *\<uygulama adı >*. exe.config dosyası:  
  
    ```  
    <configuration>  
        <system.windows.forms jitDebugging="true" />  
    </configuration>  
    ```  
  
3.  C++ Windows Form Uygulaması'nda da ayarlamanız gerekir `DebuggableAttribute` .config dosyasına veya kodunuzu. İle derleme yaparsanız [/zı](/cpp/build/reference/z7-zi-zi-debug-information-format) ve olmadan [/Og](/cpp/build/reference/og-global-optimizations), derleyici, bu öznitelik ayarlar. Ancak, iyileştirilmemiş yayın derlemesinde hata ayıklama istiyorsanız, bunu kendiniz ayarlamanız gerekir. Bu, aşağıdaki satırı olduğunuz uygulamanızın AssemblyInfo.cpp dosyasını ekleyerek yapabilirsiniz:  
  
    ```  
    [assembly:System::Diagnostics::DebuggableAttribute(true, true)];   
    ```  
  
     Daha fazla bilgi için bkz. <xref:System.Diagnostics.DebuggableAttribute>.  
  
## <a name="a-namebkmkusingjituse-just-in-time-debugging"></a><a name="BKMK_Using_JIT">Tam zamanında hata ayıklama kullanın  
 Bu bölüm, yürütülebilir bir özel durum oluşturduğunda ne olacağını gösterir.  
  
 Visual Studio'nun bu adımları izlemek için yüklü olması gerekir. Visual Studio yoksa, ücretsiz indirebilirsiniz [Visual Studio Community Edition](https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15).  
  
 Bu sadece zaman emin olun hata ayıklama işlevinin [etkin](#BKMK_Enabling).
  
 Bu bölümde amaçları doğrultusunda, biz bir C# konsol uygulaması Visual Studio'da oluşturur yapacağız bir [NullReferenceException](http://msdn.microsoft.com/Library/658af786-d893-4114-a3c5-31c7d586056a).  
  
 Visual Studio'da bir C# konsol uygulaması oluşturma (**Dosya > Yeni > Proje > Visual C# > konsol uygulaması**) adlı **ThrowsNullException**. Visual Studio'da projeler oluşturma hakkında daha fazla bilgi için bkz: [izlenecek yol: basit bir uygulama oluşturmak](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md).  
  
 Visual Studio'da projeyi oturum açtığında, Program.cs dosyasını açın. Main() yönteminin bir çizgi konsola yazdırır ve bir NullReferenceException oluşturur aşağıdaki kodla değiştirin:  
  
```csharp  
static void Main(string[] args)  
{  
    Console.WriteLine("we will now throw a NullReferenceException");  
    throw new NullReferenceException("this is the exception thrown by the console app");  
}  
```  
  
> [!IMPORTANT]
>  İş için bu yordamı için sırayla bir [yayın yapılandırma](../debugger/how-to-set-debug-and-release-configurations.md), devre dışı bırakmak gereksinim [sadece kendi kodumu](../debugger/just-my-code.md). Visual Studio'da sırasıyla **Araçlar > Seçenekler**. İçinde **seçenekleri** iletişim kutusunda **hata ayıklama**. Denetimden kaldırmak **sadece kendi kodumu etkinleştir**.  
  
 Çözüm derleme (Visual Studio'da, **Yapı > çözümü yeniden derle**). Hata ayıklama veya yayın yapılandırma seçebilirsiniz (seçin **hata ayıklama** tam hata ayıklama deneyimini için). Derleme yapılandırmaları hakkında daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).  
  
 Derleme işlemi yürütülebilir ThrowsNullException.exe oluşturur. C# projesini oluşturduğunuz klasörü altında bulabilirsiniz: **...\ThrowsNullException\ThrowsNullException\bin\Debug** veya **...\ThrowsNullException\ThrowsNullException\bin\Release**.  
  
 ThrowsNullException.exe çift tıklayın. Böyle bir komut penceresi görmeniz gerekir:  
  
 ![ThrowsNullExceptionConsole](../debugger/media/throwsnullexceptionconsole.png "ThrowsNullExceptionConsole")  
  
 Birkaç saniye sonra bir hata penceresi görüntülenir:  
  
 ![ThrowsNullExceptionError](../debugger/media/throwsnullexceptionerror.png "ThrowsNullExceptionError")  
  
 ' A tıklamayın **iptal**! Birkaç saniye sonra iki düğme görmelisiniz **hata ayıklama** ve **Programı Kapat**. Tıklatın **hata ayıklama**.  
  
> [!CAUTION]
>  Uygulamanızı güvenilmeyen kodu içeriyorsa, bir güvenlik uyarısı iletişim kutusu görüntülenir. Bu iletişim kutusu hata ayıklamaya devam edip etmemeyi karar vermenize olanak sağlar. Hata ayıklama ile devam etmeden önce kod güven karar verin. Kodu kendiniz yazdım? Kodlayıcı güveniyor musunuz? Uygulama uzak makinede çalışıyorsa, işlemin adını tanımadığınız? Uygulamayı yerel olarak çalışıyor olsa bile, mutlaka güvenilen olabilir gelmez. Bilgisayarınızda çalışan kötü amaçlı kod olasılığını göz önünde bulundurun. Kod üzeresiniz olduğunu karar verirseniz hata ayıklama güvenilir, tıklatın **hata ayıklama**. Aksi takdirde tıklatın **yok hata ayıklama**.  
  
 **Visual Studio Just-In-Time hata ayıklayıcısı** penceresi görüntülenir:  
  
 ![JustInTimeDialog](../debugger/media/justintimedialog.png "JustInTimeDialog")  
  
 Altında **olası hata ayıklayıcıları**, görmelisiniz **Microsoft Visual Studio yeni bir örneğini <available version>**  satır seçilidir. Zaten seçili değilse, şimdi seçin.  
  
 Pencerenin altındaki altında **seçili hata ayıklayıcısı ile hata ayıklama istiyor musunuz?**, tıklatın **Evet**.  
  
 ThrowsNullException projeyi Visual Studio, yeni bir örneğini özel durum oluşturur satırına durduruldu yürütme ile açar:  
  
 ![NullReferenceSecondInstance](../debugger/media/nullreferencesecondinstance.png "NullReferenceSecondInstance")  
  
 Bu noktada hata ayıklama başlatabilirsiniz. Bu gerçek bir uygulamada olsaydı, kodu özel durum neden atma bulmak gerekir.  
  
## <a name="just-in-time-debugging-errors"></a>Tam zamanında hata ayıklama hataları  
 program kilitlendiğinde iletişim görmüyorsanız, bilgisayarınızdaki Windows hata bildirimi ayarları nedeniyle bu olabilir. Daha fazla bilgi için bkz: [. WER ayarları](/windows-hardware/drivers/dashboard/windows-error-reporting-getting-started).  
  
 Sadece zaman ile ilişkili aşağıdaki hata iletileri görebilirsiniz hata ayıklama.  
  
-   **Kilitlenen işleme eklenemiyor. Belirtilen program Windows veya MS-DOS programı değil.**  
  
     Başka bir kullanıcı olarak çalışan bir işlemi iliştirmeye çalıştığınızda bu hata oluşur.  
  
     Bu soruna geçici bir çözüm, başlangıç Visual Studio için açın **ekleme işlemi için** iletişim kutusundan **hata ayıklama** menü ve istediğiniz içinde hata ayıklamak bulma işlemi **kullanılabilir işlemler**listesi. İşlemin adını bilmiyorsanız bakmak **Visual Studio Just-In-Time hata ayıklayıcısı** iletişim ve Not işlem kimliği. İşlemde seçin **kullanılabilir işlemler** listesinde ve tıklatın **Attach**. İçinde **Visual Studio Just-In-Time hata ayıklayıcısı** iletişim kutusunda, tıklatın **Hayır** iletişim kutusunu kapatmak için.  
  
-   **Hiçbir kullanıcı oturum açtığından hata ayıklayıcı başlatılamadı.**  
  
     Bu hata sadece zaman oluşur hata ayıklama çalışır bir makinede Visual Studio'yu başlatmak söz konusu olduğunda konsolda oturum açmış bir kullanıcı yok. Hiçbir kullanıcı oturum açtığından, zaman içinde hemen görüntülemek için hiçbir kullanıcı oturum yok hata ayıklama iletişim kutusu.  
  
     Bu sorunu gidermek için makinede oturum açın.  
  
-   **Sınıf kayıtlı değil.**  
  
     Bu hata, hata ayıklayıcı, büyük olasılıkla bir yükleme sorunu nedeniyle kayıtlı olmayan bir COM sınıfı oluşturmak üzere çalıştığını gösterir.  
  
     Bu sorunu gidermek için yeniden yükleyin veya Visual Studio yüklemenizi onarmak için kurulum diskini kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Yalnızca hata ayıklama, zaman içinde Seçenekler iletişim kutusu](../debugger/just-in-time-debugging-options-dialog-box.md)   
 [Güvenlik Uyarısı: Güvenilmeyen bir kullanıcının sahip olduğu işleme ekleme tehlikeli olabilir. Aşağıdaki bilgiler kuşkulu görünüyorsa ya da emin değilseniz, bu işleme eklemeyin.](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)