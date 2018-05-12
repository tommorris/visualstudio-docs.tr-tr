---
title: Vsınstr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, instrumentation
- instrumentation, VSInstr tool
- profiling tools,VSInstr
- command-line tools, instrumentation
- command line, tools
- VSInstr
- VSInstr tool
- performance tools, VSInstr tool
ms.assetid: 7b1334f7-f9b0-4a82-a145-d0607bfa8467
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 57f2857dc8a8bddcf3ea785abfe0b3a7aec806e9
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="vsinstr"></a>VSInstr
Vsınstr aracı ikili dosyalarını izlemek için kullanılır. Aşağıdaki sözdizimini kullanarak çağrılır:  
  
```cmd  
VSInstr [/U] filename [/options]  
```  
  
 Vsınstr aracı seçenekleri aşağıdaki tabloda açıklanmaktadır:  
  
|Seçenekler|Açıklama|  
|-------------|-----------------|  
|**Yardım** veya **?**|Yardımı görüntüler.|  
|**U**|Yeniden yönlendirilen konsol çıktısı Unicode olarak yazar. Belirtilen ilk seçenek olmalıdır.|  
|`@filename`|Satır başına bir komut seçeneği içeren bir yanıt dosyası adını belirtir.  Tırnak işaretleri kullanmayın.|  
|**OutputPath** `:path`|İzleme eklenmiş görüntü için hedef dizinini belirtir. Bir çıkış yolu belirtilmezse, özgün ikili aynı dizinde dosya adı "Orig" ekleyerek adlandırılır ve ikili bir kopyasını işaretlenir.|  
|**Hariç tutma** `:funcspec`|Araçları tarafından araştırmalar dışlanacak işlevi belirtimi belirtir. Bir işlevdeki araştırma ekleme profil öngörülemeyen ya da istenmeyen sonuçları neden olduğunda yararlı olacaktır.<br /><br /> Kullanmayın **hariç** ve **INCLUDE** aynı ikili işlevlerde başvurmak seçenekleri.<br /><br /> Birden çok işlev belirtimi ayrı belirtebilirsiniz **hariç** seçenekleri.<br /><br /> `funcspec` tanımlanan gibidir:<br /><br /> [ad alanı\<separator1 >] [sınıfı\<separator2 >] işlevi<br /><br /> \<separator1 > olan `::` yerel kod için ve `.` yönetilen kod için.<br /><br /> \<separator2 > her zaman `::`<br /><br /> **Dışlama** kod kapsamı ile desteklenir.<br /><br /> Joker karakter \* desteklenir. Örneğin, bir ad alanı kullanım uygulamasında tüm işlevleri dışlamak için şunu yazın:<br /><br /> MyNamespace::\*<br /><br /> Kullanabileceğiniz **Vsınstr /DumpFuncs** belirtilen ikili işlevlerin tam adlarını listelemek için.|  
|**İçerir** `:funcspec`|Bir işlev belirtimi gereç bir ikili araştırmalara sahip belirtir. Tüm ikili dosyaları işlevlerde işaretlendiğine değil.<br /><br /> Birden çok işlev belirtimleri ayrı belirtebilirsiniz **INCLUDE** seçenekleri.<br /><br /> Kullanmayın **INCLUDE** ve **hariç** aynı ikili işlevlerde başvurmak seçenekleri.<br /><br /> **Dahil** kod kapsamı ile desteklenmiyor.<br /><br /> `funcspec` tanımlanan gibidir:<br /><br /> [ad alanı\<separator1 >] [sınıfı\<separator2 >] işlevi<br /><br /> \<separator1 > olan `::` yerel kod için ve `.` yönetilen kod için.<br /><br /> \<separator2 > her zaman `::`<br /><br /> Joker karakter \* desteklenir. Örneğin, bir ad alanı kullanımda tüm işlevler eklemek için şunu yazın:<br /><br /> MyNamespace::\*<br /><br /> Kullanabileceğiniz **Vsınstr /DumpFuncs** belirtilen ikili işlevlerin tam adlarını listelemek için.|  
|**DumpFuncs**|Belirtilen görüntü işlevlerinde listeler. Hiçbir araçları gerçekleştirilir.|  
|**ExcludeSmallFuncs**|İzlemeden herhangi bir işlev çağrıları yapma kısa işlevleri küçük işlevleri dışlar. **ExcludeSmallFuncs** seçeneği, böylece geliştirilmiş araçları hızı araçları tarafından yükü daha azdır için sağlar.<br /><br /> Kısa işlevleri dışlama .vsp dosya boyutu ve çözümleme için gereken süre de azaltır.|  
|**İşareti:**{**önce**`&#124;`**sonra**`&#124;`**üst**`&#124;`**alt**}`,funcname,markid`|Bir profil işareti (raporlardaki verileri sınırlandırmak için kullanılan tanımlayıcı) ekler başlangıç veya bitiş .vsp rapor dosyasındaki veri aralığı tanımlamak için kullanabilirsiniz.<br /><br /> **Önce** - hedef işlev girdisi hemen önce.<br /><br /> **Sonra** - hedef işlevi çıkış hemen sonra.<br /><br /> **Üst** - hedef işlev girdisi hemen sonra.<br /><br /> **Alt** - hedef işlevinde her return hemen önce.<br /><br /> `funcname` -Hedef işlevin adı<br /><br /> `Markid` -Profil işareti tanımlayıcı olarak kullanılacak pozitif bir tamsayı (uzun).|  
|**Kapsamı**|Kapsama aracı gerçekleştirir. Yalnızca aşağıdaki seçenekler kullanılabilir olabilir: **ayrıntılı**, **OutputPath**, **hariç**, ve **günlük dosyası**...|  
|**Ayrıntılı**|**Ayrıntılı**seçeneği izleme işlemi hakkında ayrıntılı bilgi görüntülemek için kullanılır.|  
|**NoWarn** `[:[Message Number[;Message Number]]]`|Tüm gizlemek veya belirli uyarılar.<br /><br /> `Message Number` -uyarı sayısı. Varsa `Message Number` olan atlanırsa, tüm uyarıları görüntülenmez.<br /><br /> Daha fazla bilgi için bkz: [Vsınstr uyarıları](../profiling/vsinstr-warnings.md).|  
|**Denetim** `:{` **iş parçacığı** `&#124;` **işlem** `&#124;` **genel** `}`|Aşağıdaki Vsınstr veri toplama profil düzeyini belirtir seçeneklerini denetleme:<br /><br /> **Start**<br /><br /> **StartOnly**<br /><br /> **Askıya alma**<br /><br /> **StopOnly**<br /><br /> **SuspendOnly**<br /><br /> **ResumeOnly**<br /><br /> **İş parçacığı** -iş parçacığı düzeyinde veri toplama denetimi işlevleri belirtir. Profil oluşturma başlatılır ya da yalnızca geçerli iş parçacığı için durdurulur. Profil oluşturma durumu başka bir iş parçacığı etkilenmez. İş parçacığı varsayılandır.<br /><br /> **İşlem** -işlem düzeyinde profil oluşturma veri toplama denetimi işlevleri belirtir. Profil oluşturma başlatır veya geçerli işlemdeki tüm iş parçacıklarının durdurur. Diğer işlemlerin profil oluşturma durumu etkilenmez.<br /><br /> **Genel** -genel düzeyde (çapraz işlem) veri toplama denetimi işlevleri belirtir.<br /><br /> Profil oluşturma düzeyi belirtmezseniz, bir hata oluşur.|  
|**Başlat** `:{` **içinde** `&#124;` **dışında** `},funcname`|Bu işlev tarafından çağrılan alt işlevleri ve hedef işlevi için veri toplama sınırlar.<br /><br /> **İçinde** -hedef işlevi girişe hemen sonra StartProfile işlevi ekler. Her return hemen önce StopProfile işlevi hedef işlevi ekler.<br /><br /> **Dış** -her hedef işlevi çağrısı hemen önce StartProfile işlevi ekler. Her hedef işlevi çağrısı hemen sonra StopProfile işlevi ekler.<br /><br /> `funcname` -Hedef işlevin adı.|  
|**Askıya alma** `:{` **içinde** `&#124;` **dışında** `},funcname`|Hedef işlev ve işlev tarafından çağrılan alt işlevleri için veri toplama dışlar.<br /><br /> **İçinde** -hedef işlevi girişe hemen sonra SuspendProfile işlevi ekler. Her return hemen önce ResumeProfile işlevi hedef işlevi ekler.<br /><br /> **Dış** -hedef işlevi girişe hemen önce SuspendProfile işlevi ekler. Hedef işlevden çıkış hemen sonra ResumeProfile işlevi ekler.<br /><br /> `funcname` -Hedef işlevinin adı.<br /><br /> Hedef işlevi StartProfile işlevi içeriyorsa, SuspendProfile işlevi önce eklenir. Hedef işlevi StopProfile işlevi içeriyorsa, ResumeProfile işlevi sonra eklenir.|  
|**StartOnly:** `{` **önce** `&#124;` **sonra** `&#124;` **üst** `&#124;` **alt** `},funcname`|Profil oluşturma çalıştırılması sırasında veri toplama başlar. Bu, belirtilen konumda StartProfile API işlevi ekler.<br /><br /> **Önce** - hedef işlev girdisi hemen önce.<br /><br /> **Sonra** - hedef işlevi çıkış hemen sonra.<br /><br /> **Üst** - hedef işlev girdisi hemen sonra.<br /><br /> **Alt** - hedef işlevinde her return hemen önce.<br /><br /> `funcname` -Hedef işlevinin adı.|  
|**StopOnly:**{**önce**`&#124;`**sonra**`&#124;`**üst**`&#124;`**alt**}`,funcname`|Profil oluşturma çalıştırılması sırasında veri toplama durur. Bu, belirtilen konumda StopProfile işlevi ekler.<br /><br /> **Önce** - hedef işlev girdisi hemen önce.<br /><br /> **Sonra** - hedef işlevi çıkış hemen sonra.<br /><br /> **Üst** - hedef işlev girdisi hemen sonra.<br /><br /> **Alt** - hedef işlevinde her return hemen önce.<br /><br /> `funcname` -Hedef işlevinin adı.|  
|**SuspendOnly:**{**önce**`&#124;`**sonra**`&#124;`**üst**`&#124;`**alt**}`,funcname`|Profil oluşturma çalıştırılması sırasında veri toplama durur. Bu, belirtilen konumda SuspendProfile API ekler.<br /><br /> **Önce** - hedef işlev girdisi hemen önce.<br /><br /> **Sonra** - hedef işlevi çıkış hemen sonra.<br /><br /> **Üst** - hedef işlev girdisi hemen sonra.<br /><br /> **Alt** - hedef işlevinde her return hemen önce.<br /><br /> `funcname` -Hedef işlevinin adı.<br /><br /> Hedef işlevi StartProfile işlevi içeriyorsa, SuspendProfile işlevi önce eklenir.|  
|**ResumeOnly:**{**önce**`&#124;`**sonra**`&#124;`**üst**`&#124;`**alt**}`,funcname`|Başlayan veya veri toplama sırasında bir profil oluşturma çalıştırma sürdürür.<br /><br /> Sonra profil oluşturmayı başlatmak için genellikle kullanılan bir **SuspendOnly** seçeneği profil durdurdu. Bu, belirtilen konumda bir ResumeProfile API ekler.<br /><br /> **Önce** - hedef işlev girdisi hemen önce.<br /><br /> **Sonra** - hedef işlevi çıkış hemen sonra.<br /><br /> **Üst** - hedef işlev girdisi hemen sonra.<br /><br /> **Alt** - hedef işlevinde her return hemen önce.<br /><br /> `funcname` -Hedef işlevinin adı.<br /><br /> Hedef işlevi StopProfile işlevi içeriyorsa, ResumeProfile işlevi sonra eklenir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfMon](../profiling/vsperfmon.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [VSPerfReport](../profiling/vsperfreport.md)   
 [Vsınstr uyarıları](../profiling/vsinstr-warnings.md)   
 [Performans Raporu Görünümleri](../profiling/performance-report-views.md)