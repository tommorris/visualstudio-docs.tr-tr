---
title: Günlükleri MSBuild ile derleme edinme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, logging
- logging [MSBuild]
ms.assetid: 6ba9a754-9cc0-4fed-9fc8-4dcd3926a031
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c6953017a034257900c467e7f2fac89897fa0d9e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31574691"
---
# <a name="obtaining-build-logs-with-msbuild"></a>MSBuild ile Derleme Günlükleri Alma
MSBuild ile anahtarlarını kullanarak gözden geçirme ve yapı verileri için bir veya daha fazla kaydetmek isteyip istemediğinizi istediğiniz yapı veri miktarını belirtebilirsiniz. Yapılandırma verilerini toplamak için özel bir Günlükçü de belirtebilirsiniz. Bu konuda kapsamıyordur MSBuild komut satırı anahtarları hakkında daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  
  
> [!NOTE]
>  Visual Studio IDE kullanarak projeleri oluşturmak, yapı günlükleri gözden geçirerek bu derlemeleri giderebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: görünümü, kaydetme ve yapı günlük dosyalarını Yapılandır](../ide/how-to-view-save-and-configure-build-log-files.md).  
  
## <a name="setting-the-level-of-detail"></a>Ayrıntı düzeyini ayarlama  
 Ayrıntı düzeyini belirtmeden MSBuild kullanarak bir projeyi derlerken çıkış günlüğünde aşağıdaki bilgiler görüntülenir:  
  
-   Hataları, uyarıları ve yüksek oranda önemli olarak sınıflandırılır iletileri.  
  
-   Bazı durum olayları.  
  
-   Yapı Özeti.  
  
 Kullanarak **/verbosity** (**/v**) geçiş, ne kadar veri çıktı görünür kontrol edebilirsiniz. Sorun giderme amacıyla ya da bir ayrıntı düzeyi kullanmak `detailed` (`d`) veya `diagnostic` (`diag`), en çok bilgi sağlar.  
  
 Ayarladığınız zaman oluşturma işlemi daha yavaş olabilir **/verbosity** için `detailed` ve hatta daha yavaş ayarladığınızda **/verbosity** için `diagnostic`.  
  
```  
msbuild MyProject.proj /t:go /v:diag  
```  

## <a name="saving-the-build-log-to-a-file"></a>Derleme günlüğünü bir dosyaya kaydetme  
 Kullanabileceğiniz **/fileLogger** (**fl**) anahtar yapılandırma verilerini bir dosyaya kaydedin. Aşağıdaki örnek yapılandırma verilerini adlı bir dosyaya kaydeder. `msbuild.log`.  
  
```  
msbuild MyProject.proj /t:go /fileLogger  
```  
  
 Aşağıdaki örnekte, günlük dosyasının adı `MyProjectOutput.log`, ve günlük çıktısı ayrıntı düzeyini ayarlamak `diagnostic`. Bu iki ayar kullanarak belirtin **/filelogparameters** (`flp`) geçin.  
  
```  
msbuild MyProject.proj /t:go /fl /flp:logfile=MyProjectOutput.log;verbosity=diagnostic  
```  
  
 Daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="saving-the-log-output-to-multiple-files"></a>Günlük çıktısını birden çok dosyaya kaydetme  
 Aşağıdaki örnek tüm günlüğüne kaydeder `msbuild1.log`, hataları için `JustErrors.log`ve yeni uyarılar için `JustWarnings.log`. Örnek dosya numaraları üç dosyaların her biri için kullanır. Dosya numaraları hemen sonra belirtilen **/fl** ve **/flp** anahtarları (örneğin, `/fl1` ve `/flp1`).  
  
 **/Filelogparameters** (`flp`) için 2 ve 3 dosyaları ne her dosya adı ve her dosyasına eklenecek gerekenler belirtin geçer. Ad böylece 1 ' dosyası için belirtilen varsayılan adını `msbuild1.log` kullanılır.  
  
```  
msbuild MyProject.proj /t:go /fl1 /fl2 /fl3 /flp2:logfile=JustErrors.log;errorsonly /flp3:logfile=JustWarnings.log;warningsonly  
  
```  
  
 Daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  

## <a name="saving-a-binary-log"></a>İkili günlük kaydetme

Sıkıştırılmış, ikili biçim kullanılarak günlüğe kaydedebilirsiniz **/binaryLogger** (**bl'yi denetlemeye**) geçin. Bu günlük oluşturma işleminin ayrıntılı açıklamasını içerir ve belirli günlük analiz araçları tarafından okunabilir.

Aşağıdaki örnekte, bir ikili günlük dosyası adı ile oluşturulan `binarylogfilename`.

```  
/bl:binarylogfilename.binlog
``` 
 
Daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  

## <a name="using-a-custom-logger"></a>Özel bir günlükçü kullanma  
 Arabirimini uygulayan bir yönetilen türü yazarak kendi Günlükçü yazabilirsiniz <xref:Microsoft.Build.Framework.ILogger> arabirimi. Derleme hataları e-postayla göndermek, bir veritabanına oturum veya bir XML dosyasına oturum için özel bir Günlükçü örneği için kullanabilirsiniz. Daha fazla bilgi için bkz: [Günlükçüleri derleme](../msbuild/build-loggers.md).  
  
 MSBuild komut satırında, özel Günlükçü kullanarak belirttiğiniz **/logger** geçin. Aynı zamanda **/noconsolelogger** varsayılan konsol Günlükçü devre dışı bırakmak için anahtar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.Build.Framework.LoggerVerbosity>   
 [Günlükçüleri derleme](../msbuild/build-loggers.md)   
 [Birden çok işlemcili ortamda oturum açma](../msbuild/logging-in-a-multi-processor-environment.md)   
 [İletme Günlükçüleri oluşturma](../msbuild/creating-forwarding-loggers.md)   
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)