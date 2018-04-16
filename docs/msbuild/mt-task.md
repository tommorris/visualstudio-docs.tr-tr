---
title: MT görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCManifestTool.ResourceOutputFileName
- VC.Project.VCManifestTool.SuppressDependencyElement
- VC.Project.VCManifestTool.ManifestFromManagedAssembly
- VC.Project.VCManifestTool.GenerateCategoryTags
- VC.Project.VCManifestTool.EnableDPIAwareness
- vc.task.mt
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBUILD (Visual C++), MT task
- MT task (MSBuild (Visual C++))
ms.assetid: bb94913c-1042-4968-9f08-b394518e899f
caps.latest.revision: 6
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8a9bdfcd391a6377abf1d750330bb1a0dbd8bf80
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="mt-task"></a>MT Görevi
Microsoft Bildirimi aracı sarmalar mt.exe. Daha fazla bilgi için "Mt.exe" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **MT** görev. Çoğu görevi parametreleri ve parametreleri, birkaç kümelerini bir komut satırı seçeneğine karşılık gelir.  
  
> [!NOTE]
>  Bir tire mt.exe belgelerine kullanır (**-**) komut satırı seçenekleri, ancak bu konu öneki bir eğik çizgi kullandıkça (**/**). Ya da öneki kabul edilebilir.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**AdditionalManifestFiles**|İsteğe bağlı **String []** parametresi.<br /><br /> Bir veya daha fazla bildirim dosya adını belirtir.<br /><br /> Daha fazla bilgi için bkz: **/bildirimi** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**AdditionalOptions**|İsteğe bağlı **dize** parametresi.<br /><br /> Komut satırı seçeneklerinin listesi. Örneğin, "*/option1 /option2 /option#*". Diğer tarafından temsil edilmez komut satırı seçeneklerini belirtmek için bu parametreyi kullanın **MT** görev parametresi.<br /><br /> Daha fazla bilgi için "Mt.exe" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**AssemblyIdentity**|İsteğe bağlı **dize** parametresi.<br /><br /> Öznitelik değerlerini belirtir **assemblyIdentity** bildiriminin öğesi. İlk bileşen değerini bulunduğu bir virgülle ayrılmış listesini belirtin `name` özniteliği, formu sahip bir veya daha fazla ad/değer çiftleri tarafından izlenen  *\<öznitelik adı > < attribute_value > =*.<br /><br /> Daha fazla bilgi için bkz: **/identity** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**ComponentFileName**|İsteğe bağlı **dize** parametresi.<br /><br /> .rgs veya .tlb dosyaları oluşturmak istiyorsanız dinamik bağlantı kitaplığı adını belirtir. Belirtirseniz, bu parametre gereklidir **RegistrarScriptFile** veya **TypeLibraryFile** MT görevi parametreleri.<br /><br /> Daha fazla bilgi için bkz: **/dll** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**DependencyInformationFile**|İsteğe bağlı **dize** parametresi.<br /><br /> Bildirim aracı için yapı bağımlılık bilgileri izlemek için Visual Studio tarafından kullanılan bağımlılık bilgi dosyasını belirtir.|  
|**EmbedManifest**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, bildirim dosyası derlemeye katıştırır. Varsa `false`, tek başına bir bildirim dosyası oluşturur.|  
|**EnableDPIAwareness**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, uygulamayı DPI olarak işaretler bildirim bilgi ekler. DPI uygulaması yazma, çok çeşitli yüksek DPI görüntü ayarları arasında tutarlı bir şekilde iyi görünen bir kullanıcı arabirimi sağlar.<br /><br /> Daha fazla bilgi için "Yüksek DPI" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**GenerateCatalogFiles**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, katalog tanımı (.cdf) dosyaları oluşturur.<br /><br /> Daha fazla bilgi için bkz: **/makecdfs** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**GenerateCategoryTags**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, kategori etiketleri oluşturulmasına neden olur. Bu parametre ise `true`, **ManifestFromManagedAssemblyMT** görev parametresi de belirtilmelidir.<br /><br /> Daha fazla bilgi için bkz: **/Category** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**InputResourceManifests**|İsteğe bağlı **dize** parametresi.<br /><br /> Belirtilen tanımlayıcıya sahip RT_MANIFEST türünde bir kaynak bildirimden girin. Bir kaynak formunun belirtin *\<dosyası >[***;***[***#***]<resource_id>]*, isteğe bağlı `resource_id` parametredir negatif olmayan, 16 bit sayısı.<br /><br /> Öyle değilse `resource_id` belirtilirse, CREATEPROCESS_MANIFEST_RESOURCE varsayılan değeri (1) kullanılır.<br /><br /> Daha fazla bilgi için bkz: **/inputresource** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**ManifestFromManagedAssembly**|İsteğe bağlı **dize** parametresi.<br /><br /> Belirtilen yönetilen derlemesinden bir bildirim oluşturur.<br /><br /> Daha fazla bilgi için bkz: **/managedassemblyname** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**ManifestToIgnore**|İsteğe bağlı **dize** parametresi.<br /><br /> (Kullanılmaz.)|  
|**OutputManifestFile**|İsteğe bağlı **dize** parametresi.<br /><br /> Çıktı bildirim adını belirtir. Bu parametre atlanırsa ve yalnızca bir bildirimi üzerinde çalıştırılır, bu bildirim yerinde değiştirilir.<br /><br /> Daha fazla bilgi için bkz: **/out** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**OutputResourceManifests**|İsteğe bağlı **dize** parametresi.<br /><br /> Belirtilen tanımlayıcıya sahip RT_MANIFEST türünde bir kaynak bildirime çıktı. Kaynak, biçimidir *\<dosyası>[***;***[***#***]<resource_id >]*, isteğe bağlı `resource_id` parametredir negatif olmayan, 16 bit sayısı.<br /><br /> Öyle değilse `resource_id` belirtilirse, CREATEPROCESS_MANIFEST_RESOURCE varsayılan değeri (1) kullanılır.<br /><br /> Daha fazla bilgi için bkz: **/outputresource** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**RegistrarScriptFile**|İsteğe bağlı **dize** parametresi.<br /><br /> Kayıtsız COM bildirim desteğini kullanmak için Kaydedici betik (.rgs) dosya adını belirtir.<br /><br /> Daha fazla bilgi için bkz: **/rgs** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**ReplacementsFile**|İsteğe bağlı **dize** parametresi.<br /><br /> Kaydedici betik (.rgs) dosyasındaki değiştirilebilir dizeleri değerlerini içeren dosyayı belirtir.<br /><br /> Daha fazla bilgi için bkz: **/replacements** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**ResourceOutputFileName**|İsteğe bağlı **dize** parametresi.<br /><br /> Proje çıktı bildirimi katıştırmak için kullanılan çıkış kaynak dosyasını belirtir.|  
|**Kaynakları**|İsteğe bağlı `ITaskItem[]` parametresi.<br /><br /> Bildirim kaynağı dosyaların boşluklarla ayrılmış bir listesini belirtir.<br /><br /> Daha fazla bilgi için bkz: **/bildirimi** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**SuppressDependencyElement**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, bir bildirim olmadan dependency öğesi oluşturur. Bu parametre ise `true`, ayrıca belirtin **ManifestFromManagedAssemblyMT** görev parametresi.<br /><br /> Daha fazla bilgi için bkz: **/nodependency** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**SuppressStartupBanner**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.<br /><br /> Daha fazla bilgi için bkz: **/nologo** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**TrackerLogDirectory**|İsteğe bağlı `String` parametresi.<br /><br /> Bu görev için izleme günlüklerinin depolandığı Ara dizini belirtir.|  
|**TypeLibraryFile**|İsteğe bağlı **dize** parametresi.<br /><br /> Tür kitaplığı (.tlb) dosyasının adını belirtir. Bu parametre belirtirseniz, ayrıca belirtmeniz **ComponentFileNameMT** görev parametresi.<br /><br /> Daha fazla bilgi için bkz: **TLB** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
|**UpdateFileHashes**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, karma değeri tarafından belirtilen yoldaki tüm dosyaların hesaplar **UpdateFileHashesSearchPathMT** görev parametresi ve değeri güncelleştirmeleri **karma** özniteliği**dosya** hesaplanan değeri kullanarak bildirim öğesidir.<br /><br /> Daha fazla bilgi için bkz: **/hashupdate** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi. Ayrıca bkz. **UpdateFileHashesSearchPath** bu tabloda parametresi.|  
|**UpdateFileHashesSearchPath**|İsteğe bağlı `String` parametresi.<br /><br /> Dosya karmalarını güncelleştirildiğinde kullanılan arama yolu belirtir. Bu parametresiyle kullanmak **UpdateFileHashesMT** görev parametresi.<br /><br /> Daha fazla bilgi için bkz: **UpdateFileHashes** bu tabloda parametresi.|  
|**VerboseOutput**|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, ayrıntılı hata ayıklama bilgileri görüntüler.<br /><br /> Daha fazla bilgi için bkz: **/ verbose** "Mt.exe içinde" seçeneğini [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)