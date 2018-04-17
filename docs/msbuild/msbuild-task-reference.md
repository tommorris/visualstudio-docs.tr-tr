---
title: MSBuild görev başvurusu | Microsoft Docs
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
- MSBuild, tasks
ms.assetid: b3144b27-a426-4259-b8ae-5f7991b202b6
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a03a87486f84925a2377cf3467b14d5c904c2314
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-task-reference"></a>MSBuild Görev Başvurusu
Görevler oluşturma işlemi sırasında çalışan bir kod sağlar. Aşağıdaki listede yer alan görevler ile birlikte [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Zaman [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] yüklü, ek görevler oluşturmak için kullanılan olan [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projeleri. Daha fazla bilgi için bkz: [Visual C++ görevleri](../msbuild/msbuild-tasks-specific-to-visual-cpp.md).  
  
 Bu bölümdeki konular, listelenen parametreleri ek olarak, her görevin ayrıca aşağıdaki parametreleri içerir:  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Condition`|İsteğe bağlı `String` parametresi.<br /><br /> A `Boolean` ifadesi, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] altyapısı bu görevin gerçekleştirilip gerçekleştirilmediğini belirlemek üzere kullanır. Tarafından desteklenen koşullarla ilgili bilgiler için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|İsteğe bağlı parametre. Aşağıdaki değerlerden birini içerebilir:<br /><br /> -   **WarnAndContinue** veya **doğru**. Bir görev başarısız olduğunda, sonraki görevlerinde [hedef](../msbuild/target-element-msbuild.md) öğesi ve yapı devam yürütmek ve görevin tüm hataları, uyarıları olarak kabul edilir.<br />-   **ErrorAndContinue**. Bir görev başarısız olduğunda, sonraki görevlerinde `Target` öğesi ve yapı devam yürütmek ve görevin tüm hataları hata olarak kabul edilir.<br />-   **ErrorAndStop** veya **false** (varsayılan). Bir görev başarısız olursa, kalan görevlere `Target` öğesi ve yapı olmayan yürütülen ve tüm `Target` öğesi ve yapı olarak kabul başarısız oldu.<br /><br /> Yalnızca desteklenen 4.5 önce .NET Framework sürümleri `true` ve `false` değerleri.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: görevlerdeki hataları Yoksay](../msbuild/how-to-ignore-errors-in-tasks.md).|  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Task Temel Sınıfı](../msbuild/task-base-class.md)  
 Öğesinden türetilen görevleri için bazı parametreler ekler <xref:Microsoft.Build.Utilities.Task> sınıfı.  
  
 [TaskExtension Temel Sınıfı](../msbuild/taskextension-base-class.md)  
 Öğesinden türetilen görevleri için bazı parametreler ekler <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı.  
  
 [ToolTaskExtension Temel Sınıfı](../msbuild/tooltaskextension-base-class.md)  
 Öğesinden türetilen görevleri için bazı parametreler ekler <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı.  
  
 [AL (Derleme Bağlayıcı) Görevi](../msbuild/al-assembly-linker-task.md)  
 Bir derlemeyi ya da modüller bir veya daha fazla dosya veya kaynak dosyaları bildirimden oluşturur.  
  
 [AspNetCompiler Görevi](../msbuild/aspnetcompiler-task.md)  
 Aspnet_compiler.exe, ASP.NET uygulamaları derleneceği bir yardımcı programı sarmalar.  
  
 [AssignCulture Görevi](../msbuild/assignculture-task.md)  
 Kültür tanımlayıcıları öğelerine atar.  
  
 [AssignProjectConfiguration Görevi](../msbuild/assignprojectconfiguration-task.md)  
 Yapılandırma dizelerinin listesini kabul eder ve bunları belirtilen projelerine atar.  
  
 [AssignTargetPath Görevi](../msbuild/assigntargetpath-task.md)  
 Dosyaların bir listesini kabul eder ve ekler `<TargetPath>` zaten belirtilmezse, öznitelikleri.  
  
 [CallTarget Görevi](../msbuild/calltarget-task.md)  
 Proje dosyasında bir hedef çağırır.  
  
 [CombinePath Görevi](../msbuild/combinepath-task.md)  
 Belirtilen yol, tek bir yol birleştirir.  
  
 [ConvertToAbsolutePath Görevi](../msbuild/converttoabsolutepath-task.md)  
 Göreli bir yol veya reference mutlak bir yol dönüştürür.  
  
 [Copy Görevi](../msbuild/copy-task.md)  
 Yeni bir konum dosyalarını kopyalar.  
  
 [CreateCSharpManifestResourceName Görevi](../msbuild/createcsharpmanifestresourcename-task.md)  
 Oluşturur bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-stil bildirim adı verilen .resx dosya adı veya diğer kaynak.  
  
 [CreateItem Görevi](../msbuild/createitem-task.md)  
 Öğe koleksiyonlarını giriş öğelerinden bir listeden diğerine kopyalanması öğelerine izin vererek doldurur.  
  
 [CreateProperty Görevi](../msbuild/createproperty-task.md)  
 Bir özellik veya dize diğerine kopyalanmasına değerlere izin veren giriş değerleri özelliklerinden doldurur.  
  
 [CreateVisualBasicManifestResourceName Görevi](../msbuild/createvisualbasicmanifestresourcename-task.md)  
 Oluşturur bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]-stil bildirim adı verilen .resx dosya adı veya diğer kaynak.  
  
 [Csc Görevi](../msbuild/csc-task.md)  
 Yürütülebilir dosyalar, dinamik bağlantı kitaplıkları veya kod modülleri üretmek için Visual C# derleyici çağırır.  
  
 [Delete Görevi](../msbuild/delete-task.md)  
 Belirtilen dosyaları siler.  
  
 [Error Görevi](../msbuild/error-task.md)  
 Bir yapı durdurur ve değerlendirilen bir koşullu ifadesine dayalı olarak bir hatayı günlüğe kaydeder.  
  
 [Exec Görevi](../msbuild/exec-task.md)  
 Belirtilen bağımsız değişkenlerle belirtilen program veya komut çalıştırır.  
  
 [FindAppConfigFile Görevi](../msbuild/findappconfigfile-task.md)  
 Sağlanan listelerinde app.config dosyasını bulur  
  
 [FindInList Görevi](../msbuild/findinlist-task.md)  
 Eşleşen itemspec belirtilen bir listedeki bir öğe bulur.  
  
 [FindUnderPath Görevi](../msbuild/findunderpath-task.md)  
 Belirtilen klasör ve tüm alt klasörlerini hangi öğelerin belirtilen öğe koleksiyonunda var belirler.  
  
 [FormatUrl Görevi](../msbuild/formaturl-task.md)  
 URL doğru bir URL biçimine dönüştürür.  
  
 [FormatVersion Görevi](../msbuild/formatversion-task.md)  
 Düzeltme numarası sürüm numarası ekler.  
  
 [GenerateApplicationManifest Görevi](../msbuild/generateapplicationmanifest-task.md)  
 Oluşturan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi ya da yerel bir bildirim.  
  
 [GenerateBootstrapper Görevi](../msbuild/generatebootstrapper-task.md)  
 Algılama, indirin ve bir uygulama ve ön yükleme için otomatik bir yol sağlar.  
  
 [GenerateDeploymentManifest Görevi](../msbuild/generatedeploymentmanifest-task.md)  
 Oluşturan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi.  
  
 [GenerateResource Görevi](../msbuild/generateresource-task.md)  
 Ortak dil çalışma zamanı ikili .resources dosyaları .txt ve .resx dosyaları dönüştürür.  
  
 [GenerateTrustInfo Görevi](../msbuild/generatetrustinfo-task.md)  
 Temel bildirim ve'ndan uygulama güven oluşturur `TargetZone` ve `ExcludedPermissions` parametreleri.  
  
 [GetAssemblyIdentity Görevi](../msbuild/getassemblyidentity-task.md)  
 Belirtilen dosyalardan derleme kimlikleri alır ve kimlik bilgilerini çıkarır.  
  
 [GetFrameworkPath Görevi](../msbuild/getframeworkpath-task.md)  
 Yolunu alır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] derlemeler.  
  
 [GetFrameworkSdkPath Görevi](../msbuild/getframeworksdkpath-task.md)  
 Yolunu alır [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
 [GetReferenceAssemblyPaths Görevi](../msbuild/getreferenceassemblypaths-task.md)  
 Başvuru çeşitli çerçeveleri derleme yolunu döndürür.  
  
 [LC Görevi](../msbuild/lc-task.md)  
 .License dosyasını bir .licx dosyası oluşturur.  
  
 [MakeDir Görevi](../msbuild/makedir-task.md)  
 Dizinler oluşturur ve gerekirse, tüm dizinler üst.  
  
 [Message Görevi](../msbuild/message-task.md)  
 Derleme sırasında bir ileti kaydeder.  
  
 [Move Görevi](../msbuild/move-task.md)  
 Dosyayı yeni bir konuma taşır.  
  
 [MSBuild Görevi](../msbuild/msbuild-task.md)  
 Derlemeler [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] başka projelerden [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi.  
  
 [ReadLinesFromFile Görevi](../msbuild/readlinesfromfile-task.md)  
 Bir metin dosyasındaki öğelerin listesini okur.  
  
 [RegisterAssembly Görevi](../msbuild/registerassembly-task.md)  
 Belirtilen derlemedeki meta verileri okur ve gerekli girişleri kayıt defterine ekler.  
  
 [RemoveDir Görevi](../msbuild/removedir-task.md)  
 Belirtilen dizinlerin ve tüm alt dizinler ve dosyalar kaldırır.  
  
 [RemoveDuplicates Görevi](../msbuild/removeduplicates-task.md)  
 Yinelenen öğe belirtilen öğeyi koleksiyondan kaldırır.  
  
 [RequiresFramework35SP1Assembly Görevi](../msbuild/requiresframework35sp1assembly-task.md)  
 Uygulama .NET Framework 3.5 SP1 gerekli olup olmadığını belirler.  
  
 ResGen görevi  
 Kullanımdan kalktı. Kullanım [GenerateResource görevi](../msbuild/generateresource-task.md) için ve ortak dil çalışma zamanı ikili .resources dosyaları .txt ve .resx dosyaları dönüştürmek için görev.  
  
 [ResolveAssemblyReference Görevi](../msbuild/resolveassemblyreference-task.md)  
 Belirtilen derlemelerini bağlı tüm derlemelerde belirler.  
  
 [ResolveComReference Görevi](../msbuild/resolvecomreference-task.md)  
 Bir veya daha fazla tür kitaplığı adları ya da .tlb dosyaları listesini alır ve bu tür kitaplıklarının disk üzerindeki konumlara giderir.  
  
 [ResolveKeySource Görevi](../msbuild/resolvekeysource-task.md)  
 Güçlü ad anahtarı kaynağı belirler  
  
 [ResolveManifestFiles Görevi](../msbuild/resolvemanifestfiles-task.md)  
 Derleme sürecindeki aşağıdaki öğeleri için bildirim üretme dosyaları Çözümler: öğeler, bağımlılıkları, uydunuz, içerik, hata ayıklama simgeleri ve belgeleri oluşturulmuş.  
  
 [ResolveNativeReference Görevi](../msbuild/resolvenativereference-task.md)  
 Yerel başvuruları çözümler.  
  
 [ResolveNonMSBuildProjectOutput Görevi](../msbuild/resolvenonmsbuildprojectoutput-task.md)  
 MSBuild dışındaki proje başvuruları için çıktı dosyaları belirler.  
  
 [SGen Görevi](../msbuild/sgen-task.md)  
 XML serileştirme bütünleştirilmiş türleri için belirtilen derlemedeki oluşturur.  
  
 [SignFile Görevi](../msbuild/signfile-task.md)  
 Belirtilen sertifika kullanarak belirtilen dosyayı açar.  
  
 [Touch Görevi](../msbuild/touch-task.md)  
 Dosya erişimi ve değişiklik zamanları ayarlar.  
  
 [UnregisterAssembly Görevi](../msbuild/unregisterassembly-task.md)  
 Belirtilen derlemelere COM birlikte çalışma amacıyla kaydını siler.  
  
 [UpdateManifest Görevi](../msbuild/updatemanifest-task.md)  
 Seçilen özelliklerin bildiriminde güncelleştirir ve Çekildi.  
  
 [Vbc Görevi](../msbuild/vbc-task.md)  
 Yürütülebilir dosyalar, dinamik bağlantı kitaplıkları veya kod modülleri üretmek için Visual Basic derleyici çağırır...  
  
 [Warning Görevi](../msbuild/warning-task.md)  
 Günlükleri bir uyarı derleme sırasında değerlendirilen bir koşullu ifadesine dayalı olarak.  
  
 [WriteCodeFragment Görevi](../msbuild/writecodefragment-task.md)  
 Belirtilen oluşturulan kod parçası kullanarak bir geçici kod dosyası oluşturur. Dosyayı silmez.  
  
 [WriteLinesToFile Görevi](../msbuild/writelinestofile-task.md)  
 Belirtilen öğe belirtilen metin dosyasına yazar.  
  
 [XmlPeek Görevi](../msbuild/xmlpeek-task.md)  
 XPath sorgusu tarafından belirtilen değerinin bir XML dosyasından döndürür.  
  
 [XmlPoke Görevi](../msbuild/xmlpoke-task.md)  
 Bir XML dosyasına bir XPath sorgusu tarafından belirtilen değerlerini ayarlar.  
  
 [XslTransformation Görevi](../msbuild/xsltransformation-task.md)  
 Kullanarak bir XML girişi dönüştüren bir *Genişletilebilir Stil Sayfası Dili Dönüşümü* (XSLT) veya XSLT ve bir çıkış aygıtı veya bir dosyaya çıkışları derlenmiş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev yazma](../msbuild/task-writing.md)   
 [Görevler](../msbuild/msbuild-tasks.md)