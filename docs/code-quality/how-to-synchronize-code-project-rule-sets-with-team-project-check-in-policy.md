---
title: 'Nasıl yapılır: Takım Projesi İade İlkesiyle Kod Proje Kural Kümelerini Eşitleme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.selecttfsruleset
ms.assetid: 9b02f934-2db6-41ec-aaff-9c31ceec2f04
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bcc6fe17d9f5e7666531086549eae6ad26741a22
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy"></a>Nasıl yapılır: Takım Projesi İade İlkesiyle Kod Proje Kural Kümelerini Eşitleme

Takım projesi için iade ilkesiyle kod projeleri için Kod Analizi ayarları en az İade İlkesi'ni ayarlamak kuralında belirtilen kuralları içeren bir kural kümesi belirterek eşitleyin. Geliştirici sağlama, ad ve kural için iade ilkesi kümesi konumunu bildirebilirsiniz. Projesi için Kod Analizi kural doğru kümesi kullandığından emin olmak için aşağıdaki seçeneklerden birini kullanabilirsiniz:

-   İade İlkesi Microsoft yerleşik kural kümeleri kullanıyorsa, kod projesi için özellikleri iletişim kutusunu açın, Kod Analizi sayfası görüntülemek ve kod projesi ayarları Kod Analizi sayfasında ayarlayın kuralı seçin. Standart kural kümeleri Visual Studio ile otomatik olarak yüklenen Microsoft salt okunur olarak ayarlanır ve düzenlenmemelidir. Kural kümeleri düzenlenemez, İlkesi ve yerel kural kümeleri kurallarında eşleşen garanti.

-   İade ilkesini özel bir kural kümesini kullanıyorsa, yerel bir kopya oluşturmak için sürüm denetiminde kural kümesi dosyası üzerinde bir get işlemi gerçekleştirin. Ardından, yerel bir konum kod projesi için kod çözümleme ayarlarını belirtin. Kurallar kural kümesi için iade ilkesi güncel eşleşiyorsa garanti.

     Takım projesi kök kod projenize ile aynı ilişkide olan yerel bir klasöre sürüm denetim konumu eşlerseniz kural konumunu göreli bir yol kullanarak ayarlanır. Kod çözümleme kod projesi ayarını diğer bilgisayarlara taşınabilmesi göreli yolu sağlar.

-   Kural için bir kod projesi için iade ilkesi kümesi bir kopyasını Özelleştir. Yeni kural kümesi iade ilkedeki tüm kurallar ve dahil etmek istediğiniz herhangi bir kuralın içerdiğinden emin olun. Tüm kurallar kural kümesi için iade ilkesi ayarlama kuralı içerir emin olmanız gerekir.

## <a name="to-specify-a-microsoft-standard-rule-set"></a>Bir Microsoft Standart kural belirtmek için ayarlayın

1.  İçinde **Çözüm Gezgini**kod projesine sağ tıklayın ve ardından **özellikleri**.

2.  Tıklatın **kod çözümleme**.

3.  İçinde **bu kural kümesini çalıştırmak** listesinde, iade ilkesi kuralı Ayarla'yı tıklatın.

## <a name="to-specify-a-custom-check-in-policy-rule-set"></a>Özel İade İlkesi kural kümesini belirtmek için

1.  Gerekirse, alma işlemi iade ilkesi belirtir kural kümesi dosyası üzerinde gerçekleştirin.

2.  İçinde **Çözüm Gezgini**kod projesine sağ tıklayın ve ardından **özellikleri**.

3.  Tıklatın **kod çözümleme**.

4.  İçinde **bu kural kümesini çalıştırmak** tıklatın  **\<Gözat... >**.

5.  İçinde **açık** iletişim kutusunda, İade İlkesi kural kümesi dosyası belirtin.

## <a name="to-create-a-custom-rule-set-for-a-code-project"></a>Özel bir kural oluşturmak için bir kod projesi için ayarlayın

1.  Proje Ayarları iletişim kutusunun Kod Analizi sayfası üzerinde takım projesi iade ilkesi seçmek için daha önce bu konudaki yordamları izleyin.

2.  Tıklatın **açık**.

3.  Ekleyip kuralları kullanarak [kural kümesi düzenleyici](../code-quality/working-in-the-code-analysis-rule-set-editor.md).

4.  Değiştirilen kural .ruleset dosyasını yerel bilgisayarda veya bir UNC yolu kümesi kaydedin.

5.  Kod projesi için özellikleri iletişim kutusunu açmak ve görüntülemek **Kod Analizi** sayfası.

6.  İçinde **bu kural kümesini çalıştırmak** tıklatın  **\<Gözat... >**.

7.  İçinde **açık** iletişim kutusunda, kural dosya kümesi belirtin.