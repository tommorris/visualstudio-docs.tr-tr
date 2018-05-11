---
title: Klavye ve Fare kısayolları Sınıf Tasarımcısı
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
ms.openlocfilehash: db39f9c58c0fa2f0ea57d94cd1be404173720088
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window"></a>Sınıf diyagramında ve sınıf Ayrıntıları penceresinde klavye ve Fare kısayolları

Fare yanı sıra klavye gezinme eylemleri gerçekleştirmek için kullanabileceğiniz **Sınıf Tasarımcısı** ve **sınıfı ayrıntıları** penceresi.

## <a name="use-the-mouse-in-class-designer"></a>Sınıf Tasarımcısı'nda fare kullanma

Sınıf diyagramları aşağıdaki fare eylemleri desteklenir:

|Fare birleşimi|Bağlam|Açıklama|
|-----------------------|-------------|-----------------|
|Çift tıklatın|Şekil öğeleri|Kod Düzenleyicisi açılır.|
|Çift tıklatın|Lolipop Bağlayıcısı|Genişlet/Daralt Lolipop.|
|Çift tıklatın|Lolipop bağlayıcı etiketi|Çağırır **Göster arabirimi** komutu.|
|Fare tekerleği|Sınıf diyagramı|Dikey kaydırın.|
|**Shift** + fare tekerleği|Sınıf diyagramı|Yatay kaydırma.|
|**CTRL** + fare tekerleği|Sınıf diyagramı|Yakınlaştırma.|
|**CTRL**+**Shift** +'a tıklayın|Sınıf diyagramı|Yakınlaştırma.|

## <a name="use-the-mouse-in-the-class-details-window"></a>Sınıf Ayrıntıları penceresinde fare kullanma

Fare kullanarak görünümünü değiştirebilirsiniz **sınıfı ayrıntıları** penceresi ve aşağıdaki yollarla görüntülediği verileri:

- Düzenlenebilir bir hücre tıklatarak bu hücrenin içeriğini düzenlemenize olanak tanır. Değişikliklerinizi verileri depolanır veya görüntülenen tüm konumları yansıtılır dahil olmak üzere **özellikleri** penceresi ve kaynak kodu.

- Bir satırın herhangi bir hücreyi tıklatıldığında **özellikleri** satır tarafından temsil edilen öğesi özelliklerini görüntülemek için penceresi.

- Bir sütunun genişliği değiştirmek için sütun istediğiniz genişliğe gelinceye kadar sınır sütun başlığını sağ tarafta sürükleyin.

- Genişletin veya satırın sol ok simgeleri tıklayarak bölme ya da özellik düğümleri daraltın.

- **Sınıfı ayrıntıları** penceresi sunar geçerli sınıfında yeni üyeler oluşturmak ve üyelerin bölmeler arasında gezinme için birçok düğme **sınıfı ayrıntıları** penceresi kılavuz.

## <a name="use-the-keyboard-in-class-designer"></a>Sınıf Tasarımcısı'nda klavyeyi kullanma

Aşağıdaki klavye eylemleri sınıf diyagramlarını desteklenir:

|Anahtar|Bağlam|Açıklama|
|---------|-------------|-----------------|
|**Ok tuşları**|İç tür şekilleri|Ağaç-style Gezinti bölmesinde şekli içeriği de (kaydırma şekli geçici desteklenir). Sol ve sağ anahtarları Genişlet/geçerli öğe Genişletilebilir ise Daralt ve üst öğeye gidin değilse (ayrıntılı davranışı için ağaç görünümü Gezinti bakın).|
|**Ok tuşları**|Üst düzey şekiller|Şekilleri diyagramı taşıma.|
|**Shift**+**ok tuşları**|İç tür şekilleri|Yapı sürekli Seçimi şekil öğelerine üyeleri, iç içe geçmiş türler veya bölmeler gibi oluşan. Bu kısayolların çevresinde kaydırma desteklemez.|
|**Giriş**|İç tür şekilleri|Üst düzey şekil başlık gidin.|
|**Giriş**|Üst düzey şekiller|Diyagramda ilk şekli gidin.|
|**Bitiş**|İç tür şekilleri|Şekil içinde son görünür öğesine gidin.|
|**Bitiş**|Üst düzey şekiller|Son şekil diyagramdan gidin.|
|**Shift**+**giriş**|İç türü şekli|Geçerli öğe ile başlayıp ile aynı şekilde en üst öğede şekil öğeleri seçer.|
|**Shift**+**bitiş**|İç türü şekli|Aynı **Shift**+**giriş** ancak yukarıdan aşağı yönde.|
|**Girin**|Tüm bağlamları|Aynı zamanda çift kullanılabilir olan şekil varsayılan eylemini çağırır. Çoğu durumda bu görünümü kodu, ancak bazı öğeler farklı tanımlayın (elma şekerleri, bölme üstbilgileri, Lolipop etiket).|
|**+** Ve **-**|Tüm bağlamları|O anda odaklanılan öğeyi Genişletilebilir ise, bu anahtarlar Genişlet veya daralt öğesi.|
|**>**|Tüm bağlamları|Daraltılmış ve ilk alt öğesi olarak gider olan öğelerde bu öğeyi genişletir.|
|**<**|Tüm bağlamları|Üst öğeye gider.|
|**Alt**+**Shift**+**m**|Tür şekilleri içinde + tür şekilleri.|Varsa, seçili şekli Lolipop için gider.|
|**Alt**+**Shift**+**B**|Tür şekilleri içinde + tür şekilleri.|Temel tür listesi türü şekil üzerinde gösterilen ve birden çok öğe varsa, bu listenin (daraltma/genişletme) genişletme durumunu değiştirir.|
|**Sil**|Tür ve açıklama şekilleri|Çağırır **diyagramdan Kaldır** komutu.|
|**Sil**|Şey üzerinde.|Çağırır **koddan silme** komutu (üyeleri, parametreleri, ilişkileri, devralma, Lolipop etiket).|
|**CTRL**+**Sil**|Tüm bağlamları|Çağırır **koddan silme** seçimini komutu.|
|**Sekmesi**|Tüm bağlamları|Sonraki alt (kaydırma destekler) aynı üst içindeki gider.|
|**Shift**+**sekmesi**|Tüm bağlamları|Önceki alt (kaydırma destekler) aynı üst içindeki gider.|
|**Boşluk çubuğu**|Tüm bağlamları|Geçerli öğe seçimini değiştirir.|

## <a name="use-the-keyboard-in-the-class-details-window"></a>Sınıf Ayrıntıları penceresinde klavye kullanma

> [!NOTE]
> Aşağıdaki anahtar bağlama için özel kod yazmaya deneyimi taklit edecek şekilde seçilmiştir.

Gitmek için aşağıdaki tuşlarını **sınıfı ayrıntıları** penceresi:

|||
|-|-|
|Anahtar|Sonuç|
|**,** (virgül)|İmleci bir parametre satırda ise, virgül yazarak imleci sonraki parametrenin adı alanına taşır. İmleç bir yöntem son parametre satırda ise, imleci için taşır \<parametresini ekleyin > Yeni bir parametre oluşturmak için kullanabileceğiniz alan.<br /><br /> İmleç başka bir yerde ise **sınıfı ayrıntıları** penceresinde, virgül yazarak tam anlamıyla ekler virgül geçerli alanda.|
|**;**  (noktalı virgül) veya **)** (parantez kapatma)|Ad alanı içindeki sonraki üye satırın imleci gitme **sınıfı ayrıntıları** penceresi kılavuz.|
|**Sekmesi**|İmleci ilk sağdan sola ve ardından en alta taşıma sonraki alana taşır. İmleç metin, yazdığınız alandan taşınsa **sınıfı ayrıntıları** metnin işler ve bir hata vermezse depolar.<br /><br /> İmleç üzerinde boş alan gibi olup olmadığını \<parametresini ekleyin >, sekme, sonraki satıra ilk alanına taşır.|
|**Boşluk çubuğu**|İmleci ilk sağdan sola ve ardından en alta taşıma sonraki alana taşır. İmleç üzerinde boş alan gibi olup olmadığını \<parametresini ekleyin >, sonraki satıra ilk alanına taşır. Unutmayın \<alanı > virgül hemen yoksayılır sonra belirtilmiş.<br /><br /> İmleç Özet alanında ise, bir boşluk yazarak bir boşluk karakteri ekler.<br /><br /> İmleci belirli bir satır Gizle sütununda ise, bir boşluk yazarak Gizle onay kutusu değerini değiştirir.|
|**CTRL**+**sekmesi**|Başka bir belge penceresine geçiş yap. Örneğin, geçiş **sınıfı ayrıntıları** açık kod dosyası penceresine.|
|**ESC**|Bir alanda metin yazmak başlamıştır, ESC tuşuna basarak alanın içeriği önceki değerine geri döndürülürken bir geri alma anahtarı gibi davranır. Sınıf Ayrıntıları penceresi genel odağa sahip, ancak belirli bir hücre odaklanmış, ESC tuşuna basarak odağı merkezden taşır **sınıfı ayrıntıları** penceresi.|
|**Yukarı ok** ve **aşağı ok**|Bu anahtarları imleci satır satır dikey olarak taşımak **sınıfı ayrıntıları** penceresi kılavuz.|
|**Sol Ok**|İmleç Ad sütununda ise (açıksa) sol ok tuşuna basarak hiyerarşide geçerli düğüm daraltır.|
|**Sağ ok**|İmleç Ad sütununda ise (daraltılmışsa) sağ ok tuşuna basarak hiyerarşide geçerli düğüm genişletir.|

## <a name="see-also"></a>Ayrıca bkz.

- [Oluşturma ve tür üyeleri yapılandırma](creating-and-configuring-type-members.md)