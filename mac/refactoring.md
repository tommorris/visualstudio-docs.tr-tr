---
title: Kodu yeniden düzenleme
description: Visual Studio'da kodu Mac için yeniden düzenleme kaynak çözümleme kullanımı ile basit yapılır.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: C7782BF3-016F-4B41-8A81-85FC540A1A8F
ms.openlocfilehash: ec0ae7aa61275b9b5362db178b9bdb8e3ccedfbb
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="refactoring"></a>Yeniden Düzenle

Kodu yeniden düzenleme, yeniden düzenlemesine, yeniden yapılandırmayı ve kod genel davranışını değişmeyen sağlarken var olan kodu açıklamak için bir yoldur.

Yeniden düzenleme veya herhangi diğer geliştirici veya koda başvuran kullanıcı daha kullanışlı, okunabilir ve sürdürülebilir hale healthier bir kod temeli oluşturur.

Roslyn, Microsoft'un açık kaynaklı .NET derleyici platformu ile Mac'ın tümleştirmesi için Visual Studio için daha fazla düzenleme işlemlerine izin verir.

## <a name="renaming"></a>Yeniden adlandırma 

*Yeniden adlandırma* komutu yeniden düzenleme herhangi kodu tanımlayıcısı (örneğin, bir sınıf adı, özellik adı vb.) tanımlayıcıyı tüm örneklerini bulun ve bunları değiştirmek için kullanılabilir. Bir simge yeniden adlandırmak için üzerinde sağ tıklatın ve seçin **yeniden düzenlemeniz > yeniden adlandırma**, veya **Cmd + R** anahtar bağlama:

![Menü öğesini yeniden adlandırma](media/refactoring-renaming1.png)

Bu simgenin ve tüm başvuruları vurgulayın. Yeni bir adı yazmaya başladığınızda kodunuzdaki tüm başvuruları otomatik olarak değiştirir ve tuşuna basarak, yeniden adlandırma tamamlanmasından sinyal **Enter**:

 ![Yeniden adlandırma ve tanımlayıcı](media/refactoring-renaming2.png)

## <a name="context-actions"></a>Bağlam Eylemler

Bağlam Eylemler, herhangi bir C# kod incelemek izin ver ve tüm olası yeniden düzenleme seçenekleri görebilirsiniz. 

**Gidermek** ve **yeniden düzenlemeniz** bağlamı öğeleri tek bir birleştirilmiş *hızlı düzeltme...*  kullanılabilir tüm içerik Eylemler ile sağlayacak öğe:

![İçerik öğeleri görüntüleme](media/refactoring-context-action.png)

Herhangi bir bağlam Eylemler gelerek veya onları ne eklenecek veya kodunuzdan kaldırılan önizlemesini sağlayacaktır.

Alternatif olarak, basabilirsiniz **seçeneği + Enter** kodunuzun başka bir yerindeki:

![Seçeneğini girin bağlam öğeleri](media/refactoring-image2a.png)

Bu seçenekler etkinleştirmek için seçmelisiniz *etkinleştirmek açık dosyaların kaynak çözümleme* seçeneklerinde **Mac için Visual Studio > Tercihler > Metin Düzenleyicisi > kaynak çözümleme**:

 ![Kaynak Çözümleme etkinleştirme](media/refactoring-options.png)

Etkin veya devre dışı göz atarak önerilebilir, 100'den olası eylemler vardır **Mac için Visual Studio > Tercihler > kaynak çözümleme > C# > kod eylemleri** seçerek veya kutunun yanındaki unselecting Eylem:

 ![C# kaynak çözümleme eylemleri](media/refactoring-image3a.png)

### <a name="common-context-actions"></a>Genel bağlam eylemleri

En sık kullanılan bağlam eylemlerin bazıları aşağıda açıklanmıştır.

#### <a name="extract-method"></a>Ayıklama yöntemi

Ayıklama yöntemi yeniden düzenleme işlemi, var olan bir üye kodu seçimi çıkartarak yeni bir yöntem oluşturmanıza olanak sağlar. Bu eylem, iki şey yapar:

* Seçili kodu içeren yeni bir yöntem oluşturur
* Seçilen koda bulunduğu yerde yeni yöntemini çağırır.

##### <a name="example"></a>Örnek

1. Aşağıdaki kodu ekleyin:

```
    class MainClass
    {

        double CalculatePyramidVolume(double baseArea, double height)
        {

            double volume = (baseArea * height) / 3;

            return volume;
        }
    }
```

2. Satırı vurgulayın `double volume = (baseArea * height) / 3;`, sağ tıklayın ve seçin **yeniden düzenlemeniz > ayıklama yöntemi**.

3. Yeni yöntemi kodunuzu nereye yerleştirileceğini seçmek için ok tuşlarını kullanın.


#### <a name="encapsulate-field"></a>Alanı Yalıt

Yalıt işlemi, varolan bir alandan bir özellik oluşturmanıza olanak sağlar ve yeni oluşturulan özellik başvurmak için kodunuzu güncelleştirir. Alan yalıtan bir özellik oluşturarak, doğrudan erişim ortak alanınızı diğer nesneleri onu değiştiremezsiniz anlamına vermemek.

Bu eylem aşağıdakileri yapın:

* Özel erişim değiştiricisi değiştirir.
* (Alanın; bu durumda, yalnızca bir alıcı oluşturacak salt okunur olmadığı sürece) bir'Set ' yordamı bir alan için oluşturur.


## <a name="source-analysis"></a>Kaynak Çözümleme

Kaynak Çözümleme kodunuzu anında altı çizili olası hataları ve stil ihlalleri tarafından analiz eder ve otomatik sağlama bağlam eylemler olarak giderir. 

Metin Düzenleyicisi'ni sağ tarafta kaydırma çubuğu görüntüleyerek herhangi bir zamanda tüm her dosya için kaynak çözümleme sonuçlarını görüntüleyebilirsiniz:

 ![Kaynak Çözümleme kenar çubuğu](media/refactoring-image4a.png)

Üst daire tıklatırsanız, her bir öneri ilk gösteren yüksek önem derecesi sorunlarla yineleyebilirsiniz. Tek tek sonuç veya hattı üzerinden bekleyerek bağlam eylemleri arasında sabit sorunu görüntülenir:

 ![Kaynak Çözümleme öğesi](media/refactoring-image5.png)

