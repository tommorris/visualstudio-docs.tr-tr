---
title: İş Akışı Tasarımcısı - anahtar<T> etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: afa5932ebfaea1e0a7f61997c26e95226ed51b1d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758022"
---
# <a name="switcht-activity-designer"></a>Anahtar\<T > etkinlik Tasarımcısı

<xref:System.Activities.Statements.Switch%601> Etkinlik belirtilen ifadeyi hesaplar ve ilişkili anahtar değerlendirme sürümünden alınan değer eşleşen etkinlikler koleksiyonundan etkinlik yürütür.

**Anahtar < T\>**  etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Switch%601> etkinliği iş akışı Tasarımcısı'nda.

## <a name="the-switchtactivity"></a>Anahtar\<T > etkinliği

A <xref:System.Activities.Statements.Switch%601> etkinlik içeren bir <xref:System.Activities.Statements.Switch%601.Expression%2A> ve bir sözlükten <xref:System.Activities.Statements.Switch%601.Cases%2A>. Her durumda sözlük içeren bir çiftinden oluşur bir *anahtar* ve ilgili olarak hizmet veren bir etkinlik *değeri*. <xref:System.Activities.Statements.Switch%601> Etkinlik değerlendirir <xref:System.Activities.Statements.Switch%601.Expression%2A> ve her bir anahtarı karşı karşılaştırır. Bir eşleşme bulunamazsa, karşılık gelen etkinlik yürütülür. Sözlük anahtarları sözlük eşitlik karşılaştırıcısını tarafından tanımlanan eşitlik türüne göre benzersiz olması gerektiğinden, yalnızca bir eşleşme mümkündür. Eşleşme bulunamazsa, <xref:System.Activities.Statements.Switch%601.Default%2A> etkinlik gerçekleştirilir.

## <a name="how-to-use-the-switcht-activity-designer"></a>Anahtar kullanma\<T > etkinlik Tasarımcısı

Erişim **anahtar\<T >** etkinlik Tasarımcısı'nda **akış denetimi** kategorisini **araç**. İş Akışı Tasarımcısı bırakarak sonra görüntüler **türlerini Seç** kullanıcının genel tür belirtmesine izin verecek şekilde iletişim *T* kullanılan <xref:System.Activities.Statements.Switch%601> etkinlik. Varsayılan değer **Int32**. Bir kez genel tür *T* seçilmedi, bir **anahtar < T\>**  Tasarımcısı, iş akışı Tasarımcısı'na eklenir.

Şunlardır özelliklerini **anahtar < T\>**  Tasarımcısı. Bu özelliklerin tümünü özellik kılavuzunda düzenlenebilir. Bunlardan bazıları da tasarımcı yüzeyine düzenlenebilir.

Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.Switch%601> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.Switch%601> etkinlik Tasarımcısı. Varsayılan değer anahtarıdır < Int32\>. Değer içinde düzenlenebilir **özellikleri** penceresi veya doğrudan Tasarımcı üstbilgi.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|Doğru|Yürütülecek; bu durumda belirlemek için durumlarda koleksiyonundaki anahtarlarına karşılaştırmak için kullanılan ifade belirtir.|
|<xref:System.Activities.Statements.Switch%601.Default%2A>||Eşleşme bulunamazsa, yürütülen etkinlik belirtir. Tıklatın **bir etkinlik eklemeyi** açmak için tasarımcı düğmesinde **varsayılan** burada etkinlik bırakılan kutusunu.|
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||Değerlendirilecek durumları belirtir. Servis talebi eklemek için tıklatın **yeni durumu ekleme** alt kısmındaki düğmesi **anahtar\<T >** Tasarımcısı. Düğme için metin kutusu değişir (genel tür anahtar eklerken seçtiyseniz birleşik giriş kutusu\<T > dize ya da Enum). Bir anahtar ekledikten sonra **durumda değer** kutusunda servis talebi alanı genişler ve bir etkinlik bırakılabilir burada çalışması için yürütme mantığını tanımlamak için ipucu metnini "Buraya Bırak etkinlik".|

Servis talebi anahtarları değil yinelenir sürece birden çok çalışmaları eklenebilir. Aksi halde, belirtilen örnek anahtarı zaten raporlama ve farklı bir anahtar seçmelisiniz hata iletişim kutusu görüntüler. İçinde **anahtar\<T >** Tasarımcı, yalnızca bir örnek alanını aynı anda Genişletilmiş Görünüm olabilir. Örnek alanı daraltılmış görünümde ise, servis talebi alanı tıklatarak bunu genişletir. Daraltılmış bir servis talebi için tasarımcı etkinliği durumu içinde görünen adını sağ tarafta olup olmadığını herhangi gösterdiğine dikkat edin. Aksi takdirde gösterir **bir etkinlik eklemeyi** bunu tıklatırsanız durum genişletir ve bir etkinlik eklemenize olanak sağlayan düğmesi.

Örnek anahtarı düzenleyebilmek mevcut durumda anahtarı tıklayarak anahtarı bir etiketinden metin kutusuna değiştirir.

Servis talebi silmek için 2 yolu vardır:

- Select case ve silin.

- Bağlam menüsünü görüntülemek ve seçmek için durumda sağ seçin **silmek**.

Servis talebi silmeden kendisine seçmeniz gerektiğini unutmayın. Seçme ve etkinliği bir durum içinde silme yalnızca durum etkinlik siler.

## <a name="see-also"></a>Ayrıca bkz.

- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)