---
title: Yan yana dosya ilişkilendirmeleri yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- verbs, setting default
ms.assetid: 9b6df3bc-d15c-4a5d-9015-948a806193b7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e9144125786e7aa5f2a70823a033d49ac3fa2990
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="managing-side-by-side-file-associations"></a>Yan yana dosya ilişkilendirmeleri yönetme
Dosya ilişkilendirmeleri, VSPackage sağlıyorsa, hangi yan yana yüklemelerde nasıl ele alınacağını karar vermeniz gerekir belirli bir sürümü [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir dosyayı açmaya çağrılmalıdır. Uyumsuz dosya biçimleri sorunu bileşik.  
  
 Kullanıcıların veri kaybetmeden yeni sürümde mevcut dosyaları yüklenebilir böylece daha önceki sürümleriyle uyumlu olacak şekilde bir ürünün yeni bir sürümü bekler. İdeal olarak, VSPackage hem yükleyin ve önceki sürümlerinde dosya biçimlerinin kaydedin. Bu doğru değilse, dosya biçimi, VSPackage yeni sürümüne yükseltmek teklif. Bu yaklaşımın dezavantajı, yükseltilen dosyayı daha önceki bir sürümde açılamıyor ' dir.  
  
 Bu sorunu önlemek için dosya biçimlerini uyumsuz olduğunda uzantıları değiştirebilirsiniz. Örneğin, VSPackage 1 sürümünü uzantısı, .mypkg10 ve sürüm 2 uzantısı kullanın kullanabilirsiniz .mypkg20. Bu fark, belirli bir dosyayı açar VSPackage tanımlar. Eski bir uzantısı ile ilişkili olan programların listesi için daha yeni VSPackages eklerseniz, kullanıcıların dosyaya sağ tıklayın ve daha yeni bir VSPackage içinde açmak seçin. Bu noktada, dosya yeni biçimine yükseltmek veya dosyayı açın ve VSPackage önceki sürümleriyle uyumluluğunu korumak, VSPackage sunabilir.  
  
> [!NOTE]
>  Bu yaklaşım birleştirebilirsiniz. Örneğin, eski bir dosyayı yükleyerek geriye dönük uyumluluk sunar ve kullanıcı kaydettiğinde dosya biçimine yükseltmek sunar.  
  
## <a name="facing-the-problem"></a>Sorun karşılıklı  
 Birden çok yan yana VSPackages aynı uzantı kullanmak istiyorsanız, sürümü seçmeniz gerekir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı ile ilişkili. İki seçenekleri şunlardır:  
  
-   Dosyanın en son sürümünde açabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kullanıcının bilgisayarda yüklü.  
  
     Bu yaklaşımda, yükleyici en son sürümünü belirlemek için sorumlu olduğu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve, dosya ilişkilendirme için yazılan kayıt defteri girdisini dahil olmak üzere. Bir Windows Installer paketi en son sürümünü belirten bir özelliği ayarlamak için özel eylemler içerebilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
    > [!NOTE]
    >  Bu bağlamda "desteklenen en güncel sürümünü." "en son" anlamına gelir Bu yükleyici girişleri sonraki bir sürümünü otomatik olarak algılamaz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Giriş [algılama sistem gereksinimleri](../extensibility/internals/detecting-system-requirements.md) ve [komutları olduğunu gerekir olması çalıştırmak sonra yüklemesini](../extensibility/internals/commands-that-must-be-run-after-installation.md) burada belirtilen ayarlara benzerdir ve ek sürümlerini desteklemek için gereken [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Özel tablosundaki aşağıdaki satırları DEVENV_EXE_LATEST özelliği bir özellik tarafından AppSearch kümesi olacak şekilde ayarlayın ve RegLocator tabloları ele alınan [komutları olduğunu gerekir olması çalıştırmak sonra yüklemesini](../extensibility/internals/commands-that-must-be-run-after-installation.md). InstallExecuteSequence tablosundaki satırları yürütme sırası başlarında özel eylemler zamanlayın. Koşul sütun yapma mantığı değerlerde çalışır:  
  
    -   Yalnızca mevcut sürümü ise, visual Studio .NET 2002 en son sürümüdür.  
  
    -   Visual Studio .NET 2003 olan en son sürümü yalnızca mevcut değilse ve [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mevcut değil.  
  
    -   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Yalnızca mevcut sürümü ise son sürümüdür.  
  
     Net DEVENV_EXE_LATEST yolunda devenv.exe en son sürümünün bulunduğunu sonucudur.  
  
    ### <a name="customaction-table-rows-that-determine-the-latest-version-of-visual-studio"></a>En son Visual Studio sürümünü özel tablo satırları  
  
    |Eylem|Tür|Kaynak|Hedef|  
    |------------|----------|------------|------------|  
    |CA_SetDevenvLatest_2002|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2002]|  
    |CA_SetDevenvLatest_2003|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2003]|  
    |CA_SetDevenvLatest_2005|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2005]|  
  
    ### <a name="installexecutesequence-table-rows-that-determine-the-latest-version-of-visual-studio"></a>En son Visual Studio sürümünü InstallExecuteSequence tablo satırları  
  
    |Eylem|Koşul|Sırası|  
    |------------|---------------|--------------|  
    |CA_SetDevenvLatest_2002|DEVENV_EXE_2002 VE DEĞİL (DEVENV_EXE_2003 VEYA DEVENV_EXE_2005)|410|  
    |CA_SetDevenvLatest_2003|DEVENV_EXE_2003 VE DEVENV_EXE_2005 DEĞİL|420|  
    |CA_SetDevenvLatest_2005|DEVENV_EXE_2005|430|  
  
     HKEY_CLASSES_ROOT yazmak için Windows Installer paketi kayıt defteri tablosunda DEVENV_EXE_LATEST özelliğini kullanabilirsiniz*ProgID*ShellOpenCommand anahtarının varsayılan değeri, [DEVENV_EXE_LATEST] "%1"  
  
-   En iyi seçenek kullanılabilir VSPackage sürümlerinden yapabilirsiniz paylaşılan Başlatıcısı programını çalıştırın.  
  
     Geliştiriciler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümleri ve birçok sürümlerinden neden projeleri birden çok biçimlerinin karmaşık gereksinimlerini karşılamak için bu yaklaşım seçilmiştir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bu yaklaşımda, Başlatıcısı program uzantısı işleyici olarak kaydedin. Başlatıcı dosya inceler ve hangi sürümü karar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve bu dosyada, VSPackage işleyebilir. Bir kullanıcı, VSPackage belirli bir sürümü tarafından en son kaydedilen bir dosyayı açtığında, örneğin, Başlatıcısı bu VSPackage eşleşen sürümü başlatabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Ayrıca, bir kullanıcı Başlatıcısı'nı her zaman en son sürümünü başlatmak için yapılandırabilirsiniz. Bir başlatıcı dosyasının biçimi yükseltmek için bir kullanıcı da isteyebilir. Biçim dosyasının sürüm numarasını içeriyorsa, dosya biçimini bir veya daha fazla yüklü VSPackages sonraki bir sürümü ise Başlatıcısı kullanıcı bildirin.  
  
     Başlatıcısı, VSPackage tüm sürümleri paylaşılan bir Windows Installer bileşeninde olmalıdır. Bu işlem en son sürümü her zaman yüklü olduğundan ve tüm sürümleri, VSPackage kaldırılır kadar kaldırılmaz emin olur. VSPackage bir sürümü kaldırılmış olsa bile bu şekilde, dosya ilişkilendirmeleri ve diğer kayıt defteri girdilerini Başlatıcısı bileşeninin korunur.  
  
## <a name="uninstall-and-file-associations"></a>Kaldırın ve dosya ilişkilendirmeleri  
 Dosya ilişkilendirmeleri kayıt defteri girdilerini Yazar VSPackage kaldırma dosya ilişkilendirmeleri kaldırır. Bu nedenle, ilişkili program yok uzantılıdır. Windows Installer "VSPackage yüklendiğinde, eklenen kayıt defteri girdilerini kurtarılmıyor". Bir kullanıcının dosya ilişkilendirmeleri gidermek için bazı yollar şunlardır:  
  
-   Daha önce açıklandığı gibi bir paylaşılan Başlatıcısı bileşeni'ni kullanın.  
  
-   Kullanıcı dosya ilişkilendirme kendi istediği VSPackage sürümünün onarım çalıştırmak için kullanıcıdan isteyin.  
  
-   Uygun kayıt defteri girdilerini yeniden yazar ayrı bir yürütülebilir program belirtin.  
  
-   Dosya ilişkilendirmeleri seçin ve kaybolan ilişkilendirmeleri geri kullanıcıları olanak tanıyan bir yapılandırma seçenekleri sayfası veya iletişim kutusu sağlar. Kaldırma sonra çalıştırmak için kullanıcılara bildirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan yana dağıtımlar için dosya adı uzantılarını kaydetme](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [Dosya Adı Uzantıları için Fiil Kaydetme](../extensibility/registering-verbs-for-file-name-extensions.md)