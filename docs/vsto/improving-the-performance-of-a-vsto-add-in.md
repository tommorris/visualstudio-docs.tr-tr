---
title: Bir VSTO eklentisinin performansını
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cc1605a61d63a5d314ae1f02d864124185546ada
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="improve-the-performance-of-a-vsto-add-in"></a>Bir VSTO eklentisinin performansını artırma
  VSTO uygulamaları kapatın, bunlar hızlı bir şekilde başlatmak için Office için oluşturduğunuz eklentileri iyileştirerek, kullanıcılarınızın daha iyi bir deneyim sağlamak, öğeleri açın ve başka görevler gerçekleştirebilirsiniz. VSTO eklentinizi Outlook için ise, VSTO eklentinizi olacaktır fırsat da azaltabilir performansın nedeniyle devre dışı. Aşağıdaki stratejilerden uygulayarak VSTO eklentinizi performansını artırabilirsiniz:  
  
-   [VSTO eklentileri isteğe bağlı yükleme](#Load).  
  
-   [Windows Installer kullanarak Office çözümleri yayımlama](#Publish).  
  
-   [Şerit yansıma atlama](#Bypass).  
  
-   [Bir ayrı yürütme iş parçacığı, pahalı işlemleri](#Perform).  
  
 Bir Outlook VSTO eklenti en iyi duruma getirme hakkında daha fazla bilgi için bkz: [etkin VSTO eklentileri tutmak için performans ölçütleri](http://go.microsoft.com/fwlink/?LinkID=266503).  
  
##  <a name="Load"></a> VSTO eklentileri isteğe bağlı yükleme  
 Bir VSTO yalnızca aşağıdaki durumlarda yüklemek için eklenti yapılandırabilirsiniz:  
  
-   VSTO eklenti yüklendikten sonra kullanıcı uygulamayı başlatır ilk kez.  
  
-   Kullanıcı sonraki dilediğiniz zaman uygulama başlatıldıktan sonra VSTO eklentisi ile etkileşime giren ilk kez.  
  
 Kullanıcı etiketlenir özel bir düğmeyi seçtiğinde Örneğin, VSTO eklentinizi çalışma verilerle doldurmak **My Veri Al**. Uygulama VSTO eklentinizi en az bir kez yüklemeniz gerekir böylece **My Veri Al** düğmesi, şeritte görünebilir. Ancak, VSTO eklenti yeniden kullanıcı uygulamayı bir sonraki açışlarında başladığında yüklenmiyor. VSTO eklenti yükler yalnızca kullanıcının ne zaman seçer **My Veri Al** düğmesi.  
  
### <a name="to-configure-a-clickonce-solution-to-load-vsto-add-ins-on-demand"></a>VSTO eklentileri isteğe bağlı olarak yüklemek için ClickOnce çözümü yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, proje düğümünü seçin.  
  
2.  Menü çubuğunda seçin **Görünüm** > **özellik sayfaları**.  
  
3.  Üzerinde **Yayımla** sekmesinde, seçin **seçenekleri** düğmesi.  
  
4.  İçinde **Yayımla Seçenekleri** iletişim kutusunda, seçin **Office ayarları** liste öğesi, seçin **isteğe bağlı yük** seçeneğini ve ardından **Tamam**düğmesi.  
  
### <a name="to-configure-a-windows-installer-solution-to-load-vsto-add-ins-on-demand"></a>VSTO eklentileri isteğe bağlı olarak yüklemek için Windows Installer çözümü yapılandırmak için  
  
1.  Kayıt defterinde ayarlama `LoadBehavior` girişi **_kök_\Software\Microsoft\Office\\_ApplicationName_\Addins\\  _Eklenti kodu_** anahtarını **0x10**.  
  
     Daha fazla bilgi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).  
  
### <a name="to-configure-a-solution-to-load-vsto-add-ins-on-demand-while-you-debug-the-solution"></a>Çözüm ayıklarken VSTO eklentileri isteğe bağlı olarak yüklemek için bir çözümü yapılandırmak için  
  
1.  Ayarlar bir komut dosyası oluşturma `LoadBehavior` girişi **_kök_\Software\Microsoft\Office\\_ApplicationName_\Addins\\  _Eklenti kodu_** anahtarını **0x10**.  
  
     Aşağıdaki kod bu komut dosyası örneği gösterir.  
  
    ```cmd/sh
    [HKEY_CURRENT_USER\Software\Microsoft\Office\Excel\Addins\MyAddIn]  
    "Description"="MyAddIn"  
    "FriendlyName"="MyAddIn"  
    "LoadBehavior"=dword:00000010  
    "Manifest"="c:\\Temp\\MyAddIn\\bin\\Debug\\MyAddIn.vsto|vstolocal"  
  
    ```  
  
2.  Komut dosyası kullanarak kayıt defterini güncelleştirir oluşturma sonrası bir olay oluşturun.  
  
     Aşağıdaki kod bir oluşturma sonrası olay ekleyebilirsiniz komut dizesi örneği gösterir.  
  
    ```cmd/sh
    regedit /s "$(SolutionDir)$(SolutionName).reg"  
  
    ```  
  
     Bir C# projesi oluşturma sonrası olay oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: belirtin derleme olayları &#40;C&#35;&#41;](/visualstudio/ide/how-to-specify-build-events-csharp).  
  
     Visual Basic projesinde oluşturma sonrası olay oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: belirtin derleme olayları &#40;Visual Basic&#41;](/visualstudio/ide/how-to-specify-build-events-visual-basic).  
  
##  <a name="Publish"></a> Windows Installer kullanarak Office çözümleri yayımlama  
 Windows Installer kullanarak çözümünüzü yayımladığınızda Office çalışma zamanı için Visual Studio 2010 Araçları VSTO eklenti yüklediğinde, aşağıdaki adımları atlar.  
  
-   Bildirim şema doğrulama.  
  
-   Otomatik Güncelleştirmeler denetleniyor.  
  
-   Dağıtım bildirimleri dijital imzalarını doğrulama.  
  
    > [!NOTE]  
    >  Bu yaklaşım VSTO eklentinizi kullanıcıların bilgisayarlarına güvenli bir konuma dağıtırsanız gerekli değildir.  
  
 Daha fazla bilgi için bkz: [Windows Installer kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
##  <a name="Bypass"></a> Şerit yansıma atla  
 Bir çözümü kullanarak yapılandırdıysanız [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)], çözümü dağıttığınızda, kullanıcıların Office çalışma zamanı için Visual Studio 2010 Araçları en son sürümünü yüklediğinizden emin olun. Bu çalışma zamanı eski sürümleri Şerit Özelleştirmelerini bulmak için çözüm derlemelerine yansıtılır. Bu işlem, VSTO daha yavaş yüklemek eklenti neden olabilir.  
  
 Alternatif olarak, yansıma kullanarak Şerit Özelleştirmelerini tanımlamak için herhangi bir sürümünü Office çalışma zamanı için Visual Studio 2010 Araçları engelleyebilir. Bu strateji izlemek için geçersiz kılma `CreateRibbonExtensibility` yöntemi ve açıkça dönüş Şerit nesneleri. VSTO eklentinizi Şerit özelleştirmeler içermiyorsa, dönüş `null` yöntemi içinde.  
  
 Aşağıdaki örnek, bir alanın değerini temel bir Şerit nesnesi döndürür.  
  
 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/VisualBasic/trin_ribbon_choose_ribbon_4/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/CSharp/trin_ribbon_choose_ribbon_4/ThisWorkbook.cs#1)]  
  
##  <a name="Perform"></a> Bir ayrı yürütme iş parçacığı, pahalı işlemleri  
 Ayrı bir iş parçacığı (örneğin, uzun süre çalışan görevler, veritabanı bağlantılarını veya diğer tür ağ çağrıları) uzun süren görevler gerçekleştirmeyi düşünün. Daha fazla bilgi için bkz: [Office'te iş parçacığı desteği](../vsto/threading-support-in-office.md).  
  
> [!NOTE]  
>  Office nesne modeline çağıran tüm kodu ana iş parçacığına da yürütmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İsteğe bağlı yükleme VSTO eklentileri](http://blogs.msdn.com/b/andreww/archive/2008/07/14/demand-loading-vsto-add-ins.aspx)   
 [Office eklentileri CLR gecikme yükleme](http://blogs.msdn.com/b/andreww/archive/2008/04/19/delay-loading-the-clr-in-office-add-ins.aspx)   
 [VSTO performans: gecikme ve yükleme (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/01/07/vsto-performance-delay-loading-and-you.aspx)   
 [Bir hizmet paketine yakında performans iyileştirmeleri, (Stephen Peters) yakınında](http://blogs.msdn.com/b/vsto/archive/2010/11/30/performance-improvements-coming-soon-to-a-service-pack-near-you-stephen-peters.aspx)   
 [VSTO performans: Şerit yansıma (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/06/03/vsto-performance-ribbon-reflection.aspx)  
  
  