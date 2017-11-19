---
title: "LIB görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.Name
- VC.Project.VCLibrarianTool.TreatLibWarningsAsErrors
- VC.Project.VCLibrarianTool.Verbose
- vc.task.lib
- VC.Project.VCLibrarianTool.ErrorReporting
- VC.Project.VCLibrarianTool.LinkLibraryDependencies
- VC.Project.VCLibrarianTool.LinkTimeCodeGeneration
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), LIB task
- LIB task (MSBuild (Visual C++))
ms.assetid: e062c7f9-cc69-4a83-9361-1bb5355e5fe8
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 6bdca24340f301fc19f3bc8d1e86c97c3b98c5c5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="lib-task"></a>LIB Görevi
Microsoft 32 Bit Kitaplık Yöneticisi Aracı sarmalar lib.exe. Kitaplığı Yöneticisi'ni oluşturur ve ortak nesne dosyası biçimi (COFF) nesne dosyaları içeren bir kitaplık yönetir. Kitaplık Yöneticisi ayrıca dışarı aktarma dosyaları oluşturabilir ve kitaplıkları için dışa aktarılan başvuru tanımını içeri aktarın. Daha fazla bilgi için bkz: [LIB başvurusu](/cpp/build/reference/lib-reference) ve [çalıştıran LIB](/cpp/build/reference/running-lib).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **LIB** görev. Çoğu görevi parametreleri bir komut satırı seçeneğine karşılık gelir.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**AdditionalDependencies**|İsteğe bağlı **String []** parametresi.<br /><br /> Komut satırına eklenecek ek öğelerini belirtir.|  
|**AdditionalLibraryDirectories**|İsteğe bağlı **String []** parametresi.<br /><br /> Ortam Kitaplığı yol geçersiz kılar. Bir dizin adı belirtin.<br /><br /> Daha fazla bilgi için bkz: [/Libpath (ek Libpath)](/cpp/build/reference/libpath-additional-libpath).|  
|**AdditionalOptions**|İsteğe bağlı **dize** parametresi.<br /><br /> Komut satırında belirtilen lib.exe seçenekleri listesi. Örneğin, **"***/option1 /option2 /option#*". Diğer tarafından temsil edilmez lib.exe seçenekleri belirtmek için bu parametreyi kullanın **LIB** görev parametresi.<br /><br /> Daha fazla bilgi için bkz: [çalıştıran LIB](/cpp/build/reference/running-lib).|  
|**DisplayLibrary**|İsteğe bağlı **dize** parametresi.<br /><br /> Çıktı Kitaplığı hakkında bilgileri görüntüler. Bir dosyaya bilgi yönlendirmek için bir dosya adı belirtin. "CON" veya hiçbir şey bilgileri konsola yeniden yönlendirmek için belirtin.<br /><br /> Bu parametre karşılık gelen **/LIST** lib.exe seçeneği.|  
|**ErrorReporting**|İsteğe bağlı **dize** parametresi.<br /><br /> Çalışma zamanında lib.exe başarısız olursa iç hata bilgilerini Microsoft'a göndermek nasıl belirtir.<br /><br /> Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.<br /><br /> -   **NoErrorReport** -   **/errorreport: yok**<br />-   **PromptImmediately** - **/ERRORREPORT:PROMPT**<br />-   **QueueForNextLogin** - **/ERRORREPORT:QUEUE**<br />-   **SendErrorReport** - **/ERRORREPORT:SEND**<br /><br /> Daha fazla bilgi için bkz: **/errorreport** komut satırı seçeneği [çalıştıran LIB](/cpp/build/reference/running-lib).|  
|**ExportNamedFunctions**|İsteğe bağlı **String []** parametresi.<br /><br /> Dışarı aktarmak için bir veya daha fazla işlevleri belirtir.<br /><br /> Bu parametre karşılık gelen **/dışarı aktarma:** lib.exe seçeneği.|  
|**ForceSymbolReferences**|İsteğe bağlı **dize** parametresi.<br /><br /> Belirtilen sembolün bir başvuru eklemek için lib.exe zorlar.<br /><br /> Bu parametre karşılık gelen **/içerir:** lib.exe seçeneği.|  
|**IgnoreAllDefaultLibraries**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, tüm varsayılan kitaplık kaldırır dış başvuruları çözdüğünde kitaplıkları listesinden bu lib.exe arar.<br /><br /> Bu parametre daha az parametreli form karşılık gelen **/NODEFAULTLIB** lib.exe seçeneği.|  
|**IgnoreSpecificDefaultLibraries**|İsteğe bağlı **String []** parametresi.<br /><br /> Belirtilen kitaplıkları kaldırır dış başvuruları çözdüğünde kitaplıkları listesinden bu lib.exe arar.<br /><br /> Bu parametre karşılık gelen **/NODEFAULTLIB** geçen lib.exe seçeneği bir `library` bağımsız değişkeni.|  
|**LinkLibraryDependencies**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, proje bağımlılıklarını kitaplığı çıkışlarından içinde otomatik olarak bağlanan belirtir.|  
|**LinkTimeCodeGeneration**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, bağlama zamanı kodu oluşturma belirtir.<br /><br /> Bu parametre karşılık gelen **/LCTG** lib.exe seçeneği.|  
|**MinimumRequiredVersion**|İsteğe bağlı **dize** parametresi.<br /><br /> Gereken en düşük sürüm alt sisteminin belirtir. 0-65535 aralığında ondalık sayılar virgülle ayrılmış bir listesini belirtin.|  
|**ModuleDefinitionFile**|İsteğe bağlı **dize** parametresi.<br /><br /> Modül tanım dosyasını (.def) adını belirtir.<br /><br /> Bu parametre karşılık gelen **/def** geçen lib.exe seçeneği bir `filename` bağımsız değişkeni.|  
|**Ad**|İsteğe bağlı **dize** parametresi.<br /><br /> İçeri aktarma kitaplığı yapılandırıldığında, içeri aktarma kitaplığını oluşturulmakta olan DLL adını belirtir.<br /><br /> Bu parametre karşılık gelen **/NAME** geçen lib.exe seçeneği bir `filename` bağımsız değişkeni.|  
|**ÇıktıDosyası**|İsteğe bağlı **dize** parametresi.<br /><br /> Varsayılan geçersiz kılar ad ve konum programının bu lib.exe oluşturur.<br /><br /> Bu parametre karşılık gelen **/OUT** geçen lib.exe seçeneği bir `filename` bağımsız değişkeni.|  
|**RemoveObjects**|İsteğe bağlı **String []** parametresi.<br /><br /> Belirtilen nesne çıkış kitaplığından atlar. Lib.exe bir çıktı kitaplığı tüm nesneler (nesne dosya ya da kitaplıkları kullanılıp) birleştirerek ve bu seçeneği tarafından belirtilen herhangi bir nesne silme oluşturur.<br /><br /> Bu parametre karşılık gelen **/Kaldır** geçen lib.exe seçeneği bir `membername` bağımsız değişkeni.|  
|**Kaynakları**|Gerekli `ITaskItem[]` parametresi.<br /><br /> Kaynak dosyaları boşluklarla ayrılmış listesini belirtir.|  
|**Alt sistemi**|İsteğe bağlı **dize** parametresi.<br /><br /> Yürütülebilir dosya ortamını belirtir. Alt sistemi seçimi giriş noktası simgesi veya giriş noktası işlevi etkiler.<br /><br /> Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.<br /><br /> -   **Konsol** - **/SUBSYSTEM:CONSOLE**<br />-   **Windows** - **/SUBSYSTEM:WINDOWS**<br />-   **Yerel** - **/SUBSYSTEM:NATIVE**<br />-   **EFI uygulama** - **/SUBSYSTEM:EFI_APPLICATION**<br />-   **EFI Önyükleme hizmeti sürücü** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**<br />-   **EFI ROM** - **/SUBSYSTEM:EFI_ROM**<br />-   **EFI çalışma zamanı** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**<br />-   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**ReplaceThisText<br />-   **POSIX** - **/SUBSYSTEM:POSIX**<br /><br /> Daha fazla bilgi için bkz: [/SUBSYSTEM (alt sistemi belirtin)](/cpp/build/reference/subsystem-specify-subsystem).|  
|**SuppressStartupBanner**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.<br /><br /> Daha fazla bilgi için bkz: **/nologo** adresindeki seçeneği [çalıştıran LIB](/cpp/build/reference/running-lib).|  
|**TargetMachine**|İsteğe bağlı **dize** parametresi.<br /><br /> Hedef platformu program veya DLL belirtir.<br /><br /> Her biri bir komut satırı seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.<br /><br /> -   **MachineARM** - **/MACHINE:ARM**<br />-   **MachineEBC** - **/MACHINE:EBC**<br />-   **MachineIA64** - **/MACHINE:IA64**<br />-   **MachineMIPS** - **/MACHINE:MIPS**<br />-   **MachineMIPS16** - **/MACHINE:MIPS16**<br />-   **MachineMIPSFPU** -**/MACHINE:MIPSFPU**<br />-   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**<br />-   **MachineSH4** - **/MACHINE:SH4**<br />-   **MachineTHUMB** - **/MACHINE:THUMB**<br />-   **MachineX64** - **/MACHINE:X 64**<br />-   **MachineX86** - **/MACHINE:X 86**<br /><br /> Daha fazla bilgi için bkz: [/MACHINE (hedef platformu belirtin)](/cpp/build/reference/machine-specify-target-platform).|  
|**TrackerLogDirectory**|İsteğe bağlı **dize** parametresi.<br /><br /> İzleyici günlük dizinini belirtir.|  
|**TreatLibWarningAsErrors**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, neden **LIB** lib.exe bir uyarı oluşturursa bir çıktı dosyası değil oluşturulacak görev. Varsa `false`, bir çıktı dosyası oluşturulur.<br /><br /> Daha fazla bilgi için bkz: **/WX** adresindeki seçeneği [çalıştıran LIB](/cpp/build/reference/running-lib).|  
|**UseUnicodeResponseFiles**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, kitaplığı kökenli zaman UNICODE yanıt dosyaları oluşturmak için proje sistemi bildirir. Belirtin `true` projedeki dosyaları UNICODE yolları olduğunda.|  
|**Ayrıntılı**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, ilerleme durumunu; oturumu hakkındaki ayrıntıları görüntüler bu eklenmekte olan .obj dosyaları adlarını içerir. Bilgiler, standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.<br /><br /> Daha fazla bilgi için bkz: **/VERBOSE** seçeneğini [çalıştıran LIB](/cpp/build/reference/running-lib).|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)