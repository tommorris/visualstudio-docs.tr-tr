---
title: MSI ve DSL VSIX dağıtımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: de6b219610908503f37658ff977f042363fb8663
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="msi-and-vsix-deployment-of-a-dsl"></a>DSL'nin MSI ve VSIX Dağıtımı
Bir etki alanına özgü dil kendi bilgisayarınızda veya diğer bilgisayarlara yükleyebilirsiniz. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hedef bilgisayarda yüklü olması gerekir.  
  
##  <a name="which"></a> VSIX ve MSI dağıtım arasında seçim yapma  
 Bir etki alanına özgü dil dağıtmak için iki yöntem vardır:  
  
|Yöntem|Yararları|  
|------------|--------------|  
|VSX ([!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı)|Dağıtımı kolay: kopyalama ve yürütme **.vsix** DslPackage proje dosyasından.<br /><br /> Daha fazla bilgi için bkz: [yükleme ve VSX kullanarak DSL kaldırma](#Installing).|  
|MSI (yükleyici dosyası)|-Açmak kullanıcının sağlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL dosyasını çift tıklatarak.<br />-Hedef bilgisayardaki DSL dosya türü ile bir simge ilişkilendirir.<br />-Bir XSD (XML Şeması) DSL dosya türü ile ilişkilendirir. İçine dosya yüklendiğinde bu uyarıları önler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].<br /><br /> Çözümünüze bir MSI oluşturmak için bir kurulum projesi eklemeniz gerekir.<br /><br /> Daha fazla bilgi için bkz: [bir MSI dosyası kullanarak bir DSL dağıtma](#msi).|  
  
##  <a name="Installing"></a> Yükleme ve DSL VSX kullanarak kaldırma  
 Bu yöntem tarafından DSL yüklendiğinde, kullanıcı bir DSL dosyasını içinden açabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ancak Windows Gezgini'nden dosya açılamıyor.  
  
#### <a name="to-install-a-dsl-by-using-the-vsx"></a>DSL VSX kullanarak yüklemek için  
  
1.  Bilgisayarınızda, bulma **.vsix** DSL paket projeniz tarafından oluşturulmuş dosya.  
  
    1.  İçinde **Çözüm Gezgini**, sağ **DslPackage** proje ve ardından **klasörü Windows Gezgini'nde Aç**.  
  
    2.  Dosyayı bulmak **bin\\\*\\***projeniz***. DslPackage.vsix**  
  
2.  Kopya **.vsix** DSL yüklemek istediğiniz hedef bilgisayara dosya. Bu, kendi bilgisayarınızda veya başka bir tane olabilir.  
  
    -   Hedef bilgisayarda sürümlerinden biri olmalıdır [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] , çalışma zamanında DSL'ler destekler. Daha fazla bilgi için bkz: [Görselleştirme ve modelleme SDK'sı için Visual Studio sürümlerini desteklenen](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md).  
  
    -   Hedef bilgisayarda sürümlerinden biri olmalıdır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] belirtilen **DslPackage\source.extensions.manifest**.  
  
3.  Hedef bilgisayarda çift **.vsix** dosya.  
  
     **Visual Studio Uzantı Yükleyicisi** açar ve uzantıyı yükler.  
  
4.  Başlatma veya yeniden [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
5.  DSL sınamak için kullanın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , DSL için tanımlanan uzantısına sahip yeni bir dosya oluşturulamadı.  
  
#### <a name="to-uninstall-a-dsl-that-was-installed-by-using-vsx"></a>VSX kullanarak yüklenen DSL kaldırmak için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **Uzantı Yöneticisi**.  
  
2.  Genişletme **Uzantılar**.  
  
3.  Ardından seçip DSL tanımlanır uzantısı **kaldırma**.  
  
 Nadiren, hatalı bir uzantı yüklemede başarısız olur ve hata penceresinde bir rapor oluşturur, ancak Uzantı Yöneticisi'nde görüntülenmez. Bu durumda, dosyayı silerek uzantıyı kaldırabilirsiniz:  
  
 *LocalAppData* **\Microsoft\VisualStudio\10.0\Extensions**  
  
##  <a name="msi"></a> Bir MSI içinde DSL dağıtma  
 MSI (Windows Yükleyici) dosyasının, DSL için tanımlayarak, DSL dosyalar Windows Gezgini'nden açmasına izin verebilirsiniz. Ayrıca, dosya adı uzantısı ile bir simge ve kısa bir açıklama ilişkilendirebilirsiniz. Ayrıca, MSI DSL dosyaları doğrulamak için kullanılan bir XSD yükleyebilirsiniz. İsterseniz, aynı anda yüklü MSI içine diğer bileşenleri ekleyebilirsiniz.  
  
 MSI dosyaları ve diğer dağıtım seçenekleri hakkında daha fazla bilgi için bkz: [dağıtma uygulamaları, hizmetleri ve bileşenleri](../deployment/deploying-applications-services-and-components.md).  
  
 Bir MSI oluşturmak için Kurulum projesine ekleyin, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü. Kurulum projesi oluşturma en kolay yöntem indirebileceğiniz CreateMsiSetupProject.tt şablonu kullanmaktır [VMSDK site](http://go.microsoft.com/fwlink/?LinkID=186128).  
  
#### <a name="to-deploy-a-dsl-in-an-msi"></a>Bir MSI içinde DSL dağıtmak için  
  
1.  Ayarlama `InstalledByMsi` uzantısı bildiriminde. Bu VSX yüklü ve dışında MSI tarafından kaldırılır önler. Bu, diğer bileşenler MSI içeriyorsa önemlidir.  
  
    1.  Open DslPackage\source.extension.tt  
  
    2.  Önce aşağıdaki satırı ekleyin `<SupportedProducts>`:  
  
        ```  
        <InstalledByMsi>true</InstalledByMsi>  
        ```  
  
2.  Oluşturabilir veya Windows Gezgini'nde, DSL temsil edecek simge düzenleyebilirsiniz. Örneğin, düzenleme **DslPackage\Resources\File.ico**  
  
3.  Aşağıdaki öznitelikler, DSL, doğru olduğundan emin olun:  
  
    -   DSL Gezgini'nde kök düğümünü tıklatın ve Özellikler penceresinde gözden geçirin:  
  
        -   Açıklama  
  
        -   Sürüm  
  
    -   Tıklatın **Düzenleyicisi** düğümü ve özellikleri penceresinde **simgesi**. Bir simge dosyası başvuran bir değere ayarlayın **DslPackage\Resources**, gibi **File.ico**  
  
    -   Üzerinde **yapı** menüsünde, açık **Configuration Manager**, gibi oluşturmak istediğiniz yapılandırma seçip **sürüm** veya **hata ayıklama** .  
  
4.  Git [Görselleştirme ve modelleme SDK Giriş sayfası](http://go.microsoft.com/fwlink/?LinkID=186128), gelen ve giden **indirmeleri** sekmesinde, yükleme **CreateMsiSetupProject.tt**.  
  
5.  Ekleme **CreateMsiSetupProject.tt** Dsl projenize.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adlı bir dosya oluşturacaksınız **CreateMsiSetupProject.vdproj**.  
  
6.  Windows Gezgini'nde Dsl kopyalama\\yeni bir klasöre *.vdproj adlı kurulumu.  
  
     (İsterseniz, şimdi Dsl projenizden CreateMsiSetupProject.tt dışlayabilirsiniz.)  
  
7.  İçinde **Çözüm Gezgini**, ekleme **Kurulum\\\*.vdproj** mevcut proje olarak.  
  
8.  Üzerinde **proje** menüsünde tıklatın **proje bağımlılıkları**.  
  
     İçinde **proje bağımlılıkları** iletişim kutusunda, Kurulum projesini seçin.  
  
     Yanındaki kutuyu işaretleyin **DslPackage**.  
  
9. Çözümü yeniden derleyin.  
  
10. Windows Gezgini'nde, Kurulum projenizde yerleşik MSI dosyasını bulun.  
  
     MSI dosyası, DSL yüklemek istediğiniz bilgisayara kopyalayın. MSI dosyasını çift tıklatın. Yükleyiciyi çalıştırır.  
  
11. Hedef bilgisayarda, DSL dosya uzantısına sahip yeni bir dosya oluşturun. Aşağıdakileri doğrulayın:  
  
    -   Windows Gezgini liste görünümünde dosya simgesi ve tanımladığınız açıklaması ile görünür.  
  
    -   Dosyayı çift tıkladığınızda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] başlatır ve DSL dosya DSL Düzenleyicisi'nde açar.  
  
 İsterseniz, metin şablonu kullanmak yerine Kurulum projesi el ile oluşturabilirsiniz. Bu yordamı içeren için Bölüm 5 bkz [Görselleştirme ve modelleme SDK Laboratuvar](http://go.microsoft.com/fwlink/?LinkId=208878).  
  
#### <a name="to-uninstall-a-dsl-that-was-installed-from-an-msi"></a>Bir MSI yüklenen DSL kaldırmak için  
  
1.  Windows'da açmak **programlar ve Özellikler** Denetim Masası.  
  
2.  DSL kaldırın.  
  
3.  Visual Studio'yu yeniden başlatın.