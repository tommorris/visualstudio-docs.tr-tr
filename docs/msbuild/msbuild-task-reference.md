---
title: "MSBuild görev başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords: MSBuild, tasks
ms.assetid: b3144b27-a426-4259-b8ae-5f7991b202b6
caps.latest.revision: "32"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: c0d1474fb03acd838387677786656967e852fdf9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-task-reference"></a>MSBuild Görev Başvurusu
Görevler oluşturma işlemi sırasında çalışan bir kod sağlar. Aşağıdaki listede yer alan görevler ile birlikte [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Zaman [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] yüklü, ek görevler oluşturmak için kullanılan olan [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projeleri. Daha fazla bilgi için bkz: [Visual C++ görevleri](../msbuild/msbuild-tasks-specific-to-visual-cpp.md).  
  
 Bu bölümdeki konular, listelenen parametreleri ek olarak, her görevin ayrıca aşağıdaki parametreleri içerir:  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı `String` parametresi.<br /><br /> A `Boolean` ifadesi, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] altyapısı bu görevin gerçekleştirilip gerçekleştirilmediğini belirlemek üzere kullanır. Tarafından desteklenen koşullarla ilgili bilgiler için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|İsteğe bağlı parametre. Aşağıdaki değerlerden birini içerebilir:<br /><br /> -   **WarnAndContinue** veya **doğru**. Bir görev başarısız olduğunda, sonraki görevlerinde [hedef](../msbuild/target-element-msbuild.md) öğesi ve yapı devam yürütmek ve görevin tüm hataları, uyarıları olarak kabul edilir.<br />-   **ErrorAndContinue**. Bir görev başarısız olduğunda, sonraki görevlerinde `Target` öğesi ve yapı devam yürütmek ve görevin tüm hataları hata olarak kabul edilir.<br />-   **ErrorAndStop** veya **false** (varsayılan). Bir görev başarısız olursa, kalan görevlere `Target` öğesi ve yapı olmayan yürütülen ve tüm `Target` öğesi ve yapı olarak kabul başarısız oldu.<br /><br /> Yalnızca desteklenen 4.5 önce .NET Framework sürümleri `true` ve `false` değerleri.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: görevlerdeki hataları Yoksay](../msbuild/how-to-ignore-errors-in-tasks.md).|  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Görev taban sınıfı](../msbuild/task-base-class.md)  
 Öğesinden türetilen görevleri için bazı parametreler ekler <xref:Microsoft.Build.Utilities.Task> sınıfı.  
  
 [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md)  
 Öğesinden türetilen görevleri için bazı parametreler ekler <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı.  
  
 [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md)  
 Öğesinden türetilen görevleri için bazı parametreler ekler <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı.  
  
 [AL (derleme bağlayıcı) görevi](../msbuild/al-assembly-linker-task.md)  
 Bir derlemeyi ya da modüller bir veya daha fazla dosya veya kaynak dosyaları bildirimden oluşturur.  
  
 [AspNetCompiler görevi](../msbuild/aspnetcompiler-task.md)  
 Aspnet_compiler.exe, ASP.NET uygulamaları derleneceği bir yardımcı programı sarmalar.  
  
 [AssignCulture görevi](../msbuild/assignculture-task.md)  
 Kültür tanımlayıcıları öğelerine atar.  
  
 [AssignProjectConfiguration görevi](../msbuild/assignprojectconfiguration-task.md)  
 Yapılandırma dizelerinin listesini kabul eder ve bunları belirtilen projelerine atar.  
  
 [AssignTargetPath görevi](../msbuild/assigntargetpath-task.md)  
 Dosyaların bir listesini kabul eder ve ekler `<TargetPath>` zaten belirtilmezse, öznitelikleri.  
  
 [CallTarget görevi](../msbuild/calltarget-task.md)  
 Proje dosyasında bir hedef çağırır.  
  
 [CombinePath görevi](../msbuild/combinepath-task.md)  
 Belirtilen yol, tek bir yol birleştirir.  
  
 [ConvertToAbsolutePath görevi](../msbuild/converttoabsolutepath-task.md)  
 Göreli bir yol veya reference mutlak bir yol dönüştürür.  
  
 [Kopyalama görevi](../msbuild/copy-task.md)  
 Yeni bir konum dosyalarını kopyalar.  
  
 [CreateCSharpManifestResourceName görevi](../msbuild/createcsharpmanifestresourcename-task.md)  
 Oluşturur bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-stil bildirim adı verilen .resx dosya adı veya diğer kaynak.  
  
 [CreateItem görevi](../msbuild/createitem-task.md)  
 Öğe koleksiyonlarını giriş öğelerinden bir listeden diğerine kopyalanması öğelerine izin vererek doldurur.  
  
 [CreateProperty görevi](../msbuild/createproperty-task.md)  
 Bir özellik veya dize diğerine kopyalanmasına değerlere izin veren giriş değerleri özelliklerinden doldurur.  
  
 [CreateVisualBasicManifestResourceName görevi](../msbuild/createvisualbasicmanifestresourcename-task.md)  
 Oluşturur bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]-stil bildirim adı verilen .resx dosya adı veya diğer kaynak.  
  
 [CSC görevi](../msbuild/csc-task.md)  
 Yürütülebilir dosyalar, dinamik bağlantı kitaplıkları veya kod modülleri üretmek için Visual C# derleyici çağırır.  
  
 [Silme görevi](../msbuild/delete-task.md)  
 Belirtilen dosyaları siler.  
  
 [Hata görevi](../msbuild/error-task.md)  
 Bir yapı durdurur ve değerlendirilen bir koşullu ifadesine dayalı olarak bir hatayı günlüğe kaydeder.  
  
 [Yürütme görevi](../msbuild/exec-task.md)  
 Belirtilen bağımsız değişkenlerle belirtilen program veya komut çalıştırır.  
  
 [FindAppConfigFile görevi](../msbuild/findappconfigfile-task.md)  
 Sağlanan listelerinde app.config dosyasını bulur  
  
 [Findınlist görevi](../msbuild/findinlist-task.md)  
 Eşleşen itemspec belirtilen bir listedeki bir öğe bulur.  
  
 [FindUnderPath görevi](../msbuild/findunderpath-task.md)  
 Belirtilen klasör ve tüm alt klasörlerini hangi öğelerin belirtilen öğe koleksiyonunda var belirler.  
  
 [FormatUrl görevi](../msbuild/formaturl-task.md)  
 URL doğru bir URL biçimine dönüştürür.  
  
 [FormatVersion görevi](../msbuild/formatversion-task.md)  
 Düzeltme numarası sürüm numarası ekler.  
  
 [GenerateApplicationManifest görevi](../msbuild/generateapplicationmanifest-task.md)  
 Oluşturan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi ya da yerel bir bildirim.  
  
 [GenerateBootstrapper görevi](../msbuild/generatebootstrapper-task.md)  
 Algılama, indirin ve bir uygulama ve ön yükleme için otomatik bir yol sağlar.  
  
 [GenerateDeploymentManifest görevi](../msbuild/generatedeploymentmanifest-task.md)  
 Oluşturan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi.  
  
 [GenerateResource görevi](../msbuild/generateresource-task.md)  
 Ortak dil çalışma zamanı ikili .resources dosyaları .txt ve .resx dosyaları dönüştürür.  
  
 [Generatetrustınfo görevi](../msbuild/generatetrustinfo-task.md)  
 Temel bildirim ve'ndan uygulama güven oluşturur `TargetZone` ve `ExcludedPermissions` parametreleri.  
  
 [Getassemblyıdentity görevi](../msbuild/getassemblyidentity-task.md)  
 Belirtilen dosyalardan derleme kimlikleri alır ve kimlik bilgilerini çıkarır.  
  
 [GetFrameworkPath görevi](../msbuild/getframeworkpath-task.md)  
 Yolunu alır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] derlemeler.  
  
 [GetFrameworkSdkPath görevi](../msbuild/getframeworksdkpath-task.md)  
 Yolunu alır [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
 [GetReferenceAssemblyPaths görevi](../msbuild/getreferenceassemblypaths-task.md)  
 Başvuru çeşitli çerçeveleri derleme yolunu döndürür.  
  
 [LC görevi](../msbuild/lc-task.md)  
 .License dosyasını bir .licx dosyası oluşturur.  
  
 [MakeDir görevi](../msbuild/makedir-task.md)  
 Dizinler oluşturur ve gerekirse, tüm dizinler üst.  
  
 [İleti görevi](../msbuild/message-task.md)  
 Derleme sırasında bir ileti kaydeder.  
  
 [Taşıma görevi](../msbuild/move-task.md)  
 Dosyayı yeni bir konuma taşır.  
  
 [MSBuild görevi](../msbuild/msbuild-task.md)  
 Derlemeler [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] başka projelerden [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi.  
  
 [ReadLinesFromFile görevi](../msbuild/readlinesfromfile-task.md)  
 Bir metin dosyasındaki öğelerin listesini okur.  
  
 [RegisterAssembly görevi](../msbuild/registerassembly-task.md)  
 Belirtilen derlemedeki meta verileri okur ve gerekli girişleri kayıt defterine ekler.  
  
 [RemoveDir görevi](../msbuild/removedir-task.md)  
 Belirtilen dizinlerin ve tüm alt dizinler ve dosyalar kaldırır.  
  
 [RemoveDuplicates görevi](../msbuild/removeduplicates-task.md)  
 Yinelenen öğe belirtilen öğeyi koleksiyondan kaldırır.  
  
 [RequiresFramework35SP1Assembly görevi](../msbuild/requiresframework35sp1assembly-task.md)  
 Uygulama .NET Framework 3.5 SP1 gerekli olup olmadığını belirler.  
  
 ResGen görevi  
 Kullanımdan kalktı. Kullanım [GenerateResource görevi](../msbuild/generateresource-task.md) için ve ortak dil çalışma zamanı ikili .resources dosyaları .txt ve .resx dosyaları dönüştürmek için görev.  
  
 [ResolveAssemblyReference görevi](../msbuild/resolveassemblyreference-task.md)  
 Belirtilen derlemelerini bağlı tüm derlemelerde belirler.  
  
 [ResolveComReference görevi](../msbuild/resolvecomreference-task.md)  
 Bir veya daha fazla tür kitaplığı adları ya da .tlb dosyaları listesini alır ve bu tür kitaplıklarının disk üzerindeki konumlara giderir.  
  
 [ResolveKeySource görevi](../msbuild/resolvekeysource-task.md)  
 Güçlü ad anahtarı kaynağı belirler  
  
 [ResolveManifestFiles görevi](../msbuild/resolvemanifestfiles-task.md)  
 Derleme sürecindeki aşağıdaki öğeleri için bildirim üretme dosyaları Çözümler: öğeler, bağımlılıkları, uydunuz, içerik, hata ayıklama simgeleri ve belgeleri oluşturulmuş.  
  
 [ResolveNativeReference görevi](../msbuild/resolvenativereference-task.md)  
 Yerel başvuruları çözümler.  
  
 [ResolveNonMSBuildProjectOutput görevi](../msbuild/resolvenonmsbuildprojectoutput-task.md)  
 MSBuild dışındaki proje başvuruları için çıktı dosyaları belirler.  
  
 [SGen görevi](../msbuild/sgen-task.md)  
 XML serileştirme bütünleştirilmiş türleri için belirtilen derlemedeki oluşturur.  
  
 [SignFile görevi](../msbuild/signfile-task.md)  
 Belirtilen sertifika kullanarak belirtilen dosyayı açar.  
  
 [Dokunma görevi](../msbuild/touch-task.md)  
 Dosya erişimi ve değişiklik zamanları ayarlar.  
  
 [UnregisterAssembly görevi](../msbuild/unregisterassembly-task.md)  
 Belirtilen derlemelere COM birlikte çalışma amacıyla kaydını siler.  
  
 [UpdateManifest görevi](../msbuild/updatemanifest-task.md)  
 Seçilen özelliklerin bildiriminde güncelleştirir ve Çekildi.  
  
 [Vbc görevi](../msbuild/vbc-task.md)  
 Yürütülebilir dosyalar, dinamik bağlantı kitaplıkları veya kod modülleri üretmek için Visual Basic derleyici çağırır...  
  
 [Uyarı görevi](../msbuild/warning-task.md)  
 Günlükleri bir uyarı derleme sırasında değerlendirilen bir koşullu ifadesine dayalı olarak.  
  
 [WriteCodeFragment görevi](../msbuild/writecodefragment-task.md)  
 Belirtilen oluşturulan kod parçası kullanarak bir geçici kod dosyası oluşturur. Dosyayı silmez.  
  
 [WriteLinesToFile görevi](../msbuild/writelinestofile-task.md)  
 Belirtilen öğe belirtilen metin dosyasına yazar.  
  
 [XmlPeek görevi](../msbuild/xmlpeek-task.md)  
 XPath sorgusu tarafından belirtilen değerinin bir XML dosyasından döndürür.  
  
 [XmlPoke görevi](../msbuild/xmlpoke-task.md)  
 Bir XML dosyasına bir XPath sorgusu tarafından belirtilen değerlerini ayarlar.  
  
 [XslTransformation görevi](../msbuild/xsltransformation-task.md)  
 Kullanarak bir XML girişi dönüştüren bir *Genişletilebilir Stil Sayfası Dili Dönüşümü* (XSLT) veya XSLT ve bir çıkış aygıtı veya bir dosyaya çıkışları derlenmiş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev yazma](../msbuild/task-writing.md)   
 [Görevler](../msbuild/msbuild-tasks.md)