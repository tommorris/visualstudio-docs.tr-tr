---
title: "Dekoratörler özelliklerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, decorators
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 95338b26019a2faf2afc2eb6be019ac33d6ece3c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="properties-of-decorators"></a>Dekoratörlerin Özellikleri
Dekoratörler simgeler, metin ya da şekiller veya bağlayıcılar diyagramda görünebilir Genişlet/Daralt ayraç ' dir. Aşağıdaki tablolar oluşturma öğesi üç tür özelliklerini göster. Bazı özelliklerin yalnızca şekli dekoratörler veya yalnızca bağlayıcı dekoratörler görünür.  
  
 Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
## <a name="expandcollapse-decorator"></a>Genişlet/Daralt oluşturma öğesi  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Görünen adı|Oluşturulan Tasarımcısı'nda görüntülenen oluşturma öğesi adı.|Daraltma oluşturma öğesi genişletin|  
|Ad|Oluşturma öğesi adı.|ExpandCollapseDecorator|  
|Notlar|Bu oluşturma öğesi ile ilişkili resmi olmayan notları.|\<yok >|  
|HorizontalOffset|Oluşturma öğesi varsayılan konumunu inç göre yatay uzaklığını. (Şekiller üzerinde yalnızca.)|0|  
|VerticalOffset|Oluşturma öğesi varsayılan konumunu inç göre dikey uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|OffsetFromLine|Oluşturma öğesi satırından inç varsayılan konumuna göre uzaklığı. (Bağlayıcıların yalnızca.)|0|  
|OffsetFromShape|Oluşturma öğesi inç varsayılan konumuna göre şeklin uzaklığı. (Bağlayıcıların yalnızca.)|0|  
|Konum|Oluşturma öğesi varsayılan konumu.|SourceTop|  
  
## <a name="icon-decorator"></a>Simge oluşturma öğesi  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|DefaultIcon|Görüntülenecek simge veya görüntü dosyasının yolu.|\<yok >|  
|Görünen adı|Oluşturulan Tasarımcısı'nda görüntülenecek oluşturma öğesi adı.|Simge oluşturma öğesi|  
|Ad|Oluşturma öğesi adı.|IconDecorator|  
|Notlar|Oluşturma öğesi ile ilişkili resmi olmayan notları.|\<yok >|  
|HorizontalOffset|Oluşturma öğesi varsayılan konumunu inç göre yatay uzaklığını. (Şekiller üzerinde yalnızca.)|0|  
|VerticalOffset|Oluşturma öğesi varsayılan konumunu inç göre dikey uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|OffsetFromLine|Oluşturma öğesi satırından inç varsayılan konumuna göre uzaklığı. (Bağlayıcıların yalnızca.)|0|  
|OffsetFromShape|Oluşturma öğesi inç varsayılan konumuna göre şeklin uzaklığı. (Bağlayıcıların yalnızca.)|0|  
|Konum|Oluşturma öğesi varsayılan konumu.|SourceTop|  
  
## <a name="textdecorator"></a>Çizgi TextDecorator  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|DefaultText|Görüntülenecek varsayılan metni.|Etiketle|  
|Görünen adı|Oluşturulan Tasarımcısı'nda görüntülenecek oluşturma öğesi adı.|Etiketle|  
|FontSize|Oluşturma öğesi içinde görüntülenen metin yazı tipi boyutu.|8|  
|FontStyle|Oluşturma öğesi içinde görüntülenen metin yazı tipi stili.|Normal|  
|Ad|Oluşturma öğesi adı.|Etiketle|  
|Notlar|Oluşturma öğesi ile ilişkili resmi olmayan notları.|\<yok >|  
|HorizontalOffset|Oluşturma öğesi varsayılan konumunu inç göre yatay uzaklığını. (Şekiller üzerinde yalnızca.)|0|  
|VerticalOffset|Oluşturma öğesi varsayılan konumunu inç göre dikey uzaklık. (Şekiller üzerinde yalnızca.)|0|  
|OffsetFromLine|Oluşturma öğesi satırından inç varsayılan konumuna göre uzaklığı. (Bağlayıcıların yalnızca.)|0|  
|OffsetFromShape|Oluşturma öğesi inç varsayılan konumuna göre şeklin uzaklığı. (Bağlayıcıların yalnızca.)|0|  
|Konum|Oluşturma öğesi varsayılan konumu.|TargetBottom|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)