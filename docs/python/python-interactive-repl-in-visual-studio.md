---
title: Python etkileşimli pencere (REPL)
description: Hızlı kod geliştirme için Visual Studio'da Python kodu için etkileşimli pencere (REPL) kullanma
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: a728c164121216b259e48b502f9ca29fa7ffd1d4
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057924"
---
# <a name="work-with-the-python-interactive-window"></a>Python etkileşimli penceresiyle çalışma

Visual Studio her alma ile REPL bağlı artırır, Python ortamları için bir etkileşimli okuma değerlendirmek yazdırma döngü (REPL) penceresi sağlar `python.exe` komut satırında. Etkileşimli pencere (açılmış **Görünüm > Diğer Pencereler > &lt;ortam&gt; etkileşimli** menü komutları) rasgele Python kodu girin ve sonuçları derhal bakın sağlar. Öğrenin ve API'leri ve kitaplıkları ve etkileşimli olarak projenize eklemek için çalışma kodu geliştirmek için deneme bu şekilde kodlama yardımcı olur.

![Python etkileşimli penceresi](media/interactive-window.png)

Visual Studio Python REPL modları aralarından seçim yapabileceğiniz çeşitli sahiptir:

| REPL | Açıklama | Düzenleme | Hata Ayıklama | Görüntüler |
| --- | --- | --- | --- | --- |
| Standart | Çoğaltma, doğrudan konuşmaları Python için varsayılan | Standart düzenleme (çok satırlı, vb.). | Evet, aracılığıyla `$attach` | Hayır |
| Hata ayıklama | Varsayılan REPL, konuşmaları hata ayıklaması Python işleme | Standart düzenleme | Yalnızca hata ayıklama | Hayır |
| IPython | REPL IPython arka ucuna ettiği | IPython komutları, Pylab kolaylıklar | Hayır | Evet, satır REPL içinde |
| IPython Pylab olmadan | REPL IPython arka ucuna ettiği | Standart IPython | Hayır | Evet, pencere ayırın | 

Bu makalede **standart** ve **hata ayıklama** REPL modları. IPython modları hakkında daha fazla bilgi için bkz: [IPython REPL kullanarak](interactive-repl-ipython.md).

Ctrl + Enter gibi Düzenleyicisi ile etkileşim dahil olmak üzere örnekleriyle ayrıntılı bilgi için bkz: [Öğreticisi Adım 3: etkileşimli REPL penceresini kullanarak](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md). 

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Python-Interactive-Window-gJYKY5LWE_4605918567) etkileşimli penceresinde (2 m 22s).|

## <a name="opening-an-interactive-window"></a>Etkileşimli bir pencere açarak

Bir ortam için etkileşimli penceresini açmak için birkaç yolu vardır.

İlk olarak, Python ortamları penceresine geçiş yap (**Görünüm > Diğer Pencereler > Python ortamları** veya Ctrl-K, Ctrl-') ve seçin **açık etkileşimli pencere** komut veya seçilen bir ortam için düğmesi .

![Python ortamları penceresinde etkileşimli penceresi bağlantı](media/interactive-window-opening.png)

İkinci olarak, listenin sonuna yakınında **Görünüm > Diğer pencereler** menüsünde yoktur bir **Python etkileşimli pencere** ortamları penceresine geçiş yapmak için bir komut yanı sıra komut varsayılan ortamınız için:

![Etkileşimli pencere menüsü öğelerini Görünüm > Diğer Pencereler](media/interactive-window-menu.png)

Üçüncü başlangıç dosyada etkileşimli bir pencere projenizdeki ya da tek başına bir dosya için seçerek açabilirsiniz **hata ayıklama > Execute [Proje | Dosya] Python etkileşimli** menü komutu (Shift + Alt + F5):

![Python etkileşimli menüde proje yürütülemiyor](media/interactive-execute-project.png)

Son olarak, kod dosyasını seçin ve kullanmak [etkileşimli komutuna kod Gönder](#send-code-to-interactive-command) aşağıda açıklanmıştır.

## <a name="interactive-window-options"></a>Etkileşimli pencere seçenekleri

Etkileşimli penceresinden çeşitli yönlerini kontrol edebilir **Araçlar > Seçenekler > Python araçları > Etkileşimli Windows** (bkz [seçenekleri](python-support-options-and-settings-in-visual-studio.md)):

![Python etkileşimli pencere seçenekleri](media/options-interactive-windows.png)

## <a name="using-the-interactive-window"></a>Etkileşimli penceresini kullanma

Etkileşimli penceresi açıldıktan sonra kod satırının satır adresindeki girme başlatabilirsiniz `>>>` istemi. Etkileşimli pencere, modüller, içeri aktarma içeren değişkenleri tanımlama girin ve benzeri her satırın yürütür:

![Python etkileşimli penceresi](media/interactive-window.png)

Ne zaman gibi tam bir deyim yapmak için ek kod satırı bulunmaktadır gerektiğinde istisnadır bir `for` deyimi yukarıda gösterildiği gibi iki nokta üst üste içinde sona erdirir. Bu durumlarda, satır istemi değişikliklerini `...` yukarıdaki grafikte dördüncü ve beşinci satırlarında gösterildiği gibi ek satırlar için bloğu, girmenize gerek gösteren. Boş bir satıra Enter tuşuna bastığınızda, etkileşimli pencere blok kapatır ve yorumlayıcı çalıştırır.

> [!Tip]
> Komut satırı REPL deneyimi çevresindeki kapsamına ait deyimleri girintileme tarafından otomatik olarak normal Python bağlı etkileşimli pencere artırır. Komut satırı REPL yalnızca tek satırları sağlar (yukarı ok ile geri) geçmişi çok satırlı öğeleri de sağlar.

<a name="meta-commands"></a> Etkileşimli pencere çeşitli meta komutlar da destekler. Tüm meta komutları başlayın `$`, ve yazabilirsiniz `$help` meta komutların listesini almak için ve `$help <command>` kullanım ayrıntıları için belirli bir komut almak için.

| Meta komutu | Açıklama |
| --- | --- |
| `$$` | Açıklama kod oturumunuz boyunca yararlıdır bir açıklama ekler. |
| `$attach` | Visual Studio hata ayıklayıcısı hata ayıklamayı etkinleştirmek için REPL pencere işlemi ekler. |
| `$cls`, `$clear` | Geçmiş ve yürütme bağlamı dokunmadan Düzenleyicisi penceresinde, içeriğini temizler. |
| `$help` | Komutların listesini görüntülemek veya belirli bir komutla ilgili Yardım. |
| `$load` | Komutları dosyadan yükler ve tamamlanıncaya kadar yürütür. |
| `$mod` | Geçerli kapsam için belirtilen modül adı geçer. |
| `$reset` | Yürütme Ortamı ilk durumuna sıfırlar, ancak geçmişini tutar. |
| `$wait` | En az belirtilen milisaniye sayısını bekler. |

Komutları da Visual Studio uzantıları tarafından Genişletilebilir uygulama ve dışarı aktarma `IInteractiveWindowCommand` ([örnek](https://github.com/Microsoft/PTVS/blob/master/Python/Product/PythonTools/PythonTools/Repl/InteractiveWindowCommands.cs#L85)).

## <a name="switching-scopes"></a>Kapsam değiştirme

Komut isteminden çalıştırdıysanız gibi varsayılan olarak, projenin başlangıç dosyasına bir proje için etkileşimli pencere kapsamlıdır. Tek başına bir dosya için bu dosyaya kapsamları kullanıcının. Herhangi bir zamanda ancak etkileşimli penceresinin üst boyunca açılır menü kapsam REPL oturumunuz sırasında herhangi bir zamanda değiştirmenize olanak verir:

![Etkileşimli pencere kapsamları](media/interactive-scopes.png)

Kez yazarak gibi bir modülü içe aktardıktan sonra `import importlib`, bu modüldeki tüm kapsam içine geçmek için açılan seçenekleri görünür. Belirli bir duruma oturumunuz sırasında nasıl aldığınız izlemek için bir ileti etkileşimli penceresinde yeni kapsam de gösterir.

Girme `dir()` bir kapsamda geçerli tanımlayıcıları işlev adları, sınıflar ve değişkenler gibi bu kapsamda görüntüler. Örneğin, kullanarak `import importlib` arkasından `dir()` şunları gösterir:

![İmportlib kapsamında etkileşimli penceresi](media/interactive-importlib-scope.png)

< a name = "gönderme kod-için-etkileşimli"</a>

## <a name="send-code-to-interactive-command"></a>Etkileşimli komutuna kod Gönder

Çalışma yanı sıra etkileşimli penceresi içinde doğrudan, Kod Düzenleyicisi'nde seçebileceğiniz sağ tıklatın ve seçin **etkileşime Gönder** veya Ctrl + Enter tuşuna basın.

![Etkileşimli menü komutu Gönder](media/interactive-send-to.png)

Bu komut, geliştirdikçe kodunuzu test de dahil olmak üzere yinelemeli veya Açılım kod geliştirme için yararlıdır. Örneğin, etkileşimli penceresine paylaştırılabilen bir kod gönderildi ve çıktısını görülen sonra kodu gösterme, değiştirmek ve Ctrl + Enter tuşlarına basarak hızlı bir şekilde test yukarı ok tuşlarına basabilirsiniz. (Giriş sonunda Enter tuşuna basarak yürütülmeden, ancak giriş ortasında Enter tuşuna basarak yeni bir satır ekler.) İstediğiniz kod olduktan sonra daha kolay, proje dosyasına kopyalayabilirsiniz.

> [!Tip]
> Varsayılan olarak, Visual Studio kaldırır >>> ve... REPL etkileşimli penceresinden kod düzenleyicisine yapıştırılırken ister. Bu davranışı değiştirebilirsiniz **Araçlar > Seçenekler > Metin Düzenleyicisi > Python > Gelişmiş** kullanarak sekmesinde **Yapıştır kaldırır REPL istemleri** seçeneği. Bkz: [seçenekleri - çeşitli seçenekleri](python-support-options-and-settings-in-visual-studio.md#miscellaneous-options).

<!-- After 15.3 is released, you can also press "Undo" after pasting to restore prompts. Press "Undo" a second time to remove the pasted code entirely. -->

Bir kod dosyası karalama alanı kullanırken, genellikle küçük bir kerede göndermek istediğiniz kod bloğu sahiptir. Kod gruplamak için kod olarak işaretleme bir *kod hücresini* ile başlayan bir açıklama ekleyerek `#%%` hücre başlangıcına sona erdiği öncekinin. Kod hücresini daraltılmış ve genişletilmiş ve Ctrl + Enter kod hücresinin içine kullanarak etkileşimli penceresine tüm hücre gönderir ve Sonrakine taşır.

Visual Studio gibi yorumlar başlayarak kod hücreleri de algılar `# In[1]:`, Jupyter not defteri bir Python dosyası olarak dışarı aktarılırken alma biçimi değil. Bu algılama, bir dizüstü bilgisayarınızı çalıştırmayı kolaylaştırır [Azure not defterlerini](https://notebooks.azure.com/) Python dosya indirme, Visual Studio'da açarak ve her bir hücre çalıştırmak için Ctrl + Enter kullanma.

![Etkileşimli kod hücreleri](media/interactive-code-cells.png)

## <a name="intellisense-behavior"></a>IntelliSense davranışı

Etkileşimli penceresinde IntelliSense yalnızca kaynak kodu analize dayalı Kod düzenleyicisinde aksine dinamik nesneleri temel IntelliSense içerir. Bu özellikle dinamik olarak üretilen kod ile etkileşimli penceresinde daha doğru önerilerdir. (Örneğin, günlük iletilerini) yan etkileri olan işlevlere geliştirme deneyiminizi etkileyebilir dezavantajı olmasıdır.

Bu davranış bir sorun varsa, ayarları değiştirin **Araçlar > Seçenekler > Python araçları > Etkileşimli Windows** içinde **tamamlanma modu** açıklandığı gibi Grup [seçenekleri - Etkileşimli Windows seçenekleri](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options).
