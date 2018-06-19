---
title: XML komutu tablosu tasarlama (. Vsct) dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, designing
ms.assetid: bb87a322-bac4-4258-92bc-9a876f05d653
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 865baa3f7b4b0fe4cbbaf2cdf34e9e8041d5c121
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133367"
---
# <a name="designing-xml-command-table-vsct-files"></a>XML komutu tablosu tasarlama (. Vsct) dosyaları
Bir XML komutu tablosu (.vsct) dosyası bir VSPackage komutu öğelerinin görünümünü ve düzeni açıklar. Komut öğeleri düğmeler, birleşik giriş kutuları, menüler, araç çubukları ve komut öğe gruplarını içerir. Bu konuda, XML komut tablo dosyaları, komut öğeleri ve menüleri nasıl etkilediklerini ve bunların nasıl oluşturulacağı açıklanmaktadır.

## <a name="commands-menus-groups-and-the-vsct-file"></a>Komutlar, menüler, grupları ve .vsct dosyası
 .vsct dosyaları komutlar, menüler ve komut grupları düzenlenmiştir. XML etiketleri .vsct dosyasındaki komut düğmeleri, komut yerleşimi ve bit eşlemler gibi diğer ilişkili öğeleri yanı sıra bu öğelerin her birini temsil eder.

 Çalıştırarak yeni VSPackage oluşturduğunuzda [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] paketi şablonu şablon gerekli öğeler .vsct dosyasıyla menü komutu, araç penceresi veya özel bir düzenleyici, seçimlerinize bağlı olarak oluşturur. Bu .vsct dosyası, belirli bir VSPackage gereksinimlerini karşılamak için daha sonra değiştirilebilir. .Vsct dosyasının nasıl değiştirileceğini örnekleri görmek için örneklerde [genişletme menüleri ve komutları](../../extensibility/extending-menus-and-commands.md).

 Yeni, boş .vsct dosyası oluşturmak için bkz: [nasıl yapılır: oluşturmak bir. Vsct dosya](../../extensibility/internals/how-to-create-a-dot-vsct-file.md). XML öğeleri, öznitelikleri ve değerleri oluşturduktan sonra komutu öğesi düzenini açıklamak için dosyaya ekleyin. Ayrıntılı bir XML şeması için bkz: [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md).

## <a name="differences-between-ctc-and-vsct-files"></a>.Ctc ve .vsct dosyaları arasındaki farklar
 Şimdi de .ctc dosya biçimi kullanım dışı .vsct dosyasındaki XML etiketleri arkasında anlamı aynı olmasına karşın, bunların biraz farklı bir uygulamasıdır.

-   Yeni  **\<extern >** etiketi olduğu için olanlar gibi derlenecek diğer .h dosyaları başvuru nerede [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] araç.

-   Destek .vsct dosyaları sırada **/ dahil** deyimi, .ctc dosyaları gibi aynı zamanda özelliklerine yeni bir \< **alma >** öğesi. Fark vardır, **/ dahil** getirdiği **tüm** bilgi ancak \< **alma >** yalnızca adlarında getirir.

-   Önişlemci yönergeleri tanımlayan bir üstbilgi dosyası .ctc dosyalar gerektirir, ancak bir .vsct dosyaları için gerekli değildir. Bunun yerine, yönergeleri bulunan sembol tablosunu koyun  **\<simgesi >** .vsct dosyanın sonunda bulunan öğeler.

-   .vsct dosyaları özelliği bir  **\<ek açıklama >** istediğiniz notları veya hatta resimler gibi herhangi bir bilgi katıştırmak izin veren etiketi.

-   Değerler, öğenin öznitelikleri olarak depolanır.

-   Komut bayrakları ayrı ayrı depolanan veya yığın.  IntelliSense, yığılmış komutu bayrakları ancak çalışmaz. Komut bayrakları hakkında daha fazla bilgi için bkz: [komutu bayrağı öğesi](../../extensibility/command-flag-element.md).

-   Bölünmüş bırakmalar, birleşik vb. gibi birden çok türlerini belirtebilirsiniz.

-   GUID'ler doğrulamaz.

-   Her kullanıcı Arabirimi öğesi ile görüntülenen metni temsil eden bir dize içeriyor.

-   Üst isteğe bağlıdır. Belirtilmezse, "Grubu Bilinmeyen" değeri kullanılır.

-   Simge bağımsız değişken isteğe bağlıdır.

-   Bit eşlem bölüm--bir .ctc aynı dosya, bir dosya adı vsct.exe derleyici tarafından derleme zamanında çekebilir href aracılığıyla artık belirtebilirsiniz dışında.

-   ResID--eski bit eşlem kaynak kimliği kullanılabilir ve hala aynı .ctc dosyaları olduğu gibi çalışır.

-   HRef--bit eşlem kaynağı için bir dosya adı belirtmenize olanak tanır yeni bir yöntem. Kullanılan bölümüne atlayabilirsiniz şekilde tüm kullanılan olduğunu varsayar. Derleyici hiçbir ağ paylaşımları üzerindeki sonra dosya için yerel kaynak ve /I anahtar tarafından tanımlanan tüm kaynaklar için ilk arar.

-   KeyBinding--Artık bir öykünücü belirtmeniz gerekir. Birini belirtirseniz derleyici Düzenleyicisi ve öykünücüsü aynı olduğunu varsayar.

-   Keychord--bırakıldı. Yeni biçimi Key1, Değişiklik1, Key2, Mod2 şeklindedir.  Bir karakter, onaltılık veya VK sabiti belirtebilirsiniz.

 Yeni derleyici, vsct.exe, .ctc ve .vsct dosyalarını derler. Eski ctc.exe derleyici ancak tanıması ne .vsct dosyalarını derlemek.

 Var olan bir .cto dosyasını bir .vsct dosyasına dönüştürmek için vsct.exe derleyici kullanabilirsiniz. Bu konu hakkında daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak bir. Mevcut bir kümeden Vsct dosyası. Teknolojiden dosya](../../extensibility/internals/how-to-create-a-dot-vsct-file.md#how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file).

## <a name="the-vsct-file-elements"></a>.Vsct dosya öğeleri
 Komut tablo aşağıdaki hiyerarşi ve öğeleri vardır:

 [CommandTable öğesi](../../extensibility/commandtable-element.md) — tüm komutlar, menü grupları ve VSPackage ile ilişkili menüleri temsil eder.

 [Extern öğesi](../../extensibility/extern-element.md) — .vsct dosyasıyla Birleştir istediğiniz dış .h dosyaları başvuruyor.

 [Öğe dahil](../../extensibility/include-element.md) — istediğiniz your.vsct dosyası ile birlikte derlemek için herhangi bir ek üstbilgi (.h) dosya başvuruyor. .Vsct dosya komutları, menü grupları ve menüleri IDE veya başka bir VSPackage sağlayan tanımlayın sabitleri içeren .h dosyaları içerebilir.

 [Komutları öğesi](../../extensibility/commands-element.md) — yürütülebilir ayrı komutların tümünü gösterir. Her komut aşağıdaki dört alt öğeleri içerir:

 [Menü öğesi](../../extensibility/menus-element.md) — tüm menüleri ve araç çubuklarını VSPackage temsil eder. Menü komutları grupları için kapsayıcı görevi görür.

 [Öğesi grupları](../../extensibility/groups-element.md) — tüm VSPackage gruplarının temsil eder. Gruplar tek tek komutların koleksiyonlarıdır.

 [Düğme öğesi](../../extensibility/buttons-element.md) — tüm komut düğmeleri ve VSPackage menü öğeleri temsil eder. Düğme komutları ile ilişkilendirilebilen visual denetimleridir.

 [Bit eşlemler öğesi](../../extensibility/bitmaps-element.md) — tüm VSPackage düğmeleri için bit eşlemler tümünün temsil eder. Bit eşlemler yanındaki veya bağlam bağlı olarak komut düğmeleri görüntüleme resimleri ' dir.

 [CommandPlacements öğesi](../../extensibility/commandplacements-element.md) — burada bireysel komutları tarihli, VSPackage menülerde belirtir ek konumları.

 [VisibilityConstraints öğesi](../../extensibility/visibilityconstraints-element.md) — olsun veya olmasın bir komut görüntüler hiç kez ya da belirli iletişim kutusu veya penceresi görüntülendiğinde gibi yalnızca belirli bağlamlarında, belirtir. Belirtilen bağlam etkin olduğunda menüleri ve bu öğe için bir değere sahip komutları görüntüler. Komutu her zaman görüntülemek için varsayılan davranıştır.

 [Taşıyan öğesi](../../extensibility/keybindings-element.md) — komutları anahtar herhangi bağlamaları belirtir. Gibi komutu çalıştırmak için basılan gereken diğer bir deyişle, bir veya daha fazla tuş bileşimlerini **CTRL + S**.

 [UsedCommands öğesi](../../extensibility/usedcommands-element.md) — Informs [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ortamı geçerli VSPackage etkin olduğunda belirtilen komut başka bir kod tarafından uygulanan karşın, bu komutu uygulamasını sağlar.

 `Symbols Element` — Sembol adları ve GUID kimlikleri için paketinde, komutların tümünü içerir.

## <a name="vsct-file-design-guidelines"></a>. Vsct dosya tasarım yönergeleri
 Başarıyla .vsct dosya tasarlamak için aşağıdaki yönergeleri izleyin.

-   Komutları yalnızca gruplarında yerleştirilebilir, gruplar yalnızca menülerde yerleştirilebilir ve menüleri yalnızca gruplarında yerleştirilebilir. Komutları değildir ve yalnızca menüler gerçekte grupları IDE içinde görüntülenir.

-   Alt menüler menüye doğrudan atanamaz, ancak bir menüye sırayla atanan bir gruba atanması gerekir.

-   Bir ana öğe grubu veya kendi tanımlama yönergesi üst alanındaki kullanarak menü komutları, alt menüler ve grupları atanabilir.

-   Bir komut tabloda yalnızca yönergeleri üst alanları düzenleme önemli bir kısıtlaması vardır. Nesneleri tanımlamak yönergeleri yalnızca bir üst bağımsız değişkeni alabilir.

-   Kendi ile yeni bir nesne örneğini oluşturmak için yeni bir yönerge kullanılmasını gerektiren komutlar, grupları veya alt menüler yeniden `GUID:ID` çifti.

-   Her `GUID:ID` çifti benzersiz olmalıdır. Örneğin, bir menüsünde bir araç veya bir bağlam menüsündeki yerleştirildi bir komutu yeniden tarafından işlenir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi.

-   Komutlar ve alt menüler de atanabilir birden çok gruba ve grupları kullanarak birden çok menüleri atanabilir [komutları öğesi](../../extensibility/commands-element.md).

## <a name="vsct-file-notes"></a>. Vsct dosya Notlar
 Derlemeniz hem yerel bir uydu DLL yerleştirin sonra .vsct dosyasına herhangi bir değişiklik yaparsanız, çalışması gerektiğini **devenv.exe/Setup /nosetupvstemplates**. Bunun yapılması zorlar Deneysel kayıt defterini okunmasına ve açıklar iç veritabanı belirtilen VSPackage kaynakları [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yeniden oluşturulması için.

 Geliştirme sırasında oluşturulabilir ve IDE içinde kafa karıştırıcı dağınıklığı açabilir Deneysel kayıt defteri kovanında kayıtlı birden çok VSPackage projeleri için mümkündür. Bu sorunu gidermek için tüm kayıtlı VSPackages ve IDE yaptığınız değişiklikleri kaldırmak için varsayılan ayarlarına Deneysel hive sıfırlayabilirsiniz. Deneysel hive sıfırlamak için Visual Studio SDK ile birlikte gelen CreateExpInstance.exe aracını kullanın. Konumunda bulabilirsiniz

 **%PROGRAMFILES(x86)%\Visual Studio \<version> SDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe**

 Komut satırını kullanarak aracı çalıştırın **CreateExpInstance/reset**. Bu araç, normalde yüklenmiş tüm kayıtlı VSPackages Deneysel kovanından kaldırır unutmayın [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="see-also"></a>Ayrıca Bkz.
 [Menüleri ve Komutlari Genişletme](../../extensibility/extending-menus-and-commands.md)