---
title: 'Nasıl yapılır: MIP Düzeyleri Oluşturma ve Değiştirme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: f64d4369-2307-4175-a39a-2e45506f7fa1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b2948b33db198ddd8f7e002acbad155da66da58
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-and-modify-mip-levels"></a>Nasıl yapılır: MIP Düzeyleri Oluşturma ve Değiştirme
Bu belge nasıl kullanılacağını göstermektedir **görüntü Düzenleyicisi** oluşturmak ve değiştirmek için *MIP düzeyleri* ayrıntılı bilgi için doku alanı düzeyi-in-(LoD).

## <a name="generating-mip-levels"></a>MIP düzeyleri oluşturma
 *Mipmap oluşturma* işleme hızını artırmak ve önceden hesaplama ve farklı boyutlarda doku birkaç kopyasını depolayarak yumuşatma yapıları doku nesneler üzerinde azaltmak için kullanılan bir tekniktir. MIP düzeyi olarak bilinen her kopya yarım genişlik ve yükseklik önceki kopyasının ' dir. Bir doku nesneyi yüzey üzerinde işlendiğinde en yakından doku yüzey alanı ekran alana karşılık gelen MIP düzeyi otomatik olarak seçilir. Bu grafik donanımı tutarlı görsel kalite korumak için büyük boyutlu dokular filtrelemek yok anlamına gelir. Bellek MIP düzeyleri depolamanın maliyeti hakkında daha fazla tek başına özgün doku daha 33 yüzde olsa da, performans ve görüntü kalitesini kazançlar Hizala.

#### <a name="to-generate-mip-levels"></a>MIP düzeyleri oluşturmak için

1.  Bölümünde açıklandığı gibi temel bir doku ile başlayan [nasıl yapılır: temel bir doku oluşturma](../designers/how-to-create-a-basic-texture.md). En iyi sonuçlar için genişlik ve yükseklik iki boyutu, örneğin, 256, 512, 1024, gücünü olan sahip bir doku belirtin ve benzeri.

2.  MIP düzeyleri oluşturur. Üzerinde **görüntü Düzenleyicisi modu** araç seçin **Gelişmiş**, **Araçları**, **oluşturmak MIPS**.

     Dikkat **MIP bir sonraki düzeye gidin** ve **önceki MIP düzeyine gitmek** düğmeleri artık görünür **görüntü Düzenleyicisi modu** araç. Varsa **özellikleri** penceresi görüntülenir, ayrıca dikkat salt okunur özellikler **MIP düzeyi** ve **MIP düzey sayısı** artık görüntüsü özelliklerinde görüntülenir.

## <a name="modifying-mip-levels"></a>MIP düzeylerini değiştirme
 Özel efektler elde etmek veya belirli ayrıntı düzeylerinde görüntü kalitesini artırmak için ayrı ayrı her MIP düzeyini değiştirebilirsiniz. Örneğin, bir doku nesnesi (küçük MIP düzeylere büyük uzaklığı karşılık gelir) uzaklıkta farklı bir görünüm verebilir veya metin veya sembolleri içeren dokuları bile küçük MIP düzeylerinde okunaklı kalmasını sağlayabilirsiniz.

#### <a name="to-modify-an-individual-mip-level"></a>Tek bir MIP düzeyini değiştirmek için

1.  Değiştirmek istediğiniz MIP düzeyini seçin. Üzerinde **görüntü Düzenleyicisi modu** araç, kullanım **MIP bir sonraki düzeye gidin** ve **önceki MIP düzeyine gitmek** MIP düzeyleri arasında taşımak için düğmeler.

2.  Değiştirmek istediğiniz MIP düzeyi seçtikten sonra diğer MIP düzeyleri içeriğini değiştirmeden değiştirmek için çizim araçları kullanabilirsiniz. Çizim Araçları mevcuttur **görüntü Düzenleyicisi** araç. Bir aracı seçtikten sonra özelliklerinde değiştirebilirsiniz **özellikleri** penceresi. Çizim araçları ve özellikleri hakkında daha fazla bilgi için bkz: [görüntü Düzenleyicisi](../designers/image-editor.md).

> [!NOTE]
>  Tek tek MIP düzeyleri içeriğini değiştirmeye gerekmez, — belirli efektler elde etmek için yapabilecek şekilde — derleme zamanında kaynağı doku mipmaps oluşturmak öneririz. Bu MIP düzeyi yapılan değişiklikler diğer düzeylere otomatik olarak yayılmaz çünkü MIP düzeyleri kaynağı doku ile eşitlenmiş kalmasını sağlamaya yardımcı olur. Derleme zamanında mipmaps oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir doku bu içeren Mipmaps dışarı](../designers/how-to-export-a-texture-that-contains-mipmaps.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Temel Doku Oluşturma](../designers/how-to-create-a-basic-texture.md)