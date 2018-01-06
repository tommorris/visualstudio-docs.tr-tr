---
title: "Bir dize Görselleştirici dizeleri görüntülemek | Microsoft Docs"
ms.custom: 
ms.date: 07/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.stringviewer
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
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 801618c900f11a562b42e610c56dfa7855dfaf39
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>Dize Görselleştirici Visual Studio içinde dizelerini görüntüle
Hata ayıklarken, bir veri ipucu veya hata ayıklayıcı penceresinde görüntülemek için çok uzun dizelerini Görüntüle için dize Görselleştirici açabilirsiniz. Birçok senaryoda Görselleştirici hatalı biçimlendirilmiş dizeler belirlemenize yardımcı olabilir.

Standart yerleşik dize görselleştiriciler düz metin, XML, HTML ve JSON içerir. Hata ayıklayıcıda görünür WPF nesneleri gibi birkaç diğer türleri için windows ister **otomobiller** penceresinde görselleştiriciler da açabilirsiniz.

## <a name="open-a-string-visualizer"></a>Dize Görselleştirici açın

Düz metin, XML, HTML veya JSON dizesi görüntülemek için büyüteç simgesini tıklatın ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi") bir dize değeri içeren bir değişken gelerek veya onları oluştu. Büyüteç simgesine görmek için hata ayıklayıcıda duraklatılması gerekir.

![Dize Görselleştirici açmak](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

## <a name="view-string-data"></a>Dize verilerini görüntüleme

**İfade** dize Görselleştirici alanı, hata ayıklayıcısı'ndaki geçerli değişken veya vurgulanan üzerinden ifade gösterir.

**Değeri** alan dize değeri gösterir. Metin Görselleştirici düz metin gösterir.

Boş bir **değeri** belirli Görselleştirici dize türü tanıyamıyor gösterir. Örneğin, boş bir XML Görselleştirici gösterir **değeri** bir basit bir metin dizesiyle (XML etiket) veya bir JSON dizesi olarak biçimlendirilmiş. Tanınmayan bir dize Görselleştirici içinde görüntülemek gerekiyorsa, metin Görselleştirici kullanın.

### <a name="view-json-string-data"></a>Görünüm JSON dizesi verileri

Doğru biçimlendirilmiş JSON dizesi aşağıdaki çizimde JSON Görselleştirici benzer görünür. Hatalı biçimlendirilmiş JSON bir hata simgesi (ya da tanınmayan varsa boş) görüntüleyebilir.

![JSON dize Görselleştirici](../debugger/media/dbg-tips-string-visualizer-json.png "JSON dize Görselleştirici")

### <a name="view-xml-string-data"></a>Görünüm XML dizesi verileri

Doğru biçimlendirilmiş XML dizesi aşağıdaki çizimde XML Görselleştirici benzer görünür. Hatalı biçimlendirilmiş XML XML etiketleri (veya tanınmayan, boş olmayan) görüntüleyebilir.

![XML dizesi Görselleştirici](../debugger/media/dbg-string-visualizers-xml.png "XML dize Görselleştirici")

### <a name="view-html-string-data"></a>Görünümü HTML dizesi verileri

Doğru biçimlendirilmiş bir HTML dizesi dize bir tarayıcıda oluşturulup oluşturulmayacağını aşağıdaki çizimde gösterildiği gibi gördüğünüz görünümü benzer görünür. Hatalı biçimlendirilmiş HTML düz metin olarak görüntülenebilir.

![HTML dizesi Görselleştirici](../debugger/media/dbg-string-visualizers-html.png "HTML dize Görselleştirici")

## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Görselleştiriciler (C#, Visual Basic) oluşturma](../debugger/create-custom-visualizers-of-data.md)