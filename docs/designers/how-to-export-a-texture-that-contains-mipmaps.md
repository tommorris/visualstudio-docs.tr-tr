---
title: "Nasıl yapılır: Mipmap'leri İçeren Dokuyu Dışa Aktarma"
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0ff27404a37eb641deb8409e6e529bf052264591
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>Nasıl yapılır: Mipmap'leri İçeren Dokuyu Dışa Aktarma

Görüntü içerik ardışık düzen mipmaps kaynak görüntü projenizin yapı aşamasının bir parçası olarak oluşturabilirsiniz. Bazı efektler elde etmek için bazı durumlarda, her MIP düzeyi görüntü içeriğini el ile belirtmeniz gerekir. Her MIP düzeyi görüntü içeriğini el ile belirtmeniz gerekmediğinde, derleme zamanında mipmaps oluşturma mipmap içeriği hiçbir zaman eşitleme hale sağlar. Çalışma zamanında mipmaps oluşturma performans maliyetini ortadan kaldırır.

Bu makalede yer almaktadır:

- Görüntü içerik ardışık düzen tarafından işlenmek üzere kaynak görüntü yapılandırma.

- Görüntü içerik mipmaps oluşturmak için ardışık düzen yapılandırma.

## <a name="export-mipmaps"></a>Mipmaps dışarı aktarma

Mipmap oluşturma doku yüzeyleri 3B oyun veya uygulama için otomatik ekran alanı düzey-in-ayrıntıları sağlar. Oyun veya uygulama işleme performansını doku aşağı örneklenen sürümleri önceden bilgi işlem tarafından geliştirir. Tüm doku olmak zorunda değildir anlamına gelir aşağı-her zaman, örneklenen aşağı örneklenen sürümleri önceden bilgi işlem örneklenen.

### <a name="to-export-a-texture-that-has-mipmaps"></a>Mipmaps sahip bir doku dışarı aktarmak için

1.  Temel bir doku ile başlar. Varolan bir görüntü dosyası yüklemek ya da açıklandığı gibi oluşturmak [nasıl yapılır: temel bir doku oluşturma](../designers/how-to-create-a-basic-texture.md). Mipmaps desteklemek için genişlik ve yükseklik iki boyutu, örneğin, 64 x 64, 256 x 256 veya 512 x 512 aynı güç olan sahip bir doku belirtin.

2.  Böylece görüntü içerik ardışık düzen tarafından işlenen, yeni oluşturduğunuz doku dosyasını yapılandırın. İçinde **Çözüm Gezgini**, oluşturduğunuz doku dosyası için kısayol menüsünü açın ve ardından **özellikleri**. Üzerinde **yapılandırma özellikleri** > **genel** sayfasında **öğesi türü** özelliğine **görüntü içerik ardışık düzen**. Olduğundan emin olun **içerik** özelliği ayarlanmış **Evet** ve **gelen hariç yapı** ayarlanır **Hayır**. Seçin **uygulamak**.

   **Görüntü içerik ardışık düzen** yapılandırması özellik sayfası görüntülenir.

3.  Görüntü içerik mipmaps oluşturmak için ardışık düzenini yapılandırın. Üzerinde **yapılandırma özellikleri** > **görüntü içerik ardışık düzen** > **genel** sayfasında **MIPSOluştur** özelliğine **Evet (/ generatemips)**.

4.  Seçin **Tamam**.

Projeyi derlerken görüntü içerik ardışık düzen kaynak görüntü çalışma biçiminden MIP düzeyleri dahil belirtilen çıkış biçimine dönüştürür. Sonuç projenin çıktı dizinine kopyalanır.