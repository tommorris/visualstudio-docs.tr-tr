---
title: Visual Studio devenv komut satırı anahtarları
ms.date: 02/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- switches, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1b6cf3bf422c861d5a649e5cfa71cf2b4a4b5fea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="devenv-command-line-switches"></a>Devenv komut satırı anahtarları

Devenv tümleşik geliştirme ortamı (IDE) için çeşitli seçenekler ayarlamak yanı sıra yapı, hata ayıklama ve komut satırından projeleri dağıtmanızı sağlar. Bu anahtarları IDE bir komut dosyası veya .bat dosyası, örneğin gecelik yapı betik çalıştırmak için veya belirli bir yapılandırmada IDE başlatmak için kullanın.

> [!NOTE]
> Yapı ilgili görevler için MSBuild yerine devenv kullanmanız önerilir. Daha fazla bilgi için bkz: [MSBuild komut satırı başvurusu](../../msbuild/msbuild-command-line-reference.md).

## <a name="devenv-switch-syntax"></a>Devenv anahtarı sözdizimi

Varsayılan olarak, devenv komutları devenv.com yardımcı programı anahtarları geçer. Devenv.com yardımcı programı gibi standart sistem akışları aracılığıyla çıktı sunar `stdout` ve `stderr`. Örneğin .txt dosyası için çıktı yakalar olduğunda yardımcı programı uygun g/ç yönlendirmesi belirler.

Diğer taraftan, ile başlar komutları `devenv.exe` aynı anahtarlar kullanabilirsiniz, ancak devenv.com yardımcı programı atlanır.

Sözdizimi kuralları için `devenv` anahtarları benzer diğer DOS komut satırı yardımcı programları için olanlar. Aşağıdaki sözdizimi kurallarına tümüne uygulamak `devenv` anahtarları ve bunların bağımsız değişkenler:

- Komutları ile başlar `devenv`.

- Anahtarlar büyük küçük harfe duyarlı değildir.

- Bir çözüm ya da proje belirtirken, ilk bağımsız değişken çözüm dosyası veya dosya yolu da dahil olmak üzere, proje dosyası adıdır.

- İlk bağımsız değişkeni bir çözüm ya da proje olmayan bir dosya varsa, bu dosyayı uygun düzenleyicisinde IDE yeni bir örneğini açar.

- Çözüm, bir dosya adı yerine bir proje dosyası adı sağladığında bir `devenv` komut aynı ada sahip bir çözüme proje dosyası üst klasörünü arar. Örneğin, komut `devenv /build myproject1.vbproj` "myproject1.sln" adlı bir çözüm dosyası için üst klasör arar.

    > [!NOTE]
    > Bu projeye başvuruda bulunan bir ve yalnızca bir çözüm dosyasını kendi üst klasörde bulunmalıdır. Üst klasör herhangi bir çözüm dosyası içeriyorsa, bu projeye başvuruda bulunan veya üst klasörü ona başvurmak iki veya daha fazla çözüm dosyaları içeriyorsa, daha sonra bir geçici çözüm dosyası oluşturulur.

- Dosya yolları ve dosya adı boşluklar, bunları tırnak işaretleri içine almalısınız (""). Örneğin, "c:\project bir\\".

- Anahtarlar ve bağımsız değişkenleri aynı satırda arasında bir boşluk karakteri ekleyin. Örneğin, komut **devenv/log çıktı.txt** IDE açar ve çýktý.txt için tüm günlük bu oturum için bilgileri çıkartır.

- Desen eşleştirme sözdizimi kullanamazsınız `devenv` komutları.

## <a name="devenv-switches"></a>Devenv anahtarları

Aşağıdaki komut satırı anahtarları IDE görüntülemek ve açıklanan görevi gerçekleştirebilirsiniz.

|Komut satırı anahtarı|Açıklama|
|-------------------------|-----------------|
|[/ Komutu](../../ide/reference/command-devenv-exe.md)|IDE başlatır ve belirtilen komut yürütür.|
|[/ DebugExe](../../ide/reference/debugexe-devenv-exe.md)|Hata ayıklayıcı denetimi altında bir C++ yürütülebilir dosyayı yükler. Bu anahtar, Visual Basic veya C# yürütülebilir dosyaları için kullanılamıyor. Daha fazla bilgi için bkz: [bir işlem hata ayıklayıcısı'ndaki otomatik olarak Başlat](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger).|
|[/ LCID veya /l](../../ide/reference/lcid-devenv-exe.md)|IDE için varsayılan dili ayarlar. Belirtilen dil Visual Studio yüklemenizin bulunmuyorsa, bu ayar yok sayılır.|
|[/ Log](../../ide/reference/log-devenv-exe.md)|Visual Studio başlatılır ve tüm etkinlik günlük dosyasına kaydeder.|
|[/ Run veya/r](../../ide/reference/run-devenv-exe.md)|Derler ve belirtilen çözüm çalıştırır.|
|[/ Runexit](../../ide/reference/runexit-devenv-exe.md)|Derler ve belirtilen çözüm için çözümü çalıştırılır ve çözüm çalışması bittikten sonra IDE kapandığında IDE en aza indirir.|
|[/ UseEnv](../../ide/reference/useenv-devenv-exe.md)|VC ++ dizinleri kısmında belirtilen ayarlara yerine C++ derleme yolu, Ekle ve LIB ortam değişkenleri kullanılmak üzere IDE neden **projeleri** içinde seçenekleri **seçenekleri** iletişim kutusu. Bu anahtarı ile yüklenen **C++ ile masaüstü geliştirme** iş yükü. Daha fazla bilgi için bkz: [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds).|
|[/ Düzenle](../../ide/reference/edit-devenv-exe.md)|Belirtilen dosyaları bu uygulamanın çalışan bir örneğini açar. Hiçbir çalışan örneği varsa, Basitleştirilmiş pencere düzenini ile yeni bir örneğini başlatır.|
|[/SafeMode](../../ide/reference/safemode-devenv-exe.md)|Visual Studio güvenli modda başlatır ve yalnızca varsayılan ortamı ve hizmetleri yükler ve üçüncü taraf paketlerden sürümleri sevk.|
|[/ ResetSkipPkgs](../../ide/reference/resetskippkgs-devenv-exe.md)|VSPackages için sorun VSPackages yüklenmesini önlemek için istediğiniz kullanıcılar tarafından eklenen tüm SkipLoading etiketleri temizler.|
|[/ Kurulumu](../../ide/reference/setup-devenv-exe.md)|Menüleri, araç çubukları ve komut gruplarından tüm VSPackages kullanılabilir açıklar kaynak meta verileri birleştirmek için Visual Studio zorlar. Bu komutu bir yönetici olarak çalıştırmanız gerekir.|

Aşağıdaki komut satırı anahtarları IDE görüntülemez.

|Komut satırı anahtarı|Açıklama|
|-------------------------|-----------------|
|[/?](../../ide/reference/q-devenv-exe.md)|Devenv anahtarları için yardımı görüntüler **komut istemi penceresi**.<br /><br /> **Devenv /?**|
|[/ Yapı](../../ide/reference/build-devenv-exe.md)|Belirtilen çözüm ya da belirtilen çözüm yapılandırmasına göre proje oluşturur.<br /><br /> **Devenv myproj.csproj/BUILD**|
|[/ Temizle](../../ide/reference/clean-devenv-exe.md)|Kaynak dosyaları etkilemeden yapı komutu tarafından oluşturulan tüm dosyaları siler.<br /><br /> **Devenv myproj.csproj / Temizle**|
|[/ Dağıt](../../ide/reference/deploy-devenv-exe.md)|Çözümleri yapılandırmasına dağıtımı için gerekli dosyaları yanı sıra çözüm oluşturur.<br /><br /> **Devenv myproj.csproj / dağıtma**|
|[/ Fark](../../ide/reference/diff.md)|İki dosyayı karşılaştırır. Dört parametre alır: SourceFile TargetFile, SourceDisplayName (isteğe bağlı), TargetDisplayName (isteğe bağlı).|
|[/ Out](../../ide/reference/out-devenv-exe.md)|Oluşturma sırasında hatalar almak için bir dosya belirtmenize olanak sağlar.<br /><br /> **Devenv myproj.csproj/BUILD/log.txt out**|
|[/Project](../../ide/reference/project-devenv-exe.md)|Projeyi oluşturmak için temiz veya dağıtabilirsiniz. Yalnızca / BUILD ayrıca sağladıysanız bu anahtarı kullanabilirsiniz/rebuild / temiz, veya / deploy anahtarı.|
|[/ProjectConfig](../../ide/reference/projectconfig-devenv-exe.md)|Derleme veya dağıtmak için proje yapılandırması belirtir. Yalnızca/Project anahtarı da sağladıysanız bu anahtarı kullanabilirsiniz.|
|[/ Rebuild](../../ide/reference/rebuild-devenv-exe.md)|Temizler ve belirtilen çözüm ya da belirtilen çözüm yapılandırmasına göre proje oluşturur.|
|[/ ResetSettings](../../ide/reference/resetsettings-devenv-exe.md)|Visual Studio varsayılan ayarlarına geri yükler. İsteğe bağlı olarak belirtilen .vssettings dosyasına ayarlarını sıfırlar.|
|[/ Yükseltme](../../ide/reference/upgrade-devenv-exe.md)|Bu dosyalar için geçerli Visual Studio biçimleri için belirtilen çözüm dosyasını ve tüm proje dosyalarını ya da belirtilen proje dosyasını yükseltir.|

## <a name="see-also"></a>Ayrıca bkz.

* [Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)