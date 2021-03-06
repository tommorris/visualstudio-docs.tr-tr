---
title: Yerelleştirme için kaynakların hiyerarşik organizasyonu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- resource files, localized
- localization [Visual Studio], resources
- fallback resources
- international applications [Visual Studio], storing resources
- satellite assemblies, resource hierarchies
- globalization [Visual Studio], resources
- satellite assemblies
- resources [Visual Studio], fallback system
- resource files, fallback processes
ms.assetid: dadf8f2c-f74c-44d7-bec0-a1e956d8d38d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c46fbfe13e7e4c795703a53debedca20ae39c145
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752326"
---
# <a name="hierarchical-organization-of-resources-for-localization"></a>Yerelleştirme için kaynakların hiyerarşik organizasyonu

Visual Studio'da yerelleştirilmiş kaynaklar (dizeler ve görüntüleri her kültüre uygun gibi verileri) ayrı dosyalarda tutulur ve UI kültürü ayarına göre yüklenir. Anlamak için yerelleştirilmiş kaynakların nasıl yüklendiğini, bunların hiyerarşik olarak düzenlenir gibi düşünmek yararlı olur.

## <a name="kinds-of-resources-in-the-hierarchy"></a>Kaynak hiyerarşisindeki türleri

-   Örneğin İngilizce ("en"), varsayılan kültür için geri dönüş kaynak hiyerarşisinin en üstünde bulunur. Bu geri dönüş kaynakları kendi dosyalarına sahip olmayan tek olanlardır; Bunlar ana derlemede depolanır.

-   Aşağıda geri dönüş kaynakları nötr kültürler için kaynaklardır. Bağımsız bir kültür bir dil ancak olmayan bir ülke/bölge ile ilişkilidir. Örneğin, Fransızca ("fr") Tarafsız bir kültürdür. (Geri dönüş de bağımsız bir kültür ancak özel bir kaynaklardır.)

-   Bağımsız kültür kaynaklar özel kültürler için kaynaklardır. Belirli bir kültür bir dil ve ülke/bölge ile ilişkilidir. Örneğin, Fransızca Kanada ("fr-CA") belirli bir kültürdür.

 Bir uygulama bir dize gibi herhangi bir yerelleştirilmiş kaynağı yüklemeye çalışır ve onu bulamazsa, istenen kaynak içeren bir kaynak dosyası bulana kadar hiyerarşisinde yukarı kurulur.

 Kaynaklarınızın depolamak için en iyi mümkün olduğunca bunları genelleştirmek için yoludur. Yerelleştirilmiş dizeleri, görüntüleri vb. belirli kültürler mümkün olduğunda yerine nötr kültürler için kaynak dosyaları depolamak anlamına gelir. Örneğin, Fransızca Belçika için kaynaklarınız varsa ("fr-olabilir") kültür ve hemen üzerindeki kaynaklar İngilizce geri dönüş kaynakları, birisi Fransızca Kanada kültürü için yapılandırılmış bir sistemde, uygulamanızın kullanırken bir sorun sonuçlanabilir. Sistem "fr-CA" için bir uydu derleme arar ancak Bul değil, bu nedenle geri dönüş kaynağı içeren ana derleme yükler İngilizce, Fransızca kaynakları yüklemek yerine. Aşağıdaki resimde, bu istenmeyen senaryoyu gösterir.

 ![Yalnızca belirli kaynaklar](../ide/media/vbspecificresourcesonly.gif)

 Dilden bağımsız kaynak dosyasında "fr" kültür için mümkün olduğunca fazla kaynak yerleştirme önerilen uygulama izlerseniz, Fransızca Kanada kullanıcısı için işaretlenmiş kaynakları görmek "fr-olması" kültür ancak dizeleri Fransızca gösterilen. Tercih edilen bu senaryo aşağıdaki durum gösterir.

 ![NeutralSpecificResources grafiği](../ide/media/vbneutralspecificresources.gif)

## <a name="see-also"></a>Ayrıca bkz.

- [Yerelleştirme için bağımsız kaynak dilleri](../ide/neutral-resources-languages-for-localization.md)
- [Güvenlik ve yerleştirilmiş yardımcı derlemeler](../ide/security-and-localized-satellite-assemblies.md)
- [Uygulamaları yerelleştirme](../ide/localizing-applications.md)
- [Uygulamaları Genelleştirme ve yerelleştirme](../ide/globalizing-and-localizing-applications.md)