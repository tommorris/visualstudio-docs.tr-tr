---
title: "Geometri şekiller özelliklerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.geometryshape
helpviewer_keywords:
- Domain-Specific Language, geometry shape
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 00897fa468ef223b523101810d1bbe7b8fa533fb
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="properties-of-geometry-shapes"></a>Geometri Şekillerinin Özellikleri
Geometri şekiller, etki alanı sınıfların örnekleri bir etki alanına özgü dil görüntülenme biçimini belirtmek için kullanabilirsiniz. Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Geometri şekilleri aşağıdaki tabloda listelenen özellikleri bulunur.  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Dolgu rengi|Bu şeklin dolgu rengi.|Beyaz|  
|Gradyan modu doldurun|(Yatay, dikey, İleri çapraz, geriye dönük çapraz veya hiçbiri) Bu şeklin dolgu gradyanı modu.|Yatay|  
|Geometri|Bu şekil (dikdörtgen, yuvarlak dikdörtgen, elips veya daire) geometri.|Dikdörtgen|  
|Varsayılan bağlantı noktası içermiyor.|Varsa `True`şekli üst, alt, sol kullanacak ve doğru bağlantı noktalarını oluşturulan Tasarımcısı'nda.|False|  
|Anahat rengi|Bu şeklin kenarlık rengi.|Siyah|  
|Kenarlık Çizgi stili|Bu şekil (düz, çizgi, nokta, çizgi nokta, çizgi nokta nokta veya özel) anahat çizgi stili.|Düz|  
|Anahat kalınlığı|Bu şeklin Anahat kalınlığı.|0.03125|  
|Metin rengi|Bu şeklin ile ilişkili metin dekoratörler için kullanılan rengi.|Siyah|  
|Access Modifier|Sınıfı (ortak veya dahili) erişim değiştiricisi.|Ortak|  
|Özel Öznitelikler|Bu şeklin için oluşturulan kaynak kodu sınıfı öznitelikler eklemek için kullanılır.|\<yok >|  
|Çift oluşturur türetilmiş|Varsa `True`, bir taban sınıf ve bir parçalı sınıf (geçersiz kılmaları özelleştirmeyi desteklemek için) oluşturulur. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Özel bir oluşturucuya sahip|Varsa `True`, özel bir oluşturucu kaynak kodunda sağlanacaktır. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Devralma değiştiricisi|Şekli'ndan oluşturulan kaynak kodu sınıf devralma türünü açıklar (`none`, `abstract` veya `sealed`).|yok|  
|Temel geometri şekli|Bu şeklin temel sınıf.|(hiçbiri)|  
|Ad|Bu şeklin adı.|Geçerli adı|  
|Ad Alanı|Bu şeklin ile bağlantılı olan ad alanı.|Geçerli ad alanı|  
|Araç İpucu türü|Nasıl araç ipucu (sabit, değişken veya hiçbiri) tanımlanır. Sabit, ardından değeri `Fixed Tooltip Text` özelliği araç ipucu olarak kullanılır; ardından değişken durumunda, araç ipucu özel kod içinde tanımlanır.|Yok.|  
|Notlar|Bu öğeyle ilişkili resmi olmayan notları.|\<yok >|  
|İlk yükseklik|Bu şeklin inç ilk yüksekliği.|1.|  
|İlk genişliği|Bu şeklin inç başlangıç genişliği.|1,5|  
|Özellik olarak sunulan dolgu rengi<br /><br /> Sunulan dolgu gradyanı modu<br /><br /> Anahat rengini özelliği olarak kullanıma sunulan<br /><br /> Kenarlık Çizgi stili özelliği olarak kullanıma sunulan<br /><br /> Anahat kalınlığı özelliği olarak sunulan<br /><br /> Metin rengi gösterir|Varsa `True`, kullanıcı bir şekli belirtilen özelliğini ayarlayabilirsiniz. Bunu ayarlamak için Şekil tanımı sağ tıklatıp **eklemek açığa**.|False|  
|Açıklama|Oluşturulan Tasarımcısı belgelemek için kullanılan açıklaması.|\<yok >|  
|Görünen ad|Bu şekil için oluşturulan Tasarımcısı'nda görüntülenen ad.|\<yok >|  
|Sabit araç ipucu metni|Sabit bir araç ipucu için kullanılan metin.|\<yok >|  
|Yardım anahtar sözcüğü|Bu şeklin için F1 Yardımı dizin oluşturmak için kullanılan anahtar sözcük.|\<yok >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)