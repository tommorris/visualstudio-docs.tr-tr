---
title: 'Nasıl yapılır: Mipmaps içeren bir doku verme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 3d1ad14b-44fb-4cf0-a995-5e2f60026524
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f9bd1c303c5901b890d2aa2fb0f44c95f2ae72c6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-export-a-texture-that-contains-mipmaps"></a>Nasıl yapılır: Mipmap'leri İçeren Dokuyu Dışa Aktarma
Görüntü içerik ardışık düzen mipmaps kaynak görüntü projenizin yapı aşamasının bir parçası olarak oluşturabilirsiniz. Ne zaman gereksinim her MIP düzeyi görüntü içeriğini el ile belirtmek — belirli efektler elde etmek için yapabilecek şekilde — mipmaps derleme zamanında oluşturma sağlar mipmap içeriği hiçbir zaman eşitleme haline gelir ve mipmaps oluşturma performans maliyetini ortadan kaldırır Çalışma zamanında.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Görüntü içerik ardışık düzen tarafından işlenmek üzere kaynak görüntü yapılandırma.  
  
-   Görüntü içerik mipmaps oluşturmak için ardışık düzen yapılandırma.  
  
## <a name="exporting-mipmaps"></a>Mipmaps dışarı aktarma  
 Mipmap oluşturma doku yüzeyleri 3B oyun veya uygulama için otomatik ekran alanı düzey-in-ayrıntıları sağlar. Oyun veya uygulama işleme performansını tüm doku, örneklenen her zaman aşağı örneklenen gerekmez, doku aşağı örneklenen sürümleri önceden bilgi işlem tarafından geliştirir.  
  
#### <a name="to-export-a-texture-that-has-mipmaps"></a>Mipmaps sahip bir doku dışarı aktarmak için  
  
1.  Temel bir doku ile başlar. Varolan bir görüntü dosyası yüklemek ya da açıklandığı gibi oluşturmak [nasıl yapılır: temel bir doku oluşturma](../designers/how-to-create-a-basic-texture.md). Mipmaps desteklemek için genişlik ve yükseklik iki boyutu, örneğin, 64 x 64, 256 x 256 veya 512 x 512 aynı güç olan sahip bir doku belirtin.  
  
2.  Böylece görüntü içerik ardışık düzen tarafından işlenen, yeni oluşturduğunuz doku dosyasını yapılandırın. İçinde **Çözüm Gezgini**, az önce oluşturduğunuz doku dosyası için kısayol menüsünü açın ve ardından **özellikleri**. Üzerinde **yapılandırma özellikleri**, **genel** sayfasında **öğesi türü** özelliğine **görüntü içerik ardışık düzen**. Olduğundan emin olun **içerik** özelliği ayarlanmış **Evet** ve **gelen hariç yapı** ayarlanır **Hayır**ve ardından  **Uygulama** düğmesi. **Görüntü içerik ardışık düzen** yapılandırması özellik sayfası görüntülenir.  
  
3.  Görüntü içerik mipmaps oluşturmak için ardışık düzenini yapılandırın. Üzerinde **yapılandırma özellikleri**, **görüntü içerik ardışık düzen**, **genel** sayfasında **oluşturmak MIPS** özelliğine**Evet (/ generatemips)**.  
  
4.  Seçin **Tamam** düğmesi.  
  
 Projeyi derlerken görüntü içerik ardışık düzen kaynak görüntü çalışma biçiminden MIP düzeyleri dahil belirtilen ve sonuç projenin çıktı dizinine kopyalanır çıkış biçimine dönüştürür.