---
title: "Visual Studio için R araçları ile etkileşimli REPL | Microsoft Docs"
description: "Etkileşimli REPL ortamı için Düzenleyicisi windows ile tümleşik R çözümdeki Studio nasıl kullanıldığını."
ms.custom: 
ms.date: 06/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 7b60fa49aed09823a23d226fd7b5a908cc86af72
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="working-with-the-r-interactive-window"></a>R etkileşimli pencere ile çalışma

R araçları için Visual Studio (RTVS) sağlayan bir R etkileşimli pencere olarak da bilinen bir **REPL** (Read-değerlendir-yazdırma-döngüsü) penceresinde, R kodu girin ve hemen sonuçlarını görebilirsiniz. Tüm modülleri, sözdizimi ve değişkenleri yanı IntelliSense, kullanılabilir etkileşimli pencerede.

Etkileşimli penceresi de normal R Düzenleyicisi windows ile tümleşiktir. Kodu seçin ve Ctrl + Enter tuşuna basın veya sağ tıklatın ve seçin **etkileşimli Execute**, ve kodu çalıştırın--satır etkileşimli penceresinde sanki doğrudan belirtilmiş. İmleç bir düzenleyici penceresinde tek bir satırda olduğunda, Ctrl + Enter bu satırı etkileşimli penceresine gönderir ve ardından sonraki satıra imleci taşır. Bu şekilde, yalnızca art arda kod üzerinden adım için Ctrl + Enter tuşlarına basabilirsiniz.

Bu özellikler yaşamaya izleyin [R ile çalışmaya başlama](getting-started-with-r.md) izlenecek yanı sıra bu makaledeki bölümler. [Kod parçacıkları](code-snippets-for-r.md) R Düzenleyici pencerelerinde yaptığınız gibi etkileşimli penceresinde de çalışır.

## <a name="overview-of-the-interactive-window"></a>Etkileşimli pencere genel bakış

Geçerli R kod yazıp satırın sonunda Enter tuşuna basarak kod söz konusu satıra çalışır:

```repl
> 3 + 3
[1] 6
```

Tek satırlı giriş üzerinde herhangi bir yere ENTER tuşuna basarak, o satırdaki çalışır.

Önceki tüm giriş ve çıkış REPL salt okunurdur ve değiştirilemez. Ancak, seçin ve herhangi bir zamanda penceresinden metin yanı sıra yapıştırılan kopyalayın. Satır girilmiş gibi yapıştırılan kodu çalıştırır.

Diğer bir deyişle, bir deyim yazmaya başlayın ve Enter tuşuna basın, RTVS zaman devam deyim bilir ve çok satırlı moduyla girer + sol ve uygun girinti sor. RTVS de parantez, köşeli ayraçlar ve süslü ayraçlar gerçekleştirir:

![Etkileşimli penceresindeki çok satırlı deyimi girişine](media/repl-multiline-entry.png)

Bu çok satırlı modda Enter tuşuna yeni bir satır yalnızca blok, aksi takdirde sonunda bu eklemeleri getirildiğinde kod bloğu çalıştırır. Ancak, Ctrl + o kod bloğunun hemen çalıştırmak için Enter herhangi konumunda basabilirsiniz.

### <a name="toolbar-commands"></a>Araç çubuğu komutları

Kendi araç etkileşimli penceresiyle şöyledir:

![Araç çubuğu ile etkileşimli penceresi](media/repl-window.png)

Araç çubuğu komutlarını aşağıdaki gibidir, hangi çoğu klavye eşdeğerleri ve üzerinde de kullanılabilir **R Araçlar > oturum** ve **R Araçlar > çalışma dizini** menüler (veya bir belirtildiği gibi):

| Düğme | Komut | Tuş bileşimini | Açıklama | 
| --- | --- | --- | --- |
| ![Sıfırla düğmesi](media/repl-toolbar-01-reset.png) | Sıfırla | Ctrl+Shift+F10 | Tüm değişkenleri ve Geçmiş temizleme etkileşimli window oturumu sıfırlar. |
| ![Boş düğme](media/repl-toolbar-02-clear.png) | Temizle | Ctrl+L | Etkileşimli penceresinde gösterilen çıkış temizler; oturum değişkenleri veya geçmiş etkilemez. |
| ![Geçmişi düğmeleri](media/repl-toolbar-03-history.png) | Önceki geçmişi komutu<br/>Sonraki geçmişi komutu | Yukarı, aşağı<br/>Alt + Yukarı, Aşağı Alt | Çok satırlı kod blokları için belirli davranışları ile geçmişinde kaydırır. Bkz: [geçmişi](#history). |
| ![Yük çalışma düğmesi](media/repl-toolbar-04-load-workspace.png) | Yük çalışma | yok | Bir önceki çalışma kaydedilen yükler (bkz [çalışma alanları ve oturumlar](#workspaces-and-sessions). |
| ![Çalışma alanı Farklı Kaydet düğmesi](media/repl-toolbar-05-save-workspace-as.png)| Çalışma alanı olarak Kaydet | yok | Bir çalışma alanı olarak oturumun geçerli durumunu kaydeder (bkz [çalışma alanları ve oturumlar](#workspaces-and-sessions). |
| ![Kaynak R betiği düğmesi](media/repl-toolbar-06-source-r-script.png) | Kaynak R betiği | Ctrl+Shift+S | Çağrıları `source` Visual Studio düzenleyicisinde şu anda etkin R betiği ile çalıştığı kodu.  Bu düğme, yalnızca bir R dosyasını Visual Studio düzenleyicisinde açık olduğunda görüntülenir. | 
| ![Kaynak R betiği Yankı düğmesi](media/repl-toolbar-07-source-r-script-with-echo.png) | Echo kaynak R betiği | Ctrl+Shift+Enter | Kaynak R betiği aynı ancak betiğin içeriği etkileşimli pencerede görüntülenir. | 
| ![R düğmesi kesme](media/repl-toolbar-08-interrupt-r.png)| Kesme R | Esc | Etkileşimli penceresinde çalışan kod gibi durdurur `while` ekran döngüde bu bölümün başında gösterir. |
| ![Hata ayıklayıcı düğme ekleme](media/repl-toolbar-09b-attach-debugger.png)| Hata ayıklayıcıyı Ekle | yok | Ayrıca kullanılabilir kullanarak **hata ayıklama > R etkileşimli ekleme** komutu. | 
| ![Kaynak dosya konumu düğmesine kümesi çalışma dizini](media/repl-toolbar-10-set-working-directory-source.png)| Kaynak dosya konumu dizinine çalışma kümesi | Ctrl+Shift+E | En son kaynaklı dosya çalışma dizinine yüklenen etkileşimli penceresine kümeleri (kullanarak `source`). Bkz: [çalışma dizini](#working-directory). |
| ![Proje konumu düğmesi için çalışma dizini ayarlayın](media/repl-toolbar-11-set-working-directory-to-project.png) | Çalışma dizini proje konumuna ayarlayın | Ctrl+Shift+P | Visual Studio şu anda yüklenen proje kökündeki için çalışma dizini ayarlar. Bkz: [çalışma dizini](#working-directory). |
| (Metin alanı) | Çalışma seçin dizini | yok | Çalışma dizini için doğrudan giriş alanı. Bkz: [çalışma dizini](#working-directory). |

## <a name="workspaces-and-sessions"></a>Çalışma alanları ve oturumlar

Etkileşimli penceresinde kod çalıştıran bir bağlamı Geçerli oturumunuzda oluşturur. Bağlam genel değişkenler, işlev tanımları, kitaplık yükler ve benzeri oluşur. Bu bağlamda topluca adlı bir *çalışma*, kaydedin ve herhangi bir zamanda çalışma alanları yük. 

Seçme **çalışma Kaydet** düğmesini veya kullanarak **R Araçlar > oturum > çalışma alanı Kaydet...**  komut sizden bir konum ve dosya adı için (varsayılan uzantısı `.RData`).

Belirli bir dosya adı kullanarak bir çalışma alanı kaydetmek için (varsayılan `.RData`), REPL çalışma alanını Kaydet düğmesine tıklayın:

Daha önce kaydedilmiş bir çalışma alanı yeniden yüklemeyi seçin **yük çalışma** düğmesini tıklatın veya kullanmak **R Araçlar > oturum > Yük çalışma...**  ve çalışma alanı dosyasına gidin.

**Sıfırlama** düğmesini veya **R Araçlar > oturum > sıfırlama** oturum bağlamı temizler. Bir uzak oturum kullanıyorsanız, sıfırlama depolanan tüm dosyaları temizlemek için uzak makinede kullanıcı profili de siler. (Bkz [çalışma alanları](r-workspaces-in-visual-studio.md#directories-on-local-and-remote-computers).)

## <a name="working-directory"></a>Çalışma dizini

Geliştiriciler genellikle kendi çalışma dizini sırada etkileşimli bir oturumda değiştirmek istiyorum. Araç çubuğunda, kullanılabilen çeşitli komutları **R Araçlar > çalışma dizini** menü ve proje bağlam menüsü kaynak dosyasının konumunu, konum veya projenizin veya diğer bir çalışma dizini kolayca ayarlamanıza izin verir rastgele konumu. Bunun yapılması, dosyalar için söz konusu olduğunda tam yol adları veya uzun göreli yol adlarını yazarak önlemenize yardımcı olur.

## <a name="history"></a>Geçmiş

Etkileşimli penceresinde girin her satır bir Düzenleyicisi'nden gönderilen satırları içerir, çoğaltma'nın geçmişi korunur. Komut satırında olasılıkla alışkın için olduğu gibi sonra Yukarı ve aşağı ok tuşlarına geçmişinde gidebilirsiniz.

Geçerli satırda yazmaya başlayın ve tuşuna basın, geçerli satır içinde korunur geçmişinizi bile aracılığıyla henüz çalıştırmanızı bu satırı henüz bir farktır.

Etkileşimli pencere geçmişinde akıllıca satırları yayılan bilgilerinin diğer kod bloğu ile de çalışır. Geçmiş yukarı ve aşağı ok tuşları dolaşma, çok satırlı kod blokları tam bir birim olarak alınır ve geçerli girişi olarak gösterilir. Bu noktada, üst veya alt ulaşılana kadar ok tuşları, kod bloğunun satır gidin. Kod bloğu üst kısmında, Yukarı Ok geçmişinde önceki öğeyi alır; alt satırında aşağı oka sonraki öğeyi alır.

Bu davranış tüketiminde geçmişindeki son öğeyi yeniden çalıştırma, genellikle bu durum düzenler oku ve Enter tuş vuruşu verirken doğal olarak yukarı ok tuşlarına basarak çok satırlı kod bloğunu düzenleme için içine gitmek için birleşimi.

Çok satırlı kod bloklarda gezinme kaçınmak için araç kullanın düğmeleri veya Alt + Yukarı ve Aşağı Alt ve tüm blokları tek bir satır olarak kabul edilir.

Geçmiş özellikleri deneyimi yapmanın en kolay yolu bunları kendiniz için etkileşimli pencerede çalışmaktır. Aşağıdaki kodu birkaç uygun tek ve birden çok satırı deyimleri sağlar. Kopyala-yapıştır her deyimiyle ayrı ayrı, ancak uygun geçmişi oluşturmak için kullanın. (Ayrıca kodu ayrı kod dosyasına yapıştırın ve Ctrl + Enter etkileşimli penceresiyle satırları gönderin.)

```R
3 + 3

4 + 4

5 + 5

add <- function (x, y) {
  return (x + y)
}

sub <- function (x, y) {
  return (x - y)
}
```