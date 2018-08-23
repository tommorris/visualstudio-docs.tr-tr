---
title: Dekoratörlerin özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, decorators
ms.assetid: f6322fe5-dc08-4d32-a6b3-0bd18879136d
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: dc111cf868d2136a4d274889d96d50d2c9500a9a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691278"
---
# <a name="properties-of-decorators"></a>Dekoratörlerin Özellikleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [özellikleri, dekoratörler](https://docs.microsoft.com/visualstudio/modeling/properties-of-decorators).  
  
Dekoratörler simgeler, metin veya şekil veya diyagram üzerinde bağlayıcı görünebilir Genişlet/Daralt ayraç ' dir. Aşağıdaki tablolar, dekoratör üç tür özelliklerini gösterir. Bazı özellikler, yalnızca şekli dekoratörler veya yalnızca bağlayıcı dekoratörler görünür.  
  
 Daha fazla bilgi için [etki alanına özgü bir dili tanımlama nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikler kullanma hakkında daha fazla bilgi için bkz. [bir etki alanına özgü dili özelleştirme ve genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
## <a name="expandcollapse-decorator"></a>Dekoratör Genişlet/Daralt  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|displayName|Oluşturulan tasarımcıda görüntülenecek dekoratörün adı.|Daralt Dekoratör genişletin|  
|Ad|Dekoratörün adı.|ExpandCollapseDecorator|  
|Notlar|Bu dekoratör ile ilişkili resmi olmayan notlar.|\<yok >|  
|HorizontalOffset|Dekoratörün varsayılan konumuna inç cinsinden yatay uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|VerticalOffset|İnç, dekoratörün varsayılan konumuna göre dikey uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|OffsetFromLine|Dekoratörün satırından inç, varsayılan konumuna göre uzaklığı. (Bağlayıcı üzerinde yalnızca.)|0|  
|OffsetFromShape|Dekoratörün şekilden inç cinsinden, varsayılan konumuna göre uzaklığı. (Bağlayıcı üzerinde yalnızca.)|0|  
|Konum|Dekoratörün varsayılan konumuna.|SourceTop|  
  
## <a name="icon-decorator"></a>Dekoratör simgesi  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|DefaultIcon|Görüntülenecek simge veya resim dosyasının yolu.|\<yok >|  
|displayName|Oluşturulan tasarımcıda görüntülenecek dekoratörün adı.|Dekoratör simgesi|  
|Ad|Dekoratörün adı.|Şeklindeki Icondecorator|  
|Notlar|Dekoratör ile ilişkili resmi olmayan notlar.|\<yok >|  
|HorizontalOffset|Dekoratörün varsayılan konumuna inç cinsinden yatay uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|VerticalOffset|İnç, dekoratörün varsayılan konumuna göre dikey uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|OffsetFromLine|Dekoratörün satırından inç, varsayılan konumuna göre uzaklığı. (Bağlayıcı üzerinde yalnızca.)|0|  
|OffsetFromShape|Dekoratörün şekilden inç cinsinden, varsayılan konumuna göre uzaklığı. (Bağlayıcı üzerinde yalnızca.)|0|  
|Konum|Dekoratörün varsayılan konumuna.|SourceTop|  
  
## <a name="textdecorator"></a>TextDecorator  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|DefaultText|Görüntülenecek varsayılan metin.|Etiketle|  
|displayName|Oluşturulan tasarımcıda görüntülenecek dekoratörün adı.|Etiketle|  
|FontSize|Dekoratörde görüntülenen metnin yazı tipi boyutu.|8|  
|fontStyle|Dekoratörde görüntülenen metnin yazı tipi stili.|Normal|  
|Ad|Dekoratörün adı.|Etiketle|  
|Notlar|Dekoratör ile ilişkili resmi olmayan notlar.|\<yok >|  
|HorizontalOffset|Dekoratörün varsayılan konumuna inç cinsinden yatay uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|VerticalOffset|İnç, dekoratörün varsayılan konumuna göre dikey uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|OffsetFromLine|Dekoratörün satırından inç, varsayılan konumuna göre uzaklığı. (Bağlayıcı üzerinde yalnızca.)|0|  
|OffsetFromShape|Dekoratörün şekilden inç cinsinden, varsayılan konumuna göre uzaklığı. (Bağlayıcı üzerinde yalnızca.)|0|  
|Konum|Dekoratörün varsayılan konumuna.|TargetBottom|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



