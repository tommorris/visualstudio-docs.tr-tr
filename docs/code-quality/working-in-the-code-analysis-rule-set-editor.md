---
title: "Kod çözümleme kural kümesi de çalışma Düzenleyicisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.ruleseteditor
ms.assetid: 370c97bf-bb29-4b2f-b9ae-ba125bce7b2d
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c832b29512bfd7339ab60044ece81f1626be9bc7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="working-in-the-code-analysis-rule-set-editor"></a>Kod Çözümleme Kural Kümesi Düzenleyici'de Çalışma
Kod çözümleme kural kümesi Düzenleyici bir özel kural kümesine dahil edilen kurallarını belirtmek için ve eylemi belirtmenize olanak sağlar. Kod Analizi kural ihlal karşılaştığında gerçekleştirilecek eylemi de belirtebilirsiniz.  
  
|Eylem|Açıklama|  
|------------|-----------------|  
|**Uyarı**|Bir uyarı oluşturur **hata listesi** penceresi.|  
|**Hata:**|Bir hata oluşturur **hata listesi** penceresi.|  
|**Yok**|Kural devre dışı bırakır.|  
  
 Düzenleyici kuralları belirttiğiniz alan grupları kuralları bir kural tarafından ayarlanan ağaç yapısında görüntüler. Eklemek veya kuralları kural kümesinden kaldırmak için bir veya daha fazla aşağıdaki adımları gerçekleştirin:  
  
-   Seçin veya Grup düğümü eklemek veya gruptaki tüm kuralları kaldırmak için onay kutusunu temizleyin. Bir grup seçtiğinizde, tüm kurallar ayarlanmıştır **uyarı** eylem.  
  
-   Tıklatın **eylem** alan bir grubun ve gruptaki tüm kuralları uygulanacak eylemi belirtin.  
  
-   Seçin veya tek bir kural için onay kutusunu temizleyin. Bir kural için onay kutusunu seçtiğinizde kuralın uyarı eylemi ayarlanır.  
  
## <a name="rule-set-editor-toolbar"></a>Kural Düzenleyicisi araç kümesi  
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
  
## <a name="rule-set-fields"></a>Kural kümesi alanları  
 Kural bir kural görüntü bilgilerini ayarlayın ve sıralama ve kural listesinde gruplama için kullanılan alanları ayarlayın. Görüntülemek veya alanları gizlemek için tıklatın **sütun seçenekleri** kuralda Düzenleyicisi araç ayarlayın ve ardından denetleyin veya göstermek veya gizlemek için alanların onay kutularını temizleyin.  
  
 Aşağıdaki tabloda, bir kural kümesinin alanları açıklar.  
  
|Alan|Açıklama|  
|-----------|-----------------|  
|**KİMLİĞİ**|Kural tanımlayıcısı.|  
|**Kategori**|Kural kümeleri üyeliklerine ek olarak, kod çözümleme kurallarını da kategoriye göre gruplandırılır. Daha fazla bilgi için bkz: [yönetilen kod uyarıları için Kod Analizi](../code-quality/code-analysis-for-managed-code-warnings.md).|  
|**Ad**|Kural başlığı.|  
|**Namespace**|Kural ad alanı.|  
|**Hedef türü**|Kural için yerel, yönetilen veya kod veritabanı gösterir.|  
|**Eylem**|Kuralı çalıştırma bir kod analizi ihlal edildiğinde gerçekleştirilecek eylem.<br /><br /> **Uyarı** -bir uyarı oluşturur.<br /><br /> **Hata** -bir hata oluşturur.<br /><br /> **Hiçbiri** -kural devre dışı bırakır.<br /><br /> Eylem alanını düzenleyebilirsiniz. Değer None olarak ayarlamadan kuralı için onay kutusunu temizleyerek aynıdır.|  
|**Kaynak kural kümeleri**|Kural içeriyor kural kümesi.|  
  
## <a name="sorting-and-filtering-rule-sets"></a>Sıralama ve filtreleme kural kümeleri  
 Sütun üstbilgileri kural kümesi kılavuzunun, sıralama ve alan değerleriyle kuralları filtreleme.  
  
-   Kural kümesi listeleri sıralamak için sütun başlığına göre sıralamak istediğinizi alanının tıklatın. Kural kümeleri gruplandırma yaptıysanız, her grubu ayrı ayrı sıralanır.  
  
-   Kural kümeleri bir alan değerine göre filtre için sütun başlığına göre filtre uygulamak istediğiniz alanın filtre düğmesini tıklatın. Göstermek istediğiniz değerleri onay kutularını seçin ve gizlemek istediğiniz değerleri onay kutularını temizleyin.