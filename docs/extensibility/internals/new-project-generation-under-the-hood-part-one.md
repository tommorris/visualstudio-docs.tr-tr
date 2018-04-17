---
title: 'Yeni proje oluşturma: başlık altında bir bölüm | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 66778698-0258-467d-8b8b-c351744510eb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ac31f2866c6b69587f70775d5ed1245b1a2bb0a9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="new-project-generation-under-the-hood-part-one"></a>Yeni proje oluşturma: başlık altında bir parçası
Şimdiye kadar kendi proje türü oluşturma hakkında zorlayıcı? Yeni bir proje oluşturduğunuzda, gerçekten neler merak ediyor? Şimdi başlık altında göz atalım ve gerçekten neler olduğunu görebilirsiniz.  
  
 Visual Studio sizin için koordinatları çeşitli görevler vardır:  
  
-   Tüm kullanılabilir proje türleri ağacı görüntüler.  
  
-   Her proje türü için uygulama şablonları listesini görüntüler ve bir çekme olanak tanır.  
  
-   Proje adı ve yolu gibi uygulama için proje bilgileri toplar.  
  
-   Bu bilgiler açın proje Fabrika başarılı olur.  
  
-   Proje öğeleri ve klasörleri geçerli çözümde oluşturur.  
  
## <a name="the-new-project-dialog-box"></a>Yeni Proje iletişim kutusu  
 Yeni bir proje için bir proje türünü seçtiğinizde, tüm başlar. Tıklayarak başlayalım **yeni proje** üzerinde **dosya** menüsü. **Yeni proje** iletişim kutusu görüntülenirse, şöyle bir şey görünümlü:  
  
 ![Yeni Proje iletişim kutusu](../../extensibility/internals/media/newproject.gif "NewProject")  
  
 Daha yakın bir göz atalım. **Proje türleri** ağaç oluşturabileceğiniz çeşitli proje türleri listelenmektedir. Proje türü gibi seçtiğinizde **Visual C# Windows**, başlamanıza yardımcı olmak için uygulama şablonları listesini görürsünüz. **Visual Studio yüklenmiş şablonlar** Visual Studio tarafından yüklenir ve bilgisayarınızı herhangi bir kullanıcı için kullanılabilir. Oluşturduğunuz veya toplama yeni şablonlar eklenebilir **My şablonları** ve yalnızca sizin için kullanılabilir.  
  
 Bir şablon gibi seçtiğinizde **Windows uygulaması**, uygulama türü tanımı görünür iletişim kutusunda; Bu durumda, **bir Windows kullanıcı arabirimi ile bir uygulama oluşturmaya yönelik bir proje**.  
  
 Ekranın alt kısmındaki **yeni proje** iletişim kutusu, daha fazla bilgi toplayın birkaç denetimleri göreceksiniz. Gördüğünüz denetimleri proje türüne bağlıdır, ancak bir proje genellikle içerirler **adı** metin kutusuna bir **konumu** metin kutusu ve ilgili **Gözat** düğmesi ve bir **Çözüm adı** metin kutusu ve ilgili **çözüm için dizin oluştur** onay kutusu.  
  
## <a name="populating-the-new-project-dialog-box"></a>Yeni Proje iletişim kutusu doldurma  
 Burada mu **yeni proje** bilgilerini Al iletişim kutusu? İş için burada biri kullanım dışı iki mekanizma vardır. **Yeni proje** iletişim kutusu birleştirir ve her iki mekanizma alınan bilgileri görüntüler.  
  
 Sistem kayıt defteri girdileri ve .vsdir dosyaları eski (kullanım dışı) yöntemi kullanır. Visual Studio açıldığında, bu mekanizma çalışır. Daha yeni yöntemi .vstemplate dosyaları kullanır. Visual Studio, örneğin, çalıştırarak başlatıldığında bu düzenek çalıştırır  
  
```  
devenv /setup  
```  
  
 veya  
  
```  
devenv /installvstemplates  
```  
  
### <a name="project-types"></a>Proje türleri  
 Konumunu ve adını **proje türleri** düğümleri gibi kök **Visual C#** ve **diğer diller**, sistem kayıt defteri girdileri tarafından belirlenir. Alt düğümler organizasyonu gibi **veritabanı** ve **akıllı aygıt**, karşılık gelen .vstemplate dosyaları içeren klasörlerin hiyerarşisini yansıtır. İlk kök düğümler bakalım.  
  
#### <a name="project-type-root-nodes"></a>Proje türü kök düğümler  
 Zaman [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] olan başlatılmadığı, sistem kayıt defteri anahtarı oluşturun ve kök düğümlerini ad HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\NewProjectTemplates\TemplateDirs anahtarlarını geçeceğini **proje türleri** ağacı. Bu bilgiler daha sonra kullanmak üzere önbelleğe alınır. Ara TemplateDirs\\{FAE04EC1-301F-11D3-BF4B-00C04F79EFBC} \\ /1 anahtarı. Her giriş VSPackage GUID'dir. Alt anahtar adı (/ 1) göz ardı edilir, ancak kendi durum bu gösterir bir **proje türleri** kök düğümü. Bir kök düğümü sırayla kendi görünümünü kontrol birkaç alt anahtarlarını olabilir **proje türleri** ağacı. Bunlardan bazıları bakalım.  
  
##### <a name="default"></a>(Varsayılan)  
 Kök düğümü adlarını yerelleştirilmiş dize kaynak kimliğidir. Dize kaynak DLL VSPackage GUID ile seçili uydu bulunur.  
  
 Örnekte, VSPackage GUID'dir  
  
 {FAE04EC1-301F-11D3-BF4B-00C04F79EFBC}  
  
 ve kök düğüme kaynak kimliği (varsayılan değer) (/ 1) #2345 olduğu  
  
 Yakındaki paketleri anahtarında GUID aramak ve SatelliteDll alt anahtarını inceleyin, dize kaynaklarını içeren derleme yolu bulabilirsiniz:  
  
 \<Visual Studio yükleme yolu > \VC#\VCSPackages\1033\csprojui.dll  
  
 Bunu doğrulamak için dosya Gezgini'ni açın ve Visual Studio dizine csprojui.dll sürükleyin... Kaynak #2345 resim yazısını sahip dize tablosu gösterir **Visual C#**.  
  
##### <a name="sortpriority"></a>SortPriority  
 Bu kök düğümü konumunu belirler **proje türleri** ağacı.  
  
 SortPriority REG_DWORD 0x00000014 (20)  
  
 Öncelik, daha az sayıda ağacında yüksek konumu.  
  
##### <a name="developeractivity"></a>DeveloperActivity  
 Bu alt anahtar mevcut değilse, kök düğümü konumunu Geliştirici Ayarları iletişim kutusu tarafından denetlenir. Örneğin,  
  
 DeveloperActivity REG_SZ VC #  
  
 Visual Studio için ayarlanmışsa, Visual C# bir kök düğümü olacağını gösterir [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] geliştirme. Aksi durumda, bir alt düğüm olur **diğer diller**.  
  
##### <a name="folder"></a>Klasör  
 Bu alt anahtar mevcut değilse, kök düğümü belirtilen klasörün bir alt düğüm haline gelir. Anahtarın altında olası klasörleri listesi görüntülenir  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\NewProjectTemplates\PseudoFolders  
  
 Örneğin, veritabanı projeleri girişinin PseudoFolders diğer proje türleri girişi ile eşleşen bir klasörü anahtar vardır. Bu nedenle, içinde **proje türleri** ağacında **veritabanı projeleri** alt düğümü olacaktır **diğer proje türleri**.  
  
#### <a name="project-type-child-nodes-and-vstdir-files"></a>Proje türü alt düğümleri ve .vstdir dosyaları  
 Alt düğümler konumunu **proje türleri** ağaç ProjectTemplates klasörleri klasörlerde hiyerarşisini izler. Makine şablonları için (**Visual Studio yüklenmiş şablonlar**), Visual Studio 14.0\Common7\IDE\ProjectTemplates\ \Program tipik konumdur ve kullanıcı şablonları için (**şablonları**), \My Documents\Visual Studio 14.0\Templates\ProjectTemplates tipik konumdur\\. Bu iki konum klasör hiyerarşiden oluşturmak için birleştirilir **proje türleri** ağacı.  
  
 C# Geliştirici ayarları, Visual Studio için **proje türleri** ağaç şunun gibi görünür:  
  
 ![Proje türleri](../../extensibility/internals/media/projecttypes.png "ProjectTypes")  
  
 İlgili ProjectTemplates klasörüne şöyle görünür:  
  
 ![Proje şablonları](../../extensibility/internals/media/projecttemplates.png "ProjectTemplates")  
  
 Zaman **yeni proje** iletişim kutusu açılır ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ProjectTemplates klasörü erişir ve alt yapısında yeniden oluşturur **proje türleri** bazı değişiklikler ağacıyla:  
  
-   Kök düğümü **proje türleri** ağaç uygulama şablonu tarafından belirlenir.  
  
-   Düğüm adı yerelleştirilmiş olmalıdır ve özel karakterler içerebilir.  
  
-   Sıralama düzenini değiştirilebilir.  
  
##### <a name="finding-the-root-node-for-a-project-type"></a>Proje türü için kök düğüm bulma  
 Visual Studio ProjectTemplates klasörleri erişir, tüm .zip dosyalarını açar ve tüm .vstemplate dosyaları ayıklar. .Vstemplate dosya XML bir uygulama şablonunu tanımlamak için kullanır. Daha fazla bilgi için bkz: [yeni proje oluşturma: başlık altında bölümü iki](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md).  
  
 \<ProjectType > etiketi uygulama için proje türü belirler. Örneğin, \CSharp\SmartDevice\WindowsCE\1033\WindowsCE-EmptyProject.zip dosyası bu etikete sahip bir EmptyProject.vstemplate dosya içerir:  
  
```  
<ProjectType>CSharp</ProjectType>  
```  
  
 \<ProjectType > etiketi ve değil ProjectTemplates klasöründe alt belirler uygulamanın kök düğümde **proje türleri** ağacı. Örnekte, Windows CE uygulamaları altında görüneceğini **Visual C#** kök düğümü ve WindowsCE Visualbasic'tir klasörüne taşımak için olan olsa bile, Windows CE uygulamaları hala altında görüneceğini  **Visual C#** kök düğümü.  
  
##### <a name="localizing-the-node-name"></a>Düğüm adı yerelleştirme  
 Visual Studio ProjectTemplates klasörleri erişir, bulduğu .vstdir dosyaların inceler. Proje türü görünümünü denetleyen bir XML dosyası .vstdir dosyasıdır **yeni proje** iletişim kutusu. .Vstdir dosyasında kullanmak \<LocalizedName > etiketi adı **proje türleri** düğümü.  
  
 Örneğin, bu etiketi \CSharp\Database\TemplateIndex.vstdir dosya içerir:  
  
```  
<LocalizedName Package="{462b036f-7349-4835-9e21-bec60e989b9c}" ID="4598"/>  
```  
  
 Bu, bu durumda, kök düğümü adlarını yerelleştirilmiş dize uydu DLL ve kaynak Kimliğini belirler **veritabanı**. Yerelleştirilmiş adı gibi klasör adları için kullanılabilir olmayan özel karakterleri içerebilir **.NET**.  
  
 Öyle değilse \<LocalizedName > etiketi varsa, proje türü klasörü kendisini adlı **SmartPhone2003**.  
  
##### <a name="finding-the-sort-order-for-a-project-type"></a>Proje türü için sıralama düzenini bulma  
 Proje türü sıralama düzenini belirlemek için .vstdir dosyalarını kullanın \<SortOrder > etiketi.  
  
 Örneğin, bu etiketi \CSharp\Windows\Windows.vstdir dosya içerir:  
  
```  
<SortOrder>5</SortOrder>  
```  
  
 \CSharp\Database\TemplateIndex.vstdir dosyası daha büyük bir değer içeren bir etiket sahiptir:  
  
```  
<SortOrder>5000</SortOrder>  
```  
  
 Düşük numaralı \<SortOrder > etiketi, ağaç yüksek konumda böylece **Windows** düğümü görünür daha yüksek **veritabanı** düğümünde **proje türleri**  ağacı.  
  
 Öyle değilse \<SortOrder > etiketi belirtilen proje türü için içeren tüm proje türleri aşağıdaki alfabetik sırada göründüğü \<SortOrder > belirtimleri.  
  
 Belgelerim hiçbir .vstdir dosya olduğuna dikkat edin (**My şablonları**) klasörler. Kullanıcı uygulaması proje türü adları değil yerelleştirilir ve alfabetik olarak görüntülenir.  
  
#### <a name="a-quick-review"></a>Hızlı bir gözden geçirme  
 Değiştirelim **yeni proje** iletişim kutusuna ve yeni bir kullanıcı proje şablonu oluşturun.  
  
1.  MyProjectNode alt \Program Visual Studio 14.0\Common7\IDE\ProjectTemplates\CSharp klasörüne ekleyin.  
  
2.  Herhangi bir metin düzenleyicisi kullanarak MyProjectNode klasöründe bir MyProject.vstdir dosyası oluşturun.  
  
3.  Bu satırlar .vstdir dosyasına ekleyin:  
  
    ```  
    <TemplateDir Version="1.0.0">  
        <SortOrder>6</SortOrder>  
    </TemplateDir>  
    ```  
  
4.  .vstdir dosyasını kaydedip kapatın.  
  
5.  Herhangi bir metin düzenleyicisi kullanarak MyProjectNode klasöründe bir MyProject.vstemplate dosyası oluşturun.  
  
6.  Bu satırlar .vstemplate dosyasına ekleyin:  
  
    ```  
    <VSTemplate Version="2.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <TemplateData>  
            <ProjectType>CSharp</ProjectType>  
        </TemplateData>  
    </VSTemplate>  
    ```  
  
7.  The.vstemplate dosyayı kaydedin ve Düzenleyicisi'ni kapatın.  
  
8.  .Vstemplate dosyayı yeni bir sıkıştırılmış MyProjectNode\MyProject.zip klasöre gönderin.  
  
9. Visual Studio komut penceresinde yazın:  
  
    ```  
    devenv /installvstemplates  
    ```  
  
 Visual Studio'yu açın.  
  
1.  Açık **yeni proje** iletişim kutusuna ve genişletin **Visual C#** proje düğümüne.  
  
 ![MyProjectNode](../../extensibility/internals/media/myprojectnode.png "MyProjectNode")  
  
 **MyProjectNode** Visual C# Windows düğümü altında yalnızca bir alt düğüm olarak görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeni Proje Oluşturma: Altyapı Öğeleri, Bölüm İki](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)