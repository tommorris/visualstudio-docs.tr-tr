---
title: "Görüntü kitaplığı Görüntüleyicisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d9c7fbb-ebae-4b20-9dd8-3c9070c0d0d1
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3da2368d8d30ba54dd6b4ae6a36aba6e75ea2967
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="image-library-viewer"></a>Görüntü kitaplığı Görüntüleyicisi
Visual Studio görüntü kitaplığı Görüntüleyicisi aracı yükleme ve görüntü bildirimleri, kullanıcının Visual Studio olduğu gibi yönlendirme izin arayın. Kullanıcı, arka plan, boyutları, DPI, yüksek karşıtlık ve diğer ayarları değiştirebilir. Araç ayrıca her görüntü bildirimi yükleme bilgilerini görüntüler ve görüntü bildiriminde her görüntü kaynağı bilgilerini görüntüler. Bu aracı için yararlıdır:  
  
1.  Hatalarını tanılama  
  
2.  Özel görüntü bildirimleri sağlama öznitelikleri doğru şekilde ayarlanması  
  
3.  Visual Studio uzantısı Visual Studio stilini sığacak görüntüleri kullanabilmesi için Visual Studio Görüntü Kataloğu resimleri arama  
  
 ![Görüntü kitaplığı Görüntüleyicisi kahramanı](../../extensibility/internals/media/image-library-viewer-hero.png "görüntü kitaplığı Görüntüleyicisi kahramanı")  
  
 **Görüntü ad**  
  
 Bir görüntü bilinen ad (veya kısaca takma ad) bir görüntü varlığı veya görüntü listesi varlık Resim Kitaplığı'ndaki benzersiz olarak tanımlayan bir GUID:ID çiftidir.  
  
 **Görüntü bildirim dosyaları**  
  
 Görüntü bildirimi (.imagemanifest) dosyaları görüntü varlıklar, bu varlıkları ve gerçek görüntü ya da her varlık temsil görüntüleri temsil adlar kümesini tanımlayan XML dosyalarıdır. Eski kullanıcı Arabirimi desteği görüntü listeleri veya görüntü bildirimleri tek başına görüntüleri tanımlayabilirsiniz. Ayrıca, varlık veya ayrı ayrı görüntülere her varlık arkasında olduğunda ve bu varlıkları nasıl görüntülendiğini değiştirmek için ayarlanabilen özniteliği vardır.  
  
 **Görüntü bildirim şeması**  
  
 Bir tam görüntü bildirimi şöyle görünür:  
  
```xml  
<ImageManifest>  
      <!-- zero or one Symbols elements -->  
      <Symbols>  
        <!-- zero or more Guid, ID, or String elements -->  
      </Symbols>  
      <!-- zero or one Images elements -->  
      <Images>  
        <!-- zero or more Image elements -->  
      </Images>  
      <!-- zero or one ImageLists elements -->  
      <ImageLists>  
        <!-- zero or more ImageList elements -->  
      </ImageLists>  
</ImageManifest>  
```  
  
 **Semboller**  
  
 Okunabilirlik ve bakıma yardımcı olmak gibi görüntü bildirimi sembolleri öznitelik değerleri kullanabilirsiniz. Simgeler şu şekilde tanımlanır:  
  
```xml  
<Symbols>  
      <Import Manifest="manifest" />  
      <Guid Name="ShellCommandGuid" Value="8ee4f65d-bab4-4cde-b8e7-ac412abbda8a" />  
      <ID Name="cmdidSaveAll" Value="1000" />  
      <String Name="AssemblyName" Value="Microsoft.VisualStudio.Shell.UI.Internal" />  
</Symbols>  
```  
  
|||  
|-|-|  
|**Alt öğe**|**Tanım**|  
|İçeri aktarma|Geçerli bildirimi kullanmak için belirtilen bildirim dosyası simgelerini alır.|  
|Guid|Simgenin bir GUID temsil eder ve GUID biçimlendirme eşleşmesi gerekir.|  
|Kimlik|Simgenin bir Kimliğini temsil eder ve negatif olmayan bir tamsayı olmalıdır.|  
|Dize|Simgenin bir isteğe bağlı bir dize değeri temsil eder.|  
  
 Büyük küçük harfe duyarlı ve başvurulan $(symbol-name) sözdizimini kullanarak simgeler şunlardır:  
  
```xml  
<Image Guid="$(ShellCommandGuid)" ID="$(cmdidSaveAll)" >  
      <Source Uri="/$(AssemblyName);Component/Resources/image.xaml" />  
</Image>  
```  
  
 Bazı simgeleri tüm bildirimler için önceden tanımlanmıştır. Bu URI özniteliğinde kullanılabilir \<kaynak > veya \<alma > öğesi başvurusu yollara yerel makine üzerinde.  
  
|||  
|-|-|  
|**Simgesi**|**Açıklama**|  
|CommonProgramFiles|% CommonProgramFiles % ortam değişkeninin değeri|  
|LocalAppData|% LocalAppData % ortam değişkeninin değeri|  
|ManifestFolder|Bildirim dosyasını içeren klasör|  
|MyDocuments|Geçerli kullanıcının Belgelerim klasörün tam yolunu|  
|ProgramFiles|% ProgramFiles % ortam değişkeni değeri|  
|Sistem|Windows\System32 klasöründe|  
|WinDir|% WinDir % ortam değişkeni değeri|  
  
 **Görüntü**  
  
 \<Görüntü > öğesi bir bilinen ad tarafından başvurulan bir görüntü tanımlar. Birlikte ele alındığında kimliği ve GUID görüntü ad oluşturur. Görüntü için ad tüm görüntü kitaplığı arasında benzersiz olması gerekir. Bir verilen ad birden çok görüntü varsa, kitaplık derlenirken hatalarla karşılaşıldı birinci tutulur adrestir.  
  
 En az bir kaynak içermelidir. Boyutu Tarafsız kaynakları çok çeşitli boyutlarda arasında en iyi sonuçlar verir ancak bunlar gerekli değildir. Hizmet tanımlı olmayan bir boyutu görüntüsü için sorulan varsa \<Görüntü > öğesi ve boyutu Tarafsız kaynağı yok, hizmet en iyi boyutu özgü kaynağını seçin ve istenen boyuta ölçeklendirin.  
  
```xml  
<Image Guid="guid" ID="int" AllowColorInversion="true/false">  
      <Source ... />  
      <!-- optional additional Source elements -->  
</Image>  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|Guid|[Gerekli] Görüntü ad GUID bölümünü|  
|Kimlik|[Gerekli] Görüntü ad kimliği bölümünü|  
|AllowColorInversion|[İsteğe bağlı, varsayılan true] Görüntünün koyu bir arka plan üzerinde kullanıldığında program aracılığıyla ters renklerini sahip olup olamayacağını gösterir.|  
  
 **Kaynak**  
  
 \<Kaynak > öğesi (XAML ve PNG) tek bir görüntü kaynağı varlık tanımlar.  
  
```xml  
<Source Uri="uri" Background="background">  
      <!-- optional NativeResource element -->  
 </Source>  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|URI|[Gerekli] Gelen görüntünün nerede yüklenebilir tanımlayan bir URI. Aşağıdakilerden biri olabilir:<br /><br /> -A [Pack URI](http://msdn.microsoft.com/en-US/library/aa970069\(v=vs.100\).aspx) uygulamasını kullanarak: / / / yetkilisi<br /><br /> -Bir mutlak bileşen kaynak başvurusu<br /><br /> -Yerel kaynak içeren bir dosya yolu|  
|Arka Plan|[İsteğe bağlı] Ne tür bir arka plan kaynak kullanılması amaçlanmıştır gösterir.<br /><br /> Aşağıdakilerden biri olabilir:<br /><br /> - *Açık*: kaynağı açık bir arka plan üzerinde kullanılabilir.<br /><br /> - *Koyu*: kaynağı koyu bir arka plan üzerinde kullanılabilir.<br /><br /> - *Yüksek Karşıtlık*: kaynağı yüksek karşıtlık modunda herhangi bir arka plan üzerinde kullanılabilir.<br /><br /> - *HighContrastLight*: Kaynak açık bir arka plan yüksek karşıtlık modunda kullanılabilir.<br /><br /> -*HighContrastDark*: kaynak koyu arka plan yüksek karşıtlık modunda kullanılabilir.<br /><br /> Varsa **arka plan** özniteliği atlanırsa, kaynağı herhangi bir arka plan üzerine kullanılabilir.<br /><br /> Varsa **arka plan** olan *açık*, *koyu*, *HighContrastLight*, veya *HighContrastDark*, hiçbir zaman ters kaynağının renkler. Varsa **arka plan** atlanmış veya kümesine *Yüksek Karşıtlık*, kaynağın renkleri ters çevirmeyi görüntünün tarafından denetlenen **AllowColorInversion** özniteliği.|  
  
 A \<kaynak > öğesi aşağıdaki isteğe bağlı alt öğeleri tam olarak birine sahip olabilir:  
  
||||  
|-|-|-|  
|**Öğesi**|**Öznitelikler (tüm gerekli)**|**Tanım**|  
|\<Boyutu >|Değer|Kaynak görüntüleri verilen boyutta (aygıt birimleri) için kullanılır. Görüntü kare olur.|  
|\<SizeRange >|MinSize, MaxSize|Kaynak görüntülerden MinSize MaxSize (birimlerindeki aygıt) için ikisi de dahil olmak kullanılır. Görüntü kare olur.|  
|\<Boyutlar >|Genişlik, yükseklik|Kaynak belirtilen genişlik ve yükseklik (aygıt birimleri), görüntüleri için kullanılır.|  
|\<DimensionRange >|Değeri, MinHeight MinWidth,<br /><br /> MaxWidth, MaxHeight|Kaynak için en küçük genişliği/yüksekliğinin görüntülere (aygıt birimlerindeki) en büyük genişliği/yüksekliğinin ikisi de dahil olmak kullanılır.|  
  
 A \<kaynak > öğesi de isteğe bağlı bir olabilir \<NativeResource > tanımlar alt öğe bir \<kaynak > yönetilen bir derleme yerine yerel bir derleme yüklenir.  
  
```xml  
<NativeResource Type="type" ID="int" />  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|Tür|[Gerekli] XAML veya PNG yerel kaynak türü|  
|Kimlik|[Gerekli] Yerel kaynak tamsayı kimliği bölümünü|  
  
 **ImageList**  
  
 \<ImageList > öğesi içinde tek bir Şerit döndürülebilecek görüntüleri koleksiyonunu tanımlar. Şerit isteğe bağlı olarak, gerektiği gibi yerleşik olarak bulunur.  
  
```xml  
<ImageList>  
      <ContainedImage Guid="guid" ID="int" External="true/false" />  
      <!-- optional additional ContainedImage elements -->  
 </ImageList>  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|Guid|[Gerekli] Görüntü ad GUID bölümünü|  
|Kimlik|[Gerekli] Görüntü ad kimliği bölümünü|  
|Harici|[İsteğe bağlı, varsayılan false] Görüntü ad görüntüyü geçerli bildiriminde başvuruda bulunup bulunmadığını gösterir.|  
  
 Kapsanan görüntüsü için ad, geçerli bildiriminde tanımlanan bir görüntü başvurmak yok. Kapsanan görüntünün görüntü kitaplığı'nda bulunamazsa boş yer tutucu görüntüsü onun yerine kullanılır.  
  
## <a name="how-to-use-the-tool"></a>Aracı nasıl kullanılır  
 **Özel görüntü bildirim doğrulanıyor**  
  
 Özel bir bildirimi oluşturmak için otomatik olarak üret bildirim ManifestFromResources araç kullanmanızı öneririz. Özel bildirimi doğrulamak için görüntü kitaplığı görüntüleyiciyi Başlat ve dosyayı seçin > arama dizinlerinin iletişim kutusunu açmak için yolları belirle.... Aracı görüntü bildirimlerini yüklemek için arama dizinlerinin kullanır, ancak bunu da kullanır, bir bildirim görüntüleri içeren .dll dosyaları bulmak için bu nedenle yapmanız hem bildirim hem de DLL dizinler bu iletişim kutusunda eklediğinizden emin olun.  
  
 ![Görüntü kitaplığı Görüntüleyicisi arama](../../extensibility/internals/media/image-library-viewer-search.png "görüntü kitaplığı Görüntüleyicisi arama")  
  
 Tıklatın **Ekle...**  bildirimleri ve bunların karşılık gelen dll aramak için yeni arama dizinlerinin seçin. Aracı bu arama dizinleri unutmayın ve bunlar üzerinde veya denetleme veya bir dizin işaretleyerek açılabilir.  
  
 Varsayılan olarak, Visual Studio yükleme dizini bulmak ve bu dizinlerin arama dizinleri listesine eklemek aracı deneyecek. El ile aracı bulamadığı dizinler ekleyebilirsiniz.  
  
 Geçiş yapmak için tüm bildirimler yüklenen sonra aracı kullanılabilir **arka plan** renkler, **DPI**, **Yüksek Karşıtlık**, veya **ölçeklendirme** için görüntüleri böylece kullanıcı bunlar işlenirken doğru için çeşitli ayarları doğrulamak için görüntü varlıklarının görsel olarak inceleyebilirsiniz.  
  
 ![Görüntü kitaplığı Görüntüleyicisi arka plan](../../extensibility/internals/media/image-library-viewer-background.png "görüntü kitaplığı Görüntüleyicisi arka plan")  
  
 Arka plan rengi, hafif, koyu veya özel bir değer ayarlanabilir. "Özel renk" seçerek bir renk seçimi iletişim kutusunu açın ve bu özel renk kolay geri çağırma daha sonra için arka plan açılan kutusunun altına ekleyin.  
  
 ![Görüntü kitaplığı Görüntüleyicisi özel renk](../../extensibility/internals/media/image-library-viewer-custom-color.png "görüntü kitaplığı Görüntüleyicisi özel renk")  
  
 Bir görüntü ad seçerek, sağdaki görüntü Ayrıntılar bölmesinde o ad arkasında gerçek her görüntü bilgilerini görüntüler. Bölmesinde Ayrıca kullanıcıların bir bilinen ad adıyla veya ham GUID:ID değer kopyalamak imkan tanır.  
  
 ![Görüntü kitaplığı Görüntüleyicisi görüntü ayrıntıları](../../extensibility/internals/media/image-library-viewer-image-details.png "görüntü kitaplığı Görüntüleyicisi görüntü ayrıntıları")  
  
 Her görüntü kaynağı için görüntülenen bilgileri konulu olabilir olup olmadığını, görüntülemek için arka plan türlerini içerir veya yüksek karşıtlık, hangi boyutları için geçerli destekler veya boyutu Tarafsız olup ve görüntünün yerel bir derlemeden mı geldiği.  
  
 ![Görüntü kitaplığı Görüntüleyicisi için tema](../../extensibility/internals/media/image-library-viewer-can-theme.png "resim kitaplığı Görüntüleyicisi tema olabilir")  
  
 Bir görüntü bildirimi doğrularken bildirimi ve görüntü gerçek konumlarına DLL'de dağıtmanızı öneririz. Bu, tüm göreli yollar düzgün çalıştığından ve resim kitaplığı bulmak ve bildirim ve görüntü DLL yük doğrular.  
  
 **Görüntü Kataloğu KnownMonikers arama**  
  
 Visual Studio stil daha iyi eşleştirmek için Visual Studio uzantısı Visual Studio Görüntü Kataloğu yerine oluşturma ve kendi görüntülerini kullanabilirsiniz. Bu görüntüleri tutmak zorunda değil avantajına sahiptir ve şuna Visual Studio destekleyen tüm DPI ayarların doğru şekilde görüntü yüksek DPI yedekleme görüntü sahip olduğunu güvence altına alır.  
  
 Görüntü kitaplığı Görüntüleyicisi böylece kullanıcı bir görüntü varlığını temsil eder bilinen ad bulabilir ve bu bilinen adı kullanma aranacak bir bildirim sağlar. Görüntüler için arama yapmak istediğiniz bir arama terimi arama kutusuna girin ve Enter tuşuna basın. Durum çubuğu altındaki ne kadar eşleşme toplam görüntüleri dışında tüm bildirimleri bulundu görüntüler.  
  
 ![Görüntü kitaplığı Görüntüleyicisi filtre](../../extensibility/internals/media/image-library-viewer-filter.png "görüntü kitaplığı Görüntüleyicisi filtresi")  
  
 Görüntü adlar mevcut bildirimlerinde aranırken aramak ve yalnızca Visual Studio görüntü katalog adlar, özellikle genel olarak erişilebilir diğer adlar veya kendi özel adlar kullanmak öneririz. Ortak olmayan adlar kullanırsanız, özel kullanıcı Arabirimi kopmuş olabilir veya bu ortak olmayan adlar ve görüntüleri değiştirilmiş veya güncelleştirildiğinde, görüntüleri beklenmedik bir şekilde mı yoksa değiştirilmiştir.  
  
 Ayrıca, GUID ile arama mümkündür. Bu, bildirim bildiriminin tek alt birden çok GUID'yi içerir veya bu arama türü tek bir bildirim listesine aşağı filtreleme için yararlı olur.  
  
 ![Görüntü kitaplığı Görüntüleyicisi filtre GUID](../../extensibility/internals/media/image-library-viewer-filter-guid.png "kitaplığı Görüntüleyicisi filtre GUID görüntü")  
  
 Son olarak, Kimliğine göre arama da mümkündür.  
  
 ![Görüntü kitaplığı Görüntüleyicisi filtre kimliği](../../extensibility/internals/media/image-library-viewer-filter-id.png "görüntü kitaplığı Görüntüleyicisi filtre kimliği")  
  
## <a name="notes"></a>Notlar  
  
-   Varsayılan olarak, Visual Studio yükleme dizininde mevcut birkaç görüntü bildirimlerinde aracı çeker. Genel olarak tüketilebilir adlar sahip olan tek **Microsoft.VisualStudio.ImageCatalog** bildirimi. GUID: ae27a6b0-e345-4288-96df-5eaf394ee369 (yapmak **değil** özel bildiriminde bu GUID geçersiz kılmak) türü: KnownMonikers  
  
-   Aracı, uygulama gerçekte görünmesi birkaç saniye sürebilir şekilde bulduğu tüm görüntü bildirimlerini yüklemek için başlatılırken çalışır. Ayrıca bildirimleri yüklenirken yavaş veya yanıt vermeyen olması olabilir.  
  
## <a name="sample-output"></a>Örnek Çıktı  
 Bu aracı, herhangi bir çıktı üretmez.