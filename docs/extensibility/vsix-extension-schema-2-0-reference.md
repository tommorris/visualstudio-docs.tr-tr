---
title: VSIX uzantı şema 2.0 başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- vsix
- extension schema
ms.assetid: 0da81b98-f5e3-40d3-ba9a-94551378d0b4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 090ebd4abd7905816393a211dc817d28348611ed
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089376"
---
# <a name="vsix-extension-schema-20-reference"></a>VSIX Uzantı Şeması 2.0 Başvurusu
VSIX dağıtım bildirim dosyası VSIX paket içeriğini açıklar. Dosya biçimi, bir şema tarafından yönetilir. Özel türler ve öznitelikler ekleyerek bu şemayı 2.0 sürümünü destekler.  Bildirim şeması genişletilebilir. Bildirim yükleyicisi XML öğeleri ve onu anlamıyor öznitelikleri yoksayar.  
  
> [!IMPORTANT]
>  Visual Studio 2015, Visual Studio 2010, Visual Studio 2012 veya Visual Studio 2013 biçimleri VSIX dosyalarında yükleyebilirsiniz.  
  
## <a name="package-manifest-schema"></a>Paket bildirim şeması  
 Bildirim XML dosyası kök öğesinin `<PackageManifest>`, tek bir özniteliği olan `Version`, bildirim biçimi sürümünü olduğu. Sürüm biçimi biçimine önemli değişiklikler yaptıysanız değiştirilir. Ayarlayarak bildiriminde belirtilen bildirim biçimi sürüm 2.0, bu konuda açıklanmaktadır `Version` öznitelik değeri sürüm "2.0" =.  
  
### <a name="packagemanifest-element"></a>PackageManifest öğesi  
 İçinde `<PackageManifest>` kök öğesi, aşağıdaki öğeleri kullanabilirsiniz:  
  
-   `<Metadata>` -Meta verileri ve reklam bilgileri paket hakkında. Yalnızca bir `Metadata` bildiriminde öğesine izin verilir.  
  
-   `<Installation>` -Bu bölümde içine yükleyebilmek için uygulama SKU'ları da dahil olmak üzere bu uzantı paketinin yüklenebilir biçimini tanımlar. Yalnızca tek bir `Installation` bildiriminde öğesine izin verilir. Bir bildirim olmalıdır bir `Installation` öğesi ya da bu paketin tüm SKU yüklemek olmaz.  
  
-   `<Dependencies>` -Bu paket için bağımlılıklar isteğe bağlı bir listesi aşağıda tanımlanmıştır.  
  
-   `<Assets>` -Bu bölümde, tüm bu paket içinde yer alan ve varlıkları içerir. Bu bölümde bu paketi herhangi bir içerik yüzey olmaz.  
  
-   `<AnyElement>*` -Bildirim şema diğer öğeleri izin vermek için yeterince esnektir. Bildirim yükleyicisi tarafından tanınmayan herhangi bir alt öğe Uzantı Yöneticisi API'si fazladan XmlElement nesneler olarak sunulur. Bu alt öğeleri kullanarak VSIX uzantıları, Visual Studio'da çalışan kodu çalışma zamanında erişmek için bildirim dosyasında ek veri tanımlayabilirsiniz. Bkz: <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.AdditionalElements%2A> ve <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.LocalizedAdditionalElements%2A>.  
  
### <a name="metadata-element"></a>Meta veri öğesi  
 Bu bölüm, paket kimliğini ve bilgi reklam hakkındaki meta verileri değildir. `<Metadata>` Aşağıdaki öğeleri içerir:  
  
-   `<Identity>` -Bu, bu paket için kimlik bilgilerini tanımlar ve aşağıdaki öznitelikleri içerir:  
  
    -   `Id` -Bu öznitelik, yazarı tarafından seçilen paket için benzersiz bir kimliği olmalıdır. CLR Türleri namespaced olduğu gibi Ad nitelendirilmesi gerekir: Company.Product.Feature.Name. `Id` Özniteliği 100 karakter ile sınırlıdır.  
  
    -   `Version` -Bu sürümü bu paketi ve içeriğini tanımlar. Bu öznitelik CLR derleme sürümü oluşturma biçimdedir: Major.Minor.Build.Revision (1.2.40308.00). Daha yüksek bir sürüm numarası olan bir pakete pakete yapılan güncelleştirmeler olarak kabul edilir ve varolan yüklü olan sürümü yüklenebilir.  
  
    -   `Language` -Bu öznitelik paketi için varsayılan dildir ve bu bildiriminde metinsel verilere karşılık gelir. Örneğin kaynak derlemeler için bu öznitelik CLR yerel ayar kodu kuralını izler: en-us, tr, fr-fr. Belirleyebileceğiniz `neutral` herhangi bir Visual Studio sürümü üzerinde çalışacak bir dilden uzantısı bildirmek için. Varsayılan değer `neutral` şeklindedir.  
  
    -   `Publisher` -Bu öznitelik, bir şirket veya bireysel adı bu paketin yayımcısı tanımlar. `Publisher` Özniteliği 100 karakter ile sınırlıdır.  
  
-   `<DisplayName>` -Bu öğe Uzantı Yöneticisi Arabiriminde görüntülenen kullanıcı dostu paket adını belirtir. `DisplayName` İçerik 50 karakterle sınırlıdır.  
  
-   `<Description>` -Bu isteğe bağlı Uzantı Yöneticisi Arabiriminde görüntülenen kısa bir açıklamasını paketi ve içeriğini bir öğedir. `Description` İçerik istiyor, ancak bunun herhangi bir metin içerebilir 1000 karakter ile sınırlıdır.  
  
-   `<MoreInfo>` -Bu isteğe bağlı öğe, bu paket tam açıklamasını içeren bir sayfaya çevrimiçi URL'dir. Protokolü olarak http belirtilmelidir.  
  
-   `<License>` -Bu isteğe bağlı pakette yer alan bir lisans dosyası (.txt, .rtf) için göreli bir yol bir öğedir.  
  
-   `<ReleaseNotes>` -Bu isteğe bağlı bir sürüm notları'nı görüntüleyen bir Web sitesi URL'si için yoksa paketi (.txt, .rtf) içinde yer alan bir sürüm notları dosya için göreli yol bir öğedir.  
  
-   `<Icon>` -Bu isteğe bağlı pakette yer alan bir görüntü dosyası (png, bmp, jpeg, ICO) için göreli bir yol bir öğedir. Simge görüntüsü 32 x 32 piksel olmalıdır (ya da bu boyut küçültülebilir) ve kullanıcı Arabirimi listview içinde görüntülenir. Öyle değilse `Icon` öğesi belirtilmediyse, varsayılan kullanıcı arabirimini kullanır.  
  
-   `<PreviewImage>` -Bu isteğe bağlı bir göreli yol pakette yer alan bir görüntü dosyasına (png, bmp, jpeg) bir öğedir. Önizleme görünümü 200 x 200 piksel olmalıdır ve Ayrıntılar kullanıcı Arabirimi görüntülenir. Öyle değilse `PreviewImage` öğesi belirtilmediyse, varsayılan kullanıcı arabirimini kullanır.  
  
-   `<Tags>` -Bu isteğe bağlı öğe arama ipuçları için kullanılan ek noktalı virgülle ayrılmış metin etiketleri listeler. `Tags` Öğesi 100 karakter ile sınırlıdır.  
  
-   `<GettingStartedGuide>` -Bu isteğe bağlı bir HTML dosyasına göreli bir yol ya da bir uzantı veya bu paketin içindeki içeriğin nasıl kullanılacağı hakkında bilgi içeren bir Web sitesi URL'si için bir öğedir. Bu kılavuz, yüklemenin bir parçası olarak başlatılır.  
  
-   `<AnyElement>*` -Bildirim şema diğer öğeleri izin vermek için yeterince esnektir. Bildirim yükleyicisi tarafından tanınmayan herhangi bir alt öğe XmlElement nesneleri listesi olarak sunulur. Bu alt öğeleri kullanılarak, VSIX uzantıları bildirim dosyasında ek verileri tanımlamak ve çalışma zamanında numaralandırır.  
  
### <a name="installation-element"></a>Yükleme öğesi  
 Bu bölümde, bu paket yüklenebilir yolu ve içine yükleyebilmek için uygulama SKU'ları tanımlar. Bu bölümde aşağıdaki öznitelikleri içerir:  
  
-   `Experimental` -Bu özniteliği tüm kullanıcılar için şu an yüklü olan uzantı varsa, ancak güncelleştirilmiş bir sürümünü aynı bilgisayara geliştirdiğiniz true olarak ayarlayın. Örneğin, tüm kullanıcılar için MyExtension 1.0 yüklü, ancak aynı bilgisayarda MyExtension 2.0 hata ayıklama, Experimental ayarlamak istediğiniz "true" =. Bu, Visual Studio 2015 güncelleştirme 1'de kullanılabilir ve sonraki özniteliğidir.  
  
-   `Scope` -Bu öznitelik değerini "Genel" veya "ProductExtension" alabilir:  
  
    -   "Genel" yükleme için belirli bir SKU kapsamlı olmayan belirtir. Örneğin, bir uzantı SDK yüklendiğinde, bu değer kullanılır.  
  
    -   "ProductExtension" tek tek Visual Studio SKU'ları için kapsamlı bir geleneksel VSIX uzantısı (sürüm 1.0) yüklü olduğunu belirtir. Varsayılan değer budur.  
  
-   `AllUsers` -Bu isteğe bağlı öznitelik tüm kullanıcılar için bu paketin yüklü olup olmadığını belirtir. Varsayılan olarak, bu öznitelik paketi kullanıcı başına olduğunu belirten, false'tur. (Bu değeri true olarak ayarlayın, yüklemeyi gerçekleştiren kullanıcının sonuç VSIX yüklemek için yönetimsel ayrıcalık düzeyine Yükselt gerekir.  
  
-   `InstalledByMsi` -İsteğe bağlı bu öznitelik, bir MSI tarafından bu paketin yüklü olup olmadığını belirtir. Bir MSI tarafından yüklenen paketler yüklü ve MSI (Programlar ve Özellikler) ve değil Visual Studio uzantısı Yöneticisi tarafından yönetilir.  Varsayılan olarak, bu öznitelik tarafından bir MSI paketin yüklü olmadığını belirtir, false'tur.  
  
-   `SystemComponent` -İsteğe bağlı bu özniteliği, bu paketi bir sistem bileşeni ele alınması gerekip gerekmediğini belirtir. Sistem bileşenleri Uzantı Yöneticisi Arabiriminde gösterme ve güncelleştirilemiyor. Varsayılan olarak, bu paket sistem bileşeni değil belirten false özniteliğidir.  
  
-   `AnyAttribute*` - `Installation` Öğesi çalışma zamanında bir ad-değer çifti sözlüğü olarak sunulan öznitelikleri uçlu bir dizi kabul eder.  
  
-   `<InstallationTarget>` -Bu öğe burada VSIX Yükleyici paketi yükler konumu denetler. Varsa değerini `Scope` özniteliktir "ProductExtension" Paket içeriğini kendi kullanılabilirlik uzantılarını tanıtmak için bir parçası olarak bir bildirim dosyası tarafından yüklenen bir SKU hedef gerekir. `<InstallationTarget>` Öğeye sahip aşağıdaki durumlarda öznitelikleri `Scope` özniteliğine sahip açık veya varsayılan değer "ProductExtension":  
  
    -   `Id` -Bu öznitelik paket tanımlar.  Ad alanı kuralı öznitelik izler: Company.Product.Feature.Name. `Id` Özniteliği 100 karakter ile sınırlıdır ve yalnızca alfasayısal karakterler içerebilir. Beklenen değer:  
  
        -   Microsoft.VisualStudio.IntegratedShell  
  
        -   Microsoft.VisualStudio.Pro  
  
        -   Microsoft.VisualStudio.Premium  
  
        -   Microsoft.VisualStudio.Ultimate  
  
        -   Microsoft.VisualStudio.VWDExpress  
  
        -   Microsoft.VisualStudio.VPDExpress  
  
        -   Microsoft.VisualStudio.VSWinExpress  
  
        -   Microsoft.VisualStudio.VSLS  
  
        -   My.Shell.App  
  
    -   `Version` -Bu öznitelik, minimum ve maksimum desteklenen sürümleriyle bu SKU sürüm aralığı belirtir. Bir paket destekliyorsa SKU'ları sürümleri ayrıntı. Sürüm aralığı gösterimi [10.0-11.0] olduğu  
  
        -   [-en düşük sürüm (dahil) arasındadır.  
  
        -   ]-en yüksek sürüm (dahil) arasındadır.  
  
        -   (-özel en düşük sürümü.  
  
        -   )-en yüksek sürüm özel.  
  
        -   Tek sürüm # - yalnızca belirtilen sürümü.  
  
        > [!IMPORTANT]
        >  VSIX şema 2.0 sürümünü Visual Studio 2012'de sunulmuştur. Bu şemayı kullanmak için Visual Studio 2012 olmalıdır veya daha sonra makinede yüklü ve bu ürünün parçası olan VSIXInstaller.exe kullanın. Visual Studio 2012 veya sonraki VSIXInstaller, ancak yükleyici sonraki sürümlerini kullanarak yalnızca Visual Studio'nun önceki sürümleri hedefleyebilirsiniz.  
  
    -   `AnyAttribute*` - `<InstallationTarget>` Öğesi uçlu bir ad-değer çifti sözlüğü olarak çalışma zamanında gösterilmesine öznitelikler kümesi sağlar.  
  
### <a name="dependencies-element"></a>Bağımlılıklar öğesi  
 Bu öğe, bu paket bildiren bağımlılıkları listesini içerir. Bağımlılıkları belirtilirse, bu paketleri (tarafından tanımlanan kendi `Id`) olmalıdır önce yüklendi.  
  
-   `<Dependency>` Öğe - bu alt öğesi aşağıdaki özniteliklere sahiptir:  
  
    -   `Id` -Bu öznitelik için bağımlı paketi benzersiz bir kimliği olmalıdır. Bu kimlik değeri eşleşmelidir `<Metadata><Identity>Id` bu paket bağlı bir paketin özniteliği. `Id` Özniteliği olan ad alanı kuralını izler: Company.Product.Feature.Name. Öznitelik 100 karakter ile sınırlıdır ve yalnızca alfasayısal karakterler içerebilir.  
  
    -   `Version` -Bu öznitelik, minimum ve maksimum desteklenen sürümleriyle bu SKU sürüm aralığı belirtir. Bir paket destekliyorsa SKU'ları sürümleri ayrıntı. Sürüm aralığı gösterimi [12,0, 13.0], burada:  
  
        -   [-en düşük sürüm (dahil) arasındadır.  
  
        -   ]-en yüksek sürüm (dahil) arasındadır.  
  
        -   (-özel en düşük sürümü.  
  
        -   )-en yüksek sürüm özel.  
  
        -   Tek sürüm # - yalnızca belirtilen sürümü.  
  
    -   `DisplayName` -Bu öznitelik iletişim kutuları ve hata iletileri gibi kullanıcı Arabirimi öğeleri kullanılan bağımlı paketi görünen adıdır. Bağımlı paketi tarafından MSI yüklenmediği sürece özniteliği isteğe bağlıdır.  
  
    -   `Location` -Bu isteğe bağlı öznitelik göreli yolun iç içe geçmiş VSIX paketi için bu VSIX içinde veya bağımlılık indirme konumu için bir URL belirtir. Bu öznitelik, önkoşul paketini bulun kullanıcının yardımcı olmak için kullanılır.  
  
    -   `AnyAttribute*` - `Dependency` Öğesi çalışma zamanında bir ad-değer çifti sözlüğü olarak sunulan öznitelikleri uçlu bir dizi kabul eder.  
  
### <a name="assets-element"></a>Varlıklar öğesi  
 Bu öğe bir listesini içeren `<Asset>` her uzantı veya içerik öğesi için etiketler ortaya bu paketin.  
  
-   `<Asset>` -Bu öğe aşağıdaki öznitelikler ve öğeler içerir:  
  
    -   `Type` -Uzantısı ya da bu öğesi tarafından temsil edilen içerik türü budur. Her `<Asset>` öğesinin tek bir olmalı `Type`, ancak birden çok `<Asset>` öğeleri aynı olabilir `Type`. Bu öznitelik bir tam ad ad alanı kurallarına göre temsil. Bilinen türleri şunlardır:  
  
        1.  Microsoft.VisualStudio.VsPackage  
  
        2.  Microsoft.VisualStudio.MefComponent  
  
        3.  Microsoft.VisualStudio.ToolboxControl  
  
        4.  Microsoft.VisualStudio.Samples  
  
        5.  Microsoft.VisualStudio.ProjectTemplate  
  
        6.  Microsoft.VisualStudio.ItemTemplate  
  
        7.  Microsoft.VisualStudio.Assembly  
  
         Kendi türlerinizi oluşturabilir ve bunları benzersiz adlar verin. Visual Studio içindeki çalışma zamanında kodunuzu numaralandırır ve bu özel türler Uzantı Yöneticisi API aracılığıyla erişim.  
  
    -   `Path` -Dosya veya klasör varlığı içeren paketin içinde göreli yolu.  
    
    -   `TargetVersion` -içinde belirtilen varlık uygulandığı sürüm aralığı. Visual Studio farklı sürümlerini varlıklarına birden fazla sürümünü sevkiyat için kullanılır. Olabilmesi Visual Studio 2017.3 veya üstünü gerektirir.
  
    -   `AnyAttribute*` -Bir ad-değer çifti sözlüğü olarak çalışma zamanında gösterilmesine öznitelikleri uçlu bir dizi.  
  
         `<AnyElement>*` -Herhangi bir yapılandırılmış içerik arasında izin verilen bir `<Asset>` başlar ve bitiş etiketi. Tüm öğeleri XmlElement nesneleri listesi olarak sunulur. VSIX uzantıları bildirim dosyasında yapılandırılmış türe özgü meta veriler tanımlayabilir ve çalışma zamanında numaralandırır.  
  
### <a name="sample-manifest"></a>Örnek bildirimi  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">  
  <Metadata>  
    <Identity Id="0000000-0000-0000-0000-000000000000" Version="1.0" Language="en-US" Publisher="Company" />  
    <DisplayName>Test Package</DisplayName>  
    <Description>Information about my package</Description>  
    <MoreInfo>http://www.fabrikam.com/Extension1/</MoreInfo>  
    <License>eula.rtf</License>  
    <ReleaseNotes>notes.txt</ReleaseNotes>  
    <Icon>Images\icon.png</Icon>  
    <PreviewImage>Images\preview.png</PreviewImage>  
  </Metadata>  
  <Installation InstalledByMsi="false" AllUsers="false" SystemComponent="false" Scope="ProductExtension">  
    <InstallationTarget Id="Microsoft.VisualStudio.Pro" Version="[11.0, 12.0]" />  
  </Installation>  
  <Dependencies>  
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="[4.5,)" />  
    <Dependency Id="Microsoft.VisualStudio.MPF.12.0" DisplayName="Visual Studio MPF 12.0" d:Source="Installed" Version="[12.0]" />  
  </Dependencies>  
  <Assets>  
    <Asset Type="Microsoft.VisualStudio.VsPackage" d:Source="Project" d:ProjectName="%CurrentProject%" Path="|%CurrentProject%;PkgdefProjectOutputGroup|" />  
  </Assets>  
</PackageManifest>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Uzantıları Gönderme](../extensibility/shipping-visual-studio-extensions.md)
