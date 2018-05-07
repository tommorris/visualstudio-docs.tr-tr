---
title: Sınıf Diyagramında ve Sınıf Ayrıntıları Penceresinde Klavye ve Fare Kısayolları (Sınıf Tasarımcısı)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.classdetails.window
helpviewer_keywords:
- class diagrams, keyboard shortcuts
- class diagrams, mouse shortcuts
ms.assetid: c12d8dac-9902-4fde-b721-2a8116da53b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0762287c47494b0dd0d3f4d444d7143c8688ec2b
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer"></a>Klavye ve Fare kısayolları sınıf diyagramında ve sınıf Ayrıntıları penceresinde (Sınıf Tasarımcısı)

Fare yanı sıra klavye gezinme eylemleri gerçekleştirmek için kullanabileceğiniz **Sınıf Tasarımcısı** ve **sınıfı ayrıntıları** penceresi.

## <a name="use-the-mouse-in-class-designer"></a>Sınıf Tasarımcısı'nda fare kullanma

Sınıf diyagramları aşağıdaki fare eylemleri desteklenir:

|Fare birleşimi|Bağlam|Açıklama|
|-----------------------|-------------|-----------------|
|Çift tıklatın|Şekil öğeleri|Kod Düzenleyicisi açılır.|
|Çift tıklatın|Lolipop Bağlayıcısı|Genişlet/Daralt Lolipop.|
|Çift tıklatın|Lolipop bağlayıcı etiketi|Çağırır **Göster arabirimi** komutu.|
|Fare tekerleği|Sınıf diyagramı|Dikey kaydırın.|
|SHIFT + fare tekerleği|Sınıf diyagramı|Yatay kaydırma.|
|CTRL + fare tekerleği|Sınıf diyagramı|Yakınlaştırma.|
|CTRL + Shift + tıklatın|Sınıf diyagramı|Yakınlaştırma.|

## <a name="use-the-mouse-in-the-class-details-window"></a>Sınıf Ayrıntıları penceresinde fare kullanma

Fare kullanarak görünümünü değiştirebilirsiniz **sınıfı ayrıntıları** penceresi ve verileri görüntüler, aşağıdaki yollarla:

-   Düzenlenebilir bir hücre tıklatarak bu hücrenin içeriğini düzenlemenize olanak tanır. Değişikliklerinizi verileri depolanır veya görüntülenen tüm konumları yansıtılır Özellikleri penceresinde ve kaynak kodu da dahil olmak üzere.

-   Bir satırın herhangi bir hücre tıklatıldığında, o satırdaki tarafından temsil edilen öğesi özelliklerini görüntülemek için Özellikler penceresini neden olur.

-   Bir sütunun genişliği değiştirmek için sütun istediğiniz genişliğe gelinceye kadar sınır sütun başlığını sağ tarafta sürükleyin.

-   Genişletin veya satırın sol ok simgeleri tıklayarak bölme ya da özellik düğümleri daraltın.

-   Sınıf Ayrıntıları penceresinde geçerli sınıf içinde yeni üyeler oluşturmak ve sınıf Ayrıntıları penceresinde kılavuzunda üyelerin bölmeler arasında gezinme için birkaç düğmesi sunar. Sınıf Ayrıntıları penceresi düğmelerini daha fazla bilgi için bkz.

## <a name="use-the-keyboard-in-class-designer"></a>Sınıf Tasarımcısı'nda klavyeyi kullanma

Aşağıdaki klavye eylemleri sınıf diyagramlarını desteklenir:

|Anahtar|Bağlam|Açıklama|
|---------|-------------|-----------------|
|Ok tuşları|İç tür şekilleri|Ağaç-style Gezinti bölmesinde şekli içeriği de (kaydırma şekli geçici desteklenir). Sol ve sağ anahtarları Genişlet/geçerli öğe Genişletilebilir ise Daralt ve üst öğeye gidin değilse (ayrıntılı davranışı için ağaç görünümü Gezinti bakın).|
|Ok tuşları|Üst düzey şekiller|Şekilleri diyagramı taşıma.|
|SHIFT + ok tuşları|İç tür şekilleri|Yapı sürekli Seçimi şekil öğelerine üyeleri, iç içe geçmiş türler veya bölmeler gibi oluşan. Bu kısayolların çevresinde kaydırma desteklemez.|
|GİRİŞ|İç tür şekilleri|Üst düzey şekil başlık gidin.|
|GİRİŞ|Üst düzey şekiller|Diyagramda ilk şekli gidin.|
|END|İç tür şekilleri|Şekil içinde son görünür öğesine gidin.|
|END|Üst düzey şekiller|Son şekil diyagramdan gidin.|
|ÜST KARAKTER + HOME|İç türü şekli|Geçerli öğe ile başlayıp ile aynı şekilde en üst öğede şekil öğeleri seçer.|
|SHIFT + END|İç türü şekli|Aynı üst karakter + HOME ancak yukarıdan aşağı yönü.|
|ENTER|Tüm bağlamları|Aynı zamanda çift kullanılabilir olan şekil varsayılan eylemini çağırır. Çoğu durumda bu görünümü kodu, ancak bazı öğeler farklı tanımlayın (elma şekerleri, bölme üstbilgileri, Lolipop etiket).|
|+/-|Tüm bağlamları|O anda odaklanılan öğeyi Genişletilebilir ise, bu anahtarlar Genişlet/öğeyi Daralt.|
|>|Tüm bağlamları|Daraltılmış ve ilk alt öğesi olarak gider olan öğelerde bu öğeyi genişletir.|
|<|Tüm bağlamları|Üst öğeye gider.|
|ALT + ÜST KARAKTER + L|Tür şekilleri içinde + tür şekilleri.|Varsa, seçili şekli Lolipop için gider.|
|ALT + SHIFT + B|Tür şekilleri içinde + tür şekilleri.|Temel tür listesi türü şekil üzerinde gösterilen ve birden çok öğe varsa, bu listenin (daraltma/genişletme) genişletme durumunu değiştirir.|
|DELETE|Tür ve açıklama şekilleri|Çağırır **diyagramdan Kaldır** komutu.|
|DELETE|Şey üzerinde.|Çağırır **koddan silme** komutu (üyeleri, parametreleri, ilişkileri, devralma, Lolipop etiket).|
|CTRL + SİL|Tüm bağlamları|Çağırır **koddan silme** seçimini komutu.|
|TAB|Tüm bağlamları|Sonraki alt (kaydırma destekler) aynı üst içindeki gider.|
|SHIFT+TAB|Tüm bağlamları|Önceki alt (kaydırma destekler) aynı üst içindeki gider.|
|ALANI|Tüm bağlamları|Geçerli öğe seçimini değiştirir.|

## <a name="use-the-keyboard-in-the-class-details-window"></a>Sınıf Ayrıntıları penceresinde klavye kullanma

> [!NOTE]
> Aşağıdaki anahtar bağlama için özel kod yazmaya deneyimi taklit edecek şekilde seçilmiştir.

Gitmek için aşağıdaki tuşlarını **sınıfı ayrıntıları** penceresi:

|||
|-|-|
|Anahtar|Sonuç|
|, (virgül)|İmleci bir parametre satırda ise, virgül yazarak imleci sonraki parametrenin adı alanına taşır. İmleç bir yöntem son parametre satırda ise, imleci için taşır \<parametresini ekleyin > Yeni bir parametre oluşturmak için kullanabileceğiniz alan.<br /><br /> İmleç başka bir yerde ise **sınıfı ayrıntıları** penceresinde, virgül yazarak tam anlamıyla ekler virgül geçerli alanda.|
|; (noktalı virgül)<br /><br /> veya<br /><br /> ) (kapatma ayracı)|Ad alanı içindeki sonraki üye satırın imleci gitme **sınıfı ayrıntıları** penceresi kılavuz.|
|Tab|İmleci ilk sağdan sola ve ardından en alta taşıma sonraki alana taşır. İmleç metin, yazdığınız alandan taşınsa **sınıfı ayrıntıları** metnin işler ve bir hata vermezse depolar.<br /><br /> İmleç üzerinde boş alan gibi olup olmadığını \<parametresini ekleyin >, sekme, sonraki satıra ilk alanına taşır.|
|\<alanı >|İmleci ilk sağdan sola ve ardından en alta taşıma sonraki alana taşır. İmleç üzerinde boş alan gibi olup olmadığını \<parametresini ekleyin >, sonraki satıra ilk alanına taşır. Unutmayın \<alanı > virgül hemen yoksayılır sonra belirtilmiş.<br /><br /> İmleç Özet alanında ise, bir boşluk yazarak bir boşluk karakteri ekler.<br /><br /> İmleci belirli bir satır Gizle sütununda ise, bir boşluk yazarak Gizle onay kutusu değerini değiştirir.|
|CTRL + SEKME|Başka bir belge penceresine geçiş yap. Örneğin, geçiş **sınıfı ayrıntıları** açık kod dosyası penceresine.|
|ESC (çıkış)|Bir alanda metin yazmak başlamıştır, ESC tuşuna basarak alanın içeriği önceki değerine geri döndürülürken bir geri alma anahtarı gibi davranır. Sınıf Ayrıntıları penceresi genel odağa sahip, ancak belirli bir hücre odaklanmış, ESC tuşuna basarak odağı merkezden taşır **sınıfı ayrıntıları** penceresi.|
|Yukarı Ok ve aşağı ok|Bu anahtarları imleci satır satır dikey olarak taşımak **sınıfı ayrıntıları** penceresi kılavuz.|
|Sol Ok|İmleç Ad sütununda ise (açıksa) sol ok tuşuna basarak hiyerarşide geçerli düğüm daraltır.|
|Sağ ok|İmleç Ad sütununda ise (daraltılmışsa) sağ ok tuşuna basarak hiyerarşide geçerli düğüm genişletir.|

## <a name="see-also"></a>Ayrıca bkz.

- [Tür Üyeleri Oluşturma ve Yapılandırma](creating-and-configuring-type-members.md)