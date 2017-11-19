---
title: "İzlenecek yol: Komut satırı araçları kullanarak profil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance tools, command-line tools
ms.assetid: 1c6f1586-3d6a-431f-bedf-c54088e280ba
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 54c91b8238b21f214edda0941c0c91fd4bdda8e4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-command-line-profiling-using-instrumentation"></a>İzlenecek yol: İzleme Yöntemini Kullanarak Komut Satırı Profili Oluşturma
Bu kılavuzda profil üzerinden geçen bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ayrıntılı zamanlama toplamak ve profil oluşturma Araçları'nın izleme metodunu kullanarak çağrı sayısı verileri için tek başına uygulama. Bu kılavuzda, aşağıdaki görevleri gerçekleştirmek:  
  
-   Kullanım [Vsınstr](../profiling/vsinstr.md) izleme eklenmiş ikili dosyalar oluşturmak için komut satırı aracı.  
  
-   Kullanım [VSPerfCLREnv](../profiling/vsperfclrenv.md) aracı .NET profil oluşturma verilerini toplamak için ortam değişkenlerini ayarlama.  
  
-   Kullanım [VSPerfCmd](../profiling/vsperfcmd.md) profil oluşturma verileri toplamak için aracı.  
  
-   Kullanım [VSPerfReport](../profiling/vsperfreport.md) profil oluşturma verileri, dosya tabanlı raporlar üretmek için aracı.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)]  
  
-   C# Ara anlama  
  
-   Komut satırı araçları ile çalışma anlama Ara  
  
-   Bir kopyasını [PeopleTrax örneği](../profiling/peopletrax-sample-profiling-tools.md)  
  
-   Profil oluşturma tarafından sağlanan bilgiler ile çalışmak için hata ayıklama sembol bilgileri kullanılabilir olması en iyisidir. Daha fazla bilgi için bkz: [nasıl yapılır: başvuru pencereleri sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md).  
  
## <a name="command-line-profiling-using-the-instrumentation-method"></a>Komut satırı izleme metodunu kullanarak profili oluşturma  
 İzleme profili ikili dosyaları özel yerleşik sürümleri işaretlenmiş modülde işlevlere giriş ve çıkış zamanlama bilgilerini toplamak araştırma işlevler içerir profil bir yöntemdir. Profil oluşturma yöntemi örnekleme daha fazla bozucu olduğundan, büyük bir miktarını yük doğurur. İzleme eklenmiş ikili dosyalar da hata ayıklama veya ikili dosyaları serbest bırakır ve dağıtım için tasarlanmamıştır büyüktür.  
  
> [!NOTE]
>  İzleme eklenmiş ikili dosyalar müşterilerinize göndermeyin. İzleme eklenmiş ikili dosyalar çeşitli riskleri içerebilir. İkili dosyaları ters mühendislik, yanı sıra güvenlik riskleri uygulamanızı kolaylaştırır bilgileri içerir.  
  
#### <a name="to-profile-the-peopletrax-application-by-using-the-instrumentation-method"></a>İzleme metodunu kullanarak PeopleTrax uygulama profiline  
  
1.  PeopleTrax örneği uygulama yüklemek ve yayın sürümü oluşturun.  
  
2.  Bir komut istemi penceresi açın ve eklemek **profil oluşturma araçları** yerel yol ortam değişkenine dizin.  
  
3.  Çalışma dizini PeopleTrax ikili dosyaları içeren dizini değiştirin.  
  
4.  Dosya tabanlı raporları içeren bir dizin oluşturun. Şu komutu yazın:  
  
    ```  
    md Reports  
    ```  
  
5.  İkili dosyaları uygulamadaki işaretlemesini Vsınstr komut satırı aracını kullanın. Ayrı komut satırlarında aşağıdaki komutları yazın:  
  
    ```  
    VSInstr PeopleTrax.exe  
    VSInstr PeopleTrax.exe  
    VSInstr People.dll  
    VSInstr Person.dll  
    VSInstr Operation.dll  
    ```  
  
     **Not** varsayılan olarak, özgün dosya izlenmiş olmayan bir yedeğini Vsınstr kaydeder. Yedek dosya adı uzantısına sahip. orig. Örneğin, "MyApp.exe" özgün sürümü "MyApp.exe.orig" kaydedilecektir  
  
6.  Uygun ortam değişkenlerini ayarlamak için aşağıdaki komutu yazın:  
  
    ```  
    VsPerfCLREnv /traceon  
    ```  
  
7.  Profil Oluşturucu başlatmak için aşağıdaki komutu yazın:  
  
    ```  
    VsPerfCmd /start:trace /output:Reports\Report.vsp  
    ```  
  
8.  Profil Oluşturucu izleme modunda başlattıktan sonra verileri toplamak için PeopleTrax.exe işlem Araçlı sürümünü çalıştırın.  
  
     **PeopleTrax** uygulama penceresi görünür.  
  
9. Tıklatın **alma kişiler**.  
  
     PeopleTrax veri kılavuzu verileri ile doldurur.  
  
10. Tıklatın **dışarı veri**.  
  
     Not Defteri başlatılır ve kişilerden listesini içeren yeni bir dosya görüntüler **PeopleTrax** uygulama.  
  
11. Not Defteri'ni kapatın ve sonra kapatın **PeopleTrax** uygulama.  
  
12. Profil Oluşturucu kapatın. Şu komutu yazın:  
  
    ```  
    VSPerfCmd /shutdown  
    ```  
  
13. Ortam değişkenleri sıfırlamak için aşağıdaki komutu yazın:  
  
    ```  
    VSPerfCLREnv /off  
    ```  
  
14. VSPerfReport aracı oluşturmak için veya virgülle ayrılmış değer (.csv) raporu dosyalarını kullanın. Tür:  
  
    ```  
    VSPerfReport Reports\Report.vsp /output:Reports /summary:all  
    ```  
  
     Bir elektronik tablo programında oluşturulan raporları çözümleyebilir veya kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Report.vsp dosyasında profil oluşturma verileri çözümlemek için IDE. Daha fazla bilgi için bkz: [performans araçları verilerini analiz etme](../profiling/analyzing-performance-tools-data.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumuna genel bakış](../profiling/performance-session-overview.md)   
 [Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)   
 [Performans rapor görünümleri](../profiling/performance-report-views.md)