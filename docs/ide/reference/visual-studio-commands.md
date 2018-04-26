---
title: Visual Studio Komutları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Visual Studio, commands
- commands, Visual Studio
- command syntax
ms.assetid: 76ffa394-ee89-4629-aba9-1a62b72e6cc1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f124ccc0a4eb7af470a9631bc2291dbeb089711e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="visual-studio-commands"></a>Visual Studio Komutları
Visual Studio komutları bir komuttan çağrılacak izin **komutu** penceresinde **hemen** penceresinde veya **Bul/komut** kutusu. Her durumda, büyüktür işareti (`>`) bir arama ya da hata ayıklama işlemi yerine bir komut izlemek için olduğunu belirtmek için kullanılır.

 Komutlar ve bunların sözdiziminde tam listesini bulabilirsiniz **klavye, ortam seçenekleri** iletişim kutusu.

 Visual Studio komutları kaçış karakteri hemen ardından karakter tam anlamıyla yerine bir denetim karakteri olarak yorumlanır anlamına gelir şapka (^) karakterdir. Bu anahtar adları dışında bir parametre veya anahtar değer düz tırnak işaretleri ("), boşluk, başında bir eğik çizgi, belirliyorsanız düzeltme işaretleri veya başka bir değişmez değer karakterler katıştırmak için kullanılabilir. Örneğin,

```
>Edit.Find ^^t /regex
```

 İç veya dış tırnak işaretleri olup bir şapka aynı çalışır. Bir şapka satırında son karakter ise, yoksayılır.

 IDE yerelleştirilmiş sürümleri komut adları IDE yerel dilini veya İngilizce girilebilir. Örneğin, ya da yazabilirsiniz `File.NewFile` veya `Fichier.NouveauFichier` aynı komutu çalıştırmak için Fransızca IDE'de.

 Birçok komut diğer adları var. Komut diğer adları listesi için bkz: [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md).

 Aşağıdaki komutları, bağımsız değişkenler ve/veya anahtarları alın.

|Komut adı|Açıklama|
|------------------|-----------------|
|[Varolan öğeyi Ekle](../../ide/reference/add-existing-item-command.md)|Varolan bir dosyayı geçerli çözüme ekler ve açar.|
|[Varolan projeyi Ekle](../../ide/reference/add-existing-project-command.md)|Varolan projeyi geçerli çözüme ekler.|
|[Yeni Öğe Ekle](../../ide/reference/add-new-item-command.md)|Geçerli çözüme bir .htm, .css, .txt veya çerçeve gibi yeni bir çözüm öğesi ekler ve açar.|
|[Diğer ad](../../ide/reference/alias-command.md)|Tam komut, tam komut ve bağımsız değişkenler için yeni bir diğer ad veya hatta başka bir diğer ad oluşturur.|
|[Deyimi değerlendir](../../ide/reference/evaluate-statement-command.md)|Değerlendirir ve belirli deyim görüntüler.|
|[Bul](../../ide/reference/find-command.md)|Bir alt kümesi üzerinde kullanılabilir seçenekleri kullanarak dosyaları arar **bulma ve değiştirme** denetim.|
|[Dosyalarda Bul](../../ide/reference/find-in-files-command.md)|Bir alt kümesi üzerinde kullanılabilir seçenekleri kullanarak dosyaları arar [dosyalarda Bul](../../ide/find-in-files.md).|
|[Git](../../ide/reference/go-to-command.md)|İmleç belirtilen satıra taşır.|
|[Liste çağrı yığını](../../ide/reference/list-call-stack-command.md)|Geçerli çağrı yığını görüntüler.|
|[Liste Ayrıştırma](../../ide/reference/list-disassembly-command.md)|Hata ayıklama işlemi başlar ve hataların nasıl işleneceğini belirtmenizi sağlar.|
|[Liste bellek](../../ide/reference/list-memory-command.md)|Belirtilen aralığı bellek içeriğini görüntüler.|
|[Liste modülleri](../../ide/reference/list-modules-command.md)|Geçerli işlem için modüllerini listeler.|
|[Liste kaydeder](../../ide/reference/list-registers-command.md)|Yazmaçları listesini görüntüler.|
|[Kaynak listesi](../../ide/reference/list-source-command.md)|Kaynak kodu belirtilen satır görüntüler.|
|[Liste iş parçacıkları](../../ide/reference/list-threads-command.md)|İş parçacıklarının geçerli programa görüntüler.|
|[Günlük komut penceresi çıktısı](../../ide/reference/log-command-window-output-command.md)|Kopya tüm giriş ve bir dosyaya komut penceresinde çıktı.|
|[Yeni dosya](../../ide/reference/new-file-command.md)|Yeni bir dosya oluşturur ve şu anda seçili projeye ekler.|
|[Dosya Aç](../../ide/reference/open-file-command.md)|Varolan bir dosyayı açar ve bir düzenleyicide belirtmenize olanak tanır.|
|[Proje Aç](../../ide/reference/open-project-command.md)|Varolan projeyi açar ve geçerli çözüme proje eklemenizi sağlar.|
|[Çözümü Aç](../../ide/reference/open-solution-command.md)|Varolan bir çözümü açar.|
|[Yazdırma](../../ide/reference/print-command.md)|İfade değerlendirir ve sonuçları veya belirtilen metni görüntüler.|
|[Hızlı Bakış Komutu](../../ide/reference/quick-watch-command.md)|Seçili ya da belirtilen metni görüntüleyen **ifade** alanını **Hızlı Bakış** iletişim kutusu.|
|[Değiştir](../../ide/reference/replace-command.md)|Bir alt kümesi üzerinde kullanılabilir seçenekleri kullanarak dosyaları metinde değiştirir **bulma ve değiştirme** denetim.|
|[Dosyalarda Değiştir](../../ide/reference/replace-in-files-command.md)|Bir alt kümesini kullanılabilir seçenekleri kullanarak dosyaları metinde değiştirir [dosyalarda Değiştir](../../ide/replace-in-files.md).|
|[Geçerli yığın çerçevesini Ayarla](../../ide/reference/set-current-stack-frame-command.md)|Belirli Yığın çerçevesi görüntülemenize izin verir.|
|[Geçerli iş parçacığının ayarlayın](../../ide/reference/set-current-thread-command.md)|Belirli bir iş parçacığı görüntülemenize izin verir.|
|[Sayı tabanını Ayarla](../../ide/reference/set-radix-command.md)|Görüntülemek için bayt sayısını belirler.|
|[Kabuk](../../ide/reference/shell-command.md)|İçinden programları başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutu komut isteminden yürütülen gibi sorgulamanıza.|
|[ShowWebBrowser Komutu](../../ide/reference/showwebbrowser-command.md)|Bir Web tarayıcı penceresinde da tümleşik geliştirme ortamı (IDE) ya da dış IDE içinde belirttiğiniz URL'yi görüntüler.|
|[Start](../../ide/reference/start-command.md)|Hata ayıklama işlemi başlar ve hataların nasıl işleneceğini belirtmenizi sağlar.|
|[Yol](../../ide/reference/symbol-path-command.md)|Simgelerini aramak hata ayıklayıcı için dizinler listesinde ayarlar.|
|[Kesme](../../ide/reference/toggle-breakpoint-command.md)|Dosya geçerli konumda geçerli durumuna bağlı olarak açmak veya kapatmak kesme noktası etkinleştirir.|
|[İzle Komutu](../../ide/reference/watch-command.md)|Oluşturur ve belirtilen bir örneğini açar bir **izleme** penceresi.|

## <a name="see-also"></a>Ayrıca Bkz.

- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)