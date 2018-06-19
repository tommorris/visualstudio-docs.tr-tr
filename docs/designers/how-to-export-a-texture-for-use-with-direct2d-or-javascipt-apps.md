---
title: 'Nasıl yapılır: Direct2D veya Javascript Uygulamaları Kullanmak için Doku Dışa Aktarma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 241c25fe-764e-4e1b-ad32-b1377dcbb605
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81bfc2b3b171dffdcf77a22ccf02d5e3f70658a6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31925018"
---
# <a name="how-to-export-a-texture-for-use-with-direct2d-or-javascipt-apps"></a>Nasıl yapılır: Direct2D veya Javascript Uygulamaları Kullanmak için Doku Dışa Aktarma
Görüntü içerik ardışık düzen Direct2D'ın iç işleme kuralları ile uyumlu olan dokular oluşturabilirsiniz. Bu tür dokuları Direct2D kullanan uygulamalar ve JavaScript kullanılarak oluşturulan UWP uygulamalar için uygundur.

 Bu belgede, bu etkinlikler gösterir:

-   Görüntü içerik ardışık düzen tarafından işlenmek üzere kaynak görüntü yapılandırma.

-   Görüntü içerik kullanabileceğiniz bir doku bir Direct2D veya JavaScript uygulaması oluşturmak için ardışık düzen yapılandırma.

    -   Bir blok sıkıştırılmış .dds dosyası oluşturun.

    -   Önceden çoğaltılmış alfa oluşturur.

    -   Mipmap üretimini devre dışı bırakın.

## <a name="rendering-conventions-in-direct2d"></a>Direct2D kuralları oluşturma
 Direct2D bağlamında kullanılan dokuları bu Direct2D iç işleme kurallarına uymalıdır:

-   Direct2D saydamlık ve translucency önceden çoğaltılmış alfa kullanarak uygular. Doku saydamlığı veya translucency kullanmıyorsa bile Direct2D ile kullanılan dokuları önceden çoğaltılmış alfa içermesi gerekir. Önceden çoğaltılmış alfa hakkında daha fazla bilgi için bkz: [nasıl yapılır: alfa önceden çoğaltılmış olan doku verme](../designers/how-to-export-a-texture-that-has-premultiplied-alpha.md).

-   Bu sıkıştırma bloğu biçimlerden birini kullanarak, doku .dds biçiminde girilmesi gerekir:

    -   BC1_UNORM sıkıştırma

    -   BC2_UNORM sıkıştırma

    -   BC3_UNORM sıkıştırma

-   Mipmaps desteklenmez.

#### <a name="to-create-a-texture-thats-compatible-with-direct2d-rendering-conventions"></a>Direct2D işleme kuralları ile uyumlu bir doku oluşturmak için

1.  Temel bir doku ile başlar. Varolan bir görüntü yükleme ya da açıklandığı gibi yeni bir tane oluşturun [nasıl yapılır: temel bir doku oluşturma](../designers/how-to-create-a-basic-texture.md). Blok sıkıştırma .dds biçimde desteklemek için genişlik ve yükseklik dört boyutu, örneğin, 100 x 100, 128 x 128 veya 256 x 192 katları olan sahip bir doku belirtin. Mipmap oluşturma desteklenmediğinden doku kare olması gerekmez ve iki boyutu gücünü olması gerekmez.

2.  Görüntü içerik ardışık düzen tarafından işlenen doku dosyasını yapılandırın. İçinde **Çözüm Gezgini**, az önce oluşturduğunuz doku dosyası için kısayol menüsünü açın ve ardından **özellikleri**. Üzerinde **yapılandırma özellikleri**, **genel** sayfasında **öğesi türü** özelliğine **görüntü içerik ardışık düzen**. Olduğundan emin olun **içerik** özelliği ayarlanmış **Evet** ve **gelen hariç yapı** ayarlanır **Hayır**ve ardından  **Uygulama** düğmesi. **Görüntü içerik ardışık düzen** yapılandırması özellik sayfası görüntülenir.

3.  Çıktı biçimi blok sıkıştırılmış biçimlerden birine ayarlayın. Üzerinde **yapılandırma özellikleri**, **görüntü içerik ardışık düzen**, **genel** sayfasında **Sıkıştır** özelliğine  **BC3_UNORM sıkıştırma (/ sıkıştırma: BC3_UNORM)**. Diğer BC1, BC2 veya BC3 biçimleri, gereksinimlerinize bağlı olarak seçebilir. Direct2D BC4, BC5, BC6 veya BC7 dokuları şu anda desteklemiyor. Farklı BC biçimleri hakkında daha fazla bilgi için bkz: [blok sıkıştırma (Direct3D 10)](http://msdn.microsoft.com/library/windows/desktop/bb694531.aspx).

    > [!NOTE]
    >  Belirtilen sıkıştırma biçimi görüntü içerik ardışık düzen tarafından üretilen dosyasının biçimini belirler. Bu farklıdır **biçimi** görüntü kaynak görüntü dosyası biçimi diskte depolanmış olarak belirleyen Düzenleyicisi'nde, kaynak görüntüsünün özelliği — diğer bir deyişle, *çalışma biçimi*. Genellikle, sıkıştırılmış bir çalışma biçimi istemezsiniz.

4.  Görüntü içerik önceden çoğaltılmış alfa kullanan bir çıktı oluşturmak için ardışık düzenini yapılandırın. Üzerinde **yapılandırma özellikleri**, **görüntü içerik ardışık düzen**, **genel** sayfasında **önceden çarpılan alfa biçimine dönüştürme** özelliğine **Evet (/ generatepremultipliedalpha)**.

5.  Böylece mipmaps üretmez görüntü içerik ardışık düzenini yapılandırın. Üzerinde **yapılandırma özellikleri**, **görüntü içerik ardışık düzen**, **genel** sayfasında **oluşturmak MIPS** özelliğine**Hayır**.

6.  Seçin **Tamam** düğmesi.

 Projeyi derlerken görüntü içerik ardışık düzen kaynak görüntü çalışma biçiminden belirttiğiniz çıkış biçimine dönüştürür — dönüştürme önceden çoğaltılmış alfa nesil içerir — ve sonucu projenin çıktı dizinine kopyalanır.