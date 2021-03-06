---
title: R projeleri
description: Bir yönetici özellikleri, proje komutları ve şablonlar gibi Visual Studio'da R projeleri oluşturma
ms.date: 06/29/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: d35a8882654170b62ed3dc37de2361b86cbb1ea1
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238393"
---
# <a name="create-r-projects-in-visual-studio"></a>Visual Studio'da R projeleri oluşturma

R projesinde (bir *.rxproj* dosyası) kaynak ve projenizi ile ilişkili içerik dosyalarını tanımlar. Ayrıca her dosya için yapı bilgisi içeriyor, kaynak denetimi sistemleriyle tümleştirmeyi bilgilerini korur ve mantıksal bileşenlerin uygulamanıza düzenlemenize yardımcı olur. Çalışma ile ilgili bilgi listesi gibi yüklü paketleri, ancak, çalışma alanında ayrı olarak korunur.

Projeleri her zaman bir Visual Studio içinde yönetilen *çözüm*, herhangi bir sayıda birbirine başvurabilir projeleri içerebilir. Bkz: [birden çok proje türleri Visual Studio'da kullanın](#use-multiple-project-types-in-visual-studio).

## <a name="creating-a-new-r-project"></a>Yeni bir R projesi oluşturma

1. Visual Studio'yu başlatın.
1. Seçin **Dosya > Yeni > Proje...** (**Ctrl**+**Shift**+**N**)
1. "R" gelen altında projenizi **şablonları > R**, bir ad ve konum proje verin ve seçin **Tamam**:

    ![R (RTVS VS2017 içinde) Visual Studio'da yeni proje iletişim kutusu](media/getting-started-01-new-project.png)

Bu komut, ile boş bir proje oluşturur *komut dosyası. R* dosya düzenleyicide açık. Ayrıca, fark **Çözüm Gezgini** projede iki dosya vardır:

![Şablondan oluşturulan bir R proje içeriğini](media/projects-template-results.png)

*. Rhistory* içine girdiğiniz ne olursa olsun komutları kaydeder [R etkileşimli](interactive-repl-for-r-in-visual-studio.md) penceresi. Bir özel Geçmiş penceresi açın **R Araçları** > **Windows** > **geçmişi** komutu. Bu pencere geçmişi içeriğini temizlemek için bir araç çubuğu düğmesi ve bağlam menü öğeleri sahiptir.

*Rproject.rproj* dosyası, aksi takdirde Visual Studio tarafından yönetilmeyen bazı R özgü proje ayarları bulundurur:

| Özellik | Varsayılan | Açıklama |
| --- | --- | --- |
| Sürüm | 1.0 | Projeyi oluşturmak için kullanılan R araçları Visual Studio sürümü. |
| RestoreWorkspace | Varsayılan | Önceki çalışma değişkenleri otomatik olarak yüklenmesini `.RData` proje dizininde dosya. |
| SaveWorkspace | Varsayılan | Geçerli çalışma alanı değişkenlerini Kaydet `.RData` proje kapatırken proje dizininde dosya. |
| AlwaysSaveHistory | Varsayılan | Geçerli etkileşimli pencere geçmişine Kaydet `.RHistory` proje kapatırken proje dizininde dosya. |
| EnableCodeIndexing | Evet | Kod aramalarını hızlandırmak için bir arka plan dizin oluşturma görevi çalıştırılıp çalıştırılmayacağını belirler. |
| UseSpacesForTab | Evet | Sekme karakteri veya alanları (Evet) eklenip eklenmeyeceğini belirler (No) olduğunda **sekmesini** tuşa Düzenleyicisi'nde. |
| NumSpacesForTab | 2 | UseSpacesForTab Evet ise, eklenecek boşluk sayısı. |
| Kodlama | UTF-8 | İçin varsayılan kodlamayı `.R` dosyaları. |
| RnwWeave | Sweave | Rnw dosya weaving kullanılacak paketi. |
| LaTeX | pdfLaTeX | RMarkdwon PDF'ye dönüştürme sırasında kullanılacak kitaplığı. |

### <a name="converting-a-folder-of-files-to-an-r-project"></a>Bir klasör dosyaların bir R projesine dönüştürme

Var olan bir klasörü, varsa *. R* bir proje ile yönetmek istediğiniz dosyaları şu adımları uygulayın:

1. Yeni bir proje olduğu gibi önceki bölümde Visual Studio'da oluşturun.
1. Dosyalarınızı proje klasörüne kopyalayın.
1. Visual Studio Çözüm Gezgini'nde projeye sağ tıklayın, seçin **Ekle** > **çıkma öğesi**, eklemek istediğiniz dosyaları göz atın. Bu dosyaları seçtikten sonra proje ağacında görünür **Tamam**.
1. Kod alt klasörler halinde düzenlemek için projeye sağ tıklayın, seçin **Ekle** > **yeni klasör** ilk olarak, ardından dosyalarınızı bu klasöre kopyalayın ve bu varolan öğeleri 3. adımda ekleyin.

## <a name="project-properties"></a>Proje Özellikleri

Proje özellik sayfalarını açmak için ' nde projeye sağ **Çözüm Gezgini** seçip **özellikleri**, ya da seçin **Proje > (proje adı) özellikleri* menü öğesini seçin. Açılır pencere proje özellikleri görüntüler:

| Tab | Özellik | Açıklama |
| --- | --- | --- |
| Çalıştır | Başlangıç dosya | İle Çalıştır dosyasının adını **kaynak başlangıç dosya** komutu, **F5**, **hata ayıklama > hata ayıklamayı Başlat**, veya **hata ayıklama > Başlathataayıklamaolmadan**. Proje dosyasında sağ tıklayıp seçerek **başlangıç R betiği ayarlamak** ayrıca başlatma dosyası olarak ayarlar. |
| | R çalıştırılmasında etkileşimli Sıfırla | Etkileşimli pencerenin çalışma alanından tüm değişkenleri projeyi çalıştırırken temizler. Bunu garanti vardır, bunu hiçbir bölümü denetlerler işlemcide kalan çalışma içeriğidir. |
| | Uzak proje yolu | Bir uzak çalışma alanı yolu. |
| | Çalıştırmada dosya aktarımı | Proje, filtreye tabi dosyaları olup olmadığını gösterir **aktarılacak dosyaları**, her çalıştırma ile bir uzak çalışma alanı kopyalanacak. |
| | Dosyaları aktarmak için | Dosya adları ve joker karakterler, uzak bir çalışma alanına kopyalamak için belirli dosyaları belirten **aktarım çalıştırmada dosyaları** seçilir. |
| Ayarlar | (Settings.R dosyası) | R proje ayarları gelen *Settings.R* veya **. Settings.R* projesi içinde bulunan dosyalar. Ayarlar dosyası yoksa, sayfa ve varsayılan kaydetme değişkenleri ekleyebilirsiniz *Settings.R* dosya sizin için oluşturulur. Ayarları dosyası projeye ekleyebilirsiniz **dosya** > **Yeni Öğe Ekle** menü komutu. <br/> Ayarları R kodu olarak depolanır ve böylece ortamını önceden tanımlanmış ayarlarla önceden doldurmak diğer modüller çalıştırmadan önce dosyanın sağlanmasına. |

## <a name="r-specific-project-commands"></a>R özgü proje komutları

Visual Studio projeleri desteği sağ tıklatma menüsünden genel komutlarının sayısı ve **proje** menüsü. Bu genel özelliklerin hakkında daha fazla bilgi için bkz: [çözümler ve projeler Visual Studio'da](../ide/solutions-and-projects-in-visual-studio.md). R araçları için Visual Studio (RTVS) bir R projesi için sağ tıklatma menüsü kendi komutlarının sayısı ekler ve ayrıca dosyaları unutmayın, ancak ve klasörlerindeki proje içindeki tutun.

| Komut | Açıklama |
| --- | --- |
| Çalışma dizini burada ayarlama | Proje içinde herhangi bir alt üzerinde de kullanılabilir proje klasörüne R etkileşimli pencerenin çalışma dizini ayarlar. |
| İçeren klasörü aç | Seçilen dosya konumunda Windows Gezgini'ni açar. |
| R betiği ekleme | Oluşturur ve yeni bir açar *. R* varsayılan ada sahip dosya. Aynı zamanda **Ekle** > **yeni öğe** oluşturmak için komutu *. R* dosyaları diğer dosya türleri için bir dizi yanı sıra. Bkz: [R özgü öğe şablonları](#r-specific-item-templates). |
| R Markdown Ekle | Oluşturur ve açar Yeni *.rmd* varsayılan adı ile belge. Aynı zamanda **Ekle** > **yeni öğe** oluşturmak için komutu *.rmd* dosyaları diğer dosya türleri için bir dizi yanı sıra. Bkz: [R özgü öğe şablonları](#r-specific-item-templates).  |
| Saklı yordamlar yayımlama | R komut dosyalarında bulunan saklı yordamlarda yayımlamak için bir işlem başlatır. Bkz: [iş ile SQL Server saklı yordamları](integrating-sql-server-with-r.md#work-with-sql-server-stored-procedures). | 

## <a name="r-specific-item-templates"></a>R özgü öğe şablonları

RTVS birkaç belirli dosya türleri için şablonlar içerir. Şablonları bir R projeye sağ tıklayıp seçerek erişim **Ekle** > **yeni öğe**, seçerek **proje**  >   **Yeni Öğe Ekle**, veya kullanarak **dosya** > **yeni** > **dosya** ve seçerek **R** sekmesi. Bir şablon keşfetmek için en iyi yeni bir proje oluşturun ve her türdeki dosyaları eklemek için yoludur.

> [!Note]
> **Ekle** > **yeni öğe** komutları tablosundaki; listelenmeyen genel dosya türlerini de görüntüler **dosya** > **yeni**   >  **Dosya** bu türlerde yerine üzerinde bulunan **genel** sekmesi.

| Dosya türü | Açıklama |
| --- | --- |
| R betiği | R komut satırında girilebilir aynı komutları içeren bir metin dosyası. |
| R Markdown | Bir dosyayı içeren bir [R Markdown](rmarkdown-with-r-in-visual-studio.md) belge. |
| R ayarları | R uygulama ayarları içeren bir dosya. | 
| R belgeleri | Yalnızca ad, diğer ad ve başlık alanları içeren genel R belge dosyası. |
| R belgeleri (işlev) | Bir işlev açıklamak için açıklamaları olan birçok alanları içeren bir R belge dosyası. |
| R belgeleri (veri kümesi) | Bir veri kümesini tanımlamak için açıklamaları olan birçok alanları içeren bir R belge dosyası. |
| SQL sorgusu | Ve boş *.sql* dosya. Bkz: [iş SQL Server ve R ile](integrating-sql-server-with-r.md). |
| Saklı yordam r | Bir R dosyasıyla alt SQL sorgusunun ve alt yordamı şablon dosyası depolanır. Bkz: [iş SQL Server ve R ile](integrating-sql-server-with-r.md). |

## <a name="use-multiple-project-types-in-visual-studio"></a>Visual Studio'da birden çok proje türleri kullanma

Visual Studio çözümleri toplamak ve tek bir mantıksal yerde ilgili projeleri yönetmek için kullanışlı bir yer sağlar. Çözüm kodunuzu düzenli tutmak ve işbirliği takımlar içinde kolaylaştırır.

Aşağıdaki örnekte bir R projesi çözümü, R ve Azure Machine Learning, Python/scikit-öğrenin proje, yoğun hesaplama iş modülleri içeren C++ projesi, veri yönetimi için bir SQL projesi ve Python/Bottle kullanılarak oluşturulmuş bir model ile içerir. Proje sonucu yayımlar web sitesi için:

![Bir çözümde birden çok ilgili projeleri gösteren Visual Studio Çözüm Gezgini](media/projects-polyglot.png)

Projesi ile kalın vurgulanmış çözüm için "Başlangıç" projedir; değiştirmek için farklı bir projeye sağ tıklayın ve seçin **başlangıç projesi olarak ayarla**.

> [!Note]
> Şu anda hiç açık bir C# R / C++ dil tümleştirmesi yerinde (Python için olarak bkz [Python için C++ uzantısı oluşturma](../python/working-with-c-cpp-python-in-visual-studio.md)).  Ancak kitaplıkları r için C# ve C++ köprüleri sağlayan kullanılabilir vardır

Projeler ve çözümler genel yönetme ile ilgili daha fazla bilgi için bkz: [çözümler ve projeler Visual Studio'da](../ide/solutions-and-projects-in-visual-studio.md).
