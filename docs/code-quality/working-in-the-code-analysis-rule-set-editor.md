---
title: Visual Studio'da Kod Analizi kural kümesi düzenleyici kullanın
ms.date: 04/-4/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.ruleseteditor
ms.assetid: 370c97bf-bb29-4b2f-b9ae-ba125bce7b2d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0791cc3d4dadf132dc2da7ad591eaaca27a3a1dc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924388"
---
# <a name="use-the-code-analysis-rule-set-editor"></a>Kod çözümleme kural kümesi düzenleyici kullanın

Kod çözümleme kural kümesi Düzenleyici özel bir kural kümesini ve kural ihlallerinin önemini dahil kuralları belirtmenize olanak sağlar.

|Eylem (önem derecesi)|Açıklama|
|-|-|
|Uyarı|Bir uyarı oluşturur **hata listesi** hem de derleme zamanında.|
|Hata|Bir hata oluşturur **hata listesi** hem de derleme zamanında.|
|Bilgi|Bir ileti oluşturur **hata listesi**.|
|Hidden|İhlalin kullanıcı için görünür değil. IDE ihlal ancak bildirilir.|
|Yok.|Kural engellenir. Kuralın kural kümesi kaldırıldıysa gibi davranış aynıdır.|

Düzenleyici kuralları belirttiğiniz alan grupları kuralları bir kural tarafından ayarlanan ağaç yapısında görüntüler. Eklemek veya kuralları kural kümesinden kaldırmak için bir veya daha fazla aşağıdaki adımları gerçekleştirin:

- Seçin veya Grup düğümü eklemek veya gruptaki tüm kuralları kaldırmak için onay kutusunu temizleyin. Bir grup seçtiğinizde, tüm kurallar ayarlanmıştır **uyarı** eylem.

   > [!TIP]
   > Kuralları nasıl gruplandırılacağını değiştirebilirsiniz **Group by** açılır.

- Tıklatın **eylem** alan bir grubun ve gruptaki tüm kuralları uygulanacak eylemi belirtin.

- Seçin veya tek bir kural için onay kutusunu temizleyin. Bir kural için onay kutusunu seçtiğinizde kuralın uyarı eylemi ayarlanır.

## <a name="toolbar"></a>Araç Çubuğu

Grup, filtre ve kural kümesi kılavuzunda görüntülenen verileri aramak için kural kümesi Düzenleyici araç kullanabilirsiniz.

Aşağıdaki tabloda, kural kümesi Düzenleyici araç çubuğu denetimleri açıklar.

|Araç çubuğu denetimi|Açıklama|
|---------------------|-----------------|
|**Tümünü Genişlet**|Kuralları tüm gruplarında gösterir.|
|**Tümünü Daralt**|Tüm grupları kurallarında gizler.|
|**Gruplandırma ölçütü**|Kurallar tarafından gruplandırılır alanını belirtir. Tıklatın  **\<Hiçbiri >** grupları olmadan kuralları göstermek için.|
|**Sütun seçenekleri**|Görüntülenecek kural alanları belirtir.|
|**Geçerli çözüme uygulamayın Gizle kuralları**|Gösterir veya gizler çözümü olarak aynı hedef türünün olmayan kuralları.|
|**Kod çözümleme hatalara neden olabilir kuralları göster**|Gösterir veya gizler hata eylemi atanmış kuralları.|
|**Kod çözümleme uyarıları oluşturan kuralları göster**|Gösterir veya gizler uyarı eylemi atanmış kuralları.|
|**Etkin olmayan kuralları göster**|Gösterir veya gizler hiçbir atanan kuralları eylem.|
|**Ekleme veya kaldırma alt kural kümeleri**|Ekler veya Seçilen kuralı kümelerinde kuralları kaldırır.|
|**Kurallarında Ara**|Belirttiğiniz dize için tüm alan değerlerini arar.|

## <a name="rule-set-fields"></a>Alanları kural kümesi

Kural kümesi alanlarını bir kural kümesi hakkındaki bilgileri görüntülemek ve sıralama ve kural listesinde gruplama için kullanılır. Alanları gizleyin veya gösterin için seçin **sütun seçenekleri** kuralda Düzenleyicisi araç ayarlayın ve ardından denetleyin veya göstermek veya gizlemek için alanların onay kutularını temizleyin.

Aşağıdaki tabloda, bir kural kümesi alanlarını açıklanmaktadır:

|Alan|Açıklama|
|-----------|-----------------|
|**ID**|Kural tanımlayıcısı.|
|**Kategori**|Kural kümeleri üyeliklerine ek olarak, kod çözümleme kurallarını da kategoriye göre gruplandırılır. Daha fazla bilgi için bkz: [Kod Analizi uyarıları](../code-quality/code-analysis-for-managed-code-warnings.md).|
|**Ad**|Kural başlığı.|
|**Namespace**|Kural ad alanı.|
|**Hedef türü**|Kural için yerel, yönetilen veya kod veritabanı gösterir.|
|**Eylem**|Kuralı çalıştırma bir kod analizi ihlal edildiğinde gerçekleştirilecek eylem. Düzenleyebileceğiniz **eylem** alan.|
|**Kaynak kural kümeleri**|Kural içeriyor kural kümesi.|

## <a name="sort-and-filter-rule-sets"></a>Sıralama ve filtreleme kural kümeleri

Sütun üstbilgileri kural kümesi kılavuzunun, sıralama ve alan değerleriyle kuralları filtreleme.

- Kural kümesi listeleri sıralamak için sütun başlığına göre sıralamak istediğinizi alanının tıklatın. Kural kümeleri gruplandırma yaptıysanız, her grubu ayrı ayrı sıralanır.

- Kural kümeleri bir alan değerine göre filtre için sütun başlığına göre filtre uygulamak istediğiniz alanın filtre düğmesini tıklatın. Göstermek istediğiniz değerleri onay kutularını seçin ve gizlemek istediğiniz değerleri onay kutularını temizleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [Bir özel kural kümesi oluşturma](../code-quality/how-to-create-a-custom-rule-set.md)