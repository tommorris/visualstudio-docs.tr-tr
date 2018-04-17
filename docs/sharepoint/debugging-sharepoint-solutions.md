---
title: SharePoint çözümlerinde hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.WebConfigModificationDialog
- VS.SharePointTools.Project.DebuggingNotEnabled
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, debugging
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1be963dec8eee77efe4855c2e810af0fd1e72f1b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-sharepoint-solutions"></a>SharePoint Çözümlerinde Hata Ayıklama
  SharePoint çözümlerini kullanarak ayıklayabilirsiniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hata ayıklayıcı. Hata ayıklama, başlattığınızda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] proje dosyalarını SharePoint sunucusuna dağıtır ve sonra SharePoint sitesine örneği Web tarayıcısında açar. Aşağıdaki bölümlerde, SharePoint uygulamalarında hata ayıklama açıklanmaktadır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
-   [Hata ayıklamayı etkinleştirme](#EnableDebug)  
  
-   [F5 hata ayıklama ve dağıtım işlemi](#Deployment)  
  
-   [SharePoint Proje Özellikleri](#Features)  
  
-   [İş Akışlarında Hata Ayıklama](#Workflow)  
  
-   [Hata ayıklama özellik Olay alıcıları](#FeatureEvents)  
  
-   [Gelişmiş hata ayıklama bilgilerini etkinleştirme](#EnhancedDebug)  
  
##  <a name="EnableDebug"></a> Hata ayıklamayı etkinleştirme  
 Ne zaman önce hata ayıklama bir SharePoint çözüm [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bir iletişim kutusu, web.config dosyasında hata ayıklamayı etkinleştirmek için yapılandırılmamış sizi uyarır. (SharePoint sunucusu yüklediğinizde, web.config dosyası oluşturulur. Daha fazla bilgi için bkz: [Web.config dosyaları ile çalışma](http://go.microsoft.com/fwlink/?LinkID=149266).) İletişim kutusunun hata ayıklamayı etkinleştirmek için her iki projeyi hata ayıklama veya web.config dosyasında değişiklik olmadan çalıştıran seçeneği sunar. İlk seçeneği belirlerseniz, projeyi normal şekilde çalışır. İkinci seçeneği belirlerseniz, web.config dosyasında yapılandırılır:  
  
-   Çağrı yığınındaki Aç (`CallStack="true"`)  
  
-   Özel hatalar devre dışı [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (`<customErrors mode="Off" />`)  
  
-   Derleme hata ayıklamayı etkinleştir (`<compilation debug="true">`)  
  
 Sonuçta elde edilen web.config dosyasında aşağıdaki gibidir:  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <configuration>  
        ...  
        <SharePoint>  
            <SafeMode MaxControls="200"  
                CallStack="true"  
                DirectFileDependencies="10"  
                TotalFileDependencies="50"  
                AllowPageLevelTrace="false">  
                ...  
            </SafeMode>  
        ...  
        </SharePoint>  
        <system.web>  
            ...  
            <customErrors mode="Off" />  
            ...  
            <compilation debug="true">  
            ...  
            </compilation>  
            ...  
        </system.web>  
        ...  
    </configuration>  
```  
  
 Değişiklikleri geri almak ve hata ayıklama devre dışı bırakmak için aşağıdaki değiştirmek [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] web.config dosyasında:  
  
-   Çağrı yığını devre dışı bırakma (`CallStack="false"`)  
  
-   Özel hatalar etkinleştirmek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (`<customErrors mode="On" />`)  
  
-   Derleme hata ayıklamasını devre dışı (`<compilation debug="false">`)  
  
##  <a name="Deployment"></a> F5 hata ayıklama ve dağıtım işlemi  
 SharePoint Proje hata ayıklama modunda çalıştırdığınızda, SharePoint dağıtım işlemi aşağıdaki görevleri gerçekleştirir:  
  
1.  Özelleştirilebilir dağıtım öncesi komutları çalıştırır.  
  
2.  Kullanarak bir Web çözüm paketi (.wsp) dosyası oluşturur [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] komutları. .Wsp dosyası tüm özellikleri ve gerekli dosyaları içerir. Daha fazla bilgi için bkz: [çözümlerine genel bakış](http://go.microsoft.com/fwlink/?LinkID=128154).  
  
3.  SharePoint çözüm Grup çözümü ise, geri dönüştürüldüğünde [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] belirtilen site için uygulama havuzu [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)]. Bu adım tarafından kilitlenmiş dosyaları serbest [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] çalışan işlemi.  
  
4.  Paket önceki bir sürümü zaten varsa, özellikleri ve .wsp dosyasındaki dosyaları önceki sürümünü geri çeker. Bu adım, özellikleri devre dışı bırakır, çözüm paketi kaldırır ve SharePoint sunucusuna çözüm paketini siler.  
  
5.  Geçerli sürümü özellikleri ve dosyaları .wsp dosyasında yükler. Bu adım, ekler ve çözüm SharePoint sunucusuna yükler.  
  
6.  İş akışları, iş akışı derlemesi yükler. Kullanarak konumunu değiştirebilirsiniz *derleme konumu* özelliği.  
  
7.  Kapsam Site veya Web ise SharePoint projenin özelliğini etkinleştirir. Grup ve WebApplication kapsamlarda özellikleri etkinleştirilmedi.  
  
8.  SharePoint kitaplığı, liste veya seçtiğiniz site iş akışları, iş akışı ilişkilendirir **SharePoint Özelleştirme Sihirbazı'nı**.  
  
    > [!NOTE]  
    >  Yalnızca seçtiyseniz, bu ilişki oluşur **otomatik olarak ilişkilendirme iş akışı** Sihirbazı'nda.  
  
9. Özelleştirilebilir dağıtım sonrası komutları çalıştırır.  
  
10. İliştirir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] için hata ayıklayıcı [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] işleminin (w3wp.exe). Proje türü değiştirmenize izin veriyorsa *Korumalı çözüm* özelliği ve değerini ayarlanmış **doğru**, sonra da farklı bir işlem için (SPUCWorkerProcess.exe) hata ayıklayıcı ekler. Daha fazla bilgi için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
11. SharePoint çözüm Grup çözümü JavaScript hata ayıklayıcı başlar.  
  
12. Uygun kitaplık, liste veya site sayfası Web tarayıcısında görüntüler.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Her görev tamamlandıktan sonra çıktı penceresinde bir durum iletisini görüntüler. Bir görev tamamlandığında, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Hata Listesi penceresi bir hata iletisi görüntüler.  
  
##  <a name="Features"></a> SharePoint Proje Özellikleri  
 Bir özellik değişikliği sitelerin site tanımları kullanılarak basitleştirilir işlevlerin taşınabilir ve modüler bir birimdir. Ayrıca bir paketi olan [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] , etkinleştirilmesi için belirli bir kapsam ve belirli hedef ya da görev gerçekleştirmek kullanıcılara yardımcı olur (WSS) öğeleri. Şablonları özellikleri dağıtılır.  
  
 Bir projeyi hata ayıklama modunda çalıştırdığınızda, dağıtım işlemi bir klasörde oluşturur *özelliği* %COMMONPROGRAMFILES%\Microsoft Shared\web server extensions\14\TEMPLATE\FEATURES konumundaki dizin. Özellik adlarının biçime sahip *proje adı*_Feature*x*, TestProject_Feature1 gibi.  
  
 Özellik dizinine çözümün klasöründe içeren bir *özelliği tanımı* dosyası ve bir *iş akışı tanımı* dosya. Özellik tanım dosyası (Feature.xml dosyasına) dosyalarını açıklar projenin özelliğinin proje şablonu proje tanım dosyası (Elements.xml) açıklar. Elements.XML bulunabilir **Çözüm Gezgini**, ancak Feature.xml dosyasına çözüm paketi oluşturduğunuzda oluşturulur. Bu dosyalar hakkında daha fazla bilgi için bkz: [SharePoint Proje ve proje öğesi şablonları](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
##  <a name="Workflow"></a> İş akışları hata ayıklama  
 İş akışı projelerinde hata ayıklama işlemi yaparken [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (türüne bağlı olarak kendi) iş akışı şablonu bir kitaplık veya bir listesine ekler. İş akışı şablonu sonra el ile veya eklemek veya bir öğe tarafından da başlatabilirsiniz. Daha sonra kullanabilirsiniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] iş akışı hata ayıklamak için.  
  
> [!NOTE]  
>  Diğer derlemelerine başvurular eklerseniz, emin olun, bu derlemeleri genel derleme önbelleğinde yüklü ([!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]). Aksi takdirde, iş akışı çözümü başarısız olur. Derlemeleri yükleme hakkında daha fazla bilgi için bkz: [el ile bir iş akışı bir belge veya öğe başlatmak](http://go.microsoft.com/fwlink/?LinkID=79938).  
  
 Ancak, dağıtım işlemi, iş akışı başlatılmaz. İş akışı SharePoint Web sitesinden başlatmanız gerekir. İş akışı Ayrıca, Microsoft Office Word 2010 gibi bir istemci uygulaması kullanarak ya da ayrı sunucu tarafı kodu kullanarak da başlatabilirsiniz. Belirtilen yaklaşımlardan birini kullanın **SharePoint Özelleştirme Sihirbazı'nı**.  
  
 İş akışını el ile başlatılabilir belirtilmişse, örneğin, kitaplık veya liste öğesi doğrudan iş akışı'nı başlatın. Bir iş akışı el ile başlatma hakkında daha fazla bilgi için bkz: [el ile bir belge öğesi üzerinde bir iş akışı başlatmalarını](http://go.microsoft.com/fwlink/?LinkID=79938).  
  
##  <a name="FeatureEvents"></a> Hata ayıklama özellik Olay alıcıları  
 Varsayılan olarak çalıştırdığınızda, bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint uygulaması özelliklerini otomatik olarak sizin için SharePoint sunucusu üzerine etkinleştirilir. Özellik Olay alıcıları, hata ayıklama işlemi yaparken bir özellik tarafından etkinleştirildiğinde ancak, bu sorunlara neden olur [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], hata ayıklayıcı farklı bir işlemde çalıştırır. Başka bir deyişle, kesme noktaları gibi bazı hata ayıklama işlevleri düzgün çalışmaz.  
  
 SharePoint özelliğinde otomatik etkinleştirmeyi devre dışı bırakın ve uygun özellik Olay alıcıları hata ayıklama izin vermek için projenin değerini ayarlamak **etkin Dağıtım Yapılandırması** özelliğine **Hayır etkinleştirme** hata ayıklama önce. Ardından, SharePoint uygulamanızda hata ayıklama başladıktan sonra [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], el ile SharePoint'teki özelliği etkinleştir. Özelliğini etkinleştirmek için açık **Site eylemleri** SharePoint menüde seçin **Site Ayarları**, seçin **yönetmek Site özellikleri** bağlamak ve ardından **Etkinleştirme** normal olarak hata ayıklama devam etmek için özellik yanındaki düğmesi.  
  
##  <a name="EnhancedDebug"></a> Gelişmiş hata ayıklama bilgilerini etkinleştirme  
 Arasındaki bazen karmaşık etkileşimleri nedeniyle [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] işlemi (devenv.exe) [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint ana bilgisayar işlemi (vssphost4.exe), SharePoint ve WCF katman, derleme, dağıtma ve benzeri sırasında oluşan hataları tanılama olabilir bir sınama. Bu tür hatalar çözmenize yardımcı olacak Gelişmiş hata ayıklama bilgilerini etkinleştirebilirsiniz. Bunu yapmak için Windows Kayıt Defteri'nde aşağıdaki kayıt defteri anahtarına gidin:  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\11.0\SharePointTools]  
  
 Varsa "EnableDiagnostics" **REG_DWORD** değer zaten var, el ile oluşturun. "1." "EnableDiagnostics" değerine ayarlayın  
  
 Bu anahtarı değeri 1 nedenler yığınına ayarı izleme görünmesi bilgi **çıkış** çalışırken proje sistem hataları gerçekleştiğinde penceresi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Gelişmiş hata ayıklama bilgilerini devre dışı bırakmak için EnableDiagnostics geri 0 olarak ayarlayın veya değeri silin.  
  
 Diğer SharePoint kayıt defteri anahtarları hakkında daha fazla bilgi için bkz: [Visual Studio'da SharePoint araçları için hata ayıklama uzantıları](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümlerinde Sorun Giderme](../sharepoint/troubleshooting-sharepoint-solutions.md)  
  
  