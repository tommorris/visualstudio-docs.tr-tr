---
title: GenerateResource görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateResource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateResource task
- GenerateResource task [MSBuild]
ms.assetid: c0aff32f-f2cc-46f6-9c3e-a5c9f8f912b1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e26aae610407ceb1ebe050081f5b555d82badc92
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="generateresource-task"></a>GenerateResource Görevi
.Txt, .resx (XML tabanlı kaynak biçimi) dosyaları ve bir çalışma zamanı ikili yürütülebilir dosya katıştırılmış veya uydu derlemelerini derlenmiş ortak dil çalışma zamanı ikili .resources dosyaları arasındaki dönüştürür. Bu görev, genellikle .txt veya .resx dosyaları .resource dosyalarına dönüştürmek için kullanılır. `GenerateResource` Görev benzer işlevsellik [resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `GenerateResource` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AdditionalInputs`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bu görev tarafından gerçekleştirilen Bağımlılık denetimi ek girişleri içerir. Örneğin, böylece güncelleştirilirse, tüm kaynakları yeniden proje ve hedefleri dosyaları genellikle girişleri, olması gerekir.|  
|`EnvironmentVariables`|İsteğe bağlı `String[]` parametresi.<br /><br /> Ortam oluşturulan resgen.exe için ek olarak iletilmesi gereken değişkenleri (veya seçmeli olarak geçersiz kılma) ad-değer çiftleri dizisi belirtir normal ortam bloğu.|  
|`ExcludedInputPaths`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> İçinden izlenen girişleri güncel denetimi sırasında yok sayılacak yollarını belirtin öğelerinin bir dizisini belirtir.|  
|`ExecuteAsTool`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, uygun hedef framework çıkış gerekli sarmalayıcı derlemeleri oluşturmak için işlem dışı tlbimp.exe ve aximp.exe çalışır. Çoklu sürüm desteği, bu parametre sağlayan `ResolveComReferences`.|  
|`FilesWritten`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Yazılan tüm dosyaların adlarını içeren disk. Bu önbellek dosyası varsa içerir. Bu parametre, temiz uygulamaları için yararlıdır.|  
|`MinimalRebuildFromTracking`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Alır veya izlenen Artımlı derleme kullanılıp kullanılmayacağını belirten bir anahtar ayarlar. Varsa `true`, artımlı derleme açıktır; Aksi halde, bir yeniden oluşturma zorlanır.|  
|`NeverLockTypeAssemblies`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Yeni bir oluşturulup oluşturulmayacağını belirten bir Boole değeri alır veya ayarlar [AppDomain](/dotnet/api/system.appdomain) kaynakları (.resx) dosyaları (true) değerlendirmek için veya yeni bir oluşturmak için [AppDomain](/dotnet/api/system.appdomain) yalnızca kaynak dosyalarını bir kullanıcının ne zaman başvurusu derleme (false).|  
|`OutputResources`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> .Resources dosyaları gibi oluşturulan dosya adını belirtir. Bir ad belirtmezseniz, kullanılan eşleşen giriş dosyası adı ve oluşturulan .resources dosyası giriş dosyasını içeren dizinde yerleştirilir.|  
|`PublicClass`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, ortak bir sınıf olarak kesin türü belirtilmiş kaynak sınıfı oluşturur.|  
|`References`|İsteğe bağlı `String[]` parametresi.<br /><br /> .Resx dosyaları türlerinde yüklemek için başvuruları. Resx dosya veri öğeleri .NET türü olabilir. .Resx dosyayı okurken bu çözümlenmesi gerekir. Genellikle, bu kuralları yükleniyor standart türünü kullanarak başarıyla çözümlenir. Derlemelerde sağlarsanız, `References`, öncelik kazanır.<br /><br /> Bu parametre için kesin türü belirtilmiş kaynakları gerekli değildir.|  
|`SdkToolsPath`|İsteğe bağlı `String` parametresi.<br /><br /> Resgen.exe gibi SDK Araçları yolunu belirtir.|  
|`Sources`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Öğeleri dönüştürüleceği belirtir. Bu parametreye geçirilen öğe şu uzantılardan birine sahip olmalıdır:<br /><br /> -   `.txt`: Bir metin dosyasına dönüştürmek uzantısı belirtir. Metin dosyaları yalnızca dize kaynaklarını içerebilir.<br />-   `.resx`: Dönüştürmek bir XML tabanlı kaynak dosya uzantısı belirtir.<br />-   `.restext`: Aynı biçimde .txt belirtir. Bu farklı uzantı açıkça diğer kaynak dosyalarından yapı işleminizin kaynakları içeren kaynak dosyalarını ayırt etmek istiyorsanız kullanışlıdır.<br />-   `.resources`: Dönüştürmek bir kaynak dosya uzantısı belirtir.|  
|`StateFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> .Resx giriş dosyaları bağlantıların denetimi bağımlılık hızlandırmak için kullanılan bir isteğe bağlı önbellek dosyası yolunu belirtir.|  
|`StronglyTypedClassName`|İsteğe bağlı `String` parametresi.<br /><br /> Kesin türü belirtilmiş kaynak sınıfı için sınıf adını belirtir. Bu parametre belirtilmezse, kaynak dosyasının temel adı kullanılır.|  
|`StronglyTypedFilename`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Kaynak dosya için dosya adını belirtir. Bu parametre belirtilmezse, sınıfın adını dile bağımlı uzantılı temel dosya adı olarak kullanılır. Örneğin: `MyClass.cs`.|  
|`StronglyTypedLanguage`|İsteğe bağlı `String` parametresi.<br /><br /> Kesin türü belirtilmiş kaynak sınıfı kaynağı oluşturulurken kullanılacak dili belirtir. Bu parametre CodeDomProvider tarafından kullanılan dilleri tam olarak birine eşleşmesi gerekir. Örneğin: `VB` veya `C#`.<br /><br /> Bu parametre için bir değer geçirerek kesin türü belirtilmiş kaynakları oluşturmak için görev isteyin.|  
|`StronglyTypedManifestPrefix`|İsteğe bağlı `String` parametresi.<br /><br /> Kesin türü belirtilmiş kaynağı için oluşturulan sınıf kaynak olarak kullanmak için kaynak ad alanı veya bildirimi önekini belirtir.|  
|`StronglyTypedNamespace`|İsteğe bağlı `String` parametresi.<br /><br /> Kesin türü belirtilmiş kaynak için oluşturulan sınıf kaynağı için kullanılacak ad alanını belirtir. Bu parametre belirtilmezse, tüm kesin türü belirtilmiş genel ad alanında kaynaklardır.|  
|`TLogReadFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur parametresi.<br /><br /> İzleme günlükleri okuma temsil eden öğeleri dizisini alır.|  
|`TLogWriteFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur parametresi.<br /><br /> Yazma temsil eden öğeleri dizisi günlükleri izleme alır.|  
|`ToolArchitecture`|İsteğe bağlı <xref:System.String?displayProperty=fullName> parametresi.<br /><br /> Tracker.exe ResGen.exe oluşturma için kullanılacak gerekli olup olmadığını belirlemek için kullanılır.<br /><br /> Üye için parsable olmalıdır <xref:Microsoft.Build.Utilities.ExecutableType> numaralandırması. Varsa `String.Empty`, varsayılan mimarisi belirlemek için buluşsal yöntemi kullanır. Microsoft.Build.Utilities.ExecutableType numaralandırma üyesi için parsable olmalıdır.|  
|`TrackerFrameworkPath`|İsteğe bağlı `String` parametresi.<br /><br /> FileTracker.dll içeren uygun .NET Framework konumun yolunu belirtir.<br /><br /> Ayarlama, kullanıcı emin olmak için sorumluluk sürerse geçirirler FileTracker.dll verileri kullanmayı düşündüğünüz ResGen.exe verileri eşleşir. Aksi durumda kümesi, görevin geçerli .NET Framework sürümlerine göre uygun konuma karar verir.|  
|`TrackerLogDirectory`|İsteğe bağlı `String` parametresi.<br /><br /> Bu görev çalışmasını izleme günlükleri yer alır Ara dizinini belirtir.|  
|`TrackerSdkPath`|İsteğe bağlı `String` parametresi.<br /><br /> Tracker.exe içeren uygun Windows SDK konumun yolunu belirtir.<br /><br /> Ayarlama, kullanıcı emin olmak için sorumluluk sürerse geçirirler Tracker.exe verileri kullanmayı düşündüğünüz ResGen.exe verileri eşleşir. Aksi durumda kümesi, görev geçerli Windows SDK'sı üzerinde göre uygun konuma karar verir.|  
|`TrackFileAccess`|İsteğe bağlı <xref:System.Boolean> parametresi.<br /><br /> TRUE ise, giriş dosyasının dizin göreli dosya yolları çözümlemek için kullanılır.|  
|`UseSourcePath`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, giriş dosyası dizini göreli dosya yolları çözümlemek için kullanılması gerektiğini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 .Resx dosyaları diğer kaynak dosyalara içerebileceğinden yalnızca çıkışları güncel olup olmadığını görmek için .resx ve .resource dosya zaman damgalarını karşılaştırmak yeterli değil. Bunun yerine, `GenerateResource` görev .resx dosyaları bağlantıları izler ve bağlantılı dosyaları da damgalarının denetler. Genellikle kullanılamaz, yani `Inputs` ve `Outputs` hedef bulunduğu öznitelikleri `GenerateResource` görev Bu, aslında çalıştırılması gereken zaman Atlanan neden.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
 MSBuild 4.0 hedef .NET 3.5 projelerine kullanırken, yapı x86 üzerinde başlatılamayabilir kaynaklar. Bu sorunu geçici olarak çözmek için hedef AnyCPU derleme olarak oluşturabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `GenerateResource` tarafından belirtilen dosyalarından .resources dosyaları oluşturmak için görev `Resx` öğe koleksiyonu.  
  
```xml  
<GenerateResource  
    Sources="@(Resx)"  
    OutputResources="@(Resx->'$(IntermediateOutputPath)%(Identity).resources')">  
    <Output  
        TaskParameter="OutputResources"  
        ItemName="Resources"/>  
</GenerateResource>  
```  
  
 `GenerateResource` Görev kullanır \<LogicalName > meta verilerini bir \<EmbeddedResource > öğesi bir derlemede katıştırılmış kaynağın adı.  
  
 Aşağıdaki kod, myAssembly adlı derleme varsayılarak someQualifier.someResource.resources adlı katıştırılmış bir kaynağı oluşturur:  
  
```xml  
<ItemGroup>   <EmbeddedResource Include="myResource.resx">       <LogicalName>someQualifier.someResource.resources</LogicalName>   </EmbeddedResource></ItemGroup>  
```  
  
 Olmadan \<LogicalName > meta veriler kaynak adlı myAssembly.myResource.resources.  Bu örnek yalnızca Visual Basic ve Visual C# derleme işlemi için geçerlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
