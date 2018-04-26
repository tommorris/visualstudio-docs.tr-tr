---
title: Visual Studio'da kod ölçümleri Hesapla
ms.date: 12/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code metrics [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3d0bf9b0bf689be847e7f16f2ee01db6e3df6d7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="code-metrics-values"></a>Kod ölçüm değerleri

Modern yazılım uygulamaları artan karmaşıklık kodu güvenilir ve korunabilir hale getirme zorluk da artırır. Kod ölçümleri, geliştirmekte olduğunuz daha iyi bir anlayış kod geliştiricilerin sağlayan yazılım ölçüleri kümesidir. Kod ölçümleri yararlanarak, geliştiricilerin hangi türleri ve/veya yöntemleri yeniden veya daha fazla tamamen test anlayabilirsiniz. Geliştirme ekiplerinin olası riskleri tanımlamak, bir projenin geçerli durumu anlamanıza ve yazılım geliştirme sırasında ilerleme durumunu izlemek.

Geliştiriciler Visual Studio karmaşıklığı ve bunların yönetilen kod bakımı ölçmek kod ölçümleri verileri üretme için kullanabilirsiniz. Kod ölçümleri verileri çözümün tamamında veya tek bir proje için oluşturulabilir.

Visual Studio'da kod ölçümleri verileri üretme hakkında daha fazla bilgi için bkz: [nasıl yapılır: kod ölçümleri verileri üretme](../code-quality/how-to-generate-code-metrics-data.md).

## <a name="software-measurements"></a>Yazılım ölçümleri

Aşağıdaki listede kod Visual Studio hesaplar ölçümleri sonuçları gösterir:

- **Bakım dizin** -kodunu sürdürme göreli kolaylığını temsil eden bir dizin değeri 0 ile 100 arasında hesaplar. Yüksek bir değer daha iyi bakım anlamına gelir. Renk kodlu derecelendirmeleri, hızlı bir şekilde kodunuzda sorunlu noktaları tanımlamak için kullanılabilir. Yeşil bir derecelendirme 20 ile 100 arasındadır ve kod iyi bakım sahip olduğunu gösterir. Sarı bir derecelendirme 10 ve 19 arasında ve kodu oldukça sürdürülebilir olduğunu gösterir. Kırmızı bir derecelendirme 0 ile 9 arasında bir derecelendirme ve düşük bakım gösterir.

- **Cyclomatic karmaşıklık** -kod yapısal karmaşıklığını ölçer. Program akışı farklı kod yolları sayısı hesaplayarak oluşturulur. Karmaşık denetim akışı olan bir program iyi kod kapsamı elde etmek için daha fazla test gerektirir ve daha az sürdürülebilir olacaktır.

- **Devralma derinliği** -sınıf hiyerarşisi köküne genişletmek sınıf tanımları sayısını gösterir. Belirli yöntemler ve alanları tanımlandığı anlamak için olabilir daha derin hiyerarşi daha zor veya / ve yeniden tanımlanan.

- **Sınıf bağ** -ölçer bağlantı parametreleri, yerel değişkenleri, dönüş türleri, yöntem çağrıları, genel veya şablonu örneklemesi, temel sınıfları, arabirim uygulamaları, dış türlerinde tanımlanan alanları benzersiz sınıflarına ve öznitelik decoration. İyi yazılım tasarımı türleri ve yöntemleri yüksek cohesion sahip ve Kuplaj düşük olduğunu belirler. Yüksek bağlantı yeniden kullanmak ve diğer türleri üzerinde birçok onun bağımlılıklarını nedeniyle sağlamak zor bir tasarım gösterir.

- **Kod satırlarını** -yaklaşık kodu satır sayısını belirtir. Sayı IL kodu göre ve bu nedenle tam kaynak kodu dosyasının satır sayısını değil. Çok yüksek bir sayı türü veya yöntemi çok fazla iş işlemini yapmaya çalışan ve bölmek gösteriyor olabilir. Türü veya yöntemi sağlamak zor olabilir gösterebilir.

## <a name="anonymous-methods"></a>Anonim yöntemler

Bir *anonim yöntemi* bir ada sahip bir yöntem. Anonim yöntemler, en sık kod bloğu temsilci parametre olarak geçirmek için kullanılır. Ölçümleri sonuçları yöntemi veya erişimci gibi bir üye olarak bildirilen bir anonim yöntemi için yöntem bildirir üye ile ilişkili. Bunlar yöntemini çağırır üye ile ilişkili değildir.

Kod ölçümleri anonim yöntemler nasıl işler hakkında daha fazla bilgi için bkz: [anonim yöntemler ve Kod Analizi](../code-quality/anonymous-methods-and-code-analysis.md).

## <a name="generated-code"></a>Oluşturulan kod

Bazı yazılım araçları ve derleyicileri projeye eklendi ve proje Geliştirici görmezsiniz veya değil değiştirmelisiniz kod oluşturur. Çoğunlukla, ölçüm değerleri hesaplarken kod ölçümleri oluşturulan kod yok sayar. Bu ne Geliştirici bakın ve değiştirebileceğini yansıtmak üzere ölçümleri değerleri sağlar.

Geliştirici bakın ve değiştirebileceğini kodu olduğundan Windows Forms için oluşturulan kod, göz ardı edilir değil.

## <a name="next-steps"></a>Sonraki adımlar

- [Nasıl yapılır: kod ölçümleri verileri üretme](../code-quality/how-to-generate-code-metrics-data.md)
- [Kod ölçümleri sonuçları penceresi kullanın](../code-quality/working-with-code-metrics-data.md)