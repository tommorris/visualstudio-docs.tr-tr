---
title: Windows Installer kullanarak Office çözümü dağıtma
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, setup project
- Office development in Visual Studio, MSI
- deploying applications [Office development in Visual Studio], setup project
- deploying applications [Office development in Visual Studio], MSI
- ClickOnce deployment [Office development in Visual Studio], MSI
- publishing Office solutions [Office development in Visual Studio], setup project
- Office applications [Office development in Visual Studio], MSI
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6f9936111360d6734e1280e84f34416efbedb05c
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="deploy-an-office-solution-by-using-windows-installer"></a>Windows Installer kullanarak Office çözümü dağıtma
Office çözümünüz için Windows Installer kullanarak oluşturmayı öğrenin [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].  
  
Windows Installer oluşturmak için Visual Studio kullanarak, son kullanıcının bilgisayarda yönetici erişimi gerektiren Office çözümü dağıtabilirsiniz. Örneğin, böyle bir dosya için bir çözüm yalnızca bir kez bir bilgisayarın tüm kullanıcıları yüklemek için kullanabilirsiniz. Çözüm bilgisayarı her bir kullanıcı için ayrı olarak yüklenmesi gereken ancak bu ClickOnce kullanarak Office çözümü de dağıtabilirsiniz.  
  
  
## <a name="in-this-topic"></a>Bu konuda  
  
- [VSTO eklenti örnekleri indirin](#Download)  
  
- [Get InstallShield Limited Edition](#Obtain)  
  
- [Çözümlerine güven verme konusunda karar verin](#ApplySecurity)  
  
- [Kurulum projesi oluşturma](#Create)  
  
- [Proje Çıktı Ekle](#Add)  
  
- [Dağıtım ve uygulama bildirimleri ekleme](#AddD)  
  
- [Önkoşul olarak bağımlı bileşenlerini yapılandırma](#Configure)  
  
- [Kullanıcının bilgisayarında çözümü dağıtmak istediğiniz yeri belirtin](#Location)  
  
- [Bir VSTO eklentisinin yapılandırın](#ConfigureRegisitry)  
  
- [Belge düzeyi özelleştirme yapılandırın](#ConfigureDocument)  
  
- [Kurulum projesi oluşturma](#Build)  
  
ClickOnce kullanarak Office çözümü dağıtma hakkında daha fazla bilgi için bkz: [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
Kullanarak bir Windows Installer dosyası oluşturma hakkında bilgi için [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], bkz: [bir Visual Studio 2010 Araçları için Windows Installer kullanarak Office çözümü dağıtma](http://go.microsoft.com/fwlink/?LinkId=201807).  
  
  
## <a name="Download"></a>Örnekleri indirin  
Bu konuda aşağıdaki indirilebilir örnekleri gösterir.  
  
  
  
|Örnek<br /><br />|Açıklama<br /><br />|  
|----------|---------------|  
|[ExcelAddIn](http://go.microsoft.com/fwlink/?LinkID=275492)<br /><br />|Bir Excel VSTO Office 32 bit veya 64-bit sürümünü çalıştıran bir bilgisayara yüklemek için eklenti.<br /><br />|  
|[ExcelWorkbook](http://go.microsoft.com/fwlink/?LinkID=275493)<br /><br />|Office'in 32 bit veya 64-bit sürümünü çalıştıran bir bilgisayara yüklemek için bir Excel belge düzeyi özelleştirme.<br /><br />|  
  
## <a name="ApplySecurity"></a>Çözümlerine güven verme konusunda karar verin  
Bir çözüm kullanıcı bilgisayarlarında çalıştırmadan önce aşağıdaki yollardan biriyle güvende vermelidir ya da çözüm yüklediğinizde kullanıcılar için bir güven istemi yanıtlaması gerekir.  
  
  
- Bildirimleri bilinen ve güvenilen bir yayımcı tanımlayan bir sertifika kullanarak oturum açın. Daha fazla bilgi için bkz: [uygulama ve dağıtım bildirimlerini imzalama tarafından çözümü güven](../vsto/granting-trust-to-office-solutions.md#Signing).  
  
- Kullanıcının bilgisayarda Program Files dizini için çözüm yükleyin.  
  
> [!NOTE]  
> Belge düzeyi özelleştirmeleri için belgenin konumunu da güvenilmesi gerekir. Daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
  
## <a name="Obtain"></a>Get InstallShield Limited Edition  
Visual Studio yüklediyseniz boş olduğu InstallShield Limited Edition (işle), kullanarak bir Windows Installer dosyası oluşturabilirsiniz. İşle Visual Studio'nun önceki sürümleri sunulan Kurulum ve dağıtım için proje şablonları işlevselliğini değiştirir.  
  
  
### <a name="to-get-installshield-limited-edition"></a>InstallShield Limited Edition almak için  
  
1. Menü çubuğunda seçin **dosya** > **yeni** > **proje**.  
  
   **Yeni proje** iletişim kutusu açılır.  
  
2. Şablonlar bölmesinde **diğer proje türleri**ve ardından **Kurulum ve dağıtım** şablonu.  
  
3. Proje türleri için listesinde **Kurulum ve dağıtım**, seçin **etkinleştirmek InstallShield Limited Edition**ve ardından **Tamam** düğmesi.  
  
   InstallShield Limited Edition alma hakkında bilgi sağlayan bir sayfa görüntülenir.  
  
4. Bu sayfada seçin **indirme web sitesine gidin** bağlantı.  
  
5. İndirme sayfasındaki InstallShield Limited Edition için uygun alanlara gerekli bilgileri girin ve ardından **Şimdi Yükle** bağlantı.  
  
   İndirme, yükleme ve ürünü etkinleştirildikten sonra **InstallShield Limited Edition proje** şablon Visual Studio'da görüntülenir.  
  
  
## <a name="Create"></a>Kurulum projesi oluşturma  
  
1. İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], dağıtmak istediğiniz Office projeyi açın.  
  
   Bu konu ile ilişkili VSTO eklenti örnekleri adlı projesi **ExcelAddIn**. Belge düzeyi özelleştirme örnekleri adlı projesi **ExcelWorkbook**. Bu konu, bu iki adlarından birini kullanarak Office proje çözümünüzü ile başvurur.  
  
2. Menü çubuğunda seçin **dosya** > **Ekle** > **yeni proje**.  
  
   **Yeni Proje Ekle** iletişim kutusu açılır.  
  
3. Şablonlar bölmesinde **diğer proje türleri**ve ardından **Kurulum ve dağıtım** şablonu.  
  
4. Proje türleri için listesinde **Kurulum ve dağıtım**, seçin **InstallShield Limited Edition proje**Projeyi adlandırın ve ardından **Tamam** düğmesi.  
  
   Yeni oluşturduğunuz InstallShield Kurulum projesi çözümünüzde görünür.  
  
   Bu konu için örnek adlı bir kurulum projesi **OfficeAddInSetup**. Bu konu, aynı adı kullanarak, çözümünüzdeki Kurulum projesi için başvurur.  
  
  
## <a name="Add"></a>Proje Çıktı Ekle  
Yapılandırdığınız **OfficeAddInSetup** Office projenizi çıktısını eklemek için proje. VSTO eklenti projeleri için proje çıktı çözüm yalnızca derlemesidir. Belge düzeyi özelleştirme projeleri için proje çıktı yalnızca çözümü derleme aynı zamanda belge içerir.  
  
  
### <a name="to-add-the-project-output"></a>Proje çıktı eklemek için  
  
1. İçinde **Çözüm Gezgini**, genişletin **OfficeAddInSetup** proje düğümünü ve ardından **proje Yardımcısı** aşağıda gösterilmiştir dosya.  
  
   ![Proje Çözüm Gezgini'nde Yardımcısı dosyası](../vsto/media/installshield-projectassistant.png "proje Çözüm Gezgini'nde Yardımcısı dosyası")  
  
2. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
3. Ekranın alt kısmındaki **proje Yardımcısı** sayfasında, **uygulama dosyalarını** aşağıda gösterilmiştir düğmesi.  
  
   ![Uygulama dosyaları düğmesi. ] (../vsto/media/installshield-applicationfiles.png "Uygulama dosyalarını düğmesi.")  
  
4. İçinde **uygulama dosyalarını** sayfasında, **eklemek proje çıktıları** düğmesi.  
  
5. İçinde **Visual Studio çıkış Seçici** iletişim kutusunda **birincil çıktı** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
  
## <a name="AddD"></a>Dağıtım ve uygulama bildirimleri ekleme  
  
###  
1. İçinde **uygulama dosyalarını** sayfasında, **dosyaları Ekle** düğmesi.  
  
2. İçinde **açık** iletişim kutusunda, Gözat çıktı dizinine **ExcelAddIn** projesi.  
  
   Genellikle, çıktı dizini olan **bin\release** seçtiğiniz yapı yapılandırmasına bağlı olarak proje kök dizinin alt klasörü.  
  
3. Çıktı dizini seçin **ExcelAddIn.vsto** ve **ExcelAddIn.dll.manifest** dosyaları ve ardından **açık** düğmesi.  
  
   **Uygulama dosyalarını** sayfası artık proje çıktı dosyası, dağıtım bildirimi ve uygulama bildirimi aşağıdaki çizimde gösterildiği gibi içerir.  
  
   ![Kurulum projenizin çıktı dosyaları. ] (../vsto/media/installshield-outputfiles.png "Kurulum projenizin çıktı dosyaları.")  
  
  
## <a name="Configure"></a>Önkoşul olarak bağımlı bileşenlerini yapılandırma  
Kurulum uygulamanızda, yalnızca aşağıdaki bileşenleri, ancak de çalıştırmak çözümünüz için gerekli olan aynı zamanda tüm diğer bileşenleri eklemeniz gerekir.  
  
  
- .NET Framework sürümünü, Office çözümü hedefler.  
  
- Office çalışma zamanı için Microsoft Visual Studio 2010 Araçları.  
  
  
### <a name="add-the-net-framework-4-or-the-net-framework-45-as-a-prerequisite"></a>Bir önkoşul olarak .NET Framework 4 veya .NET Framework 4.5 ekleme  
  
1. İçinde **Çözüm Gezgini**, genişletin **OfficeAddInSetup** proje düğümünü, genişletin **uygulama verilerini belirtin** düğümünü ve ardından  **Yeniden dağıtılabilir öğeleri** aşağıda gösterilmiştir dosya.  
  
   ![Çözüm Gezgini'nde yeniden dağıtılabilir öğeleri dosyaya](../vsto/media/installshield-redistributablesfile.png "Çözüm Gezgini'nde yeniden dağıtılabilir öğeleri dosyaya")  
  
2. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
   **Yeniden dağıtılabilir öğeleri** sayfası açılır.  
  
3. .NET Framework sürümü için onay kutusunu seçin yeniden dağıtılabilir bileşenleri listesinde, uygun, çözüm hedefler.  
  
   Örneğin, varsa, çözüm hedeflerine [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]seçin **Microsoft .NET Framework 4.5 tam** onay kutusu. Yeniden dağıtılabilir bileşeni yüklemek isteyip istemediğinizi soran bir iletişim kutusu görünebilir InstallShield önce gerektiren bir önkoşul olarak bileşen ekleyebilirsiniz. Bu iletişim kutusunu görünmüyorsa, bileşen bilgisayarınızda zaten var.  
  
4. Bu iletişim kutusu görüntülenirse, seçin **Hayır** düğmesi.  
  
  
### <a name="AddToolsForOffice"></a>Office çalışma zamanı için Visual Studio 2010 Araçları Ekle  
**Yeniden dağıtılabilir öğeleri** sayfa adlı bir öğe içeriyor **Microsoft VSTO 2010 Çalışma zamanı**, ancak çalışma zamanı daha eski bir sürümü ifade eder. Bu nedenle, en son sürüme başvuran bir yapılandırma dosyası el ile oluşturabilirsiniz. Bu dosya daha sonra tüm diğer öğeler için görünür yapılandırma dosyaları ile aynı dizine konulmalıdır **yeniden dağıtılabilir öğeleri** sayfası.  
  
  
#### <a name="to-add-the-visual-studio-2010-tools-for-office-runtime-as-a-prerequisite"></a>Office çalışma zamanı için Visual Studio 2010 Araçları bir önkoşul olarak eklemek için  
  
1. Not Defteri'ni açın ve aşağıdaki XML bir metin dosyasına yapıştırın.  
  
  
   ```xml  
   <?xml version="1.0" encoding="UTF-8"?>  
   <SetupPrereq>  
   <conditions>  
       <condition Type="32" Comparison="2" Path="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSTO Runtime Setup\v4R" FileName="Version" ReturnValue="10.0.50903" Bits="2"></condition>  
   <condition Type="32" Comparison="2" Path="HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSTO Runtime Setup\v4R" FileName="Version" ReturnValue="10.0.50903" Bits="2"></condition>  
   </conditions>  
   <files>  
       <file LocalFile="<ISProductFolder>\SetupPrerequisites\VSTOR\vstor_redist.exe" URL="http://download.microsoft.com/download/C/0/0/C001737F-822B-48C2-8F6A-CDE13B4B9E9C/vstor_redist.exe" CheckSum="88b8aa9e8c90818f98c80ac4dd998b88" FileSize=" 0,40117912"></file>  
   </files>  
   <execute file="vstor_redist.exe" returncodetoreboot="1641,3010" requiresmsiengine="1">  
   </execute>  
   <properties Id="{15965040-56BB-49B8-A88F-3525C48D9BA8}" Description="This prerequisite installs the most recent version of the Microsoft Visual Studio 2010 Tools for Office Runtime." >  
   </properties>  
     
   </SetupPrereq>  
   ```  
  
2. Visual Studio'da bir GUID oluşturur. Üzerinde **Araçları** menüsünde seçin **Create GUID**.  
  
3. İçinde **GUID Oluşturucu** programı, seçin **kayıt defteri biçimi** seçenek düğmesi, seçin **kopya** düğmesine tıklayın ve ardından **çıkış** düğme.  
  
4. Not Defteri'nde, metnin yerine **bilgisayarınızı GUID Buraya** onun yerine GUID yapıştırma tarafından.  
  
   **&lt;Özellikleri&gt;** öğesi dosyanızın aşağıdakine benzer.  
  
  
   ```xml  
   <properties Id="{87989B73-21DC-4403-8FD1-0C68A41A6D8C}" Description="This prerequisite installs the most recent version of the Microsoft Visual Studio 2010 Tools for Office Runtime." >  
   </properties>  
   ```  
  
5. Not Defteri'nde menü çubuğunda seçin **dosya** > **kaydetmek**.  
  
6. İçinde **Kaydet** iletişim kutusunda, Gözat, **Masaüstü** klasör.  
  
7. İçinde **farklı türde Kaydet** listesinde, seçin **tüm dosyalar (&#42;.&#42;)** .  
  
8. İçinde **dosya adı** kutusuna **Office Runtime.prq için Visual Studio 2010 Araçları**ve ardından **kaydetmek** düğmesi.  
  
   > [!NOTE]  
   >    Eklediğiniz emin olun **.prq** bu dosyayı bir önkoşul dosyası olarak tanımlamak için dosya adının sonunda.  
  
9. Not Defteri'ni kapatın.  
  
10. Öğesinden, **Masaüstü** klasörü, kopya *Office Runtime.prq için Visual Studio 2010 Araçları* aşağıdaki dizinlerin bir dosyayı bilgisayarınıza.  
  
   32-bit işletim sistemleri için: *%ProgramFiles%\InstallShield\2013LE\SetupPrerequisites\\*  
  
   64-bit işletim sistemleri için: *% ProgramFiles (x86) %\2013LE\SetupPrerequisites\\*  
  
11. İçinde **yeniden dağıtılabilir** sayfa InstallShield projenin seçin **yenileme** düğme aşağıdaki çizimde gösterildiği gibi yeniden dağıtılabilir bileşenleri listesini yenileyin.  
  
   ![Yenile düğmesini. ] (../vsto/media/installshield-refreshbutton.png "Yenile düğmesini.")  
  
12. Yeniden dağıtılabilir bileşenleri listesinde seçin **Office çalışma zamanı için Visual Studio 2010 Araçları** onay kutusu.  
  
   Yeniden dağıtılabilir bileşeni yüklemek istediğinizi soran bir iletişim kutusu de görünebilir. Bu iletişim kutusunu görünmüyorsa, adımına atlayabilirsiniz [belirtin, kullanıcının bilgisayarındaki çözümü dağıtmak istediğiniz](#Location) bölümüne.  
  
13. Bu iletişim kutusu görüntülenirse, seçin **Hayır** düğmesi.  
  
  
## <a name="Location"></a>Kullanıcının bilgisayarında çözümü yükleneceği yeri belirtin  
  
1. İçinde **Çözüm Gezgini**, genişletin **OfficeAddInSetup** düğümünü genişletin **kurulumunuzu düzenlemek** düğümü ve ardından **genel bilgiler** dosya.  
  
2. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
3. Özellikler listesinde seçin **Gözat** düğmesine **INSTALLDİR** özelliği.  
  
4. İçinde **ayarlamak INSTALLDİR** iletişim kutusunda, kullanıcının bilgisayarındaki, çözümü yüklemek istediğiniz klasörü seçin.  
  
   > [!NOTE]  
   >    Dizinlerde de oluşturabilirsiniz **ayarlamak INSTALLDİR** listede herhangi bir klasör için kısayol menüsünü açarak iletişim kutusu.  
  
  
## <a name="ConfigureRegisitry"></a>Bir VSTO eklentisinin yapılandırın  
VSTO (bilgisayar başına) bilgisayarın tüm kullanıcıları için veya yalnızca (kullanıcı başına) yüklemeyi gerçekleştiren kullanıcı için yüklenecek eklentinizi isteyip istemediğinizi belirtebilirsiniz.  
  
Bilgisayar başına yüklemelerini desteklemek iki ayrı yükleyicileri oluşturun. Office sürüm (32 bit ve 64 bit) veya Windows sürüm (32 bit ve 64 bit) dayanan yükleyiciler kullanıcı çalıştıran bölebilirsiniz.  
  
Kullanıcı başına yüklemeleri Office veya Windows sürümü bağımsız olarak yalnızca bir yükleyici gerektirir.  
  
> [!NOTE]  
> Bu bölüm, yalnızca bir VSTO eklenti dağıtıyorsanız geçerlidir. Belge düzeyi özelleştirme dağıtıyorsanız, hemen gidebilirsiniz [bir belge düzeyi özelleştirme yapılandırma](#ConfigureDocument) bölümü.  
  
  
### <a name="to-specify-whether-you-want-to-support-per-user-or-per-computer-installations"></a>Kullanıcı başına veya bilgisayar başına yüklemeleri destek isteyip istemediğinizi belirtmek için  
  
1. İçinde **Çözüm Gezgini**, genişletin **OfficeAddInSetup** proje düğümünü, genişletin **düzenlemek bilgisayarınızı Kurulum** düğümünü ve ardından **genel bilgiler**  dosya.  
  
2. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
   Kurulum projesi özellikleri görüntülenir.  
  
3. Listesinde **AllUSERS** özelliği, çözümü yükleyen kullanıcının veya bilgisayarın tüm kullanıcıları için yüklenmesi için bu çözümün isteyip istemediğinizi belirtin.  
  
   Geçerli kullanıcı için VSTO eklentisini yüklemek için tercih **ALLUSERS = "" (kullanıcı başına yükleme)**. Bilgisayarın tüm kullanıcıları için VSTO eklentisini yüklemek için tercih **ALLUSERS = 1 (makine başına yükleme)**  
  
   Sonraki yordamda bulup VSTO eklenti Office uygulamasını etkinleştirmek için kayıt defteri anahtarlarını oluşturacaksınız. Bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).  
  
  
### <a name="to-create-registry-keys"></a>Kayıt defteri anahtarları oluşturmak için  
  
1. İçinde **Çözüm Gezgini**, seçin **proje Yardımcısı** düğümü.  
  
   Menü çubuğunda seçin **Görünüm** > **açık**.  
  
2. Ekranın alt kısmındaki **proje Yardımcısı** sayfasında, **uygulama kayıt defteri** aşağıda gösterilmiştir düğmesi.  
  
   ![Uygulaması kayıt defteri düğmesi. ] (../vsto/media/installshield-applicationregistry.gif "Uygulaması kayıt defteri düğmesi.")  
  
   **Uygulama kayıt defteri** sayfası görüntülenir.  
  
3. Altında **uygulamanızı yükleyecek kayıt defteri verilerini yapılandırmak istiyor musunuz?**, seçin **Evet** seçenek düğmesi.  
  
4. İçinde **hedef bilgisayarın kayıt defteri Görünüm** listesinde, oluşturmak istediğiniz yükleyici türü etkinleştirir anahtar hiyerarşi ekleyin.  
  
   Bu bölümdeki yapılandırma yolu olup, bir kullanıcı başına yükleyici veya bir bilgisayar başına yükleyici oluşturduğunuzda üzerinde bağlıdır.  
  
   **Kullanıcı başına yükleyici**  
  
   **HKEY_CURRENT_USER\Software\Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**  
  
   **Bilgisayar başına yükleyicileri Office sürümlerine göre**  
  
  
  
|Office sürümü<br /><br />|InstallShield yapılandırma yolu<br /><br />|  
|------------------|------------------------------------|  
|32 bit:<br /><br />|**HKEY_LOCAL_MACHINE\Software(32-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
|64 bit<br /><br />|**HKEY_LOCAL_MACHINE\Software(64-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
   **Bilgisayar başına yükleyicileri Windows sürümlerine göre**  
  
  
  
|Windows sürümü<br /><br />|InstallShield yapılandırma yolu<br /><br />|  
|-------------------|------------------------------------|  
|32 bit:<br /><br />|**HKEY_LOCAL_MACHINE\Software(32-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
|64 bit<br /><br />|**HKEY_LOCAL_MACHINE\Software(32-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />**HKEY_LOCAL_MACHINE\Software(64-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
   > [!NOTE]  
   >    Kullanıcıların, Office'in 32 bit ve 64 bit sürümlerinde 64-bit Windows çalıştıran bir bilgisayarda çalıştırmak olası olduğundan bir yükleyici 64-bit Windows için iki kayıt defteri yolu gerektirir.  
  
   > [!NOTE]  
   >    En iyi uygulama, şirketinizin adını, VSTO eklenti adı başlatın. Bu kural anahtar için benzersiz olacaktır ve bir VSTO eklentiden başka bir sağlayıcı ile Çakışma olasılığını azaltır şansı artar. Örneğin, aynı ada sahip eklentiler birbirlerinin Kayıt anahtarlarını kılabilirsiniz. Bu yaklaşım, anahtar benzersiz olacak ancak olası ad çakışmaları azaltabilir garanti edemez.  
  
5. Anahtarları hiyerarşisini oluşturduktan sonra kısayol menüsünü açın **SampleCompany.ExcelAddIn** anahtar, seçin **yeni**ve ardından **dize değeri**.  
  
   Yeni bir dize değeri görünür **hedef bilgisayarın kayıt defteri verilerini** listesi. Dize değeri adını, böylelikle onu yeniden adlandırabilirsiniz vurgulanır.  
  
6. Değeri için yeniden adlandırmak **açıklama**.  
  
7. Aşağıdaki değerleri oluşturmak için bu işlemi yineleyin.  
  
  
  
|Değer türü<br /><br />|Ad<br /><br />|  
|--------------|--------|  
|Dize değeri<br /><br />|**FriendlyName**<br /><br />|  
|DWORD değeri<br /><br />|**LoadBehavior**<br /><br />|  
|Dize değeri<br /><br />|**Bildirimi**<br /><br />|  
  
8. Kısayol menüsünü açın **açıklama** değer ve ardından **Değiştir**.  
  
   **Verilerini düzenleme** iletişim kutusu görüntülenir.  
  
9. İçinde **değer verisi** metin kutusuna **Excel Demo Eklenti**ve ardından **Tamam** düğmesi.  
  
   Bu açıklama açılır Office uygulamasının kullanıcı oturum açtığında görünür **seçenekleri** iletişim kutusu ve ardından **eklentileri** bölmesinde seçtiği için VSTO eklentisi.  
  
10. Kısayol menüsünü açın **FriendlyName** değer ve ardından **Değiştir**.  
  
   **Verilerini düzenleme** iletişim kutusu görüntülenir.  
  
11. İçinde **değer verisi** metin kutusuna **Excel Demo Eklenti**ve ardından **Tamam** düğmesi.  
  
   Bu dize görünür **COM eklentileri** Office uygulamasında iletişim kutusu. Varsayılan olarak, dize değeri VSTO eklenti kimliğidir  
  
12. Kısayol menüsünü açın **LoadBehavior** değer ve ardından **Değiştir**.  
  
   **Verilerini düzenleme** iletişim kutusu görüntülenir.  
  
13. İçinde **değer verisi** metin kutusuna **3**ve ardından **Tamam** düğmesi.  
  
   Uygulama başladığında 3 değerini VSTO eklenti yükler. LoadBehavior değerleri hakkında daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).  
  
14. Kısayol menüsünü açın **bildirim** değer ve ardından **Değiştir**.  
  
   **Verilerini düzenleme** iletişim kutusu görüntülenir.  
  
15. İçinde **değer verisi** metin kutusuna **file:///[INSTALLDIR]ExcelAddIn.vsto|vstolocal**ve ardından **Tamam** düğmesi.  
  
   Office çalışma zamanı için Visual Studio 2010 Araçları dağıtım bildirimi bulmak için bu yolu kullanır. **[INSTALLDİR]** bu yolu bölümüdür eşleyen bir makro **INSTALLDİR** özelliğinde **genel bilgiler** InstallShield Kurulum projenizin özellik sayfası. Bu özellik için VSTO eklentisi yüklemek için hedef bilgisayarda konumu belirtir. **| Vstolocal** soneki sağlar, çözümünüzün yükleme klasöründen ClickOnce önbelleğine yüklenir.  
  
> [!IMPORTANT]  
> Outlook için VSTO ek bileşeni içinde bir özel form bölgesi oluşturursanız, Outlook ile bölge kaydettirmek için daha fazla kayıt defteri girdileri oluşturmanız gerekir. Daha fazla bilgi için bkz: [kayıt defteri girdilerini Outlook form bölgeleri](../vsto/registry-entries-for-vsto-add-ins.md#OutlookEntries).  
  
  
## <a name="ConfigureDocument"></a>Belge düzeyi özelleştirme yapılandırın  
Bu bölüm, yalnızca bir belge düzeyi özelleştirme dağıtıyorsanız geçerlidir. Bir VSTO eklenti dağıtıyorsanız, hemen gidebilirsiniz [Kurulum projesi derleme](#Build) bölümü.  
  
Belge düzeyi özelleştirmeleri kayıt defteri anahtarlarını kullanmayın. Bunun yerine, özel belge özellikleri dağıtım bildirimi konumunu içerir.  
  
Özel özelliklerini değiştirmek için belge düzeyi özelleştirme belgeden kaldırır, uygun özelliklerini değiştirir ve belgeye özelleştirme yeniden iliştirir bir program oluşturun. Ardından programı çalıştıran özel bir eylem oluşturun ve bu eylem kurulum projenize ekleyin.  
  
### <a name="to-create-a-program-that-modifies-document-properties"></a>Belge özellikleri değiştiren bir program oluşturmak için  
  
1. Menü çubuğunda seçin **dosya** > **Ekle** > **yeni proje**.  
  
   **Yeni Proje Ekle** iletişim kutusu görüntülenir.  
  
2. Kullanmak istediğiniz dil düğümünde Şablonlar bölmesinde seçin **Windows** klasör.  
  
3. Proje türleri için listesinde **Windows**, seçin **konsol uygulaması** şablonu.  
  
4. Proje adı **SetExcelDocumentProperties**ve ardından **Tamam** düğmesi.  
  
5. İçinde **Çözüm Gezgini**, seçin **tüm dosyaları göster** düğmesini tıklatın, kısayol menüsünü açın **SetExcelDocumentProperties** proje düğümünü ve ardından **Başvuru ekleme**.  
  
6. İçinde **başvuru Yöneticisi** iletişim kutusunda, seçin **uzantıları** sekmesinde ve ardından aşağıdaki derlemeler yanındaki onay kutusunu seçin ve ardından **Tamam** düğmesi.  
  
  
   - Microsoft.VisualStudio.Tools.Applications.Runtime'a  
  
   - Microsoft.VisualStudio.Tools.Applications.ServerDocument'a  
  
7. İçinde **Çözüm Gezgini**, seçin **Program.cs** dosyası (C# uygulamalarının) veya **Module1.vb** dosyası (Visual Basic uygulamaları).  
  
8. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
9. Tüm dosyasının içeriğini aşağıdaki kodla değiştirin.  
  
[!code-vb[Trin_CustomAction#1](../vsto/codesnippet/VisualBasic/setexceldocumentproperties/module1.vb#1)]
[!code-csharp[Trin_CustomAction#1](../vsto/codesnippet/CSharp/setexceldocumentproperties/program.cs#1)]  
  
10. Projeyi derleyin.  
  
  
### <a name="to-add-a-custom-action-that-runs-your-program"></a>Programınızı bir çalışan özel bir eylem eklemek için  
  
1. İçinde **Çözüm Gezgini**, genişletin **OfficeAddInSetup** proje düğümünü ve ardından **proje Yardımcısı** aşağıda gösterilmiştir dosya.  
  
   ![Proje Çözüm Gezgini'nde Yardımcısı dosyası](../vsto/media/installshield-projectassistant.png "proje Çözüm Gezgini'nde Yardımcısı dosyası")  
  
2. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
3. Ekranın alt kısmındaki **proje Yardımcısı** sayfasında, **uygulama dosyalarını** aşağıda gösterilmiştir düğmesi.  
  
   ![Uygulama dosyaları düğmesi. ] (../vsto/media/installshield-applicationfiles.png "Uygulama dosyalarını düğmesi.")  
  
4. İçinde **uygulama dosyalarını** sayfasında, **eklemek proje çıktıları** düğmesi.  
  
   **Visual Studio çıkış Seçici** iletişim kutusu görüntülenir.  
  
5. Altında **SetExcelDocumentProperties** düğümü, select **birincil çıktı** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
6. İçinde **Çözüm Gezgini**altında **OfficeAddInSetup** düğümünü genişletin **Kurulum gereksinimleri tanımlayın ve eylemleri** düğümü ve ardından **özel Eylemler** klasör.  
  
7. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
   Ekranın tarafındaki bölmesine olaylarının bir listesi görüntülenir.  
  
   > [!NOTE]  
   >    Bu listede yalnızca birkaç olaylar InstallShield sınırlı Edition'da kullanılabilir. Bu yordamda kullanarak programı çalıştıracaksınız **sonra Kurulum başarıyla tamamlandı iletişim** olay.  
  
8. Olaylar, listesinde altında **yüklemesi sırasında özel eylemler**, kısayol menüsünü açın **sonra Kurulum başarıyla tamamlandı iletişim** olay ve ardından **yeni EXE**.  
  
   Adlı özel bir eylem **NewCustomAction1** altında görünür **sonra Kurulum başarıyla tamamlandı iletişim** olay. Özel eylem için özellikler kümesi olayları yanında bir bölmesinde görüntülenir.  
  
   > [!IMPORTANT]  
   >    İki **sonra Kurulum başarıyla tamamlandı iletişim** olaylar, olaylar listesinde görünür. Örneğinin seçtiğinizden emin olun **sonra Kurulum başarıyla tamamlandı iletişim** altında görüntülenen olay **yüklemesi sırasında özel eylemler** düğümü.  
  
9. Listesinde **kaynak konumu** özelliği seçin **ürünle birlikte yüklenen**.  
  
10. Seçin **Gözat** düğmesine **dosya adı** özelliği.  
  
11. İçinde **gözatmak için bir hedef dosya** iletişim kutusunda, Gözat ' **SetExcelDocumentProperties.Primary.output** dosya ve ardından **açık** düğmesi.  
  
   Bu dosyanın konumu için belirtilen klasör bağlıdır **INSTALLDİR** Kurulum projesi özelliği. Örneğin, bu özellik adlı bir klasöre ayarlarsanız **[PersonalFolder] DemoWorkbookApp**, bulabileceğiniz **SetExcelDocumentProperties.Primary.output** için gözatarak dosya **[ Programfılesfolder] \DemoWorkbookApp**.  
  
   Sonraki birkaç adımda belgenin çözüm kimliği alın ve sonra bu kimliği konsol uygulaması için bir parametre olarak geçirin. Ayrıca belge, dağıtım bildirimi ve belge derleme konumunu geçmesi.  
  
12. Kısayol menüsünü açın **ExcelWorkbook** proje ve ardından **klasörü Windows Gezgini'nde Aç** veya **dosya Gezgini'nde klasör Aç** , işletim bağlı olarak Sistem.  
  
   Çözümünüzü içeren klasörü açılır.  
  
13. Çözümünüzün proje dosyasını Not Defteri'nde açın. Visual Basic projeleri için dosyanın adıdır *ExcelWorkbook.vbproj*. C# projeleri için dosyanın adıdır *ExcelWorkbook.csproj*.  
  
14. Proje dosyasında arama **&lt;SolutionID&gt;** öğenin değerini panoya kopyalayın ve Not Defteri'ni kapatın.  
  
   Bu değer bir parametre olarak konsol uygulaması geçirin.  
  
15. Özellikler sayfasındaki **NewCustomAction1**ayarlayın **komut satırı** aşağıdaki metin satırının özelliğine.  
  
  
   ```cmd
   /assemblyLocation="[INSTALLDIR]ExcelWorkbook.dll" /deploymentManifestLocation="[INSTALLDIR]ExcelWorkbook.vsto" /documentLocation="[INSTALLDIR]ExcelWorkbook.xlsx" /solutionID="Your Solution ID"  
   ```  
  
16. Değiştir **bilgisayarınızı çözüm kimliği** çözüm kimlikli panoya kopyalandı.  
  
   > [!IMPORTANT]  
   >    Bu özel eylem çalıştıran konsol uygulaması [INSTALLDİR] dizininde belgelere erişmesini doğrulamak için yükleyici sınayın. Bazı dizinler kullanıcının bilgisayarda yönetim erişimi (örneğin, Program Files dizini) gerektirebilir. Yönetimsel erişim gerektiren bir dizine çözümünüzü dağıtıyorsanız açılmalıdır **özellikleri** iletişim kutusunun *setup.exe* dosya, seçin **Uyumluluk** sekmesini tıklatın ve ardından **bu programı yönetici olarak çalıştır** yükleyici dağıtmadan önce kutuyu. Kurulum programı yönetici izinleriyle çalıştırmak için kullanıcıların istemiyorsanız kullanıcı büyük olasılıkla olan erişim dizine [INSTALLDİR] özelliği ayarlamak zaten gibi **belgeleri** dizin. Daha fazla bilgi için bkz: [belirtin çözümü kullanıcının bilgisayarında yüklemek istediğiniz](#Location) bölümüne.  
  
  
## <a name="Build"></a>Kurulum projesi oluşturma  
  
1. İçinde **Çözüm Gezgini**, genişletin **hazırlamak için yayın** düğümünü ve ardından **sürümleri** dosya.  
  
2. Menü çubuğunda seçin **Görünüm** > **açık**.  
  
   **Derlemeler** Gezgini'ni açar taraftaki bölmede böylece oluşturmak istediğiniz sürüm türünü seçebilirsiniz.  
  
3. İçinde **derlemeler** Gezgini seçin **SingleImage** klasör.  
  
4. Bölmesinde yanındaki **derlemeler** Gezgini seçin **Setup.exe** sekmesi.  
  
5. İçinde **Setup.exe** özellik sayfası, gelen **InstallShield Önkoşullar konumu** listesinde, seçin **Web'den indirme**.  
  
6. Menü çubuğunda seçin **yapı** > **Configuration Manager**.  
  
7. İçinde **etkin çözüm yapılandırması** listesinde, seçin **SingleImage**.  
  
8. İçinde **proje bağlamları** tablo, buna **yapılandırma** sütunu **OfficeAddInSetup** seçin, proje **SingleImage**ve ardından seçin **Kapat** düğmesi.  
  
9. Menü çubuğunda seçin **yapı** > **yapı OfficeAddInSetup**.  
  
   Yapı tamamlandıktan sonra bulabilir *setup.exe* dosyasının **OfficeAddInSetup** proje şu konumda: *OfficeAddInSetupProjectRoot *** \OfficeAddInSetup\ Express\SingleImage\DiskImages\DISK1\**  
  
  
## <a name="see-also"></a>Ayrıca bkz.  
[Dağıtım için Office çözümleri önkoşulları](http://msdn.microsoft.com/en-us/library/9f672809-43a3-40a1-9057-397ce3b5126e)  
[Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)  
[VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md)  
[Özel belge özelliklerine genel bakış](../vsto/custom-document-properties-overview.md)  
[Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md)  
[Belgelere güven verme](../vsto/granting-trust-to-documents.md)  
[Bir Visual Studio 2010 Araçları için Windows Installer kullanarak Office çözümü dağıtma](http://go.microsoft.com/fwlink/?LinkId=201807)  
  