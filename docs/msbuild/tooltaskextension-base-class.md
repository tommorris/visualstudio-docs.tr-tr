---
title: "ToolTaskExtension taban sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MSBuild.ToolTask.ToolCommandFailed
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 258ae433-f68a-49f1-b276-da20e3472e68
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e2d370f559478f0fd11f4d1edb10618658a87ccc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="tooltaskextension-base-class"></a>ToolTaskExtension Taban Sınıfı
Birçok görevi devralınmalıdır <xref:Microsoft.Build.Tasks.ToolTaskExtension> devraldığı sınıfı <xref:Microsoft.Build.Utilities.ToolTask> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu devralma zincirini aktarımlar görevleri birkaç parametre ekler. Bu parametreler, bu belgede listelenir.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda temel sınıflarının parametreler açıklanmaktadır.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine> parametresi.<br /><br /> Görevler için kullanılabilir yapı altyapısı arabirimi belirtir. Yapı altyapısı geri içine çağırmak görevler izin vermek için bu parametreyi otomatik olarak ayarlar.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine2> parametresi.<br /><br /> Görevler için kullanılabilir yapı altyapısı arabirimi belirtir. Yapı altyapısı geri içine çağırmak görevler izin vermek için bu parametreyi otomatik olarak ayarlar.<br /><br /> Bu bir kolaylık özelliği, böylelikle bu sınıfından devralan görev yazarlar değerinden cast gerekmez `IBuildEngine` için `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine3> parametresi.<br /><br /> Ana bilgisayar tarafından sağlanan yapı altyapısı arabirimi belirtir.|  
|<xref:Microsoft.Build.Utilities.ToolTask.EchoOff%2A>|İsteğe bağlı `bool` parametresi.<br /><br /> Ayarlandığında `true`, bu görev geçişleri **/Q** cmd.exe komut satırı sağlayacak şekilde komut satırı stdout kopyalanmaz.|  
|<xref:Microsoft.Build.Utilities.ToolTask.EnvironmentVariables%2A>|İsteğe bağlı `String` dizi parametresi.<br /><br /> Ortam değişkenleri, eşittir işaretiyle ayırarak çiftleri dizisi. Bu değişkenler, oluşturulan yürütülebilir ek olarak geçirilen veya seçmeli olarak geçersiz kılma normal ortam bloğu.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ExitCode%2A>|İsteğe bağlı `Int32` çıkış parametresi salt okunur.<br /><br /> Yürütülen komutun tarafından sağlanan çıkış kodu belirtir. Görev hataları günlüğe, ancak bir çıkış kodu 0 (başarılı) işlemi var, bu -1 olarak ayarlanır.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskHost> parametresi.<br /><br /> (Null olabilir) ana bilgisayar nesnesi örneği belirtir. IDE konak bir konak nesnesi belirli bu görevle ilişkili varsa yapı altyapısı bu özelliği ayarlar.|  
|<xref:Microsoft.Build.Tasks.ToolTaskExtension.Log%2A>|İsteğe bağlı <xref:Microsoft.Build.Utilities.TaskLoggingHelper> salt okunur parametresi.<br /><br /> Örneğini alır bir <xref:Microsoft.Build.Tasks.TaskLoggingHelperExtension> görev günlük yöntemleri içeren sınıf.|  
|<xref:Microsoft.Build.Utilities.ToolTask.LogStandardErrorAsError%2A>|Seçenek `bool` parametresi.<br /><br /> Varsa `true`, standart hata akışına alınan tüm iletileri hata olarak kaydedilir.|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardErrorImportance%2A>|İsteğe bağlı `String` parametresi.<br /><br /> Önem akış çıkışı standardı metin oturum kullanılacak.|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardOutputImportance%2A>|İsteğe bağlı `String` parametresi.<br /><br /> Önem akış çıkışı standardı metin oturum kullanılacak.|  
|<xref:Microsoft.Build.Utilities.ToolTask.Timeout%2A>|İsteğe bağlı sanal `Int32` parametresi.<br /><br /> Süresini, daha sonra çalıştırılabilir görev sonlandırıldığından milisaniye cinsinden belirtir. Varsayılan değer `Int.MaxValue`, hiçbir zaman aşımı süresi olduğunu gösterir. Zaman aşımı milisaniye cinsindendir.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolExe%2A>|İsteğe bağlı sanal `string` parametresi.<br /><br /> Projeleri bu bir ToolName geçersiz kılmak için uygulayabilir. Görevler bu ToolName korumak için geçersiz kılabilir.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolPath%2A>|İsteğe bağlı `string` parametresi.<br /><br /> Burada görev temel yürütülebilir dosyayı yükler konumdaki belirtir. Bu parametre belirtilmezse, görevin çalıştığı framework sürümüne karşılık gelen SDK yükleme yolunu kullanır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|<xref:Microsoft.Build.Utilities.ToolTask.UseCommandProcessor%2A>|İsteğe bağlı `bool` parametresi.<br /><br /> Ayarlandığında `true`, bu görev komut satırı için bir toplu iş dosyası oluşturur ve komutu yürütmek yerine doğrudan Komut işlemcisi kullanarak yürütür.|  
|<xref:Microsoft.Build.Utilities.ToolTask.YieldDuringToolExecution%2A>|İsteğe bağlı `bool` parametresi.<br /><br /> Ayarlandığında `true`, kendi görev yürütülürken bu görevi düğümün verir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)