---
title: Komut satırından katman etkileşim verileri ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- tier interaction profiling method
- profiling tools,tier interaction method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 42bc9219b3e1af5b1ae25ee2049b7293e2f4c344
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="add-tier-interaction-data-from-the-command-line"></a>Komut satırından katman etkileşim verileri ekleme

Katman etkileşim profil sağlar, zaman uyumlu yürütme sürelerinin hakkında ek bilgi [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] , bir veya daha fazla veritabanı ile iletişim kuran çok katmanlı uygulamaları işlevlerini çağırır.

**Windows 8 ve Windows Server 2012**

Masaüstü uygulamaları Windows 8 ve Windows Server 2012 uygulamalar katman etkileşim verileri toplamak için izleme metodunu kullanmanız gerekir. UWP uygulamaları katman etkileşim verileri toplama desteklenmiyor.

**Visual Studio sürümleri**

Katman etkileşim profil, herhangi bir sürümünü Visual Studio kullanarak toplanabilir. Ancak, katman etkileşimli profil oluşturma verilerini, yalnızca Visual Studio kuruluş içinde görüntülenebilir.

**Uzak makinede ipucu verilerini topla**

Uzak makinede katman etkileşim verileri toplamak için kopyalamanız gerekir **vs_profiler_***\<Platform >***_***\<dil >***.exe** dosyası gelen *%VSInstallDir%***\Team Araçlar\Performans Tools\Setups** klasör Visual Studio'nun makine uzak bilgisayara ve yükleyin. Profil oluşturma araçları kullanamazsınız [uzaktan hata ayıklama](../debugger/remote-debugging.md) paketini indirin.

**İpucu raporları**

Katman etkileşim verileri yalnızca Visual Studio Enterprise görüntülenebilir. Dosya tabanlı katman etkileşimli raporlar aracılığıyla [VSPerfReport](../profiling/vsperfreport.md) kullanılabilir değil.

## <a name="add-tier-interaction-data-with-vsperfcmd"></a>VSPerfCmd ile Katman etkileşim verileri ekleme

VSPerfASPNETCmd komut satırı aracı, tam işlevsellik profil oluşturma araçları kullanılabilir erişim sağlar. Katman etkileşimli profil oluşturma verilerini VSPerfCmd kullanılarak toplanan eklemek için kullanmanız gerekir **VSPerfCLREnv** katman etkileşim verileri sağlayan ayarlamak ve ortam değişkenleri kaldırmak için yardımcı programı. Belirttiğiniz seçenekleri ve veri toplamak için gerekli yordamlarda profil uygulama türüne bağlıdır.

## <a name="profile-stand-alone-applications"></a>Bağımsız uygulamalar profili

Zaman uyumlu yapan bir Windows masaüstü uygulaması gibi başka bir işlem tarafından çalıştırılmaz bir uygulama katman etkileşim verileri eklemek için [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] çağrıları SQLServer veritabanına kullanır **VSPerfClrEnv /InteractionOn** ortam değişkenlerini ayarlama seçeneği ve **VSPerfClrEnv /InteractionOff** bunları kaldırmak için seçeneği.

Aşağıdaki örnekte, izleme metodunu kullanarak bir Windows Masaüstü uygulama profili ve katman etkileşim verileri toplanır.

### <a name="profile-a-windows-desktop-application-example"></a>Windows masaüstü uygulaması örnek profil

1. Yönetici ayrıcalıklarıyla bir komut istemi penceresi açın. Tıklatın **Başlat**, işaret **tüm programlar**, üzerine gelin ve ardından **Donatılar**. Sağ **komut istemi**ve ardından **yönetici olarak çalıştır**.

2. .NET profili oluşturma ve ipucu ortam değişkenleri başlatır. Aşağıdaki komutları yazın:

    ```cmd
    vsperfclrenv /traceon
    vsperfclrenv /interactionon
    ```

3. Profil Oluşturucu başlatın. Şu komutu yazın:

    ```cmd
    vsperfcmd /start:trace /output:Desktop_tip.vsp 
    ```

4. Uygulama ile VSPerfCmd başlatın. Şu komutu yazın:

    ```cmd
    vsperfcmd /launch:DesktopApp.exe
    ```

5. Profil oluşturma verileri toplamak için uygulama çalışma ve sonra normal şekilde uygulamayı kapatın.

6. İpucu ortam değişkenleri temizleyin. Şu komutu yazın:

    ```cmd
    vsperfclrenv /off
    ```

Daha fazla bilgi için bkz: [bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md).

## <a name="profile-services"></a>Profil Hizmetleri

Dahil olmak üzere profil hizmetlerine [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulamaları, **VSPerfClrEnv /GlobalInteractionOn** ortam değişkenlerini ayarlama seçeneği ve **VSPerfClrEnv /GlobalInteractionOff** bunları kaldırmak için seçeneği.

Ne zaman, profil oluşturma gibi hizmetler [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamaları, genellikle gerekir profil oluşturmayı etkinleştirmek için bilgisayarı yeniden başlatın.

Aşağıdaki örnekte, bir Windows hizmeti izleme metodunu kullanarak profili ve katman etkileşim verileri toplanır.

### <a name="profile-a-windows-service-example"></a>Profil bir Windows hizmeti örneği

1. Gerekirse, hizmetini yükleyin.

2. Yönetici ayrıcalıklarıyla bir komut istemi penceresi açın. Tıklatın **Başlat**, işaret **tüm programlar**, üzerine gelin ve ardından **Donatılar**. Sağ **komut istemi**ve ardından **yönetici olarak çalıştır**.

3. Ortam değişkenleri profil .NET başlatır. Şu komutu yazın:

    ```cmd
    vsperfclrenv /globaltraceon
    ```

4. İpucu ortam değişkenleri başlatır. Şu komutu yazın:

    ```cmd
    vsperfclrenv /globalinteractionon
    ```

5. Ortam değişkenleri kaydetmek için bilgisayarı yeniden başlatın.

6. Yönetici ayrıcalıklarıyla bir komut istemi penceresi açın.

7. Profil Oluşturucu başlatın. Şu komutu yazın:

    ```cmd
    vsperfcmd /start:trace /output:MiddleTier_tip.vsp /user:SYSTEM /crosssession 
    ```

8. Gerekirse, hizmeti başlatın.

9. Hizmete profil oluşturucu ekleme. Şu komutu yazın:

    ```cmd
    vsperfcmd /attach:MiddleTier.exe /output:MyService_tip.vsp /user:SYSTEM /crosssession 
    ```

10. Hizmet çalışma ve profil oluşturma verileri toplar.

11. Profil Oluşturucu durdurun. Şu komutu yazın:

     `vsperfcmd /detach`

12. .NET ve ortam değişkenleri profil ipucu temizleyin. Şu komutu yazın:

    ```cmd
    vsperfclrenv /globaloff
    ```

13. Temizlenmiş ortam değişkenleri kaydetmek için bilgisayarı yeniden başlatın.

Daha fazla bilgi için aşağıdaki konulardan birine bakın:

[ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)

[Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)

## <a name="add-tier-interaction-data-with-vsperfaspnetcmd"></a>VSPerfASPNETCmd ile Katman etkileşim verileri ekleme

VSPerfASPNETCmd komut satırı aracı kolayca profiline sağlar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulamaları. İle karşılaştırılan **VSPerfCmd** komut satırı aracı seçenekleri azaltılmış, ortam değişkenleri ayarlanması gerekir ve bilgisayar yeniden başlatıldığı gerekli değildir. VSPerfASPNETCmd bu özelliklerini katman etkileşim verileri toplama olağanüstü kolay hale getirir.

Katman etkileşimli profil oluşturma verilerini VSPerfASPNETCmd kullanılarak toplanan eklemek için Ekle **/İpucu** komut satırı seçeneği. Örneğin, katman etkileşim verileri toplamak için aşağıdaki komut satırını kullanın bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması izleme metodunu kullanarak:

```cmd
vsperfaspnetcmd /tip /trace http://localhost/MyWebApp
```

VSPerfASPNETCmd hakkında daha fazla bilgi için bkz: [VSPerfASPNETCmd ile Hızlı Web sitesi profil](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).