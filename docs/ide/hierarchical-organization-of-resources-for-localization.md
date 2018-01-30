---
title: "Yerelleştirme için kaynakların hiyerarşik organizasyonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cc663c02d3151e6dd55c1c35388ac7b33f049bb1
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="hierarchical-organization-of-resources-for-localization"></a>Yerelleştirme için Kaynakların Hiyerarşik Organizasyonu
Visual Studio'da yerelleştirilmiş kaynaklar (dizeler ve görüntüleri her kültüre uygun gibi verileri) ayrı dosyalarda tutulur ve UI kültürü ayarına göre yüklenir. Anlamak için yerelleştirilmiş kaynakların nasıl yüklendiğini, bunların hiyerarşik olarak düzenlenir gibi düşünmek yararlı olur.  
  
## <a name="kinds-of-resources-in-the-hierarchy"></a>Kaynak hiyerarşisindeki türleri  
  
-   Örneğin İngilizce ("en"), varsayılan kültür için geri dönüş kaynak hiyerarşisinin en üstünde bulunur. Bunları kendi dosyalarına sahip olmayan tek kaynaklardır; Bunlar ana derlemede depolanır.  
  
-   Aşağıda geri dönüş kaynakları nötr kültürler için kaynaklardır. Bağımsız bir kültür bir dil ancak olmayan bir ülke/bölge ile ilişkilidir. Örneğin, Fransızca ("fr") Tarafsız bir kültürdür. (Geri dönüş kaynakları da bağımsız bir kültür ancak özel bir olduğunu unutmayın.)  
  
-   Bu özel kültürler için kaynaklardır. Belirli bir kültür bir dil ve ülke/bölge ile ilişkilidir. Örneğin, Fransızca Kanada ("fr-CA") belirli bir kültürdür.  
  
 Bir uygulama bir dize gibi herhangi bir yerelleştirilmiş kaynağı yüklemeye çalışır ve onu bulamazsa, istenen kaynak içeren bir kaynak dosyası bulana kadar hiyerarşisinde yukarı kurulur.  
  
 Kaynaklarınızın depolamak için en iyi mümkün olduğunca bunları genelleştirmek için yoludur. Yerelleştirilmiş dizeleri, görüntüleri vb. belirli kültürler mümkün olduğunda yerine nötr kültürler için kaynak dosyaları depolamak anlamına gelir. Örneğin, Fransızca Belçika için kaynaklarınız varsa ("fr-olabilir") kültür ve hemen üzerindeki kaynaklar İngilizce geri dönüş kaynakları, birisi Fransızca Kanada kültürü için yapılandırılmış bir sistemde, uygulamanızın kullanırken bir sorun sonuçlanabilir. Sistem "fr-CA" için bir uydu derleme arayın, değil bulmak ve İngilizce, Fransızca kaynakları yüklemek yerine geri dönüş kaynağı içeren ana derleme yüklenemiyor. Aşağıdaki resimde, bu istenmeyen senaryoyu gösterir.  
  
 ![Yalnızca belirli kaynaklar](../ide/media/vbspecificresourcesonly.gif "vbSpecificResourcesOnly")  
  
 Dilden bağımsız kaynak dosyasında "fr" kültür için mümkün olduğunca fazla kaynak yerleştirme önerilen uygulama izlerseniz, Fransızca Kanada kullanıcısı için işaretlenmiş kaynakları görmek "fr-olması" kültür, ancak çözemiyorsa getirirseniz dizeleri Fransızca. Tercih edilen bu senaryo aşağıdaki durum gösterir.  
  
 ![NeutralSpecificResources grafiği](../ide/media/vbneutralspecificresources.gif "vbNeutralSpecificResources")  
  
## <a name="see-also"></a>Ayrıca bkz.

[Yerelleştirme İçin Bağımsız Kaynak Dilleri](../ide/neutral-resources-languages-for-localization.md)  
[Güvenlik ve Yerelleştirilmiş Yardımcı Derlemeler](../ide/security-and-localized-satellite-assemblies.md)  
[Uygulamaları Yerelleştirme](../ide/localizing-applications.md)  
[Uygulamaları Genelleştirme ve Yerelleştirme](../ide/globalizing-and-localizing-applications.md)