---
title: Dize Görselleştirici içinde dizelerini görüntüle | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2017
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.stringviewer
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- string visualizer
- visualizers, string
ms.assetid: 080fd8f1-72b0-461f-8451-3c84d5dc51df
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca6e4519a85659b36e5cf6baebaadd1d1c626f1a
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151041"
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>Visual Studio'da dize görselleştiricide dizelerini görüntüle
Hata ayıklarken, veri ipucu veya hata ayıklayıcı penceresinde görüntülemek için çok uzun görünüm dizeler için dize Görselleştirici açabilirsiniz. Birçok senaryoda görselleştiricisi hatalı biçimlendirilmiş dizeler belirlemenize yardımcı olabilir.

Standart yerleşik dize görselleştiriciler, düz metin, XML, HTML ve JSON içerir. Windows Hata Ayıklayıcısı'nda görünen WPF nesneler gibi birkaç diğer türleri için ister **Otolar** penceresinde görselleştiriciler da açabilirsiniz.

## <a name="open-a-string-visualizer"></a>Dize Görselleştirici açın

Düz metin, XML, HTML veya JSON dizesini görüntülemek için büyüteç simgesini tıklayın ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi") bir dize değeri içeren bir değişken gelindiğinde. Büyüteç simgesinin görmek için hata ayıklayıcısında duraklatıldıktan gerekir.

![Dize Görselleştirici açın](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

## <a name="view-string-data"></a>Dize verileri görüntüle

**İfade** dize Görselleştirici alanda hata ayıklayıcıda geçerli bir değişken veya üzerine gelindiğinde ifadesi gösterir.

**Değer** alan dize değerini gösterir. Metin Görselleştirici düz metin gösterir.

Boş bir **değer** özel Görselleştirici dize türünü tanıyamaz gösterir. Örneğin, boş bir XML Görselleştirici gösterir **değer** bir basit metin dize (XML etiket yok) veya bir JSON dizesi olarak biçimlendirilmiş. Görselleştirici içinde tanınmayan bir dize görüntülemek gerekiyorsa, metin görselleştiricisi kullanın.

### <a name="view-json-string-data"></a>JSON dizesi veri görünümü

İyi biçimlendirilmiş bir JSON dizesi aşağıdaki çizimde JSON Görselleştirici benzer görünür. Hatalı biçimlendirilmiş JSON, bir hata simgesi (veya tanınmayan ise boş) görüntüleyebilir. Bir hata simgesi görürseniz, kopyalama ve JSON dizesi gibi bir JSON linting aracına yapıştırın [JSLint](https://www.jslint.com/) JSON hatası tanımlamak için.

![JSON dizesi Görselleştirici](../debugger/media/dbg-tips-string-visualizer-json.png "JSON dize Görselleştirici")

### <a name="view-xml-string-data"></a>XML dizesi veri görünümü

İyi biçimlendirilmiş bir XML dizesi aşağıdaki çizimde XML Görselleştirici benzer görünür. Hatalı biçimlendirilmiş XML XML etiketleri (veya tanınmayan, boşluk olmadan) görüntüleyebilir.

![XML dizesi Görselleştirici](../debugger/media/dbg-string-visualizers-xml.png "XML dize Görselleştirici")

### <a name="view-html-string-data"></a>Dize verileri HTML'yi görüntüle

İyi biçimlendirilmiş bir HTML dizesi dize bir tarayıcıda işlenip işlenmeyeceğini aşağıdaki çizimde gösterildiği gibi gördüklerinizle görünümüne benzer görünür. Hatalı biçimlendirilmiş HTML düz metin olarak görüntülenebilir.

![HTML dizesi Görselleştirici](../debugger/media/dbg-string-visualizers-html.png "HTML dize Görselleştirici")

## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Görselleştiriciler (C#, Visual Basic) oluşturma](../debugger/create-custom-visualizers-of-data.md)