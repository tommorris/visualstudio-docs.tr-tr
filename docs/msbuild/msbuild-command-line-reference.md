---
title: MSBuild komut satırı başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, msbuild.exe
- MSBuild, command line reference
- msbuild.exe
ms.assetid: edaa65ec-ab8a-42a1-84cb-d76d5b2f4584
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ceecae39a04182b456c3b49d92c69a10297781bc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-command-line-reference"></a>MSBuild Komut Satırı Başvurusu
Bir proje veya çözüm dosyası oluşturmak için MSBuild.exe kullandığınızda, işlemi çeşitli yönlerini belirlemek için birkaç anahtar ekleyebilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
MSBuild.exe [Switches] [ProjectFile]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Bağımsız Değişken|Açıklama|  
|--------------|-----------------|  
|`ProjectFile`|Proje dosyasında belirttiğiniz hedefleri oluşturur. MSBuild proje dosyası belirtmezseniz, geçerli çalışma dizini "proj içinde" sona erer ve bu dosyayı kullanan bir dosya adı uzantısı için arar. Bu bağımsız değişken için bir Visual Studio çözümü dosyası da belirtebilirsiniz.|  
  
## <a name="switches"></a>Anahtarlar  
  
|Anahtar|Kısa biçim|Açıklama|  
|------------|----------------|-----------------|  
|/help|/? veya /h|Kullanım bilgilerini görüntüler. Aşağıdaki komutu bir örnek verilmiştir:<br /><br /> `msbuild.exe /?`|  
|/detailedsummary|/DS|Derleme günlüğünde sonunda oluşturulan yapılandırmaları ve bunlar düğümlere nasıl zamanlanmış hakkında ayrıntılı bilgi gösterir.|  
|/ignoreprojectextensions: `extensions`|/ Yoksay: `extensions`|Belirtilen uzantılara oluşturmak için hangi proje dosyası belirlerken yoksay. Aşağıdaki örnekte gösterildiği gibi birden çok uzantı ayırmak için noktalı virgül veya virgül kullanın:<br /><br /> `/ignoreprojectextensions:.vcproj,.sln`|  
|/maxcpucount [:`number`]|/m [:`number`]|Eş zamanlı işlemler oluştururken kullanılacak en fazla sayısını belirtir. Bu anahtar eklemezseniz, varsayılan değer 1'dir. Bu anahtarı bir değer belirtmeden eklerseniz, MSBuild bilgisayar işlemci sayısı için kullanacağı. Daha fazla bilgi için bkz: [yapı paralel olarak birden çok proje](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).<br /><br /> Aşağıdaki örnek, aynı anda oluşturmak üç projeleri sağlayan üç MSBuild işlemleri kullanarak oluşturmak için MSBuild bildirir:<br /><br /> `msbuild myproject.proj /maxcpucount:3`|  
|/ noautoresponse|/noautorsp|Tüm MSBuild.rsp dosyaları otomatik olarak dahil etmeyin.|  
|/nodeReuse:`value`|/nr:`value`|Etkinleştirmek veya yeniden kullanımını MSBuild düğümleri devre dışı. Aşağıdaki değerleri belirtebilirsiniz:<br /><br /> -   **Doğru**. Böylece sonraki yapılar (varsayılan) kullanabilmek için yapı tamamlandıktan sonra düğümleri kalır.<br />-   **Yanlış**. Düğüm oluşturma tamamlandıktan sonra kalır yok.<br /><br /> Bir düğüm yürütüyor bir projeye karşılık gelir. Dahil ederseniz **/maxcpucount** anahtarı, birden çok düğümün aynı anda yürütebilir.|  
|/nologo||Başlangıç başlığını veya telif hakkı iletisi görüntülemiyor.|  
|<a name="preprocess"></a> / önişle [:`filepath`]|/PP [:`filepath`]|Tarafından toplanan, tek proje dosyası oluşturma satır içi kullanım tüm işaretlenmiş sınırlarının sahip bir derleme sırasında aktarılacak dosyalar. Dosyaların nerede içeri ve hangi dosyaların yapı katkıda, hangi dosyaların içe daha kolay belirlemek için bu anahtarı kullanabilirsiniz. Bu anahtarı kullandığınızda, proje yerleşik değil.<br /><br /> Belirtirseniz bir `filepath`, çıktı dosyasına toplanmış proje dosyasıdır. Aksi takdirde, çıktı konsol penceresinde görünür.<br /><br /> Nasıl kullanılacağı hakkında bilgi için `Import` öğesi bir proje dosyası başka bir proje dosyasına eklemek için bkz: [içeri aktarma öğesi (MSBuild)](../msbuild/import-element-msbuild.md) ve [nasıl yapılır: birden çok proje dosyasında aynı hedefi kullanma](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md).|  
|/Property:`name`=`value`|p:`name`=`value`|Ayarlama veya belirtilen proje düzeyi özelliklerini geçersiz kılmak nerede `name` özellik adı ve `value` özellik değeri. Her bir özellik ayrı ayrı belirtin veya aşağıdaki örnekte gösterildiği gibi birden çok özellik ayırmak için noktalı virgül veya nokta kullanın:<br /><br /> `/property:WarningLevel=2;OutDir=bin\Debug`|  
|/ target:`targets`|/ t:`targets`|Projede belirtilen hedefleri oluşturun. Her hedef ayrı ayrı belirtin veya aşağıdaki örnekte gösterildiği gibi birden çok hedef ayırmak için noktalı virgül veya nokta kullanın:<br /><br /> `/target:Resources;Compile`<br /><br /> Bu anahtarı kullanarak tüm hedefleri belirtirseniz, tüm hedefleri yerine çalıştıkları `DefaultTargets` proje dosyasında özniteliği. Daha fazla bilgi için bkz: [hedef derleme sırası](../msbuild/target-build-order.md) ve [nasıl yapılır: belirtin, hedef yapı ilk](../msbuild/how-to-specify-which-target-to-build-first.md).<br /><br /> Bir hedef görevler grubudur. Daha fazla bilgi için bkz: [hedefleri](../msbuild/msbuild-targets.md).|  
|/toolsversion:`version`|/TV:`version`|Aşağıdaki örnekte gösterildiği gibi projeyi oluşturmak için kullanılacak araç takımı sürümünü belirtir: `/toolsversion:3.5`<br /><br /> Bu anahtarı kullanarak, bir projeyi oluşturun ve belirtilen sürümden farklı bir sürüm belirtin [proje öğesi (MSBuild)](../msbuild/project-element-msbuild.md). Daha fazla bilgi için bkz: [ToolsVersion ayarlarını geçersiz kılma](../msbuild/overriding-toolsversion-settings.md).<br /><br /> MSBuild 4.5 için için aşağıdaki değerleri belirtebilirsiniz `version`: 2.0, 3.5 ve 4.0. 4.0 belirtirseniz `VisualStudioVersion` yapı özelliği kullanmak için hangi alt toolset belirtir. Daha fazla bilgi için alt toolsets bölümüne bakın [araç takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).<br /><br /> Bir araç takımı, görevler, hedefler ve bir uygulama oluşturmak için kullanılan araçlar oluşur. Csc.exe ve vbc.exe gibi derleyicileri araçları içerir. Toolsets hakkında daha fazla bilgi için bkz: [araç takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md), [standart ve özel araç takımı yapılandırmaları](../msbuild/standard-and-custom-toolset-configurations.md), ve [çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md). **Not:** araç takımının sürüm üzerinde bir proje oluşturulan çalıştırmak için .NET Framework sürümü hedef çerçeve olarak aynı değildir. Daha fazla bilgi için bkz: [hedef çerçeve ve hedef Platform](../msbuild/msbuild-target-framework-and-target-platform.md).|  
|/ doğrulanamıyor: [`schema`]|/VAL [`schema`]|Proje dosyası doğrulayın ve doğrulama başarılı olursa, projeyi oluşturun.<br /><br /> Belirtmediyseniz `schema`, projenin varsayılan şemasına göre doğrulanır.<br /><br /> Belirtirseniz `schema`, proje belirttiğiniz şemasına göre doğrulanır.<br /><br /> Aşağıdaki ayar bir örnek verilmiştir: `/validate:MyExtendedBuildSchema.xsd`|  
|/verbosity:`level`|/v:`level`|Derleme günlüğünde görüntülemek için bilgi miktarını belirtir. Her Günlükçü bu Günlükçü için ayarladığınız ayrıntı düzeyi dayalı olayları görüntüler.<br /><br /> Aşağıdaki ayrıntı düzeylerinden belirtebilirsiniz: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.<br /><br /> Aşağıdaki ayar bir örnek verilmiştir: `/verbosity:quiet`|  
|/ VERSION|/ ver|Yalnızca sürüm bilgilerini görüntüleyin. Proje yerleşik değil.|  
|@`file`||Komut satırı anahtarları bir metin dosyasından ekleyin. Birden fazla dosya varsa, bunları ayrı olarak belirtin. Daha fazla bilgi için bkz: [yanıt dosyaları](../msbuild/msbuild-response-files.md).|  
  
### <a name="switches-for-loggers"></a>Günlükçüler için anahtarlar  
  
|Anahtar|Kısa biçim|Açıklama|  
|------------|----------------|-----------------|  
|/consoleloggerparameters:<br /><br /> `parameters`|/clp:`parameters`|Derleme bilgileri konsol penceresinde görüntüler konsol Günlükçü için belirttiğiniz parametreleri geçirin. Aşağıdaki parametreleri belirtebilirsiniz:<br /><br /> -   **PerformanceSummary**. Görevler, hedefler ve projeleri harcanan zamanı gösterir.<br />-   **Özet**. Hata ve uyarı özetini sona erdiğinde gösterir.<br />-   **NoSummary**. Hata ve uyarı özetini sona erdiğinde gösterme.<br />-   **ErrorsOnly**. Yalnızca hataları göster.<br />-   **WarningsOnly**. Yalnızca uyarıları göster.<br />-   **NoItemAndPropertyList**. Öğeleri ve ayrıntı düzeyi ayarlanırsa, her bir proje derlemesi başlangıcında görüneceği özellikler listesini gösterme `diagnostic`.<br />-   **ShowCommandLine**. Göster `TaskCommandLineEvent` iletileri.<br />-   **ShowTimestamp**. Herhangi bir iletisi öneki olarak zaman damgasını gösterir.<br />-   **ShowEventId**. Olay Kimliği her başlatıldı olayı, tamamlanan olay ve iletinizi için gösterir.<br />-   **ForceNoAlign**. Konsol arabellek boyutu için metni hizalama yok.<br />-   **DisableConsoleColor**. Varsayılan konsol renkleri tüm günlük iletilerini için kullanın.<br />-   **DisableMPLogging**. Çıktı çok işlemcili günlük stilini çok işlemcili olmayan modda çalışırken devre dışı bırakın.<br />-   **EnableMPLogging**. Çok işlemcili günlük stilini bile çok işlemcili olmayan modda çalışırken etkinleştirin. Bu günlük stili varsayılan olarak açıktır.<br />-   **Ayrıntı**. Geçersiz kılma **/verbosity** bu Günlükçü için ayarlama.<br /><br /> Aşağıdaki örnekte gösterildiği gibi birden çok parametre ayırmak için noktalı virgül veya nokta kullanın:<br /><br /> `/consoleloggerparameters:PerformanceSummary;NoSummary /verbosity:minimal`|  
|/distributedFileLogger|/dfl|Derleme çıktı her MSBuild düğümün kendi dosyasına kaydedin. İlk konum bu dosyalar için geçerli dizin değil. Varsayılan olarak, dosya adında "MSBuild*nodeId*.log". Kullanabileceğiniz **/fileLoggerParameters** anahtar dosyaları ve diğer parametreleri fileLogger için konumu belirtin.<br /><br /> Kullanarak bir günlük dosyası adı **/fileLoggerParameters** anahtarı, dağıtılmış Günlükçü kullanır, şablon olarak adlandırın ve her düğüm için bir günlük dosyası oluştururken, bu ada düğüm kimliği ekleyin.|  
|/distributedlogger:<br /><br /> `central logger`*<br /><br /> `forwarding logger`|/DL:`central logger`*`forwarding logger`|Günlük olayları MSBuild, her düğüme farklı Günlükçü örneği ekleniyor. Birden çok günlükçüleri belirtmek için her Günlükçü ayrı olarak belirtin.<br /><br /> Günlükçü sözdizimi Günlükçü belirtmek için kullanın. Günlükçü sözdizimi için bkz: **/logger** aşağıdaki anahtar.<br /><br /> Aşağıdaki örnekler, bu anahtarı kullanmayı gösterir:<br /><br /> `/dl:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`<br /><br /> `/dl:MyLogger,C:\My.dll*ForwardingLogger,C:\Logger.dll`|  
|/fileLogger<br /><br /> *[sayı]*|/fl [`number`]|Derleme çıktı tek bir dosya geçerli dizinde oturum. Belirtmediyseniz `number`, çıktı dosyası msbuild.log olarak adlandırılır. Belirtirseniz `number`, çıktı dosyası msbuild adlı`n`n .log `number`. `Number` 1 ile 9 rakam olabilir.<br /><br /> Kullanabileceğiniz **/fileLoggerParameters** anahtar dosyası için ve diğer parametreleri fileLogger konumunu belirtin.|  
|/fileloggerparameters:[number]<br /><br /> `parameters`|/FLP: [ `number`] `parameters`|Herhangi bir ek parametre dosyası Günlükçü ve dağıtılmış dosya Günlükçü için belirtir. Bu anahtar varlığını gelir karşılık gelen /**filelogger [**`number`**]** anahtarı mevcut değil. `Number` 1 ile 9 rakam olabilir.<br /><br /> İçin listelenen tüm parametreleri kullanabilirsiniz **/consoleloggerparameters**. Ayrıca, bir veya daha fazla şu parametreleri kullanabilirsiniz:<br /><br /> -   **Günlük dosyası**. Derleme günlüğünde üzerine yazılan günlük dosyası yolu. Dağıtılmış dosya Günlükçü günlük dosyalarının adlarını bu yoluna ekler.<br />-   **Append**. Derleme günlüğü günlük dosyasına eklenir veya bu raporun üzerine olup olmadığını belirler. Anahtar ayarladığınızda, derleme günlüğünde günlük dosyasına eklenir. Anahtar mevcut olmadığında, varolan bir günlük dosyasının içeriğini üzerine yazılır.<br />     True veya false, olup ayarlandı olsun Ekle anahtarı eklerseniz günlük eklenir. Append anahtar içermiyorsa, günlük üzerine yazılır.<br />     Bu durumda dosyanın üzerine yazılır: `msbuild myfile.proj /l:FileLogger,Microsoft.Build.Engine;logfile=MyLog.log`<br />     Bu durumda, dosyayı eklenir: `msbuild myfile.proj /l:FileLogger,Microsoft.Build.Engine;logfile=MyLog.log;append=true`<br />     Bu durumda, dosyayı eklenir: `msbuild myfile.proj /l:FileLogger,Microsoft.Build.Engine;logfile=MyLog.log;append=false`<br />-   **Kodlama**. (Örneğin, UTF-8, Unicode ve ASCII) için dosya kodlamasını belirtir.<br /><br /> Aşağıdaki örnek, uyarıları ve hataları için farklı günlük dosyaları oluşturur:<br /><br /> `/flp1:logfile=errors.txt;errorsonly /flp2:logfile=warnings.txt;warningsonly`<br /><br /> Aşağıdaki örnekler diğer olasılıklar gösterir:<br /><br /> `/fileLoggerParameters:LogFile=MyLog.log;Append; Verbosity=diagnostic;Encoding=UTF-8`<br /><br /> `/flp:Summary;Verbosity=minimal;LogFile=msbuild.sum`<br /><br /> `/flp1:warningsonly;logfile=msbuild.wrn`<br /><br /> `/flp2:errorsonly;logfile=msbuild.err`|  
|/binaryLogger [: [günlük dosyası =]`output.binlog`[; ProjectImports = [None, ekleme, ZipFile]]]|/Bl|Sıkıştırılmış bir ikili dosya tüm yapı olayları serileştirir. Varsayılan olarak dosya geçerli dizinde ve adlı `msbuild.binlog`. İkili günlük daha sonra metin günlükleri yeniden oluşturmak için kullanılan ve diğer analiz araçları tarafından kullanılan yapılandırma işlemi ayrıntılı bir açıklaması ' dir. İkili günlük genellikle 10-20 x en ayrıntılı metin tanılama düzeyi günlük küçük, ancak daha fazla bilgi içerir.<br /><br />İkili Günlükçü varsayılan olarak tüm içeri aktarılan projeleri ve hedef dosya derleme sırasında karşılaşılan gibi proje dosyalarını kaynağı metnin toplar. İsteğe bağlı `ProjectImports` anahtarı bu davranışı denetler:<br /><br /> -   **ProjectImports = None**. Proje içeri aktarmalar toplamayız.<br /> -   **ProjectImports = katıştırmak**. Proje içeri aktarmalar günlük dosyasında (varsayılan) ekleyin.<br /> -   **ProjectImports ZipFile =**. Proje dosyalarına Kaydet `output.projectimports.zip` burada `output` ikili günlük dosyası adı adıyla aynı değil.<br /><br />Embed ProjectImports için varsayılan ayardır.<br />**Not**: Günlükçü MSBuild dışındaki kaynak dosyaları gibi toplamaz `.cs`, `.cpp` vs.<br />A `.binlog` dosya "yürütülen geri" geçirerek `msbuild.exe` proje/çözüm yerine bağımsız değişken olarak. Diğer günlükçüleri özgün yapı gerçekleştiği gibi günlük dosyasında yer alan bilgileri alır. Daha fazla bilgiyi ikili günlük ve kendi kullanımları adresindeki hakkında: https://github.com/Microsoft/msbuild/wiki/Binary-Log <br /><br />**Örnekler**:<br /> -   `/bl`<br /> -    `/bl:output.binlog`<br /> -   `/bl:output.binlog;ProjectImports=None`<br /> -   `/bl:output.binlog;ProjectImports=ZipFile`<br /> -   `/bl:..\..\custom.binlog`<br /> -   `/binaryLogger`|
|/Logger:<br /><br /> `logger`|/ l:`logger`|MSBuild olayları günlüğe kaydetmek için Günlükçü belirtir. Birden çok günlükçüleri belirtmek için her Günlükçü ayrı olarak belirtin.<br /><br /> İçin aşağıdaki sözdizimini kullanın `logger`: `[``LoggerClass``,]``LoggerAssembly``[;``LoggerParameters``]`<br /><br /> İçin aşağıdaki sözdizimini kullanın `LoggerClass`: `[``PartialOrFullNamespace``.]``LoggerClassName`<br /><br /> Derleme tam olarak bir Günlükçü içeriyorsa Günlükçü sınıfı belirtmeniz gerekmez.<br /><br /> İçin aşağıdaki sözdizimini kullanın `LoggerAssembly`: `{``AssemblyName``[,``StrongName``] &#124;` `AssemblyFile``}`<br /><br /> Günlükçü parametreler isteğe bağlıdır ve Günlükçü için girdiğiniz tam olarak geçirilir.<br /><br /> Aşağıdaki örneklerde **/logger** geçin.<br /><br /> `/logger:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`<br /><br /> `/logger:XMLLogger,C:\Loggers\MyLogger.dll;OutputAsHTML`|  
|/noconsolelogger|/noconlog|Varsayılan konsol Günlükçü devre dışı bırakın ve olayları konsolda oturum yok.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek derlemeler `rebuild` hedefinin `MyProject.proj` projesi.  
  
```  
MSBuild.exe MyProject.proj /t:rebuild  
```  
  
## <a name="example"></a>Örnek  
 MSBuild.exe, daha karmaşık derlemeleri gerçekleştirmek için kullanabilirsiniz. Örneğin, belirli projelerin bir çözümde belirli hedefler derleme için kullanabilirsiniz. Aşağıdaki örnek projeyi yeniden oluşturur `NotInSolutionFolder` ve projeyi temizler `InSolutionFolder`, içinde olduğu `NewFolder` Çözüm klasörü.  
  
```  
msbuild SlnFolders.sln /t:NotInSolutionfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Yaygın MSBuild Proje Özellikleri](../msbuild/common-msbuild-project-properties.md)
