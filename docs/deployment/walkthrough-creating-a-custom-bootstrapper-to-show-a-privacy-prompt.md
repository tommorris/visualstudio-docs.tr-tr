---
title: 'İzlenecek yol: bir gizlilik istemi göstermek için özel bir önyükleyici oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, prerequisites
- dependencies [.NET Framework], custom bootstrapper package
- deploying applications [Visual Studio], custom prerequisites
- Windows Installer deployment, prerequisites
- prerequisites [.NET Framework], custom bootstrapper package
ms.assetid: 2f3edd6a-84d1-4864-a1ae-6a13c5732aae
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 6f20389e0487fd548ac239503faae01adb7dbdf1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt"></a>İzlenecek yol: Bir Gizlilik İstemi Göstermek için Özel Bir Önyükleyici Oluşturma
Derlemeleri yeni dosya sürümleri ve derleme sürümleri ile kullanılabilir olduğunda otomatik olarak güncelleştirmek için ClickOnce uygulamalarını yapılandırabilirsiniz. Müşterileriniz için bu davranışı kabul emin olmak için bunları bir gizlilik istemi görüntüleyebilirsiniz. Ardından, bunlar otomatik olarak güncelleştirmek için uygulama izni vermek seçebilirsiniz. Uygulama otomatik olarak güncelleştirmeye izin verilmiyorsa, yüklemez.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Visual Studio 2010.  
  
## <a name="creating-an-update-consent-dialog-box"></a>Bir güncelleştirme onay iletişim kutusu oluşturma  
 Bir gizlilik istemi görüntülemek için uygulama için otomatik güncelleştirmeler için kabul okuyucu soran bir uygulama oluşturun.  
  
#### <a name="to-create-a-consent-dialog-box"></a>Onay iletişim kutusu oluşturmak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusu, tıklatın **Windows**ve ardından **WindowsFormsApplication**.  
  
3.  İçin **adı**, türü **ConsentDialog**ve ardından **Tamam**.  
  
4.  Form Tasarımcısı'nda tıklatın.  
  
5.  İçinde **özellikleri** penceresinde, değişiklik **metin** özelliğine **Güncelleştirme Onayı iletişim**.  
  
6.  İçinde **araç**, genişletin **tüm Windows Formları**, sürükleyin bir **etiket** forma denetim.  
  
7.  Etiket denetimi Tasarımcısı'nda tıklatın.  
  
8.  İçinde **özellikleri** penceresinde, değişiklik **metin** altında özellik **Görünüm** şu:  
  
     Web üzerinde en son güncelleştirmeleri yüklemek üzere olduğunuz uygulama denetler. "Kabul ediyorum" tıklayarak, denetlemek ve güncelleştirmeleri otomatik olarak Internet'ten yüklemek için uygulama izin verirsiniz.  
  
9. İçinde **araç**, sürükleyin bir **onay kutusunu** biçiminde ortasından denetimine.  
  
10. İçinde **özellikleri** penceresinde, değişiklik **metin** altında özellik **düzeni** için **ediyorum**.  
  
11. İçinde **araç**, sürükleyin bir **düğmesini** sol alt form denetimi.  
  
12. İçinde **özellikleri** penceresinde, değişiklik **metin** altında özellik **düzeni** için **İlerle**.  
  
13. İçinde **özellikleri** penceresinde, değişiklik **(ad)** altında özellik **tasarım** için **ProceedButton**.  
  
14. İçinde **araç**, sürükleyin bir **düğmesini** sağ alt köşesindeki form denetimi.  
  
15. İçinde **özellikleri** penceresinde, değişiklik **metin** altında özellik **düzeni** için **iptal**.  
  
16. İçinde **özellikleri** penceresinde, değişiklik **(ad)** altında özellik **tasarım** için **CancelButton**.  
  
17. Tasarımcıda çift **ediyorum** olay oluşturmak için onay kutusunu.  
  
18. Form1 kod dosyasında olay için aşağıdaki kodu ekleyin.  
  
     [!code-csharp[ConsentDialog#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.cs)]
     [!code-vb[ConsentDialog#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.vb)]  
  
19. Devre dışı bırakmak için sınıf oluşturucusunu güncelleştirin **İlerle** varsayılan düğme.  
  
     [!code-csharp[ConsentDialog#6](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.cs)]
     [!code-vb[ConsentDialog#6](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.vb)]  
  
20. Form1 kod dosyasında, son kullanıcının çevrimiçi güncelleştirmeleri seçtiği varsa izlemek bir Boolean değişkeni için aşağıdaki kodu ekleyin.  
  
     [!code-csharp[ConsentDialog#3](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.cs)]
     [!code-vb[ConsentDialog#3](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.vb)]  
  
21. Tasarımcıda çift **İlerle** Click olay işleyicisi oluşturmak için düğmeye.  
  
22. Form1 kod dosyasına Click olay işleyicisi için aşağıdaki kodu ekleyin **İlerle** düğmesi.  
  
     [!code-csharp[ConsentDialog#2](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.cs)]
     [!code-vb[ConsentDialog#2](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.vb)]  
  
23. Tasarımcıda çift **iptal** Click olay işleyicisi oluşturmak için düğmeye.  
  
24. Form1 kod dosyasına Click olay işleyicisi için aşağıdaki kodu ekleyin **iptal** düğmesi.  
  
     [!code-csharp[ConsentDialog#4](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.cs)]
     [!code-vb[ConsentDialog#4](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.vb)]  
  
25. Son Kullanıcı çevrimiçi güncelleştirmelere onay vermezse hata dönmek için uygulamayı güncelleştir.  
  
     Yalnızca Visual Basic geliştiricileri için:  
  
    1.  İçinde **Çözüm Gezgini**, tıklatın **ConsentDialog**.  
  
    2.  Üzerinde **proje** menüsünde tıklatın **Modül Ekle**ve ardından **Ekle**.  
  
    3.  Module1.vb kod dosyasında aşağıdaki kodu ekleyin.  
  
         [!code-vb[ConsentDialog#7](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_6.vb)]  
  
    4.  Üzerinde **proje** menüsünde tıklatın **ConsentDialog özellikleri**ve ardından **uygulama** sekmesi.  
  
    5.  İşaretini **etkinleştir uygulama çerçevesi**.  
  
    6.  İçinde **Başlangıç nesnesi** açılır menüsünde, select **Module1**.  
  
        > [!NOTE]
        >  Uygulama Çerçevesi devre dışı bırakma Windows XP görsel stilleri, uygulama olayları, giriş ekranı, tek örnek uygulama ve daha fazlasını gibi özellikleri devre dışı bırakır. Daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md).  
  
     Visual C# yalnızca geliştiricileri için:  
  
     Program.cs kod dosyasını açın ve aşağıdaki kodu ekleyin.  
  
     [!code-csharp[ConsentDialog#5](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_7.cs)]  
  
26. Üzerinde **yapı** menüsünde tıklatın **BuildSolution**.  
  
## <a name="creating-the-custom-bootstrapper-package"></a>Özel önyükleyici paketi oluşturma  
 Son kullanıcılara gizlilik istemi göstermek için Güncelleştirme Onayı iletişim uygulaması için bir özel önyükleyici paketi oluşturabilir ve bir önkoşul olarak tüm ClickOnce uygulamalarını içerir.  
  
 Bu yordam aşağıdaki belgeler oluşturarak özel önyükleyici paketi oluşturma göstermektedir:  
  
-   Bir Product.XML önyükleyici içeriğini açıklamak için dosya.  
  
-   Dizeler ve Yazılım Lisans Koşulları'nı gibi paketinizi yerelleştirmeye özgü yönlerini listelemek için package.xml bildirim dosyası.  
  
-   Yazılım Lisans Koşulları'nı bir belge.  
  
#### <a name="step-1-to-create-the-bootstrapper-directory"></a>1. adım: önyükleyici dizini oluşturmak için  
  
1.  Adlı bir dizin oluşturun **UpdateConsentDialog** SDKs\Windows\v7.0A\Bootstrapper\Packages %PROGRAMFILES%\Microsoft içinde.  
  
    > [!NOTE]
    >  Bu klasörü oluşturmak için yönetici ayrıcalıkları gerekir.  
  
2.  UpdateConsentDialog dizininde tr adlı bir dizin oluşturun.  
  
    > [!NOTE]
    >  Her yerel ayar için yeni bir dizin oluşturun. Örneğin, fr ve de yerel ayarlar için alt dizinler ekleyebilirsiniz. Bu dizinleri Fransızca ve Almanca dizeleri ve dil paketleri, gerekirse içerecektir.  
  
#### <a name="step-2-to-create-the-productxml-manifest-file"></a>2. adım: product.xml bildirim dosyası oluşturmak için  
  
1.  Adlı bir metin dosyası oluşturun `product.xml`.  
  
2.  Product.xml dosyasında aşağıdaki XML kodunu ekleyin. Var olan XML kodunun üzerine yazma emin olun.  
  
    ```  
    <Product  
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      ProductCode="Microsoft.Sample.EULA">  
      <!-- Defines the list of files to be copied on build. -->  
      <PackageFiles CopyAllPackageFiles="false">  
        <PackageFile Name="ConsentDialog.exe"/>  
      </PackageFiles>  
  
      <!-- Defines how to run the Setup package.-->  
      <Commands >  
        <Command PackageFile = "ConsentDialog.exe" Arguments=''>  
          <ExitCodes>  
            <ExitCode Value="0" Result="Success" />  
            <ExitCode Value="-1" Result="Fail" String="AU_Unaccepted" />  
            <DefaultExitCode Result="Fail"   
              FormatMessageFromSystem="true" String="GeneralFailure" />  
          </ExitCodes>  
        </Command>  
      </Commands>  
  
    </Product>  
    ```  
  
3.  Dosyayı UpdateConsentDialog önyükleyici dizinine kaydedin.  
  
#### <a name="step-3-to-create-the-packagexml-manifest-file-and-the-software-license-terms"></a>3. adım: package.xml bildirimi oluşturmak için dosya ve yazılım lisans koşulları  
  
1.  Adlı bir metin dosyası oluşturun `package.xml`.  
  
2.  Package.xml dosyasında yerel tanımlar ve Yazılım Lisans Koşulları'nı eklemek için aşağıdaki XML kodunu ekleyin. Var olan XML kodunun üzerine yazma emin olun.  
  
    ```  
    <Package   
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      Name="DisplayName"  
      Culture="Culture"  
      LicenseAgreement="eula.rtf">  
      <PackageFiles>  
        <PackageFile Name="eula.rtf"/>  
      </PackageFiles>  
  
      <!-- Defines a localizable string table for error messages. -->  
      <Strings>  
        <String Name="DisplayName">Update Consent Dialog</String>  
        <String Name="Culture">en</String>  
        <String Name="AU_Unaccepted">The automatic update agreement is not accepted.</String>  
        <String Name="GeneralFailure">A failure occurred attempting to launch the setup.</String>  
      </Strings>  
    </Package>  
    ```  
  
3.  Dosyayı UpdateConsentDialog önyükleyici dizinindeki en alt kaydedin.  
  
4.  Yazılım Lisans koşulları EULA.rtf adlı bir belge oluşturun.  
  
    > [!NOTE]
    >  Yazılım Lisans Koşulları'nı lisans, garanti, borçları ve yerel yasalarınız hakkında bilgiler içermelidir. Bu dosyalar, yerel ayarlara özgü, böylece dosya MBCS veya UNICODE karakter destekleyen bir biçimde kaydedilir emin olun. İçeriği hakkında hukuk departmanınıza Yazılım Lisans Koşulları'nın başvurun.  
  
5.  Belgeyi UpdateConsentDialog önyükleyici dizinindeki en alt kaydedin.  
  
6.  Gerekirse, her yerel ayar için yazılım lisans koşulları için yeni package.xml bildirim dosyası ve yeni bir eula.rtf belgesi oluşturun. Örneğin, fr ve de yerel ayarlar için alt dizinler oluşturduysanız, ayrı.xml bildirim dosyaları ve yazılım lisans koşulları oluşturun ve bunları fr ve de alt dizinlere kaydedin.  
  
## <a name="setting-the-update-consent-application-as-a-prerequisite"></a>Güncelleştirme Onayı uygulamasını bir önkoşul olarak ayarlama  
 Visual Studio'da Güncelleştirme Onayı uygulamasını bir önkoşul olarak ayarlayabilirsiniz.  
  
#### <a name="to-set-the-update-consent-application-as-a-prerequisite"></a>Güncelleştirme Onayı uygulaması bir önkoşul olarak ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, dağıtmak istediğiniz uygulamanızın adına tıklayın.  
  
2.  Üzerinde **proje** menüsünde tıklatın *ProjectName* **özellikleri**.  
  
3.  Tıklatın **Yayımla** sayfasında ve ardından **Önkoşullar**.  
  
4.  Seçin **güncelleştirme onay iletişim**.  
  
    > [!NOTE]
    >  Önkoşullar iletişim kutusunda Güncelleştirme Onayı iletişim görmek için Visual Studio'yu kapatıp gerekebilir.  
  
5.  **Tamam**'ı tıklatın.  
  
## <a name="creating-and-testing-the-setup-program"></a>Oluşturma ve Kurulum programını test etme  
 Güncelleştirme Onayı uygulamasını bir önkoşul olarak ayarladıktan sonra uygulamanız için yükleyici ve önyükleyici oluşturabilirsiniz.  
  
#### <a name="to-create-and-test-the-setup-program-by-not-clicking-i-agree"></a>Oluşturma ve Kurulum programını tıklamadan test kabul ediyorum  
  
1.  İçinde **Çözüm Gezgini**, dağıtmak istediğiniz uygulamanızın adına tıklayın.  
  
2.  Üzerinde **proje** menüsünde tıklatın *ProjectName* **özellikleri**.  
  
3.  Tıklatın **Yayımla** sayfasında ve ardından **Şimdi Yayımla**.  
  
4.  Yayımlama çıktısı otomatik olarak açılmazsa yayımlama çıktısına gidin.  
  
5.  Setup.exe programını çalıştırın.  
  
     Kurulum programı Güncelleştirme Onayı iletişim yazılım lisans sözleşmesi gösterir.  
  
6.  Yazılım Lisans Sözleşmesi'ni okuyun ve ardından **kabul**.  
  
     Güncelleştirme Onayı iletişim uygulaması görünür ve aşağıdaki metni gösterir: Web üzerindeki en son güncelleştirmeleri yüklemek üzere olduğunuz uygulama denetler. Kabul ediyorum tıklayarak, Internet'te otomatik olarak güncelleştirmeleri denetlemek için uygulama izin verirsiniz.  
  
7.  Uygulamayı kapatın veya İptal'i tıklatın.  
  
     Uygulama bir hata gösterir: sistemi bileşenleri için yüklenirken bir hata oluştu *ApplicationName*. Tüm sistem bileşenleri başarıyla yüklenene kadar kurulum devam edemiyor.  
  
8.  Aşağıdaki hata iletisini göstermek için Ayrıntılar'ı tıklatın: Bileşen Güncelleştirme Onayı iletişim kutusu aşağıdaki hata iletisiyle başarısız oldu: "otomatik güncelleştirme anlaşması kabul edilmedi." Aşağıdaki bileşenler yüklenemedi:-Güncelleştirme Onayı iletişim  
  
9. **Kapat**'ı tıklatın.  
  
#### <a name="to-create-and-test-the-setup-program-by-clicking-i-agree"></a>Oluşturma ve Kurulum programını tıklayarak test kabul ediyorum  
  
1.  İçinde **Çözüm Gezgini**, dağıtmak istediğiniz uygulamanızın adına tıklayın.  
  
2.  Üzerinde **proje** menüsünde tıklatın *ProjectName* **özellikleri**.  
  
3.  Tıklatın **Yayımla** sayfasında ve ardından **Şimdi Yayımla**.  
  
4.  Yayımlama çıktısı otomatik olarak açılmazsa yayımlama çıktısına gidin.  
  
5.  Setup.exe programını çalıştırın.  
  
     Kurulum programı Güncelleştirme Onayı iletişim yazılım lisans sözleşmesi gösterir.  
  
6.  Yazılım Lisans Sözleşmesi'ni okuyun ve ardından **kabul**.  
  
     Güncelleştirme Onayı iletişim uygulaması görünür ve aşağıdaki metni gösterir: Web üzerindeki en son güncelleştirmeleri yüklemek üzere olduğunuz uygulama denetler. Kabul ediyorum tıklayarak, Internet'te otomatik olarak güncelleştirmeleri denetlemek için uygulama izin verirsiniz.  
  
7.  Tıklatın **ediyorum**ve ardından **İlerle**.  
  
     Uygulama yüklemeye başlar.  
  
8.  Uygulama Yükle iletişim kutusu görüntülenirse, tıklatın **yükleme**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama dağıtımının önkoşulları](../deployment/application-deployment-prerequisites.md)   
 [Önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md)   
 [Nasıl yapılır: Ürün bildirimi oluşturma](../deployment/how-to-create-a-product-manifest.md)   
 [Nasıl yapılır: Paket bildirimi oluşturma](../deployment/how-to-create-a-package-manifest.md)   
 [Ürün ve Paket Şema Başvurusu](../deployment/product-and-package-schema-reference.md)