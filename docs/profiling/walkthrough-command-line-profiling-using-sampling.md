---
title: 'İzlenecek yol: Örnekleme kullanarak komut satırı profili oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance tools, command-line tools
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 76f843133a31dd62129bb45e58337ca4a612cc01
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="walkthrough-command-line-profiling-using-sampling"></a>İzlenecek yol: Örnekleme Yöntemini Kullanarak Komut Satırı Profili Oluşturma

Bu kılavuz, bir uygulama komut satırı araçlarını kullanarak ve performans sorunlarını tanımlamak için örnekleme profili gösterilmiştir.

Bu kılavuzda, komut satırı araçlarını kullanarak bir yönetilen uygulama profili oluşturma işlemi adım adım ve örnekleme yalıtmak ve uygulamada performans sorunlarını belirlemek için kullanın.

Bu kılavuzda, şu adımları izler:

- Komut satırı araçlarını kullanma ve örnekleme tarafından bir uygulama profili.
- Bulun ve performans sorunlarını düzeltmek için örneklenen profil oluşturma sonuçlarını çözümleyin.

## <a name="prerequisites"></a>Önkoşullar

- Ara anlayış [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)]
- Komut satırı araçları ile çalışma anlama Ara
- Bir kopyasını [PeopleTrax örneği](../profiling/peopletrax-sample-profiling-tools.md)
- Profil oluşturma tarafından sağlanan bilgiler ile çalışmak için hata ayıklama sembol bilgileri kullanılabilir olması en iyisidir.

## <a name="command-line-profiling-using-the-sampling-method"></a>Komut satırı örnekleme yöntemini kullanarak profil oluşturma

Örnekleme olarak belirli bir işlemi düzenli aralıklarla etkin işlevi belirlemek için sorgulanan profil bir yöntemdir. Sonuçta elde edilen veri işlem örneklenen olduğunda ne sıklıkta işlevi üstünde çağrı yığını olan sayısına sağlar.

> [!NOTE]
> Profil Oluşturma Araçlarının komut satırı araçları, Visual Studio yükleme dizini altındaki \Team Tools\Performance Tools alt dizininde yer alır. 64 bit bilgisayarlarda, araçların 64-bit ve 32 bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçları kullanmak için komut istemi penceresini PATH ortam değişkenine yolu ekleyin veya komutuna ekleyin. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). PeopleTrax 32-bit uygulamadır.

### <a name="to-profile-the-peopletrax-application-by-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak PeopleTrax uygulama profiline

1. PeopleTrax örneği uygulama yüklemek ve uygulama sürümü oluşturun.

2. Bir komut istemi penceresi açın ve profil oluşturma araçları dizinine yerel yol ortam değişkenine ekleyin.

3. Çalışma dizini PeopleTrax ikili dosyaları içeren dizine geçin.

4. Uygun ortam değişkenlerini ayarlamak için aşağıdaki komutu yazın:

    ```cmd
    VSPerfCLREnv /sampleon
    ```

5. Profil Oluşturucu denetleyen komut satırı aracıdır VSPerfCmd.exe çalıştırarak başla Aşağıdaki komut uygulama ve profil oluşturucu örnekleme modunda başlatır:

    ```cmd
    VsPerfCmd /start:sample /output:PeopleTraxReport.vsp /launch:PeopleTrax.exe
    ```

     Profil Oluşturucu işlemi başlatır ve PeopleTrax.exe işleme ekler. Rapor dosyası için toplanan profil oluşturma veri yazmak profil oluşturucu işlemi başlatır.

6. Tıklatın **alma kişiler**.

7. Tıklatın **ExportData**.

     Not Defteri'nde açılır ve dışarı aktarılan verileri içeren yeni bir dosya görüntüler **PeopleTrax**.

8. Not Defteri'ni kapatın ve sonra kapatın **PeopleTrax** uygulama.

9. Profil Oluşturucu kapatın. Şu komutu yazın:

    ```cmd
    VSPerfCmd /shutdown
    ```

10. Ortam değişkenleri sıfırlamak için aşağıdaki komutu kullanın:

    ```cmd
    VSPerfCLREnv /sampleoff
    ```

11. Profil oluşturma verilerini the.vsp dosyasında depolanan aşağıdaki yöntemlerden birini kullanarak sonuçları çözümleyebilirsiniz:

    - Visual Studio IDE içinde the.Vsp dosyasını açın.

         — veya —

    - VSPerfReport.exe komut satırı aracını kullanarak bir virgülle ayrılmış değer (.csv) dosyası oluşturun. Dışında kullanmak için raporlar üretmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE aşağıdaki komutu kullanın:

        ```cmd
        VSPerfReport <dir> PeopleTraxReport.vsp /output:<dir> /summary:all
        ```

## <a name="see-also"></a>Ayrıca Bkz.

[Performans oturumuna genel bakış](../profiling/performance-session-overview.md)  
[Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)  
[VSPerfCmd](../profiling/vsperfcmd.md)  
[Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)  
[Performans Raporu Görünümleri](../profiling/performance-report-views.md)