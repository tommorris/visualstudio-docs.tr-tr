---
title: Visual Studio'da kod yapısını görüntüleme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.documentoutline.window
- vs.objectbrowser
- vs.classview
- VS.CodeDefinitionView
- VS.CodeDefinitionWindow
- vs.componentpicker
- vs.callbrowser
helpviewer_keywords:
- document outline window.
- Visual Studio, object browser
- call hierarchy
- Visual Studio, document outline window
- code definition window [Visual Studio]
- Visual Studio, class view
- Visual Studio, call hierarchy window
- class view
- object browser
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44e0d6527227dfb638452337d1978bcbede29ef4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="view-the-structure-of-code"></a>Kod yapısını görüntüleme

Nesne ve Visual Studio projeleri, .NET Framework bileşenlerini, COM bileşenleri, dinamik bağlantı kitaplığı (DLL) üyeler inceleyebilirsiniz ve kitaplıkları (TLB) yazın.

Aynı zamanda **Çözüm Gezgini** türleri ve sembolleri Ara projelerinizi üyelerinde göz atmak için bir yöntemin çağrı hiyerarşisi, Bul simge başvurularını ve birden çok araç pencereleri arasında geçiş yapmak zorunda kalmadan daha fazla bilgi görüntüleyin daha önce listelenen.

Visual Studio Enterprise varsa, çözümün tamamında arasında kodunuzu ve bağımlılıklarını yapısını görselleştirmek ve sizi ilgilendiren kod parçalarını aşağıya doğru incelemek için kod haritalarını kullanabilirsiniz. Daha fazla bilgi için bkz: [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md).

> [!NOTE]
> Visual Studio sürümü ve kullandığınız ayarlar IDE özelliklerinde etkileyebilir. Bunlar, bu konuda açıklanan kullanılanlardan farklı olabilir.

## <a name="class-view-visual-basic-c-c"></a>Sınıf Görünümü (Visual Basic, C# ' ta, C++)

**Sınıf Görünümü** parçası olarak gösterilen **Çözüm Gezgini** gibi ayrı bir pencerede yanı. **Sınıf görünümü** penceresi, bir uygulama öğelerini görüntüler. Üst bölmede ad alanlarını, türleri, arabirimler, numaralandırmalar ve sınıfları ve üst bölmede seçili türüne ait üyeleri alt bölmesinde görüntüler. Bu pencere kullanarak, kaynak kodu üye tanımlarında taşıyabilirsiniz (veya **Nesne Tarayıcısı** öğesi çözümünüzü dışında tanımlanmışsa).

Alt öğelerini görüntülemek için bir proje derleme gerekmez **sınıf görünümü**. Projenizde kodu değiştirirken penceresi yenilenir.

Kod projenize proje düğümüne ve seçerek ekleyebileceğiniz **Ekle** açmak için düğmeye **Yeni Öğe Ekle** iletişim kutusu. Kod ayrı bir dosyaya eklenir.

Projenizi kaynak kodu denetimi için işaretliyse, her **sınıf görünümü** öğesi dosya kaynak kodu durumunu belirten bir simge görüntülenir. Ortak kaynak kodu denetimi komutları gibi **kullanıma**, **iade**, ve **en son sürümü Al** öğesi için kısayol menüsünde de mevcuttur.

### <a name="class-view-toolbar"></a>Sınıf Görünümü araç çubuğu

Sınıf Görünümü araç aşağıdaki komutları içerir.

|||
|-|-|
|**Yeni klasör**|Bir sanal klasör veya sık kullanılan öğeleri düzenleyebilirsiniz alt klasör oluşturur. Bunlar etkin çözüm (.suo) dosyasına kaydedilir. Yeniden adlandırma veya öğenin kodunuzda sildikten sonra sanal bir klasörde bir hata düğümü olarak görünebilir. Bu sorunu düzeltmek için hata düğümü silin. Bir öğeyi yeniden adlandırdıysanız, bu proje hiyerarşiden klasöre yeniden taşıyabilirsiniz.|
|**Geri**|Daha önce seçilen öğeye gider.|
|**İlet**|Sonraki seçilen öğeye gider.|
|**Sınıf diyagramında görüntülemek** (yönetilen kod projeleri yalnızca)|Bir ad seçin veya yazın kullanılabilir duruma gelir **sınıf görünümü**. Bir ad alanı seçildiğinde, sınıf diyagramı içinde tüm türleri gösterilmektedir. Bir Türü seçildiğinde, sınıf diyagramı yalnızca o türünü gösterir.|

### <a name="class-view-settings"></a>Sınıf Görünümü Ayarları

**Sınıfı görünüm ayarlarını** araç çubuğunda, aşağıdaki ayarlara sahip.

|||
|-|-|
|**Taban türleri Göster**|Taban türleri görüntülenir.|
|**Türetilen türlerin Göster**|Türetilen türlerin görüntülenir.|
|**Gizli türleri ve üyeleri Göster**|Gizli türleri ve üyeleri (istemciler tarafından kullanılmaya değil) gri açık metin olarak görüntülenir.|
|**Genel üyeleri Göster**|Genel üyeler görüntülenir.|
|**Korumalı Üyeleri Göster**|Korumalı üyeleri görüntülenir.|
|**Özel üyeleri Göster**|Özel üyelerin görüntülenir.|
|**Diğer üyeleri Göster**|Diğer tür üye görüntülenir, iç dahil olmak üzere (veya Visual Basic arkadaş) üyeleri.|
|**Devralınan üyeleri Göster**|Devralınan üyeleri görüntülenir.|
|**Genişletme yöntemleri Göster**|Genişletme yöntemleri görüntülenir.|

### <a name="class-view-shortcut-menu"></a>Sınıf Görünümü kısayol menüsü

Kısayol menüsünde **sınıf görünümü** Seçili proje türüne bağlı olarak aşağıdaki komutları içerebilir.

|||
|-|-|
|**Tanıma gitme**|Öğesinin tanımı veya kaynak kodundaki bulan **Nesne Tarayıcısı**, öğesi açık projeye tanımlı değil.|
|**Tanımı Gözat**|Seçilen öğeyi görüntüler **Nesne Tarayıcısı**.|
|**Tüm başvuruları Bul**|Seçili nesne öğesi bulur ve sonuçları görüntüler bir **Bul sonuçları** penceresi.|
|**Filtre türü için** (yönetilen yalnızca kodu)|Yalnızca seçili türü veya ad alanı görüntüler. Filtre seçerek kaldırabilirsiniz **Temizle bulmak** (X) için İleri düğmesini **Bul** kutusu.|
|**Kopyala**|Öğenin tam adı kopyalar.|
|**Alfabetik olarak sıralamak**|Alfabetik olarak türleri ve üyeleri adına göre listelenmiştir.|
|**Üye türü göre sırala**|Türleri ve üyeleri türüne göre sırayla (sınıfları arabirimleri koyun, temsilciler arabirimleri koyun ve yöntemleri özellikleri koyun şekilde) listeler.|
|**Üye erişimi göre sırala**|Liste türleri ve üyeleri erişim sırayla, ortak veya özel gibi yazın.|
|**Üye türü göre Gruplandır**|Nesne türüne göre gruplara türleri ve üyeleri sıralar.|
|**Bildirim Git** (yalnızca C++ kodu)|Tür veya üye bildirimi varsa kaynak kodunu görüntüler.|
|**Tanıma gitme**|Tür veya üye tanımını varsa kaynak kodunu görüntüler.|
|**Başvuru gidin**|Bir başvuru türü veya üyesi kullanılabilir durumdaysa kaynak kodunda gösterir.|
|**Çağrı hiyerarşisini görüntüleme**|Seçili yönteminde görüntüler **çağrı hiyerarşisi** penceresi.|

## <a name="call-hierarchy-window-visual-basic-c-c"></a>Çağrı hiyerarşisi penceresi (Visual Basic, C# ' ta, C++)

**Çağrı hiyerarşisi** penceresi burada bir verilen yöntemi (veya özelliği veya oluşturucusu) adı verilir ve bu yönteminden çağrılan yöntemler listelenmiştir gösterir. Belirtilen bir kapsamda yöntemleri arasındaki arayan/Aranan ilişkiler gösterilmektedir arama grafiği birden çok düzeyi görüntüleyebilirsiniz.

Görüntüleyebileceğiniz **çağrı hiyerarşisi** bir yöntem (veya özellik veya oluşturucusu) seçerek ve ardından seçme penceresi **görünüm sınıf hiyerarşisi** kısayol menüsünde. Görüntü, aşağıdaki resimde benzemelidir.

![Çağrı hiyerarşisi birden çok düğümü açık](../ide/media/multiplenodes.png "MultipleNodes")

Araç çubuğundaki aşağı açılan listeyi kullanarak hiyerarşi kapsamını belirleyebilirsiniz: çözüm, geçerli projenin ya da geçerli belge.

Ana bölmede yöntemi gelen ve giden çağrıları görüntüler ve **çağrısı siteleri** bölmesi, seçilen arama konumunu görüntüler. Sanal ya da soyut, üyeleri için bir **geçersiz kılmaları yöntem adı** düğümü görüntülenir. Arabirim üyeleri için bir **uygulayan yöntem adı** düğümü görüntülenir.

**Çağrı hiyerarşisi** penceresi yöntemi, bir yöntem olay işleyici eklenir veya bir temsilciye atanmış yerler dahil grup başvuruları bulamazsa. Bu başvuruları bulmak için **tüm başvuruları Bul** komutu.

Kısayol menüsünde **çağrı hiyerarşisi** penceresinde aşağıdaki komutları içerir.

|||
|-|-|
|**Yeni bir kökü olarak Ekle**|Seçili düğümün yeni bir kök düğümü ekler.|
|**Kök Kaldır**|Seçili kök düğümü ağaç görünümü bölmesindeki kaldırır.|
|**Tanıma gitme**|Bir yöntem orijinal tanımına gider.|
|**Tüm başvuruları Bul**|Projede seçili yöntemine yönelik tüm başvuruları bulur.|
|**Kopyala**|Seçili düğümün (ancak, alt düğümleri) kopyalar.|
|**Yenileme**|Bilgileri yeniler.|

## <a name="BKMK_ObjectBrowser"></a> Nesne Tarayıcısı

**Nesne Tarayıcısı** penceresi projelerinizde kodu açıklamalarını görüntüler.

Pencerenin en üstünde açılan listeyi kullanarak görüntülemek istediğiniz bileşenleri filtreleyebilirsiniz. Özel bileşenler, yönetilen kod yürütülebilir dosyaları, kitaplık derlemeleri, tür kitaplıklarını ve .ocx dosya içerebilir. C++ özel bileşenleri eklemek mümkün değildir. Özel ayarlar, Visual Studio kullanıcı uygulama dizininde, % APPDATA%\Microsoft\VisualStudio\15.0\ObjBrowEX.dat kaydedilir.

Sol bölmesinde **Nesne Tarayıcısı** derlemeler gösterir. İçerdikleri ad alanları görüntülemek için derlemeleri genişletin ve içerdikleri türleri görüntülenecek ad alanları'nı genişletin. Bir türünü seçtiğinizde, üyelerine (örneğin, özellikleri ve yöntemleri) sağ bölmede listelenir. Sağ alt kısmında seçili öğe hakkında ayrıntılı bilgiler görüntüler.

Kullanarak belirli bir öğe için arama yapabilirsiniz **arama** pencerenin üstündeki kutusu. Aramalar büyük/küçük harfe duyarsızdır. Arama sonuçları, sol bölmede görüntülenir. Bir aramayı temizlemek için tercih **Aramayı Temizle** (X) için İleri düğmesini **arama** kutusu.

**Nesne Tarayıcısı** yaptığınız seçimleri izini ve gidin seçimlerinizi arasında kullanarak **İleri** ve **geri** araç çubuğundaki düğmeler.

Kullanabileceğiniz **Nesne Tarayıcısı** bir derleme başvurusu çözüm açmak için bir öğe (derleme, ad alanı, tür veya üye) ve seçerek eklemek için **Başvuru Ekle** araç çubuğunda.

### <a name="object-browser-settings"></a>Nesne Tarayıcısı ayarları

Kullanarak **nesne tarayıcı ayarlarını** düğmesi araç çubuğunda, aşağıdaki görünümlerden birini belirtebilirsiniz.

|||
|-|-|
|**Görünüm ad alanları**|Sol bölmede, fiziksel kapsayıcıları yerine ad alanları görüntüler. Ad alanları birden çok fiziksel kapsayıcılarında depolanan birleştirilir.|
|**Görünüm kapsayıcıları**|Ad alanları, yerine fiziksel kapsayıcılar'ın sol bölmesinde görüntüler. **Ad alanları görüntülemek** ve **görünüm kapsayıcıları** birbirini dışlayan ayarlardır.|
|**Taban türleri Göster**|Taban türleri görüntüler.|
|**Türetilen türlerin Göster**|Türetilmiş tür görüntüler.|
|**Gizli türleri ve üyeleri Göster**|Gizli görüntüler türleri ve açık gri renkte (istemciler tarafından kullanılmaya değil) üyeleri.|
|**Genel üyeleri Göster**|Genel üyeler görüntüler.|
|**Korumalı Üyeleri Göster**|Korumalı üyeler görüntüler.|
|**Özel üyeleri Göster**|Özel üyelerin görüntüler.|
|**Diğer üyeleri Göster**|Diğer iç dahil olmak üzere üyeleri (veya Visual Basic'te arkadaş) türleri üyeleri görüntüler.|
|**Devralınan üyeleri Göster**|Devralınan üyeleri görüntüler.|
|**Genişletme yöntemleri Göster**|Genişletme yöntemleri görüntüler.|

### <a name="object-browser-shortcut-menu-commands"></a>Nesne Tarayıcısı kısayol menü komutları

Kısayol menüsünde **Nesne Tarayıcısı** öğesi türüne bağlı olarak aşağıdaki komutları içerebilir seçili.

|||
|-|-|
|**Tanımı Gözat**|Seçilen öğe için birincil düğüm gösterir.|
|**Tüm başvuruları Bul**|Seçili nesne öğesi bulur ve sonuçları görüntüler bir **Bul sonuçları** penceresi.|
|**Filtre türü için**|Yalnızca seçili türü veya ad alanı görüntüler. Filtre seçerek kaldırabilirsiniz **Aramayı Temizle** düğmesi.|
|**Kopyala**|Öğenin tam adı kopyalar.|
|**Kaldır**|Kapsam özel bir bileşen kümesi ise, seçilen bileşenin kapsamından kaldırır.|
|**Alfabetik olarak sıralamak**|Alfabetik olarak türleri ve üyeleri adına göre listelenmiştir.|
|**Nesne türüne göre sırala**|Türleri ve üyeleri türüne göre sırayla (sınıfları arabirimleri koyun, temsilciler arabirimleri koyun ve yöntemleri özellikleri koyun şekilde) listeler.|
|**Nesne erişimi göre sırala**|Liste türleri ve üyeleri erişim sırayla, ortak veya özel gibi yazın.|
|**Nesne türüne göre Gruplandır**|Nesne türüne göre gruplara türleri ve üyeleri sıralar.|
|**Bildirim Git** (C++ projeleri yalnızca)|Tür veya üye bildirimi varsa kaynak kodunu görüntüler.|
|**Tanıma gitme**|Tür veya üye tanımını varsa kaynak kodunu görüntüler.|
|**Başvuru gidin**|Bir başvuru türü veya üyesi kullanılabilir durumdaysa kaynak kodunda gösterir.|
|**Çağrı hiyerarşisini görüntüleme**|Seçili yönteminde görüntüler **çağrı hiyerarşisi** penceresi.|

## <a name="code-definition-window-c"></a>Kod tanımı penceresi (C++)

**Kod tanımı** penceresinde seçili C++ tür veya üye tanımının etkin projesinde. Kod Düzenleyicisi'ni veya kod Görünüm penceresi tür veya üye seçilebilir.

Bu pencere salt okunur olsa da, kesme noktaları veya yer işaretleri ayarlayabilirsiniz. Görüntülenen tanımını değiştirmeyi seçerek **tanımını Düzenle** kısayol menüsünde. Bu kod Düzenleyicisi'nde kaynak dosyasını açar ve tanımı başladığı satırına ekleme noktasını taşır.

> [!NOTE]
> Visual Studio 2015'ten başlayarak, kod tanımı penceresi yalnızca C++ kodu ile kullanılabilir.

### <a name="code-definition-shortcut-menu"></a>Kod tanımı kısayol menüsü

Kısayol menüsünde **kod tanımı** penceresinde aşağıdakileri içerebilir:

|||
|-|-|
|**Hızlı Eylemler ve yapan yeniden düzenlemeler...**||
|**Yeniden Adlandır...**||
|**Dosyaları Ekle Grafiği Oluştur**||
|**Özet tanımı**||
|**Tanıma gitme**|Tanımı (veya kısmi sınıflar için tanımları) bulur ve bunları görüntüler bir **Bul sonuçları** penceresi.|
|**Bildirimine gidin**||
|**Tüm başvuruları Bul**|Tür veya üye başvuruları çözümde bulur.|
|**Çağrı hiyerarşisini görüntüleme**|Yönteminde görüntüler **çağrı hiyerarşisi** penceresi.|
|**Geçiş üstbilgi / kod dosyası**||
|**Testleri çalıştırma**|Projede birim testleri varsa, seçili kodu için testleri çalıştırır.|
|**Testleri hata ayıklama**||
|**Kesme noktası**|Bir kesme noktası (veya bir tracepoint) ekler.|
|**İmleci çalıştırın**|Program imleç konumu için hata ayıklama modunda çalışır.|
|**kod parçacığında**||
|**Kesme**, **kopya**, **Yapıştır**||
|**Ek Açıklama**||
|**Anahat Oluşturma**|Standart anahat komutları.|
|**Yeniden tara**||
|**Tanımını düzenleme**|Kod penceresinde tanımına ekleme noktasını taşır.|
|**Kodlama seçin**|Açılır **kodlama** penceresi bir dosya için kodlama ayarlayabilirsiniz.|

### <a name="document-outline-window"></a>Belge Anahattı penceresi

Kullanabileceğiniz **belge anahattı** XAML sayfası Tasarımcı veya bir Windows Form Tasarımcısı gibi tasarımcı görünümlerle veya HTML sayfaları ile birlikte penceresi. Böylece form ya da sayfa mantıksal yapısını görüntüleyebilir ve son derece katıştırılmış veya gizli denetimleri bulmak Bu pencere öğeleri ağaç görünümünde görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

- [Sınıf Görünümü ve Nesne Tarayıcısı simgeleri](../ide/class-view-and-object-browser-icons.md)