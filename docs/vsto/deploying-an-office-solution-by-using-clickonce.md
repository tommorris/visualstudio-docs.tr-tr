---
title: ClickOnce kullanarak Office çözümü dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, deploying solutions
- ClickOnce deployment [Office development in Visual Studio], deploying solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0b5e1b9437412f343874b8cca6513a551d9900d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-an-office-solution-by-using-clickonce"></a>ClickOnce Kullanarak Office Çözümü Dağıtma
  ClickOnce kullanıyorsanız, Office çözümünüzde daha az adım dağıtabilirsiniz. Güncelleştirmeleri yayımlarsanız, çözümünüz bunları otomatik olarak algılar ve yükler. Bununla birlikte, ClickOnce, çözümünüzü bir bilgisayarın her kullanıcısı için ayrı ayrı yüklemenizi gerektirir. Bu nedenle, aynı bilgisayarda çözümünüzü birden fazla kullanıcı çalıştıracaksa Windows Installer (.msi) kullanmayı düşünmelisiniz.  
  
## <a name="in-this-topic"></a>Bu konuda  
  
-   [Çözüm yayımlama](#Publish)  
  
-   [Çözüme güven vermek istediğiniz nasıl karar verin](#Trust)  
  
-   [Çözümü kullanıcıların Yardım](#Helping)  
  
-   [(Yalnızca belge düzeyi özelleştirmeleri) son kullanıcının bilgisayarına bir çözüm belge yerleştirin](#Put)  
  
-   [SharePoint (yalnızca belge düzeyi özelleştirmeleri) çalıştıran bir sunucuya bir çözüm belge yerleştirin](#SharePoint)  
  
-   [Özel bir yükleyici oluşturma](#Custom)  
  
-   [Bir güncelleştirme yayımlama](#Update)  
  
-   [Çözümün yükleme konumunu değiştirme](#Location)  
  
-   [Bir çözümü bir önceki sürüme geri](#Roll)  
  
 Bir Windows Installer dosyası oluşturarak Office çözümü dağıtma hakkında daha fazla bilgi için bkz: [tarafından Windows Installer kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
##  <a name="Publish"></a> Çözüm yayımlama  
 Çözümünüzü kullanarak yayımlayabilirsiniz **Yayımlama Sihirbazı** veya **Proje Tasarımcısı**. Bu yordamda kullanacağınız **Proje Tasarımcısı** çünkü tam Yayımlama seçenekleri kümesi sağlar. Bkz: [Yayımlama Sihirbazı &#40;Visual Studio'da Office geliştirme&#41;](../vsto/publish-wizard-office-development-in-visual-studio.md).  
  
#### <a name="to-publish-the-solution"></a>Çözümü yayımlamak için  
  
1.  İçinde **Çözüm Gezgini**, projeniz için adlı düğümü seçin.  
  
2.  Menü çubuğunda seçin **proje**, *ProjectName* **özellikleri**.  
  
3.  İçinde **Proje Tasarımcısı**, seçin **Yayımla** sekmesinde, aşağıdaki çizimde gösterilmektedir.  
  
     ![Proje Tasarımcısı'nın Yayımla sekmesinde](../vsto/media/vsto-publishtab.png "Yayımla sekmesi Proje Tasarımcısı")  
  
4.  İçinde **yayımlama klasörü konumu (ftp sunucusu veya dosya yolu)** kutusunda, istediğiniz klasörün yolunu girin **Proje Tasarımcısı** çözüm dosyalarını kopyalamak için.  
  
     Aşağıdaki yol türlerinden herhangi birini girebilirsiniz.  
  
    -   Yerel bir yol (örneğin, *C:\FolderName\FolderName*).  
  
    -   Bir Evrensel Adlandırma Kuralı (UNC) yolu, ağ üzerindeki bir klasöre (örneğin,  *\\\ServerName\FolderName*).  
  
    -   Göreli bir yol (örneğin, *yayınklasörü\\*, içine projenin varsayılan olarak yayımlanır klasör olduğu).  
  
5.  İçinde **yükleme klasörü URL'si** kutusuna, son kullanıcılar nerede çözümünüzü konumunun tam yolunu girin.  
  
     Konum henüz bilmiyorsanız, herhangi bir şey bu alana girmeyin. Varsayılan olarak, ClickOnce, kullanıcılarınızın çözümü yüklediği klasörde güncelleştirmeleri arar.  
  
6.  Seçin **Önkoşullar** düğmesi.  
  
7.  İçinde **Önkoşullar** iletişim kutusunda **Önkoşul bileşenlerini yüklemek için Kurulum programını oluşturun** onay kutusu seçilidir.  
  
8.  İçinde **yüklemek için hangi Önkoşullar seçin** listesinde, onay kutularını seçin **Windows Installer 4.5** ve uygun .NET Framework paket.  
  
     Örneğin, varsa, çözüm hedeflerine [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], onay kutularını işaretleyin **Windows Installer 4.5** ve **Microsoft .NET Framework 4.5 tam**.  
  
9. Çözümünüzü .NET Framework 4.5 hedefliyorsa, ayrıca seçin **Office çalışma zamanı için Visual Studio 2010 Araçları** onay kutusu.  
  
    > [!NOTE]  
    >  Varsayılan olarak, bu onay kutusu görünmüyor. Bu onay kutusunu göstermek için bir Önyükleyici paketi oluşturmanız gerekir. Bkz: [ile Visual Studio 2012 için bir Office 2013 VSTO eklenti önyükleyici paketi oluşturma](http://blogs.msdn.com/b/vsto/archive/2012/12/21/creating-a-bootstrapper-package-for-an-office-2013-vsto-add-in-with-visual-studio-2012.aspx).  
  
10. Altında **Önkoşullar için yükleme konumu belirtmek**, görüntülenen ve ardından seçeneklerden birini **Tamam** düğmesi.  
  
     Aşağıdaki tabloda her bir seçenek açıklanmaktadır.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |**Bileşen satıcısının web sitesinden önkoşulları**|Kullanıcıdan, bu önkoşulları satıcının sitesinden indirmesi ve yüklemesi istenir.|  
    |**Önkoşulları Uygulamamla aynı konumdan indir**|Önkoşul yazılımı çözümle birlikte yüklenir. Bu seçeneği tercih ederseniz, Visual Studio sizin için önkoşul paketlerinin tümünü yayımlama konumuna kopyalar. Bu seçeneğin çalışması için önkoşul paketleri geliştirme bilgisayarında olmalıdır.|  
    |**Önkoşulları aşağıdaki konumdan indir**|Visual Studio tüm önkoşul paketlerini belirttiğiniz konuma kopyalar ve bunları çözümle birlikte yükler.|  
  
     Bkz: [Önkoşullar iletişim kutusu](/visualstudio/ide/reference/prerequisites-dialog-box).  
  
11. Seçin **güncelleştirmeleri** düğmesini tıklatın, her son kullanıcının VSTO eklenti veya özelleştirme güncelleştirmeleri denetlemek ve ardından istediğiniz sıklıkta belirlemenizi **Tamam** düğmesi.  
  
    > [!NOTE]  
    >  Bir CD ya da bir çıkarılabilir sürücü kullanarak dağıtıyorsanız seçin **hiçbir zaman güncelleştirmeleri denetlemek için** seçenek düğmesi.  
  
     Bir güncelleştirme yayımlama hakkında daha fazla bilgi için bkz: [bir güncelleştirme yayımlama](#Update).  
  
12. Seçin **seçenekleri** düğmesini tıklatın, seçenekleri gözden **seçenekleri** iletişim kutusuna ve ardından **Tamam** düğmesi.  
  
13. Seçin **Şimdi Yayımla** düğmesi.  
  
     Visual Studio, bu yordamda daha önce belirttiğiniz yayımlama klasörüne aşağıdaki klasörleri ve dosyaları ekler.  
  
    -   **Uygulama dosyalarını** klasör.  
  
    -   Kurulum programı.  
  
    -   En son sürümün dağıtım bildirimine işaret eden bir dağıtım bildirimi.  
  
     **Uygulama dosyalarını** klasörü, yayımladığınız her bir sürümü için bir alt klasör içerir. Her bir sürüme özgü alt klasörde aşağıdaki dosyalar bulunur.  
  
    -   Uygulama bildirimi.  
  
    -   Dağıtım bildirimi.  
  
    -   Özelleştirme derlemeleri.  
  
     Aşağıdaki çizimde, Outlook VSTO eklenti için yayımlama klasörü yapısını gösterir.  
  
     ![Klasör yapısını yayımlama](../vsto/media/publishfolderstructure.png "klasör yapısını yayımlama")  
  
    > [!NOTE]  
    >  Internet Information Services (IIS) güvenli bir yüklemesi nedeniyle güvenli olmayan bir uzantı dosyaları engellemez böylece ClickOnce derlemelere .deploy uzantısı ekler. Kullanıcı çözümü yüklediğinde ClickOnce .deploy uzantısını kaldırır.  
  
14. Çözüm dosyalarını, bu yordamda daha önce belirttiğiniz yükleme konumuna kopyalayın.  
  
##  <a name="Trust"></a> Çözüme güven vermek istediğiniz nasıl karar verin  
 Bir çözümün kullanıcı bilgisayarları üzerinde çalışması için önce, sizin güven kazandırmanız ya da kullanıcıların çözümü yükledikleri sırada bir güvenlik istemine yanıt vermeleri gerekir. Çözüme güven kazandırmak için, bilinen ve güvenilir bir yayımcıyı tanımlayan bir sertifika kullanarak bildirimleri imzalayın. Bkz: [uygulama ve dağıtım imzalayarak çözümü güvenen bildirimleri](../vsto/granting-trust-to-office-solutions.md#Signing).  
  
 Belge düzeyi özelleştirme dağıtıyorsanız ve belgenin kullanıcının bilgisayarda bir klasöre yerleştirin veya belge bir SharePoint sitesinde kullanılabilir yapmak istediğiniz, Office belgesinin konumunu güvenleri emin olun. Bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
##  <a name="Helping"></a> Çözümü kullanıcıların Yardım  
 Kullanıcılar kurulum programını çalıştırarak, dağıtım bildirimini açarak veya belge düzeyinde bir özelleştirme olması durumunda belgeyi doğrudan açarak çözümü yükleyebilirler. En iyi uygulama olarak, kullanıcılar çözümünüzü kurulum programını kullanarak yüklemelidir. Diğer iki yaklaşım önkoşul yazılımı yüklü olduğundan emin olun yok. Kullanıcılar belgeyi yükleme konumundan açmak isterse, Office uygulamasının Güven Merkezi'nde bu konumu güvenilir konumlar listesine eklemeleri gerekir.  
  
### <a name="opening-the-document-of-a-document-level-customization"></a>Belge düzeyinde bir özelleştirmenin belgesini açma  
 Kullanıcılar, belge düzeyinde bir özelleştirmenin belgesini doğrudan yükleme konumundan açabilirler veya belgeyi kendi yerel bilgisayarlarına kopyalayıp sonra bu kopyayı açabilirler.  
  
 En iyi uygulama olarak, kullanıcılar belgenin bir kopyasını kendi bilgisayarlarında açmalıdır; böylece birden fazla kullanıcı aynı anda aynı kopyayı açmaya çalışmaz. Bu uygulamayı zorunlu tutmak için, kurulum programınızı, belgeyi kullanıcı bilgisayarlarına kopyalayacak şekilde yapılandırabilirsiniz. Bkz: [(yalnızca belge düzeyi özelleştirmeleri) son kullanıcının bilgisayarına bir çözüm belgenin Put](#Put).  
  
### <a name="installing-the-solution-by-opening-the-deployment-manifest-from-an-iis-website"></a>Bir IIS web sitesinden dağıtım bildirimini açarak çözümü yükleme  
 Kullanıcılar, web'ten dağıtım bildirimini açmak suretiyle bir Office çözümünü yükleyebilirler. Ancak, güvenliği sağlanmış bir Internet Information Services (IIS) yüklemesi .vsto uzantılı dosyaları engelleyecektir. Bir Office çözümünü IIS kullanarak dağıtabilmeniz için önce MIME türü IIS'de tanımlanmalıdır.  
  
##### <a name="to-add-the-vsto-mime-type-to-iis-60"></a>IIS 6.0'a .vsto MIME türünü eklemek için  
  
1.  IIS 6.0 çalıştıran sunucu seçin **Başlat**, **tüm programlar**, **Yönetimsel Araçlar**, **Internet Information Services (IIS) Yöneticisi'ni**.  
  
2.  Bilgisayar adı seçin **Web siteleri** klasör veya yapılandırmakta web sitesi.  
  
3.  Menü çubuğunda seçin **eylem**, **özellikleri**.  
  
4.  Üzerinde **HTTP üstbilgileri** sekmesinde, seçin **MIME türleri** düğmesi.  
  
5.  İçinde **MIME türleri** penceresinde, seçin **yeni** düğmesi.  
  
6.  İçinde **MIME türü** penceresinde girin **.vsto** uzantısı olarak girin **uygulama/x-ms-vsto** MIME olarak yazın ve ardından yeni ayarlar uygulanır.  
  
    > [!NOTE]  
    >  Değişikliklerin etkili olması için, World Wide Web Yayımlama Hizmeti'ni yeniden başlatmalı veya çalışan işleminin tekrar geri dönmesini beklemelisiniz. Bundan sonra tarayıcının disk önbelleğini temizlemeli ve .vsto dosyasını yeniden açmayı denemelisiniz.  
  
##### <a name="to-add-the-vsto-mime-type-to-iis-70"></a>IIS 7.0 .vsto MIME türü eklemek için  
  
1.  IIS 7.0 çalıştıran sunucu seçin **Başlat**, **tüm programlar**, **Donatılar**.  
  
2.  Kısayol menüsünü açın **komut istemi**ve ardından **yönetici olarak çalıştır.**  
  
3.  İçinde **açık** kutusunda, aşağıdaki yolunu girin ve ardından **Tamam** düğmesi.  
  
    ```  
    %windir%\system32\inetsrv   
    ```  
  
4.  Aşağıdaki komutu girin ve ardından yeni ayarları uygulayın.  
  
    ```  
    set config /section:staticContent /+[fileExtension='.vsto',mimeType='application/x-ms-vsto']  
    ```  
  
    > [!NOTE]  
    >  Değişikliklerin etkili olması için, World Wide Web Yayımlama Hizmeti'ni yeniden başlatmalı veya çalışan işleminin tekrar geri dönmesini beklemelisiniz. Bundan sonra tarayıcının disk önbelleğini temizlemeli ve .vsto dosyasını yeniden açmayı denemelisiniz.  
  
##  <a name="Put"></a> (Yalnızca belge düzeyi özelleştirmeleri) son kullanıcının bilgisayarına bir çözüm belge yerleştirin  
 Çözümünüzü son kullanıcının bilgisayarına belgenin bunları için dağıtım sonrası eylemi oluşturarak kopyalayabilirsiniz. Böylece, kullanıcı çözümünüzü yükledikten sonra belgeyi kendi bilgisayarlarına yükleme konumundan el ile kopyalamak sahip değil. Dağıtım sonrası eylemi tanımlayan bir sınıf oluşturun, yapı ve Çözümü yayımlamak, uygulama bildirimini değiştirin ve uygulama ve dağıtım bildirimini yeniden imzalamak gerekir.  
  
 Aşağıdaki yordamlar projenizin adına olduğunu varsayar **ExcelWorkbook** ve çözüme yayımlama **C:\publish** bilgisayarınızda dizin.  
  
### <a name="create-a-class-that-defines-the-post-deployment-action"></a>Dağıtım sonrası eylemi tanımlayan bir sınıf oluşturma  
  
1.  Menü çubuğunda seçin **dosya**, **Ekle**, **yeni proje**.  
  
2.  İçinde **Yeni Proje Ekle** iletişim kutusunda **yüklü şablonlar** bölmesinde seçin **Windows** klasör.  
  
3.  İçinde **şablonları** bölmesinde seçin **sınıf kitaplığı** şablonu.  
  
4.  İçinde **adı** alanına, **FileCopyPDA**ve ardından **Tamam** düğmesi.  
  
5.  İçinde **Çözüm Gezgini**, seçin **FileCopyPDA** projesi.  
  
6.  Menü çubuğunda seçin **proje**, **Başvuru Ekle**.  
  
7.  Üzerinde **.NET** sekmesinde, Microsoft.VisualStudio.Tools.Applications.Runtime'a ve Microsoft.VisualStudio.Tools.Applications.ServerDocument'a başvurular ekleyin.  
  
8.  Sınıfı için yeniden adlandırma `FileCopyPDA`ve ardından dosyanın içeriğini kod ile değiştirin. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Belgeyi kullanıcının masaüstüne kopyalar.  
  
    -   _AssemblyLocation özelliği göreli bir yol dağıtım bildirimi için tam bir yol olarak değişir.  
  
    -   Kullanıcı çözümü kaldırırsa, dosyayı siler.  
  
     [!code-vb[Trin_ExcelWorkbookPDA#7](../vsto/codesnippet/VisualBasic/trin_excelworkbookpda/filecopypda/class1.vb#7)]
     [!code-csharp[Trin_ExcelWorkbookPDA#7](../vsto/codesnippet/CSharp/trin_excelworkbookpda/filecopypda/class1.cs#7)]  
  
### <a name="build-and-publish-the-solution"></a>Çözümü derleme ve yayımlama  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **FileCopyPDA** proje ve ardından **yapı**.  
  
2.  Kısayol menüsünü açın **ExcelWorkbook** proje ve ardından **yapı**.  
  
3.  Kısayol menüsünü açın **ExcelWorkbook** proje ve ardından **Başvuru Ekle**.  
  
4.  İçinde **Başvuru Ekle** iletişim kutusunda, seçin **projeleri** sekmesinde, seçin **FileCopyPDA**ve ardından **Tamam** düğmesi.  
  
5.  İçinde **Çözüm Gezgini**, seçin **ExcelWorkbook** projesi.  
  
6.  Menü çubuğunda seçin **proje**, **yeni klasör**.  
  
7.  ENTER **veri**ve ardından Enter tuşuna seçin.  
  
8.  İçinde **Çözüm Gezgini**, seçin **veri** klasör.  
  
9. Menü çubuğunda seçin **proje**, **varolan öğeyi Ekle**.  
  
10. İçinde **varolan öğeyi Ekle** iletişim kutusunda, Gözat için çıktı dizinine **ExcelWorkbook** seçin, proje **ExcelWorkbook.xlsx** dosya ve seçin **Ekleme** düğmesi.  
  
11. İçinde **Çözüm Gezgini** seçin **ExcelWorkbook.xlsx** dosya.  
  
12. İçinde **özellikleri** penceresinde, değişiklik **yapı eylemi** özelliğine **içerik** ve **çıktı dizinine Kopyala** özelliği **Yeniyse Kopyala**.  
  
     Bu adımları tamamladıktan sonra projenizin aşağıdaki çizimde benzer.  
  
     ![Dağıtım sonrası eylemini yapısını yansıtın. ] (../vsto/media/vsto-postdeployment.png "Proje dağıtım sonrası eylemini yapısı.")  
  
13. Yayımlama **ExcelWorkbook** projesi.  
  
### <a name="modify-the-application-manifest"></a>Uygulama bildiriminde değişiklik yapma  
  
1.  Açık **c:\publish** kullanarak dizin **dosya Gezgini**.  
  
2.  Açık **uygulama dosyalarını** klasörünü ve ardından en son karşılık gelen klasörünü açın yayımlanan çözümünüzü sürümü.  
  
3.  Açık **ExcelWorkbook.dll.manifest** dosyasını Not Defteri gibi bir metin düzenleyicisinde.  
  
4.  Sonra `</vstav3:update>` öğesi, kodu ekleyin. Sınıf özniteliği için `<vstav3:entryPoint>` öğesi, aşağıdaki sözdizimini kullanın: *İsimUzayıAdı.SınıfAdı*. Sonuçta elde edilen giriş noktası adı olacak şekilde aşağıdaki örnekte, ad alanı ve sınıf adları aynıdır `FileCopyPDA.FileCopyPDA`.  
  
    ```  
    <vstav3:postActions>  
      <vstav3:postAction>  
        <vstav3:entryPoint  
          class="FileCopyPDA.FileCopyPDA">  
          <assemblyIdentity  
            name="FileCopyPDA"  
            version="1.0.0.0"  
            language="neutral"  
            processorArchitecture="msil" />  
        </vstav3:entryPoint>  
        <vstav3:postActionData>  
        </vstav3:postActionData>  
      </vstav3:postAction>  
    </vstav3:postActions>  
    ```  
  
### <a name="re-sign-the-application-and-deployment-manifests"></a>Uygulama ve dağıtım bildirimlerini yeniden imzalama  
  
1.  İçinde **%USERPROFILE%\Documents\Visual Studio 2013\Projects\ExcelWorkbook\ExcelWorkbook** klasörü, kopya **ExcelWorkbook_TemporaryKey.pfx** yapıştırınvesertifikadosyası *Yayınklasörü* **\Application Files\ExcelWorkbook**\__MostRecentPublishedVersion_ klasör.
  
2.  Visual Studio komut istemi açın ve dizinleri değiştirmek **c:\publish\Application Files\ExcelWorkbook**\__MostRecentPublishedVersion_ klasörünü (örneğin, **c:\publish\Application Files\ExcelWorkbook_1_0_0_4**).  
  
3.  Aşağıdaki komutu çalıştırarak değiştirilmiş uygulama bildirimini imzalayın:  
  
    ```  
    mage -sign ExcelWorkbook.dll.manifest -certfile ExcelWorkbook_TemporaryKey.pfx  
    ```  
  
     "ExcelWorkbook.dll.manifest başarıyla imzalandı" iletisi görüntülenir.  
  
4.  Dönüştür **c:\publish** klasörünü ve ardından güncelleştirme ve oturum dağıtım bildirimi için aşağıdaki komutu çalıştırın:  
  
    ```  
    mage -update ExcelWorkbook.vsto -appmanifest "Application Files\Ex  
    celWorkbookMostRecentVersionNumber>\ExcelWorkbook.dll.manifest" -certfile "Application Files\ExcelWorkbookMostRecentVersionNumber>\ExcelWorkbook_TemporaryKey.pfx"  
    ```  
  
    > [!NOTE]  
    >  Önceki örnekte, çözümünüzü yayımlanan en son sürümünü sürüm numarasıyla MostRecentVersionNumber değiştirin (örneğin, **1_0_0_4**).  
  
     "ExcelWorkbook.vsto başarıyla imzalandı" iletisi görüntülenir.  
  
5.  ExcelWorkbook.vsto dosyaya Kopyala **c:\publish\Application Files\ExcelWorkbook**\__MostRecentVersionNumber_ dizini.  
  
##  <a name="SharePoint"></a> SharePoint (yalnızca belge düzeyi özelleştirmeleri) çalıştıran bir sunucuya bir çözüm belge yerleştirin  
 Belge düzeyinde özelleştirmenizi SharePoint kullanarak son kullanıcılara yayımlayabilirsiniz. Kullanıcılar SharePoint sitesine gidip belgeyi açtığında, çalışma zamanı çözümü paylaşılan ağ klasöründen kullanıcının yerel bilgisayarına otomatik olarak yükler. Çözüm yerel olarak yüklendikten sonra, belge başka bir yere (örneğin, masaüstüne) kopyalansa bile özelleştirme işlevini yerine getirmeye devam eder.  
  
#### <a name="to-put-the-document-on-a-server-thats-running-sharepoint"></a>Belgeyi SharePoint çalıştıran bir sunucuya koymak için  
  
1.  Çözüm belgesini SharePoint sitesindeki bir belge kitaplığına ekleyin.  
  
2.  Aşağıdaki yaklaşımlardan biri için adımları uygulayın:  
  
    -   SharePoint çalıştıran sunucuyu, tüm bilgisayarlarda Word veya Excel'deki Güven Merkezi'ne eklemek için Office Yapılandırma Aracı'nı kullanın.  
  
         Bkz: [güvenlik ilkeleri ve Office 2010'daki ayarları](http://go.microsoft.com/fwlink/?LinkId=99227).  
  
    -   Her kullanıcının aşağıdaki adımları uygulamasını sağlayın.  
  
        1.  Yerel bilgisayarda açık Word veya Excel seçin **dosya** sekmesini ve ardından **seçenekleri** düğmesi.  
  
        2.  İçinde **Güven Merkezi** iletişim kutusunda, seçin **Güvenilen Konumlar** düğmesi.  
  
        3.  Seçin **güvenilir konumlara izin ver (önerilmez) Ağımdaki** onay kutusunu işaretleyin ve ardından **yeni konum Ekle** düğmesi.  
  
        4.  İçinde **yolu** kutusunda, karşıya yüklediğiniz belge içeren SharePoint belge kitaplığı URL'si girin (örneğin, *http://SharePointServerName/TeamName/ProjectName/DocumentLibraryName*).  
  
             Default.aspx veya AllItems.aspx gibi varsayılan Web sayfasının adı eklemeyin.  
  
        5.  Seçin **bu konumun alt klasörleri güvenilir de** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
             Kullanıcılar belgeyi SharePoint sitesinden açtığında, belge açılır ve özelleştirme yüklenir. Kullanıcılar belgeyi kendi masaüstlerine kopyalayabilir. Belgedeki özellikler belgenin ağ konumuna işaret ettiğinden, özelleştirme çalışmaya devam edecektir.  
  
##  <a name="Custom"></a> Özel bir yükleyici oluşturma  
 Çözümü yayımladığınızda, sizin için oluşturduğu kurulum programını kullanmak yerine, Office çözümünüz için özel bir yükleyici oluşturabilirsiniz. Örneğin, yüklemeyi başlatmak için bir oturum açma komut dosyası kullanabilir veya çözümü, kullanıcı etkileşimi olmadan yüklemek için bir toplu iş dosyası kullanabilirsiniz. Bu senaryolar en çok, önkoşullar son kullanıcı bilgisayarlarında zaten yüklü olduğunda işe yarar.  
  
 Özel yükleme işleminizin bir parçası olarak, Office çözümleri için yükleyici aracını (VSTOInstaller.exe) çağırın; bu araç varsayılan olarak aşağıdaki konuma yüklenir:  
  
 %commonprogramfiles%\microsoft shared\VSTO\10.0\VSTOInstaller.exe  
  
 Araç bu konumda yoksa, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSTO Runtime Setup\v4\InstallerPath veya HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSTO Runtime Setup\v4\InstallerPath kayıt defteri anahtarını kullanarak bu aracın yolunu bulabilirsiniz.  
  
 VSTOinstaller.exe ile birlikte aşağıdaki parametreleri kullanabilirsiniz.  
  
|Parametre|Tanım|  
|---------------|----------------|  
|/Install veya /I|Çözümü yükler. Bu seçeneğin ardından bir dağıtım bildiriminin konumunu vermelisiniz. Yerel bilgisayarda, bir Evrensel Adlandırma Kuralı (UNC) dosya paylaşımına bir yol belirtebilirsiniz. Yerel bir yol belirtin (*C:\FolderName\PublishFolder*), göreli bir yol (*Yayımla\\*), ya da tam bir konum (*\\\ServerName\ KlasörAdı* veya http://*SunucuAdı/KlasörAdı*).|  
|/Uninstall veya /U|Çözümü kaldırır. Bu seçeneğin ardından bir dağıtım bildiriminin konumunu vermelisiniz. Bir yol yerel bilgisayarda, bir UNC dosya paylaşımı olabilir belirtebilirsiniz. Yerel bir yol belirtin (*c:\FolderName\PublishFolder*), göreli bir yol (*Yayımla\\*), ya da tam bir konum (*\\\ServerName\ KlasörAdı* veya http://*SunucuAdı/KlasörAdı*).|  
|/Silent veya /S|Kullanıcıdan bir şey girmesini istemeden veya ileti görüntülemeden yükler veya kaldırır. Güven istemi gerekiyorsa, özelleştirme yüklendiklerini veya değil.|  
|/Help or /?|Yardım bilgilerini görüntüler.|  
  
 VSTOinstaller.exe dosyasını çalıştırdığınızda aşağıdaki hata kodları görünebilir.  
  
|Hata Kodu|Tanım|  
|----------------|----------------|  
|0|Çözüm başarıyla yüklendi ya da kaldırıldı veya VSTOInstaller Yardımı görüntülendi.|  
|-100|Bir veya daha fazla komut satırı seçeneği geçerli değil veya bir kereden fazla ayarlandı. Daha fazla bilgi için girin "vstoinstaller /?" veya bkz [özel yükleyici için ClickOnce Office çözümü oluşturma](http://msdn.microsoft.com/en-us/3e5887ed-155f-485d-b8f6-3c02c074085e).|  
|-101|Bir veya daha fazla komut satırı seçenekleri geçerli değil. Daha fazla bilgi için "vstoinstaller /?" girin.|  
|-200|Dağıtım bildirimi URI geçerli değil. Daha fazla bilgi için "vstoinstaller /?" girin.|  
|-201|Dağıtım bildirimi geçerli değil çünkü çözüm yüklenemedi. Bkz: [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md).|  
|-202|Çözüm, uygulama bildirimi bölümünü Office için Visual Studio Araçları geçerli olmadığı için yüklenemedi. Bkz: [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md).|  
|-203|Bir yükleme hatası oluştuğundan çözüm yüklenemedi. Dağıtım bildiriminin URI'sini veya ağ dosya konumunu denetleyin ve sonra yeniden deneyin.|  
|-300|Bir güvenlik özel durumu oluştuğu için çözüm yüklenemedi. Bkz: [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).|  
|-400|Çözüm yüklenemedi.|  
|-401|Çözüm kaldırılması tamamlanamadı.|  
|-500|Çözüm yüklenemediğinden ya da kaldırılamadığından veya dağıtım bildirimi indirilemediğinden işlem iptal edildi.|  
  
##  <a name="Update"></a> Bir güncelleştirme yayımlama  
 Bir çözüm güncelleştirmek için yeniden kullanarak yayımlamadan **Proje Tasarımcısı** veya **Yayımlama Sihirbazı**, ve ardından güncelleştirilmiş çözüm yükleme konumuna kopyalayın. Dosyaları yükleme konumuna kopyalarken, önceki dosyaların üzerine yazdığınızdan emin olun.  
  
 Çözüm denetleyen bir sonraki seferde bir güncelleştirme bulmak ve en yeni sürümü otomatik olarak yüklemek.  
  
##  <a name="Location"></a> Çözümün yükleme konumunu değiştirme  
 Bir çözüm yayımlandıktan sonra yükleme yolunu ekleyebilir veya değiştirebilirsiniz. Yükleme yolunu değiştirmek istemenizin nedeni şunlardan biri veya daha fazlası olabilir:  
  
-   Kurulum programı, henüz yükleme yolu bilinmezken derlenmiştir.  
  
-   Çözüm dosyaları farklı bir konuma kopyalanmıştır.  
  
-   Yükleme dosyalarını barındıran sunucu yeni bir ada veya konuma sahiptir.  
  
 Bir çözümün yükleme yolunu değiştirmek için kurulum programını güncelleştirmelisiniz; daha sonra da kullanıcıların bunu çalıştırması gerekir. Belge düzeyinde özelleştirmeler için, kullanıcıların ayrıca belgelerindeki bir özelliği de yeni konuma işaret edecek şekilde güncelleştirmeleri gerekir.  
  
> [!NOTE]  
>  Belge özelliklerini güncelleştirmek için kullanıcılara sor istemiyorsanız, kullanıcıların güncelleştirilmiş belge yükleme konumundan almak isteyebilirsiniz.  
  
#### <a name="to-change-the-installation-path-in-the-setup-program"></a>Kurulum programındaki yükleme konumunu değiştirmek için  
  
1.  Açık bir **komut istemi** penceresi ve yükleme klasörünü değiştir dizinleri.  
  
2.  Kurulum programını çalıştırın ve dahil `/url` parametresi, yeni yükleme yolu bir dize olarak alır.  
  
     Aşağıdaki örnekte, Fabrikam web sitesindeki bir konumun yükleme yolunun nasıl değiştirileceği gösterilmektedir; ancak siz bu URL'yi istediğiniz yol ile değiştirebilirsiniz:  
  
    ```  
    setup.exe /url="http://www.fabrikam.com/newlocation"  
    ```  
  
    > [!NOTE]  
    >  Bir ileti ekrana gelir ve yürütülebilir öğenin imzasının geçersiz kılınacağını belirtirse, çözümü imzalamak için kullanılan sertifika artık geçerli değil ve yayımcısı bilinmiyor demektir. Sonuç olarak, kullanıcıların, çözümü yüklemeden önce çözümün kaynağına güvendiklerini onaylamaları gerekecektir.  
  
    > [!NOTE]  
    >  URL geçerli değerini görüntülemek için Çalıştır `setup.exe /url`.  
  
 Belge düzeyi özelleştirmeleri için kullanıcıların belgeyi açın ve kendi _AssemblyLocation özelliği güncelleştirmesi gerekir. Aşağıdaki adımlarda kullanıcıların bu görevi nasıl yerine getirecekleri açıklanmaktadır.  
  
#### <a name="to-update-the-assemblylocation-property-in-a-document"></a>Bir belgede _AssemblyLocation özelliğini güncelleştirmek için  
  
1.  Üzerinde **dosya** sekmesinde, seçin **bilgisi**, hangi aşağıda gösterilmektedir.  
  
     ![Excel'de bilgileri sekmesi](../vsto/media/vsto-infotab.png "Excel'de bilgileri sekmesi")  
  
2.  İçinde **özellikleri** listesinde, seçin **Gelişmiş Özellikler**, hangi aşağıda gösterilmektedir.  
  
     ![Gelişmiş özellikler Excel'de. ] (../vsto/media/vsto-advanceddocumentproperties.png "Gelişmiş özellikler Excel'de.")  
  
3.  Üzerinde **özel** sekmesinde **özellikleri** listesinde, aşağıdaki çizimde gösterildiği gibi _AssemblyLocation, seçin.  
  
     ![AssemblyLocation özelliği. ] (../vsto/media/vsto-assemblylocationproperty.png "AssemblyLocation özelliği.")  
  
     **Değeri** kutusu içeren dağıtım bildirimi tanımlayıcısı.  
  
4.  Bir tanımlayıcı önce biçimde bir çubuğu arkasından belgesinin tam yolunu girin *yolu*|*tanımlayıcısı* (örneğin, *File://ServerName/ KlasörAdı/FileName | 74744e4b-e4d6-41eb-84f7-ad20346fe2d9*.  
  
     Bu tanımlayıcı biçimlendirme hakkında daha fazla bilgi için bkz: [özel belge özelliklerine genel bakış](../vsto/custom-document-properties-overview.md).  
  
5.  Seçin **Tamam** button ve ardından belgesini kaydedin ve kapatın.  
  
6.  Çözümü belirtilen konuma yüklemek için, kurulum programını /url parametresi olmadan çalıştırın.  
  
##  <a name="Roll"></a> Bir çözümü bir önceki sürüme geri  
 Bir çözümü geri aldığınızda, kullanıcıları bu çözümün önceki bir sürümüne geri döndürmüş olursunuz.  
  
#### <a name="to-roll-back-a-solution"></a>Bir çözümü geri almak için  
  
1.  Çözümün yükleme konumunu açın.  
  
2.  En üst düzey publish klasöründe dağıtım bildirimini (.vsto dosyası) silin.  
  
3.  Geri almak istediğiniz sürüme ait alt klasörü bulun.  
  
4.  O alt klasördeki dağıtım bildirimini üst düzey publish klasörüne kopyalayın.  
  
     Örneğin, çağrılan bir çözüm geri almak için **OutlookAddIn1** sürümden 1.0.0.1 1.0.0.0 sürümü, dosyayı kopyalama **OutlookAddIn1.vsto** gelen **Outlookaddın1_1_0_0_0** klasör. Yapıştır üst düzey dosyasına yayımlamak için sürüme özgü dağıtım bildirimini üzerine klasörü **Outlookadın1_1_0_0_1** , edildi zaten vardır.  
  
     Aşağıdaki resimde, bu örnekteki publish (yayımlama) klasörü yapısı gösterilmektedir.  
  
     ![Klasör yapısını yayımlama](../vsto/media/publishfolderstructure.png "klasör yapısını yayımlama")  
  
     Kullanıcının uygulamayı ya da özelleştirilmiş belgeyi bir sonraki açışında, dağıtım bildirimindeki değişiklik algılanır. Office çözümünün önceki sürümü ClickOnce önbelleğinden çalışır.  
  
> [!NOTE]  
>  Yerel veriler çözümün sadece bir önceki sürümü için kaydedilir. İki sürümü geri alma yerel veriler korunur değil. Yerel veriler hakkında daha fazla bilgi için bkz: [erişme yerel ve uzak veri ClickOnce uygulamalarında](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office çözümleri yayımlama](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Nasıl yapılır: ClickOnce kullanarak Office çözümü yayımlama](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)   
 [Nasıl yapılır: ClickOnce Office çözümünü yükleme](http://msdn.microsoft.com/en-us/14702f48-9161-4190-994c-78211fe18065)   
 [Nasıl yapılır: ClickOnce kullanarak bir SharePoint sunucusu için belge düzeyi Office çözümü yayımlama](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58)   
 [ClickOnce Office çözümü için özel bir yükleyici oluşturma](http://msdn.microsoft.com/en-us/3e5887ed-155f-485d-b8f6-3c02c074085e)  
  
  
