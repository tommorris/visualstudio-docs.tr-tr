---
title: Unity için Visual Studio Araçları'nı kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: e67ec9a2-a449-413e-8930-9a471bd43a06
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: c0300e26c8811dc877ad6d01e1afbc5ef6ca35df
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="using-visual-studio-tools-for-unity"></a>Unity için Visual Studio Araçlarını Kullanma
Bu bölümde, Visual Studio Araçları Unity'nın tümleştirme ve verimlilik özellikleri için nasıl kullanılacağını ve nasıl Unity geliştirme için Visual Studio hata ayıklayıcısı kullanılacağını öğreneceksiniz.

## <a name="unity-integration-and-productivity"></a>Unity tümleştirme ve verimlilik
 Unity için Visual Studio Araçları daha üretken olmanıza yardımcı olması için Unity Düzenleyicisi ile tümleşir. Bu üretkenliği geliştirme özelliklere genel komut dosyası görevleri otomatik hale getirmek ve böylece bulmak için Unity Düzenleyicisi geçiş yapmanız gerekmez bilgi Unity Visual Studio'ya duruma getirin.

### <a name="unity-documentation-access"></a>Unity belgelerine erişim
 Visual Studio'dan hızlı bir şekilde belge scripting Unity erişebilir. Unity için Visual Studio Araçları için API belgelerine yerel olarak bulamazsa, çevrimiçi bulmak deneyecek.

##### <a name="to-access-unity-documentation"></a>Unity belgelerine erişmek için

-   Visual Studio'da vurgulayın veya Unity hakkında bilgi edinin ve basın istediğiniz API imleci yerleştirin **Ctrl + Alt + M, Ctrl + H**

### <a name="unity-monobehavior-scripting-wizard"></a>Unity MonoBehavior komut dosyası oluşturma Sihirbazı
 Unity içinde çoğu betikleri MonoBehavior sınıfından türetilen ve kendi yöntemlerin bazıları geçersiz kılma uygulanır. Hızlı bir şekilde aşırı MonoBehavior yöntemleri boş tanımları oluşturmak için MonoBehavior Sihirbazı'nı kullanabilirsiniz. Bu sihirbazı kullanarak, kullanılabilir yöntemler listesinden aşırı yükleme, burada şirketlerin kodunuza eklenir ve nasıl kullanıldıkları hakkında yorum dahil edilip edilmeyeceğini karar seçin istediğiniz bir veya daha fazla yöntemleri belirtebilirsiniz.

 ![Monobehavior Sihirbazı iletişim kutusu.](../cross-platform/media/vstu_monobehavior_wizard_full.png "vstu_monobehavior_wizard_full")

##### <a name="to-create-empty-monobehavior-method-definitions-by-using-the-monobehavior-wizard"></a>MonoBehavior Sihirbazı'nı kullanarak boş MonoBehavior yöntemi tanımları oluşturmak için

1.  Visual Studio'da imleci eklenir ve basın için yöntemleri istediğiniz yere **Ctrl + Shift + M** MonoBehavior Sihirbazı'nı başlatmak için. Veya yeni yöntemleri zaten uygulanmış bir sonra eklemek istiyorsanız, daha sonra belirtebilirsiniz; yalnızca basın **Ctrl + Shift + M**.

2.  Aşırı yükleme istediğiniz yöntemi seçin. İçinde **betik yöntemleri oluşturma** penceresi altında **seçin oluşturmak için yöntem**, aşırı yükleme istediğiniz her bir yöntemin adını yanındaki onay kutusunu işaretleyin.

3.  Görüntülenen framework sürümü emin **Framework sürümü** açılır kullanmakta olduğunuz sürümü ile eşleşir. Eşleşmiyorsa, açılır değerini kullanmak istediğiniz sürüm olarak değiştirin.

4.  Yöntemleri ekleneceği seçin. Varsayılan olarak, imleç konumunda yöntemleri eklenir; başka bir yere eklemek istiyorsanız, bunları sınıfınızda zaten uygulanmış herhangi bir yöntemini after INSERT seçebilirsiniz. Bu konumlardan birini seçmek için değerini değiştirme **ekleme noktasını** açılan istediğiniz konuma aşağı kaydırın.

5.  Seçtiğiniz yöntemler için açıklamalar oluşturmak, işaretlemek için Sihirbazı'nı istiyorsanız **yöntemi açıklamaları oluşturmak** onay kutusu. Bu açıklamalar zaman yöntemi çağrılır ve genel sorumlulukları nelerdir anlamanıza yardımcı olması amaçlanmıştır.

6.  Seçin **Tamam** sihirbazdan çıkın ve yöntemleri kodunuza Ekle düğmesi.

 MonoBehavior Sihirbazı'nı Unity API hala öğrenme aşamasında veya alışık değilseniz yöntemi aşırı gerektiğinde özellikle yararlıdır. Unity API ile daha deneyimli dönüşürken, zaten aşina yöntemleri hızlı bir şekilde oluşturmak için hızlı MonoBehavior Sihirbazı'nı tercih edebilirsiniz.

#### <a name="quick-monobehavior-scripting-wizard"></a>Hızlı MonoBehavior komut dosyası oluşturma Sihirbazı
 Zaten Unity API ile tanıdık, hızlı MonoBehavior Sihirbazı'nı kullanarak aşırı yüklenmiş yöntemler bile daha hızlı uygulayabilirsiniz. Bu sihirbazı kullanarak, imlecin konumundaki yöntemi açıklamalar olmadan eklenen tek yöntemi belirtebilirsiniz.

 ![Hızlı monobehavior Sihirbazı iletişim kutusu.](../cross-platform/media/vstu_monobehavior_wizard_quick.png "vstu_monobehavior_wizard_quick")

###### <a name="to-create-an-empty-monobehavior-method-definition-by-using-the-quick-monobehavior-wizard"></a>Hızlı MonoBehavior Sihirbazı'nı kullanarak bir boş MonoBehavior yöntemi tanımı oluşturmak için

1.  Visual Studio'da imleci eklenir ve basın yöntemi istediğiniz yere **Ctrl + Shift + Q** hızlı MonoBehavior Sihirbazı'nı başlatmak için. Diğer MonoBehavior Sihirbazı, imleci bilerek yeni yöntemi her zaman eklenen bu sihirbaz var. kullanırken getirin.

2.  Üst sağ köşesinde görüntülenen framework sürümü emin **Create betik yöntemi** penceresi eşleşen kullanmakta olduğunuz sürümü. Eşleşmiyorsa, açılır değerini kullanmak istediğiniz sürüm olarak değiştirin.

3.  Aşırı yükleme istediğiniz yöntemini bulun. Oluşturma komut dosyası yöntemi penceresinde, metin kutusuna yöntemin adını yazmaya başlayın. Girmiş olduğunuz adları eşleşen yöntemlerin listesi görüntülenir.

4.  Aşırı yükleme istediğiniz yöntemi seçin. Kullanmak istediğiniz yöntemi listesinde görüntülendiğinde seçin fare veya ok tuşları ile tuşuna **Enter**. Listesinde yalnızca yöntemi etkinleştirilmişse, yalnızca basabilirsiniz **Enter**. Yöntemi, kodunuza eklenir.

### <a name="unity-project-explorer"></a>Unity Proje Gezgini
 Unity Proje Gezgini, Unity projeniz Visual Studio içinde gezinmek için kullanabilirsiniz.

 ![Unity Proje Gezgini penceresi.](../cross-platform/media/vstu_unity_project_explorer.png "vstu_unity_project_explorer")

##### <a name="to-view-the-unity-project-explorer"></a>Unity Proje Gezgini görüntülemek için

-   Visual Studio'da ana menüde seçin **Görünüm**, **Unity Proje Gezgini**. Klavye: **Alt + SHIFT + E**

     ![Unity Proje Gezgini penceresi görüntüleyin.](../cross-platform/media/vstu_view_unity_project_explorer.png "vstu_view_unity_project_explorer")

 Unity Proje Gezgini tüm Unity proje dosyaları ve dizinleri Unity Düzenleyicisi'ni yapan aynı şekilde gösterir - bu komut dosyanızı yalnızca içeren Çözüm Gezgini ile unity komut dosyalarınızı gezinme dosyaları ve bunları görüntüler farklı Proje ve çözüm Unity için Visual Studio Araçları tarafından oluşturulan bunları düzenler. Özellikle büyük projelerinde Unity Proje Gezgini kullanarak değiştirmek istediğiniz komut dosyasını bulmak kolaydır; Ayrıca diğer tür dosyalarda değiştirmek kolaylaştırır — Örneğin, metin tabanlı yapılandırma dosyaları — bir Visual Studio çözümü projelerinde eklemeden olmadan Visual Studio.

### <a name="unity-error-list"></a>Unity hata listesi
 Unity örneğine bağlandığında, Visual Studio içinde Unity konsolundan iletileri görüntüleyebilirsiniz. Bu, hataları ve Uyarıları Unity gelen içerir. Visual Studio'nun görüntülenen iletiler **hata listesi** penceresi; hata Unity gelen iletileri görüntülenir **hataları** sekmesinde, uyarı iletilerini üzerinde **uyarıları** sekmesinde ve diğer iletileri — Örneğin, Debug.Log Unity API kullanılarak gönderilen iletileri — görüntülenir **iletileri** sekmesi.

 İletilerini görmek için Unity projenizi olmalıdır [Unity Player projenizde hata ayıklama](#debugging-your-project-in-a-unity-player) komut dosyası hata ayıklamayı desteklemek için ve Visual Studio Araçları Visual Studio sürümünüz için doğru Unity paketini içeri aktarmak için ve Visual Studio olmalıdır [Unity için Visual Studio bağlanmayı](#connecting-visual-studio-to-unity).

 Hataları, uyarıları ve Visual Studio'nun Unity gelen iletileri görmek istemiyorsanız, **hata listesi** penceresinde devre dışı bırakabilirsiniz bunları yapılandırma menüde.

### <a name="keyboard-shortcuts"></a>Klavye kısayolları
 Kendi klavye kısayollarını kullanarak Unity araçları Visual Studio işlevselliği için hızlı bir şekilde erişebilir. Kullanılabilir kısayolları bir özeti aşağıda verilmiştir.

|Komut|Kısayol|Kısayol komut adı|
|-------------|--------------|---------------------------|
|MonoBehavior Sihirbazı'nı açın|**Ctrl+Shift+M**|**EditorContextMenus.CodeWindow.ImplementMonoBehaviours**|
|Hızlı MonoBehavior Sihirbazı'nı açın|**Ctrl+Shift+Q**|**EditorContextMenus.CodeWindow.QuickMonoBehaviours**|
|Unity Proje Gezgini|**Alt+Shift+E**|**View.UnityProjectExplorer**|
|Unity belgelere erişebilir|**Ctrl+Alt+M, Ctrl+H**|**Help.UnityAPIReference**|
|Unity (player veya düzenleyicisini) hata ayıklayıcısını|***Varsayılan değer yok***|**Debug.AttachUnityDebugger**|

 Varsayılan hoşlanmıyorsanız kısayol tuş birleşimleri değiştirebilirsiniz. Bunun nasıl değiştirileceği hakkında daha fazla bilgi için bkz: [tanımlama ve özelleştirme klavye kısayolları Visual Studio'da](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).

## <a name="unity-debugging"></a>Unity hata ayıklama
 Unity için Visual Studio Araçları, hem Düzenleyici hem de oyun betikler Unity projeniz Visual Studio'nun güçlü hata ayıklayıcıyı kullanma için hata ayıklama olanak tanır.

###  <a name="connecting-visual-studio-to-unity"></a> Unity için Visual Studio bağlanma
 Unity için Visual Studio Araçları ile Unity bir UDP bağlantı iletişim kurar. Bu, tam olarak aynı şekilde yerel olarak çalışan bir Unity örneğine veya herhangi bir ağınızdaki bağlanabileceği anlamına gelir. Herhangi bir kullanarak, ağınızdaki görebilir Unity örneklerinin bağlanabilir **Unity örneği seçin** iletişim.

##### <a name="to-open-the-select-unity-instance-dialog"></a>Unity örnek Seç iletişim kutusunu açmak için

-   Visual Studio'da ana menüde seçin **hata ayıklama**, **Attach Unity hata ayıklayıcı**.

     ![Hata ayıklayıcısını birlik ekleyin.](../cross-platform/media/vstu_debugging_attach_unity_debugger.png "vstu_debugging_attach_unity_debugger")

-   *Veya*, Visual Studio'da durum çubuğunda Visual Studio sağ alt köşesindeki Tak simgesini seçin.

     ![Bu simge, Unity için VSTU bağlı gösterir.](../cross-platform/media/vstu_connection_connected.png "vstu_connection_connected")

> [!TIP]
>  Bağlama simgesi işareti gösteriyorsa, Unity örneğine zaten bağlandınız.

 **Unity örneği seçin** iletişim bağlanabileceğiniz her Unity örneği hakkında bazı bilgileri görüntüler.

 ![Bağlanmak için Unity örneği seçin.](../cross-platform/media/vstu_connection_to_unity.png "vstu_connection_to_unity")

 **Proje** Unity Bu örneği çalışıyor Unity projesinin adı.

 **Makine** bilgisayar veya Unity'nın bu örneğinin üzerinde çalıştığı aygıt adı.

 **Tür** **Düzenleyicisi** Unity'nın bu örneğinin Unity Düzenleyicisi'nin; bir parçası olarak çalışıyorsa, **Player** Unity'nın bu örneğinin bir oynatıcı ise.

 **Bağlantı noktası** Unity'nın bu örneğinin üzerinden iletişim UDP yuva bağlantı noktası sayısı.

> [!IMPORTANT]
>  Unity ve Unity örneği için Visual Studio Araçları UDP ağ yuva kurduğundan, Güvenlik Duvarı hakkında isteyebilir. Bu durumda, VSTU ve Unity iletişim kurabilmesi için bağlantıyı yetkilendirmek zorunda kalırsınız.

### <a name="troubleshooting-the-connection-between-unity-and-visual-studio"></a>Unity ve Visual Studio arasındaki bağlantı sorunlarını giderme

#### <a name="confirm-editor-attaching-is-enabled"></a>Düzenleyici ekleme etkinleştirilmiş doğrulayın

Unity menüde seçin **Düzenle > Tercihler** ve ardından **Harici Araçlar** sekmesi. Onaylayın **Düzenleyicisi ekleme** onay kutusunu etkindir. Daha fazla bilgi için başvurun [Unity Tercihler belgelerine](https://docs.unity3d.com/Manual/Preferences.html).

###  <a name="debugging-your-project-in-a-unity-player"></a> Unity Player projenizde hata ayıklama
 Unity Düzenleyicisi çalışmadığında bir oynatıcı veya platforma özgüdür sorunlarında hata ayıklamak için çalışan doğrudan Unity uygulamanıza Unity için Visual Studio Araçları bağlanabilir.

##### <a name="to-enable-script-debugging-in-a-unity-player"></a>Bir Unity oynatıcı komut dosyası hata ayıklamayı etkinleştirmek için

-   Etkin komut dosyası hata ayıklamaya geliştirme yapı oluşturduğunuzdan emin olun. Unity projenizi derleme ayarlarında işaretlemek **geliştirme yapı** ve **komut dosyasında hata ayıklama** onay kutuları.

 ![Hata ayıklama için Unity derleme ayarlarını yapılandırın.](../cross-platform/media/vstu_debugging_build_settings.png "vstu_debugging_build_settings")

 Ayrıca, çalışır durumda bir Unity uygulamasının hata ayıklamak için **Unity Web Player**, kullanacak şekilde yapılandırmanız gereken **geliştirme yayın kanal**.

##### <a name="to-configure-the-development-release-channel-in-unity-web-player"></a>Unity Web Player geliştirme yayın kanalı yapılandırmak için

-   Unity Web Player bağlam menüsünü seçin **yayın kanal** emin olun **geliştirme** seçeneği etkinleşir.

    > [!IMPORTANT]
    >  Unity 4.2 ve üzeri, **yayın kanal** bağlam menüsü öğesini Web Player bağlam menüsünde kullanılabilir yalnızca zaman **Alt** bağlam menüsü açılır gibi tuşuna basıldığında. Web Player Mac OS X üzerinde çalışıyorsa, basın **seçeneği** yerine anahtar.

 Son olarak, hata ayıklamak istediğiniz Unity örneğine bağlı olduğunuzdan emin olun. Bunun hakkında daha fazla bilgi için bkz: [Unity için Visual Studio bağlanmayı](#connecting-visual-studio-to-unity) bölümü.

### <a name="debugging-a-dll-in-your-unity-project"></a>Unity projenizdeki DLL hata ayıklama
 Böylece bunlar geliştirmek işlevselliği diğer projelerle kolaylıkla paylaşılabilir birçok Unity geliştiriciler kod bileşenleri dış DLL'ler olarak yazarsınız. Unity için Visual Studio Araçları, Unity projenizdeki diğer kod ile sorunsuz bir şekilde bu DLL'lerde kodda hata ayıklama kolay hale getirir.

> [!NOTE]
>  Şu anda yalnızca destekler Unity için Visual Studio Araçları DLL'leri yönetilen. C++ ile yazılmış olanlar gibi yerel kod DLL'lerde hata ayıklama desteklemez.

 Burada açıklanan senaryo kaynak koduna sahip varsaydığını unutmayın — diğer bir deyişle, geliştirme veya kendi birinci taraf kodu yeniden kullanma veya kod bir üçüncü taraf Kitaplığı'na ve Unity projenize DLL olarak dağıtmayı planlıyorsanız kaynağının sahip. Bu senaryoda, kaynak kodu içermeyen bir DLL hata ayıklama açıklanmaz.

##### <a name="to-debug-a-managed-dll-project-used-in-your-unity-project"></a>Unity projenizde kullanılan yönetilen DLL projesinde hata ayıklamak için

1.  Unity için Visual Studio Araçları tarafından oluşturulan Visual Studio çözümü varolan DLL projenize ekleyin. Daha az yaygın olarak, Unity projenizdeki kod bileşenlerini içerecek yeni bir yönetilen DLL projesi başlatılıyor; Bu durumda, yeni bir yönetilen DLL projesi için Visual Studio çözümü yerine ekleyebilirsiniz. Bir çözüme yeni veya var olan bir proje ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir çözüm projelerine ekleme](https://msdn.microsoft.com/en-us/library/vstudio/ff460187.aspx).

     ![Varolan DLL projenize ekleyin.](../cross-platform/media/vstu_debugging_dll_add_existing.png "vstu_debugging_dll_add_existing")

     Yalnızca bu adımları bir kez yapmanız gereken şekilde proje ve çözüm dosyaları yeniden yeniden oluşturmak sahip olsa bile her iki durumda da, Unity için Visual Studio Araçları proje başvurusu tutar.

2.  DLL projesi doğru Unity framework profilinde başvuru. Visual Studio'da DLL projenin özelliklerinde ayarlanan **hedef framework** özelliği kullanmakta olduğunuz Unity framework sürümü için. Bu Unity taban sınıf, Unity tam, mikro veya web gibi projenizin hedeflediği sınıf kitaplıkları temel API Uyumluluk eşleşen kitaplığıdır. Bu, diğer çerçeveler veya uyumluluk düzeyleri var, ancak Unity framework sürümünü kullanmakta olduğunuz varolmayabilir framework yöntemlerini çağırma, DLL önler.

     ![DLL hedef Framework'ü Unity framework ayarlayın.](../cross-platform/media/vstu_debugging_dll_target_framework.png "vstu_debugging_dll_target_framework")

3.  DLL Unity projenizin varlık klasörüne kopyalayın. Unity varlıklar paketlenir ve böylece bunlar çalışma zamanında yüklenebilir Unity uygulamanız ile birlikte dağıtılan dosyalardır. Çalışma zamanında bağlı DLL'ler olduğundan, DLL'leri varlıklar olarak dağıtılması gerekir. Bir varlık dağıtılması için Unity projenizdeki varlıklar klasörün içine yerleştirilecek DLL'leri Unity Düzenleyicisi'ni gerektirir. Bunu yapmak için iki yolu vardır:

    -   Çıkış klasörüne çıkış DLL ve PDB dosyalarını kopyalar sonrası yerleşik bir görev eklemek için DLL projesi derleme ayarlarını değiştirme **varlıklar** Unity projenizin klasör.

    -   Çıkış klasörü olarak ayarlamak için DLL projesi derleme ayarlarını değiştirme **varlıklar** Unity projenizin klasör. DLL ve PDB dosyalarını yerleştirilecek **varlıklar** klasör.

     PDB dosyaları, çünkü bunlar DLL'nin hata ayıklama simgeleri içerir ve kendi kaynak kodu biçiminde DLL kod eşleme hata ayıklama için gereklidir. Unity için Visual Studio Araçları, DLL oluşturmak için DLL ve PDB bilgileri kullanır. Unity komut dosyası motoru tarafından kullanılan hata ayıklama simgesi biçimi MDB dosyası.

4.  Kodunuzdaki hataları ayıklamanıza. Şimdi, DLL kaynak kodunuz Unity projenizin kaynak kodu ile birlikte hata ayıklama ve tüm hata ayıklama özellikleri gibi kesme noktaları için kullanılır ve kod atlama kullanın.
