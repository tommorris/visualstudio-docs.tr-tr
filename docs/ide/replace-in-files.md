---
title: Visual Studio bulmak ve dosyalarda Değiştir
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.findreplace.replaceinfiles
- vs.replaceinfiles
helpviewer_keywords:
- text searches, replacing text
- find and replace
- replace in files
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6d1a59e3e07120e01fa7757b53b71833a7bc09c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="replace-in-files"></a>Dosyalarda Değiştir

**Dosyalarda Değiştir** belirtilen birtakım dosyalarda dize ya da ifade için kod arama ve bazılarını veya tümünü bulunan eşleşmeler değiştirmenizi sağlar. Eşleşme bulundu ve yapılan Eylemler listelenen **Bul sonuçları** penceresinde seçili **neden seçenekleri**.

> [!NOTE]
> İletişim kutuları ve menü komutlarını gördüğünüz içinde açıklanana değişebilir **yardımcı** etkin ayarlarınıza veya edition bağlı olarak. Ayarlarınızı, örneğin değiştirmek için **genel** veya **Visual C++** ayarları seçebilirsiniz **Araçları** > **içeri ve dışarı aktarma ayarları**ve ardından **tüm ayarlara**.

Görüntülemek için aşağıdaki yöntemlerden herhangi birini kullanabilirsiniz **dosyalarda Değiştir** içinde **bulma ve değiştirme** penceresi.

## <a name="to-display-replace-in-files"></a>Dosyalarda Değiştir görüntülemek için

1. Üzerinde **Düzenle** menüsünde genişletin **bulma ve değiştirme**.

1. Seçin **dosyalarda Değiştir**.

   — veya —

  Varsa **bulma ve değiştirme** penceresi zaten açık araç çubuğunda, seçin **dosyalarda Değiştir**.

## <a name="find-what"></a>Aranan

Yeni metin dizesi veya deyim için aramak için kutusunda belirtin. İçin en son'Aranan 20 dizelerden herhangi birinde aramak için açılır listeyi açın ve dize seçin. Bitişik seçin **ifade oluşturucusu** bir veya daha fazla normal ifadeler, arama dizesinde kullanmak istiyorsanız, düğme. Daha fazla bilgi için bkz: [Visual Studio'da normal ifadeleri kullanma](../ide/using-regular-expressions-in-visual-studio.md).

> [!NOTE]
> **İfade oluşturucusu** düğmesi, yalnızca seçtiyseniz etkinleştirilir **normal ifadeler kullanmanız** altında **bulma seçeneklerini**.

## <a name="replace-with"></a>Değiştirin

Dizede örneklerini değiştirmek için **Aranan** kutusuna başka bir dizeyle, değiştirme dizesini girin **konan** kutusu. Dizede örneklerini silmek için **Aranan** kutusunda, bu alanı boş bırakın. Kendisi için en son aranır 20 dizelerini listesini açın. Bitişik seçin **ifade oluşturucusu** değiştirme dizesi içinde bir veya daha fazla normal ifadeler kullanmak istiyorsanız, düğme. Daha fazla bilgi için bkz: [Visual Studio'da normal ifadeleri kullanma](../ide/using-regular-expressions-in-visual-studio.md).

## <a name="look-in"></a>Bakılacak yer

Gelen seçilen seçeneği **konum** aşağı açılan liste belirler olup olmadığını **dosyalarda Değiştir** arar yalnızca şu anda etkin dosyalarda veya belirli klasörlerde depolanan tüm dosyaları arar. Listeden bir arama kapsamı seçin, bir klasör yolunu yazın veya tıklatın **Gözat (...)**  görüntülemek için düğmesini **Arama Klasörleri Seç** iletişim kutusuna ve arama klasörlerinin kümesi seçin. Doğrudan bir yol da yazabilirsiniz **konum** kutusu.

> [!NOTE]
> Varsa **konum** seçeneğe kullanıma kaynak kodu denetiminden yalnızca yerel makinenize indirilen bu dosyanın sürümü aranır bir dosya aramak neden olur.

## <a name="find-options"></a>Bulma seçenekleri

Genişlet veya daralt **bulma seçeneklerini** bölümü. Aşağıdaki seçenekler seçilen veya temizlenmiş:

**Büyük küçük harf duyarlı**

Seçili olduğunda, **Bul sonuçları** windows yalnızca örneklerini görüntülemek **Aranan** hem içerik ve servis talebi tarafından eşleşen dize. Örneğin, "MyObject" ile bir arama **eşleşen durumda** seçili olacak "MyObject" ancak "myobject" veya "MYOBJECT." döndürür

**Tam sözcükleri eşleştir**

Seçili olduğunda, **Bul sonuçları** windows yalnızca örneklerini görüntülemek **Aranan** tam sözcükleri eşleşen dize. Örneğin, "MyObject" Ara "MyObject" ancak "CMyObject" veya "MyObjectC." döndürür

**Normal İfadeler Kullanma**

Bu onay kutusu seçili olduğunda özel gösterimler metinde desenlerini tanımlamak için kullanabileceğiniz **Aranan** veya **yerine** metin kutuları. Bu gösterimler listesi için bkz: [Visual Studio'da normal ifadeleri kullanma](../ide/using-regular-expressions-in-visual-studio.md).

**Bu dosya türlerini arayın**

Bu liste içinde arama yapmak dosya türlerini gösterir **konum** dizinleri. Bu alan bırakılırsa boş, tüm dosyaların **konum** dizinleri arama yapılır. Herhangi bir öğeyi listeden, bu belirli türdeki dosyaları bulacağı önceden yapılandırılmış arama dizesini girmek için seçin.

## <a name="result-options"></a>Sonuç seçenekleri

Genişlet veya daralt **neden seçenekleri** bölümü. Aşağıdaki seçenekler seçilen veya temizlenmiş:

**Sonuçları 1 Bul** penceresi

Seçili olduğunda, geçerli arama sonuçları içeriğinin yerine geçecek **Bul sonuçları 1** penceresi. Bu pencere arama sonuçlarınızı görüntülemesi için otomatik olarak açılır. Bu pencere el ile açın, seçin **diğer pencereler** gelen **Görünüm** menü ve seçin **Bul sonuçları 1**.

**Sonuçları 2 bulmak** penceresi

Seçili olduğunda, geçerli arama sonuçları içeriğinin yerine geçecek **Bul sonuçları 2** penceresi. Bu pencere arama sonuçlarınızı görüntülemesi için otomatik olarak açılır. Bu pencere el ile açın, seçin **diğer pencereler** gelen **Görünüm** menü ve seçin **Bul sonuçları 2**.

**Dosya adları yalnızca görüntüleme**

Bu onay kutusu seçili olduğunda, **Bul sonuçları** windows tam adlarını ve yollarını arama dizesini içeren tüm dosyalar için liste. Ancak, sonuçlar dize göründüğü kod satırını eklemeyin. Bu onay kutusu için kullanılabilir **dosyalarda Bul** yalnızca.

**Değiştirilen dosyalar açık sonra Tümünü Değiştir tutun**

Seçili olduğunda, tüm dosyalar geri veya değişiklikleri kaydetmek için değişiklik yapılmıştır açık durumda bırakır. Bellek kısıtlamaları sonra bir değiştirme işlemi açık kalabileceği dosyalarının sayısını sınırlayabilir.

> [!CAUTION]
> Kullanabileceğiniz **geri** düzenleme için açık kalan dosyaları. Bu seçenek seçilmezse düzenleme kapalı, kalacak için zaten değildi dosyaları açmak ve hiçbir **geri** seçeneği kullanılabilir bu dosyaları.

## <a name="see-also"></a>Ayrıca bkz.

- [Metin bulma ve değiştirme](../ide/finding-and-replacing-text.md)
- [Dosyalarda Bul](../ide/find-in-files.md)
- [Visual Studio komutları](../ide/reference/visual-studio-commands.md)
