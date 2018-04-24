---
title: GenerateDeploymentManifest görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateDeploymentManifest
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateDeploymentManifest task
- GenerateDeploymentManifest task [MSBuild]
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1eb989972f8cfd2e44516b798c25e5f579e5f66
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="generatedeploymentmanifest-task"></a>GenerateDeploymentManifest Görevi

Oluşturan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] , tanımlayıcı dağıtım özellikleri yükleme veya uygulama belirtme çevrimiçi moda gibi ayarları ve güncelleştirme konumları, dağıtım bildirimi dağıtımı için benzersiz bir kimlik tanımlayarak bir uygulamanın dağıtımı açıklanır ve karşılık gelen belirten [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi.

## <a name="parameters"></a>Parametreler

Aşağıdaki tabloda parametrelerini açıklar `GenerateDeploymentManifest` görev.

|Parametre|Açıklama|
|---------------|-----------------|
|`AssemblyName`|İsteğe bağlı `String` parametresi.<br /><br /> Belirtir `Name` üretilen bildirim için derleme kimlik alanı. Bu parametre belirtilmezse, ad alanından algılanır `EntryPoint` veya `InputManifest` parametreleri. Görev adı çıkarsanamıyor, bir hata oluşturur.|
|`AssemblyVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Belirtir `Version` üretilen bildirim için derleme kimlik alanı. Bu parametre belirtilmezse, görev "1.0.0.0" değeri kullanır.|
|`CreateDesktopShortcut`|İsteğe bağlı `Boolean` parametresi.<br /><br /> TRUE ise, simge masaüstünde ClickOnce Uygulama yükleme sırasında oluşturuldu.|
|`DeploymentUrl`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama için güncelleştirme konumunu belirtir. Bu parametre belirtilmezse, hiçbir güncelleştirme konumu uygulama için tanımlanır. Ancak, varsa `UpdateEnabled` parametresi `true`, güncelleştirme konumu belirtilmelidir. Belirtilen değeri tam bir URL veya UNC yolu olmalıdır.|
|`Description`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama için isteğe bağlı bir açıklama belirtir.|
|`DisallowUrlActivation`|İsteğe bağlı `Boolean` parametresi.<br /><br /> URL yoluyla açıldığında uygulama otomatik olarak çalıştırılıp çalıştırılmayacağını belirtir. Bu parametre ise `true`, uygulamanın yalnızca Başlat menüsünden başlatılabilir. Bu parametrenin varsayılan değeri `false`. Yalnızca bu girişi geçerlidir `Install` parametre değeri `true`.|
|`EntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Giriş noktası için oluşturulan bildirim derleme gösterir. İçin bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi, bu girişi belirtir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi.<br /><br />Varsa `EntryPoint` görev parametresi belirtilmezse, `<customHostSpecified>` etiketi bir alt öğesi olarak eklenen `<entryPoint>` etiketi, örneğin:<br /><br /> `<entryPoint xmlns="urn:schemas-`<br /><br /> `microsoft-com:asm.v2">`<br /><br /> `<co.v1:customHostSpecified />`<br /><br /> `</entryPoint>`<br /><br /> Aşağıdaki adımları kullanarak uygulama bildirimine DLL bağımlılıklar ekleyebilirsiniz:<br /><br /> 1.  Derleme başvuruları çağrısıyla çözümlemek <xref:Microsoft.Build.Tasks.ResolveAssemblyReference>.<br />2.  Önceki görev ve derleme çıktısı geçirmek için <xref:Microsoft.Build.Tasks.ResolveManifestFiles>.<br />3.  Kullanarak bağımlılıkları geçirmek `Dependencies` parametresi <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>.|
|`ErrorReportUrl`|İsteğe bağlı <xref:System.String?displayProperty=fullName> parametresi.<br /><br /> İletişim kutularında ClickOnce yüklemeleri sırasında görüntülenen Web sayfasının URL'sini belirtir.|
|`InputManifest`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Bildirim oluşturucu için bir temel olarak hizmet verecek bir girdi XML belgesi gösterir. Bu çıktı bildiriminde yansıtılması özel bildirim tanımları gibi yapılandırılmış verileri sağlar. XML belgesi kök öğesinde bir derleme düğümü asmv1 ad alanında olması gerekir.|
|`Install`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Uygulamanın yüklü bir uygulama veya bir yalnızca çevrimiçi uygulama olup olmadığını belirtir. Bu parametre ise `true`, uygulama kullanıcının başlangıç menüsünde yüklenmiş ve Program Ekle veya Kaldır iletişim kutusunu kullanarak kaldırılabilir. Bu parametre ise `false`, uygulama bir Web sayfasından çevrimiçi kullanıma yöneliktir. Bu parametrenin varsayılan değeri `true`.|
|`MapFileExtensions`|İsteğe bağlı `Boolean` parametresi.<br /><br /> .Deploy dosya adı uzantısı eşleme kullanılıp kullanılmayacağını belirtir. Bu parametre ise `true`, her program dosyası .deploy dosya adı uzantısı ile yayımlanır. Web sunucunuzun güvenliğini sağlamak için engelinin kaldırılması gerekir dosya adı uzantılarını sayısını sınırlamak bu seçenek kullanışlıdır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama dağıtımı. Bu parametrenin varsayılan değeri `false`.|
|`MaxTargetPath`|İsteğe bağlı `String` parametresi.<br /><br /> Bir dosya yolu uzunluğu izin verilen belirtir bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama dağıtımı. Bu parametre belirtilmezse, uygulamadaki her dosya yolunun uzunluğu bu sınırınızı denetlenir. Sınırı aşan tüm öğeleri bir yapı uyarısına neden olur. Bu giriş belirtilmemiş ya da sıfır hiçbir denetimi gerçekleştirilir.|
|`MinimumRequiredVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Kullanıcıyı güncelleştirmeyi atlayabilirsiniz olup olmadığını belirtir. Kullanıcı, gerekli en düşük'dan küçük bir sürüm varsa, kendisinin güncelleştirme atlamak için seçeneğiniz vardır değil. Bu giriş yalnızca zaman geçerlidir değerini `Install` parametresi `true`.|
|`OutputManifest`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Oluşturulan çıktı bildirim dosyasının adını belirtir. Bu parametre belirtilmezse, çıktı dosyası adını üretilen bildirim kimlikten algılanır.|
|`Platform`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulamanın hedef platformu belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `AnyCPU`<br />-   `x86`<br />-   `x64`<br />-   `Itanium`<br /><br /> Varsayılan değer `AnyCPU` şeklindedir.|
|`Product`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulamanın adını belirtir. Bu parametre belirtilmezse, adı üretilen bildirim kimlikten algılanır. Bu ad Başlat menüsündeki kısayol adı için kullanılan ve Program Ekle veya Kaldır iletişim kutusunda görünen adı bir parçasıdır.|
|`Publisher`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama yayımcısının belirtir. Bu parametre belirtilmezse, adı kayıtlı kullanıcı veya üretilen bildirim kimliğini algılanır. Bu ad Başlat menüsündeki klasör adı için kullanılan ve Program Ekle veya Kaldır iletişim kutusunda görünen adı bir parçasıdır.|
|`SuiteNamel`|İsteğe bağlı `String` parametresi.<br /><br /> ClickOnce dağıtımı uygulamayı nerede olduğunu Başlat menüsündeki klasörünün adını belirtir.|
|`SupportUrl`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama için Program Ekle veya Kaldır iletişim kutusunda görünür bağlantıyı belirtir. Belirtilen değeri tam bir URL veya UNC yolu olmalıdır.|
|`TargetCulture`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama kültürünü tanımlar ve belirtir `Language` üretilen bildirim için derleme kimlik alanı. Bu parametre belirtilmezse, uygulama sabit kültür olduğu varsayılır.|
|`TrustUrlParameters`|İsteğe bağlı `Boolean` parametresi.<br /><br /> URL sorgu dizesi parametreleri uygulamaya kullanılabilir olması olup olmadığını belirtir. Bu parametrenin varsayılan değeri `false`, belirten parametreleri uygulamaya kullanılabilir olmayacak.|
|`UpdateEnabled`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Uygulama güncelleştirmeleri etkinleştirilip etkinleştirilmediğini gösterir. Bu parametrenin varsayılan değeri `false`. Bu parametre yalnızca zaman geçerlidir değerini `Install` parametresi `true`.|
|`UpdateInterval`|İsteğe bağlı `Int32` parametresi.<br /><br /> Uygulama için güncelleştirme aralığını belirtir. Bu parametrenin varsayılan değeri sıfırdır. Bu parametre yalnızca zaman geçerlidir değerlerini `Install` ve `UpdateEnabled` parametreleridir her ikisi de `true`.|
|`UpdateMode`|İsteğe bağlı `String` parametresi.<br /><br /> Uygulama başlatıldığında veya uygulama arka planda çalışan önce güncelleştirmelerin ön planda seçili olup olmadığını belirtir. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `Foreground`<br />-   `Background`<br /><br /> Bu parametrenin varsayılan değeri `Background`. Bu parametre yalnızca zaman geçerlidir değerlerini `Install` ve `UpdateEnabled` parametreleridir her ikisi de `true`.|
|`UpdateUnit`|İsteğe bağlı `String` parametresi.<br /><br /> İçin birimleri belirleyen `UpdateInterval` parametresi. Bu parametre aşağıdaki değerlere sahip olabilir:<br /><br /> -   `Hours`<br />-   `Days`<br />-   `Weeks`<br /><br /> Bu parametre yalnızca zaman geçerlidir değerlerini `Install` ve `UpdateEnabled` parametreleridir her ikisi de `true`.|

## <a name="remarks"></a>Açıklamalar

Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.GenerateManifestBase> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Task sınıfı parametrelerinin listesi için bkz: [görev taban sınıfı](../msbuild/task-base-class.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Görevler](../msbuild/msbuild-tasks.md)  
[GenerateApplicationManifest Görevi](../msbuild/generateapplicationmanifest-task.md)  
[SignFile Görevi](../msbuild/signfile-task.md)  
[Görev başvurusu](../msbuild/msbuild-task-reference.md)