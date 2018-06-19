---
title: Hata ayıklama - veri görselleştirmeleri
description: Hata ayıklama, programlama, ortak ve gerekirse, bir parçasıdır. Mac için Visual Studio tüm dizisi kolay hata ayıklama kolaylaştıran özellikler içerir. Bu makalede hata ayıklayıcısında nesneleri incelerken görüntülenebilir farklı veri görselleştirmeleri bakar.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.technology: vs-ide-debug
ms.assetid: 527E6BEC-EF15-4002-ACB5-62AE1C16F6B7
ms.openlocfilehash: 5ee16324a312eca79de2f3b356a5f3be941f5e7b
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33868426"
---
# <a name="data-visualizations"></a>Veri görselleştirmeleri

Mac için Visual Studio kullanıcı Arabirimi hata ayıklama sırasında görselleştirmeleri bir değişkeni, alan veya özellik değerlerini sağlayan, hata ayıklayıcı desteği içerir. Bu veri görselleştiriciler verileri genişletilmiş bir sürümünü Göster ve örneğin renk yapı rengini gösteren geliştiriciler bilinen yapıları incelemek izin verin.

Hata ayıklama görselleştiriciler **yerel** defteri değeri, sağda kullanıcı satırın geldiğinde görüntülenen Önizleme simgesine tıklayarak görüntülenebilir:

 ![Yerel paneli](media/data-visualizations-image9.png)

Mac için Visual Studio'da hata ayıklama sırasında listesi kullanılabilir yeni görselleştirmeler çoğunu arar

## <a name="point"></a>noktası
Bir noktayı/PointF veya CGPoint, iOS ve Mac, hata ayıklama defterinde X ve Y değerleri gösteren bir tanımlama grubu olarak oluşturulur:

 ![Noktası Görselleştirme](media/data-visualizations-image10.png)

## <a name="size"></a>Boyut
Bir boyut/SizeF veya CGSize, iOS ve Mac, bir dikdörtgen kabul eder. Çizildiğinde, bu noktada, en büyük boyutu 250px olarak dikdörtgen ayarlayacaktır 250px, geçmiş bir boyut büyümesi kadar ölçek için:

![Boyutu Görselleştirme](media/data-visualizations-image11.png)


## <a name="rectangle"></a>Dikdörtgen
Bir dikdörtgen/RectangleF veya CGRect, iOS ve Mac, boyutlar ve kaynağını görüntüler. Benzer şekilde boyutu, çizildiğinde 250px bir boyutu büyüdükçe kadar ölçek için:

 ![Dikdörtgen Görselleştirme](media/data-visualizations-image12.png)

## <a name="coordinate"></a>Koordinat
Koordinatları merkezine sabitlenmiş konumla bir haritada çizilmiştir:

![Koordinat Görselleştirme](media/data-visualizations-image13.png)

## <a name="color"></a>Renk
Bu renk Önizleme, RGBA bileşenleri, ton doygunluğu açıklık değerlerinin ve rengi onaltılı değerini gösteren UIColor, CGColor ve renk özelliklerini görüntüler:

![Renk Görselleştirme](media/data-visualizations-image14.png)


## <a name="images"></a>Görüntüler

Medya kadar 250px, için bir maksimum boyut ölçeklendirmek için işlenir ve görüntünün 250px aştığında uyacak şekilde ölçeklendirilir:

 ![Görüntü Görselleştirme](media/data-visualizations-image15.png)


## <a name="bezier-curves"></a>Bezier eğrileri

Görselleştirici görüntüleyecek bir `NSBezierPath`:

![Bezier eğrisi Görselleştirme](media/data-visualizations-image16.png)


## <a name="string"></a>Dize

100'den az karakter dizesi önizlemesi olmadan tam görüntülenir. Uzun dizeleri tam önizleme olarak görüntülenir. Dizeleri düzenlenebilir ve Görselleştirici Önizleme veya dize değeri aşağıda gösterilen Düzenleyicisi'nde, düzenlenecek dize değeri izin vererek bir Düzenle düğmesi tarafından eşlik:

![Dize Görselleştirme](media/data-visualizations-image17.png)

### <a name="small-strings"></a>Küçük dizeleri:
![Küçük dize Görselleştirme](media/data-visualizations-image18.png)]

### <a name="medium-length-strings"></a>Orta uzunluklu dizeler:
![Orta dize Görselleştirme](media/data-visualizations-image19.png)

### <a name="editor"></a>Düzenleyen:

 ![Düzenleyici Görselleştirme](media/data-visualizations-image21.png)

## <a name="ienumerable"></a>IEnumerable

IEnumerable tüm değerlerini sıralar; değerlerin her tıklayarak görüntülenebilir **Göster** değerleri düğmesi. IEnumerable seçeneği nesnelerin değerlerini gibi görüntülemez `Array`, `ArrayList`, `List<>`, `Dictionary<,>` bu kendi hata ayıklayıcı görselleştiriciler sahip olarak.

![IEnumerable Görselleştirme](media/data-visualizations-image22.png)

## <a name="other-visualizers"></a>Diğer Görselleştiriciler

Ayrıca, kendi satır içi görselleştiriciler bazı diğer türleri aşağıda listelenmiştir:

 ![Diğer Görselleştirme](media/data-visualizations-image23.png)

*   **Temel Türler**
    *   Bu basit tür ham değeri gösterir.
*   **Enum**
    *   Bu numaralandırma türü niteleyicisi olmadan alan değeri görüntüler.
*   **Tanımlama grubu**
    *   (,) Biçiminde gösterilen
*   **Null**
    *   "Null" değer gösterir.
*   **URL**
    *   Bu tıklanabilir köprü görüntüler.
*   **IntPtr**
    *   Bu IntPtr onaltılık bir gösterimini görüntüler.
