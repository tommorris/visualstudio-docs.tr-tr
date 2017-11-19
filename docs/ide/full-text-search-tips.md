---
redirect_url: /visualstudio/ide/how-to-search-for-topics
ms.openlocfilehash: a66c168ca81b22c32fc05afddd01266950791d1e
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
Başlık: "tam metin arama ipuçları | Microsoft Docs"MS.özel:" "ms.date:" 11/04/2016"ms.reviewer:" "MS.Paket:" "ms.technology: 
  - "vs Yardım Görüntüleyicisi" ms.tgt_pltfrm: "" ms.topic: "makale" f1_keywords: 
  - "hv_search" helpviewer_keywords: 
  - "Yardım Görüntüleyicisi, tam metin arama ipuçları"
  - "[Yardım Görüntüleyicisi] tam metin arama ipuçları" ms.assetid: bcaad23d-2ca7-4bec-8b54-b884bc34e70b caps.latest.revision: 13 Yazar: "gewarren" ms.author: "gewarren" Yöneticisi: ghogen
---
# <a name="full-text-search-tips"></a>Tam metin arama ipuçları
Yardım'da bilgi bulmak için daha kullanışlı yöntemler tam metin araması gerçekleştirerek biridir. Sözdizimi sorgunuzu nasıl etkileyeceğini anlamak, sizi ilgilendiren konular da sonuç olarak daha hedeflenen aramalar oluşturabilirsiniz. Sözdizimi, özel karakterler, ayrılmış sözcükleri ve filtreleri içerir. Bu konu, sorgularınızı ipuçları, yordamlar ve craft daha iyi yardımcı olmak için ayrıntılı sözdizimi bilgi sağlar.
  
### <a name="general-guidelines"></a>Genel yönergeleri  
Aşağıdaki tabloda bazı temel kurallar ve arama sorguları Yardım geliştirmek için yönergeler içerir.  
  
|Sözdizimi|Açıklama|  
|------------|-----------------|  
|Büyük/küçük harfe duyarlılık|Aramalar büyük küçük harfe duyarlı değildir. Büyük veya küçük harf karakterler kullanarak arama ölçütlerinizi geliştirin. Örneğin, "OLE" ve "ole" aynı sonuçları döndürür.|  
|Karakter birleşimleri|Yalnızca tek tek harfler için (a-z) arayamaz veya sayılar (0-9). Kullanmayı denerseniz arama belirli, gibi "ve", "Kimden" ayrılmış sözcükler ve "ile" bunlar göz ardı edilir. Daha fazla bilgi için "bu konunun ilerleyen bölümlerinde yer alan" joker karakterlerini kullanabilirsiniz (Durma sözcükleri) yoksayıldı sözcükler.|  
|Değerlendirme sırası|Arama sorguları soldan sağa doğru olarak değerlendirilir.|  
  
### <a name="search-syntax"></a>Search sözdizimi  
 "Word1 word2" gibi birden çok sözcük içeren bir arama dizesi belirtirseniz, o dizeyi yazmakla eşdeğerdir: "word1 ve word2", tüm arama dizesi bağımsız sözcükleri içeren konular döndürür.  
  
> [!IMPORTANT]
> - Tümcecik aramalar desteklenmez. Bir arama dizesi birden fazla sözcük belirtirseniz, döndürülen konuları tüm belirttiğiniz sözcükleri ancak mutlaka belirttiğiniz terimin içerir.  
> - Mantıksal işleçler Boole sözcükleri arasındaki ilişkiyi belirtmek için kullanın. AND, OR, NOT, gibi mantıksal işleçler içerir ve yakın, daha fazla için aramanızı daraltın. Örneğin, "Birliği bildirmek için" arıyorsanız, arama sonuçları sözcükler "bildirme" ve "birleşim" en fazla birbirlerinden birkaç sözcükler içeren konuları içerir. Daha fazla bilgi için bkz: [arama ifadelerindeki mantıksal işleçler](../ide/logical-operators-in-search-expressions.md).  
  
### <a name="filters"></a>FilTReleri  
 Gelişmiş arama işleçleri kullanarak arama sonuçlarını daha fazla kısıtlayabilirsiniz. Yardım, bir tam metin arama sonuçlarını filtrelemek için kullanabileceğiniz üç kategorileri içerir: Başlık, kodu ve anahtar sözcüğü.
  
### <a name="ranking-of-search-results"></a>Arama sonuçlarını sıralama  
 Arama algoritması derece yardımcı olmak için belirli ölçütlere geçerlidir sonuçlar listesinde arama sonuçlarını daha yüksek veya düşük. Genel olarak:  
  
1.  Başlık arama sözcükler içeren içerikleri değil içerik daha yüksek önem derecesi.  
  
2.  Arama sözcükleri yakınında içeren içerikleri değil içerik daha yüksek önem derecesi.  
  
3.  Arama sözcükleri daha yüksek yoğunluğu bulunduğu içeriği arama sözcükleri daha düşük yoğunluğu olan içeriği, daha yüksek önem derecesi.  
  
### <a name="words-ignored-in-searches-stop-words"></a>Aramaları (Durma sözcükleri) yok sayılan sözcükler  
 Otomatik olarak sık tekrarlanan sözcükleri veya bazen Durma sözcükleri adı verilen sayı bir tam metin araması sırasında göz ardı edilir. Tümcecik "geçiş" için arama yaparsanız, örneğin, arama sonuçları "geçiş" sözcüğünü içeren konular değil "ile ancak" görüntüler.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Bilgi bulun](../ide/locate-information.md)   
[Arama ifadelerindeki mantıksal işleçler](../ide/logical-operators-in-search-expressions.md)