---
title: "&#39; Visual Studio tasarımındaki yenilikler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 94f00e808df433279128a0241ffd3ab376ebc5b3
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="what39s-new-for-design-in-visual-studio"></a>&#39; Visual Studio tasarımındaki yenilikler

## <a name="live-dependency-validation"></a>Canlı bağımlılık doğrulama

İstenmeyen bağımlılıklarını kaldırma teknik borç yönetme önemli bir parçasıdır.
Canlı doğrulama bağımlılıklarının dahil artık sorunlar hakkında kesin bilgi sağlama ve hata listesi ve düzenleyici yeni özelliklerinden tam olarak teknolojisinden yararlanan.

![Eylem Canlı bağımlılık doğrulama](media/dep-validation-whatsnew-01.png)

Daha fazla bulunabilir ve daha erişilebilir değiştirme "Katman diyagramı" den "Bağımlılık diyagrama" terminolojisi bağımlılık doğrulama yapmak için geliştirme deneyimi değiştirdi.

**Mimarisi** menüsü artık doğrudan bir bağımlılık diyagramı oluşturmak için bir komut içerir:

![Mimari menüsündeki Canlı bağımlılık öğesi](media/dep-validation-whatsnew-02.png)

... ve bir bağımlılık diyagramı ve açıklamaları, katmanda özellik adlarını daha anlamlı hale getirilmek üzere değiştirilmiştir:

![Güncelleştirilmiş Canlı bağımlılık özellik adları](media/dep-validation-whatsnew-03.png)

Değişikliklerinizi hemen çözüm geçerli kod çözümleme sonuçlarını etkisini şimdi diyagram her kaydettiğinizde bakın. Artık "Bağımlılıkları doğrula" komutu tamamlanmasını beklemek zorunda değilsiniz.

Daha fazla ayrıntı için bkz: [bu blog gönderisine](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/). 
 
## <a name="uml-designers-have-been-removed"></a>UML tasarımcılarına kaldırıldı

UML tasarımcılarına bu Visual Studio Enterprise sürümünden kaldırılmıştır.

* UML diyagramları şimdi XML dosyası olarak sunulur
* UML Model Gezgini artık yok
* Proje başvuruları artık bağımlılık doğrulama için kullanılan modelleme
* Çözüm Gezgini "Katman başvuruları" düğümünde artık görüntülenir
* Bir bağımlılık (katman) diyagramı "Doğrula" yapı eylemini artık kullanılmayan - derleme görevi kaldırılmıştır 
* Proje yapısı sürümleri arasındaki gidiş için korunur
* Hala açın, oluşturabilir, düzenleyebilir ve bir bağımlılık (katman) diyagramı XML olarak kaydetme
* Bir bağımlılık (katman) diyagrama bağlı TFS iş öğeleri tasarım yüzeyine erişilebilir değil
* Geri gelen DSL veya bir katmanına bağlama artık desteklenmiyor 
* UML Genişletilebilirlik modelleme SDK artık desteklenmiyor

Ancak, .NET ve C++ kodu mimarisini görselleştirme aracılığıyla kullanılabilir desteği [kod eşlemeleri](map-dependencies-across-your-solutions.md)ve yukarıda açıklanan bağımlılık doğrulama için önemli geliştirmeler.

UML tasarımcılarına önemli kullanıcısı varsa, Visual Studio 2015 veya önceki sürümleri UML ihtiyaçlarınız için alternatif bir aracı üzerinde karar sırada kullanmaya devam edebilirsiniz.

Daha fazla ayrıntı için bkz: [bu blog gönderisine](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/). 

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

<a name="VersionSupport"></a>
##  <a name="version-support-for-architecture-and-modeling-tools"></a>Mimari ve Modelleme Araçları sürüm desteği  

Visual Studio birkaç sürümlerinde kullanılabilir. Bunların tümü mimari ve Modelleme Araçları için destek sağlar. Aşağıdaki tabloda her aracı kullanılabilirliğini gösterir.  
  
|**Özelliği**|**Enterprise**|**Professional**|**Topluluk**|**Express**|  
|-----------------|--------------------|----------------------|-------------------|-----------------|  
|**Kod haritaları**|Evet|Bkz. Not (1)|-|-|  
|**Bağımlılık grafikleri**|Evet|Bkz. Not (2)|Bkz. Not (2)|-|  
|**Yönlendirilmiş Grafik** (DGML diyagramları)|Evet|Evet|Evet|-|  
|**Kodu Kopyala**|Evet|-|-|-|  
  
(1). Not: kod haritalarını okuma, kod haritalarını filtreleme, yeni genel düğüm ekleme ve yeni bir yönlendirilmiş grafik seçimden oluşturma yalnızca destekler.

(2). Not: yalnızca destekler bağımlılık diyagramları okuma.
