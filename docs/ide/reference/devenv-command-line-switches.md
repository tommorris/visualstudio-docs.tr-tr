---
title: "Devenv komut satırı anahtarları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- switches, Devenv
- builds [Team System], command-line
- applications [Visual Studio], executing
- compiling source code, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
- environment, Devenv commands
- compilers, Devenv commands
- switches
- Devenv, syntax and list of switches
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a22ac991b88dd62c91a9bf08f5397fe80e4ae37d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="devenv-command-line-switches"></a>Devenv Komut Satırı Anahtarları
Devenv tümleşik geliştirme ortamı (IDE) için çeşitli seçenekler ayarlamak ve ayrıca yapı, hata ayıklama ve komut satırından projeleri dağıtmanızı sağlar. Bu anahtarları bir komut dosyası veya .bat dosyası, her gece yapı betik, IDE çalıştırmak için veya belirli bir yapılandırmada IDE başlatmak için kullanın.  
  
> [!NOTE]
>  Yapı ilgili görevler için yerine devenv MSBuild kullanma şimdi önerilir. Daha fazla bilgi için bkz: [komut satırı başvurusu](../../msbuild/msbuild-command-line-reference.md).  
  
> [!NOTE]
>  Kullanmak için bir yönetici devenv çalıştırmalısınız [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) ve [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) anahtarları.  
  
## <a name="devenv-switch-syntax"></a>Devenv anahtarı sözdizimi  
 Varsayılan olarak, devenv komutları devenv.com yardımcı programı anahtarları geçer.  
  
 Devenv.com yardımcı programı çıkışı standart sistem akışları üzerinden teslimini gibi sağlar `stdout` ve `stderr`ve bir .txt dosyasına çıktı, örneğin, yakalar olduğunda uygun g/ç yönlendirmesi belirler. Bunun yerine ile başlayan komutlar `devenv.exe` aynı anahtarlar kullanabilirsiniz, ancak bunları devenv.com yardımcı programı atlayarak devenv.exe programına gönderir.  
  
 Sözdizimi kuralları için `devenv` anahtarları benzer diğer DOS komut satırı yardımcı programları için olanlar. Aşağıdaki sözdizimi kurallarına tümüne uygulamak `devenv` anahtarları ve bunların bağımsız değişkenler:  
  
-   Komutları ile başlar `devenv`.  
  
-   Anahtarlar büyük küçük harfe duyarlı değildir.  
  
-   Bir çözüm ya da proje belirtirken, ilk bağımsız değişken çözüm dosyası veya dosya yolu da dahil olmak üzere, proje dosyası adıdır.  
  
-   İlk bağımsız değişkeni bir çözüm ya da proje olmayan bir dosya varsa, bu dosyayı uygun düzenleyicisinde IDE yeni bir örneğini açar.  
  
-   Çözüm, bir dosya adı yerine bir proje dosyası adı sağladığında bir `devenv` komut aynı ada sahip bir çözüme proje dosyası üst klasörünü arayacaktır. Örneğin, komut `devenv /build myproject1.vbproj` "myproject1.sln" adlı bir çözüm dosyası için üst klasör arar.  
  
    > [!NOTE]
    >  Bu projeye başvuruda bulunan bir ve yalnızca bir çözüm dosyasını kendi üst klasörde bulunmalıdır. Bu projeye başvuruda bulunan herhangi bir çözüm dosyası üst klasörü içeriyorsa veya üst klasörü ona başvurmak iki veya daha fazla çözüm dosyaları içeriyorsa, ardından bir geçici çözüm dosyası oluşturulur, bu proje için adlı ve başvurur.  
  
-   Dosya yolları ve dosya adı boşluklar, bunları çift tırnak içine almalısınız (""). Örneğin, "c:\project bir\\".  
  
-   Anahtarlar ve bağımsız değişkenleri aynı satırda arasında bir boşluk karakteri ekleyin. Örneğin, komut **devenv/log çıktı.txt** IDE açar ve çýktý.txt için tüm günlük bu oturum için bilgileri çıkartır.  
  
-   Desen eşleştirme sözdizimi kullanamazsınız `devenv` komutları.  
  
## <a name="devenv-switches"></a>Devenv anahtarları  
 IDE görüntülemek ve açıklanan görevi gerçekleştirmek için aşağıdaki komut satırı anahtarları kullanın.  
  
|Komut satırı anahtarı|Açıklama|  
|-------------------------|-----------------|  
|[/ Command (devenv.exe)](../../ide/reference/command-devenv-exe.md)|IDE başlatır ve belirtilen komut yürütür.|  
|[/ DebugExe (devenv.exe)](../../ide/reference/debugexe-devenv-exe.md)|Yükleri bir [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] hata ayıklayıcı denetiminde çalıştırılabilir. Bu anahtar için kullanılamıyor [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] veya [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] yürütülebilir. Daha fazla bilgi için bkz: [bir işlem hata ayıklayıcısı'ndaki otomatik olarak Başlat](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger).|  
|[/ LCID (devenv.exe)](../../ide/reference/lcid-devenv-exe.md) veya`/l`|IDE için varsayılan dili ayarlar. Belirtilen dil Visual Studio yüklemenizin bulunmuyorsa, bu ayar yoksayılır.|  
|[/ Log (devenv.exe)](../../ide/reference/log-devenv-exe.md)|Başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve tüm etkinlik günlük dosyasına kaydeder.|  
|[/ (Devenv.exe) çalıştırmak](../../ide/reference/run-devenv-exe.md) veya`/r`|Derler ve belirtilen çözüm çalıştırır.|  
|[/ Runexit (devenv.exe)](../../ide/reference/runexit-devenv-exe.md)|Derler ve belirtilen çözüm için çözümü çalıştırılır ve çözüm çalışması bittikten sonra IDE kapandığında IDE en aza indirir.|  
|[/ UseEnv (devenv.exe)](../../ide/reference/useenv-devenv-exe.md)|YOL, Ekle ve LIB ortam değişkenleri için kullanılacak IDE neden [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] derleme VC ++ dizinleri kısmında belirtilen ayarlara yerine **projeleri** içinde seçenekleri **seçenekleri** iletişim kutusu. Daha fazla bilgi için bkz: [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds)|  
|[/ Düzenle (devenv.exe)](../../ide/reference/edit-devenv-exe.md)|Belirtilen dosyaları bu uygulamanın çalışan bir örneğini açar. Hiçbir çalışan örneği varsa, yeni bir örneği ile Basitleştirilmiş pencere düzenini başlayacaktır.|  
|[/ ResetAddin (devenv.exe)](../../ide/reference/resetaddin-devenv-exe.md)|Belirtilen eklenti yüklemeden Visual Studio IDE bir örneğini başlatır.|  
|[/ SafeMode (devenv.exe)](../../ide/reference/safemode-devenv-exe.md)|Başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] güvenli modda, yalnızca varsayılan ortamı ve hizmetleri yükler ve üçüncü taraf paketlerden sürümleri sevk.|  
|[/ ResetSkipPkgs (devenv.exe)](../../ide/reference/resetskippkgs-devenv-exe.md)|VSPackages için sorun VSPackages yüklenmesini önlemek için istediğiniz kullanıcılar tarafından eklenen tüm SkipLoading etiketleri temizler.|  
|[/ Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md)|Menüleri, araç çubukları ve komut gruplarından tüm VSPackages kullanılabilir açıklar kaynak meta verileri birleştirmek için Visual Studio zorlar.|  
  
 Aşağıdaki komut satırı anahtarları açıklanan görevi gerçekleştirmek için kullanın. Bu komut satırı anahtarları IDE görüntülemez.  
  
|Komut satırı anahtarı|Açıklama|  
|-------------------------|-----------------|  
|[/? (devenv.exe)](../../ide/reference/q-devenv-exe.md)|Devenv anahtarları için yardımı görüntüler **komut istemi penceresi**.<br /><br /> **Devenv /?**|  
|[/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)|Belirtilen çözüm ya da belirtilen çözüm yapılandırmasına göre proje oluşturur.<br /><br /> **Devenv myproj.csproj/BUILD**|  
|[/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)|Kaynak dosyaları etkilemeden yapı komutu tarafından oluşturulan tüm dosyaları siler.<br /><br /> **Devenv myproj.csproj / Temizle**|  
|[/ (Devenv.exe) dağıtma](../../ide/reference/deploy-devenv-exe.md)|Çözümleri yapılandırmasına dağıtımı için gerekli dosyaları yanı sıra çözüm oluşturur.<br /><br /> **Devenv myproj.csproj / dağıtma**|  
|[/ Fark](../../ide/reference/diff.md)|İki dosyayı karşılaştırır.  Dört parametreleri: SourceFile, TargetFile, SourceDisplayName(optional),TargetDisplayName(optional) alır.|  
|[/ Installvstemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md)|Bulunan öğe veya proje şablonları kaydeder  *\<VisualStudioInstallDir >*\Common7\IDE\ProjectTemplates veya  *\<VisualStudioInstallDir >*\Common7 \IDE\ItemTemplates aracılığıyla erişilebilir böylece **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları.<br /><br /> **Devenv /InstallVSTemplates**|  
|[/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)|Oluşturma sırasında hatalar almak için bir dosya belirtmenize olanak sağlar.<br /><br /> **Devenv myproj.csproj/BUILD/log.txt out**|  
|[/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)|Projeyi oluşturmak için temiz veya dağıtabilirsiniz. Yalnızca / BUILD ayrıca sağladıysanız bu anahtarı kullanabilirsiniz/rebuild / temiz, veya / deploy anahtarı.|  
|[/ ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)|Derleme veya dağıtmak için proje yapılandırması belirtir. Yalnızca/Project anahtarı da sağladıysanız bu anahtarı kullanabilirsiniz.|  
|[/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)|Temizler ve belirtilen çözüm ya da belirtilen çözüm yapılandırmasına göre proje oluşturur.|  
|[/ ResetSettings (devenv.exe)](../../ide/reference/resetsettings-devenv-exe.md)|Visual Studio varsayılan ayarlarına geri yükler. İsteğe bağlı olarak belirtilen .vssettings dosyasına ayarlarını sıfırlar.|  
|[/ Updateconfiguration (devenv.exe)](../../ide/reference/updateconfiguration-devenv-exe.md)|Bildirir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] birleştirmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sistem ve onay MEF paketleri önbelleğe herhangi bir değişiklik.|  
|[/ Yükseltme (devenv.exe)](../../ide/reference/upgrade-devenv-exe.md)|Belirtilen çözüm dosyasını ve tüm proje dosyalarını ya da belirtilen proje dosyası geçerli yükseltme [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bu dosyalar için biçimleri.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)