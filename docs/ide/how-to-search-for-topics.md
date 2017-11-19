---
title: "Nasıl yapılır: Konu Arama | Microsoft Docs"
ms.custom: 
ms.date: 11/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683f1b0c-1551-4bba-91fe-3855f03fdd69
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ec4ec1c06d6c64a344e9e39d01c850b901534af8
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-search-for-topics"></a>Nasıl yapılır: Konu Arama
Belirli bir sözcük içeren tüm konuları bulmak için tam metin arama özelliğini kullanın. Ayrıca, daraltın ve joker karakter ifadeleri, mantıksal işleçler ve Gelişmiş arama işleçleri kullanarak aramanızı özelleştirin.  
  
Ara sekmesini açmak için **arama** sekmesinde Yardım Görüntüleyici penceresinde veya klavye kullanıcısıysanız seçin **Ctrl + E**.  
  
## <a name="to-perform-a-full-text-search"></a>Tam metin araması gerçekleştirmek için 
1.  Arama kutusuna, bulmak istediğiniz sözcük yazın.  
  
2.  Arama sorgusu, aramayı uygulamak için hangi mantıksal veya Gelişmiş arama işleçleri varsa belirtin. Tüm kullanılabilir yardım aramak için işleçleri kullanmayın.  
  
    > [!NOTE]
    >  İçinde **Görüntüleyici seçenekleri** iletişim kutusu, arama sonuçları sayısı gibi ek Tercihler bir saat ve birincil yerel ayarınız İngilizce değilse İngilizce içerik dahil edilip edilmeyeceğini görüntülenecek belirtebilirsiniz.  
  
3.  Seçin **Enter** anahtarı.  
  
     Bir arama varsayılan olarak en fazla 200 eşleşmeli döndürür ve arama sonuçları alanında görüntüler. Her bir sonucu için ek sürüm bilgileri, içerik bağlı olarak görünebilir.  
  
4.  Bir konu görmek için sonuçları listesinden başlığını seçin.

## <a name="full-text-search-tips"></a>Tam metin arama ipuçları
Sözdizimi sorgunuzu nasıl etkileyeceğini anlamak, sizi ilgilendiren konular da sonuç olarak daha hedeflenen aramalar oluşturabilirsiniz. Sözdizimi, özel karakterler, ayrılmış sözcükleri ve filtreleri içerir. Bu konu, sorgularınızı ipuçları, yordamlar ve craft daha iyi yardımcı olmak için ayrıntılı sözdizimi bilgi sağlar.
  
### <a name="general-guidelines"></a>Genel yönergeleri  
Aşağıdaki tabloda bazı temel kurallar ve arama sorguları Yardım geliştirmek için yönergeler içerir.  
  
|Sözdizimi|Açıklama|  
|------------|-----------------|  
|Büyük/küçük harfe duyarlılık|Aramalar büyük küçük harfe duyarlı değildir. Büyük veya küçük harf karakterler kullanarak arama ölçütlerinizi geliştirin. Örneğin, "OLE" ve "ole" aynı sonuçları döndürür.|  
|Karakter birleşimleri|Yalnızca tek tek harfler için (a-z) arayamaz veya sayılar (0-9). Kullanmayı denerseniz arama belirli, gibi "ve", "Kimden" ayrılmış sözcükler ve "ile" bunlar göz ardı edilir. Daha fazla bilgi için bkz: [sözcükler göz ardı aramalarda](#stopwords) bu konuda daha sonra.|  
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
  
### <a name="stopwords">Aramaları (Durma sözcükleri) yok sayılan sözcükler</a>
Otomatik olarak sık tekrarlanan sözcükleri veya bazen Durma sözcükleri adı verilen sayı bir tam metin araması sırasında göz ardı edilir. Tümcecik "geçiş" için arama yaparsanız, örneğin, arama sonuçları "geçiş" sözcüğünü içeren konular değil "ile ancak" görüntüler.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Mantıksal ve Gelişmiş işleçler](../ide/logical-operators-in-search-expressions.md)  
[Nasıl yapılır: dizinde konuları Bul](../ide/how-to-find-topics-in-the-index.md)  
[Nasıl yapılır: TOC konuları Bul](../ide/how-to-find-topics-in-the-table-of-contents.md)  
[Microsoft Yardım Görüntüleyicisi](../ide/microsoft-help-viewer.md)