---
title: Visual Studio tasarımındaki yenilikler
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c25d89ae3ab3d25e415b4407a46fc903b1c05266
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33870968"
---
# <a name="whats-new-for-design-in-visual-studio"></a>Visual Studio tasarımındaki yenilikler

## <a name="live-dependency-validation"></a>Canlı bağımlılık doğrulama

İstenmeyen bağımlılıklarını kaldırma teknik borç yönetme önemli bir parçasıdır. Canlı doğrulama bağımlılıklarının dahil artık sorunlar hakkında kesin bilgi sağlama ve hata listesi ve düzenleyici yeni özelliklerinden tam olarak teknolojisinden yararlanan.

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

## <a name="a-nameversionsupport-version-support-for-architecture-and-modeling-tools"></a><a name="VersionSupport" />Mimari ve Modelleme Araçları sürüm desteği

Visual Studio 2015 birkaç sürümlerinde kullanılabilir. Bunların tümü mimari ve Modelleme Araçları için destek sağlar. Aşağıdaki tabloda her aracı kullanılabilirliğini gösterir.

|**Özelliği**|**Enterprise**|**Professional**|**Topluluk**|**Express**|
|-----------------|--------------------|----------------------|-------------------|-----------------|
|**Kod haritaları**|Evet|Yalnızca kod haritalarını okuma destekler, kod filtreleme, yeni genel düğümleri eklemek ve yeni bir yönlendirilmiş grafik seçimden oluşturma eşler.|-|-|
|**Bağımlılık grafikleri**|Evet|Bağımlılık diyagramları okuma destekler.|Bağımlılık diyagramları okuma destekler.|-|
|**Yönlendirilmiş Grafik** (DGML diyagramları)|Evet|Evet|Evet|-|
|**Kodu Kopyala**|Evet|-|-|-|