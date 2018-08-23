---
title: Visual Studio için etkileşim desenleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3643792-b0df-481c-bc35-576f948e04cf
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf21a8aa3c2a2813c71907d1d79bdcd4f7cde323
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686181"
---
# <a name="interaction-patterns-for-visual-studio"></a>Visual Studio için etkileşim desenleri
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [etkileşim desenleri için Visual Studio](https://docs.microsoft.com/visualstudio/extensibility/ux-guidelines/interaction-patterns-for-visual-studio).  
  
## <a name="overview"></a>Genel Bakış  
 Bir tasarım deseni, genel olarak, çekirdeği kısıtlamaları benzer kümeleriyle ilgili sorunları çözmek için belirli durumlarda uygulanabilir bir tasarım olur. Özellik ve sistem tasarımcılarına bu tasarım desenleri, ardından kendi özel durum için uyarlanabilir noktaları, başlangıç olarak kullanın.  
  
 Visual Studio, kitaplığa yeni özellikler oluştururken dikkate alınması ortak etkileşim düzeni sahiptir. Bizim tasarım modelleri için iki çekirdek bağlamları vardır: Visual Studio istemcisi (devenv) ve Visual Studio Online. Bazı tasarım sorunlar için tüm durumlarda düzgün çalışıyor bulunabilen bir düzeni vardır. Çoğu durumda, ancak çözüm bir tarayıcısı ve bir istemci uygulamasında barındırılan, içinde sunulan kullanıcı arabirimi farklı olabilir.  
  
### <a name="visual-studio-client-pattern-types"></a>Visual Studio istemci Deseni türleri  
  
|Desen türü|Açıklama|Örnekler|  
|------------------|-----------------|--------------|  
|**Uygulama düzeyi desenleri**|Belirleme veya uygulama içeriği görüntüleme ve bunların içindeki bileşik ve denetim desenleri içeren uygulama için ortak üst düzey desenleri|-Araç pencereleri<br />-Belge pencereleri|  
|**Bileşik desenler**|Uygulama desenleri arasında yayılabilir ortak desenler veya farklı bir yapılandırmada çeşitli denetimler oluşan tanınan bir deseni|-Görünümü değiştirme<br />-List oluşturucular<br />-Verileri görüntüleme<br />-Bildirimler<br />-Doğrulama<br />-Seçimi modelleri|  
|**Denetim desenleri**|Özellikleri nasıl alt düzey denetimleri hakkında davranış beklenir|-Ağaç görünümleri<br />-Bir kılavuz denetimi içinde düzenleme|  
  
## <a name="application-patterns"></a>Uygulama desenleri  
 Yüksek düzeyde, Visual Studio arabirimini birden çok windows, iletişim kutuları, komutları ve araç çubukları tek bir IDE içinde oluşur. Visual Studio hiyerarşisi bağlam ve sürücüleri menüleri belirler. Belge pencerelerini, araç pencerelerini, projeler, komut yapısını, metin düzenleyici, araç, Özellikler penceresinde ve araçları kullanıcı arabiriminde anahtar tümleştirme noktaları IDE olan > Seçenekleri.  
  
 Her bir kullanıcı arabiriminde anahtar tümleştirme noktası IDE için temel kullanım desenlerini vardır:  
  
-   [Menüler ve komutlar için Visual Studio](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md)  
  
-   [Visual Studio için uygulama desenleri](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)  
  
    -   [Pencere etkileşimleri](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_WindowInteractions)  
  
    -   [Araç pencereleri](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_ToolWindows)  
  
    -   [Belge Düzenleyicisi kuralları](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_DocumentEditorConventions)  
  
    -   [İletişim Kutuları](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs)  
  
    -   [Projeler](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Projects)  
  
## <a name="common-control-patterns"></a>Yaygın denetim desenleri  
 Denetim desenleri, çoğunlukla tek denetimleri hakkında davranış beklenir alır. Bu tutarlılık en önemli bir noktadır.  
  
 Visual Studio'da ortak denetimleri Masaüstü Windows yönergeleri izlemelidir. Koşullarımıza yalnızca, Visual Studio özgü etkileşimleri veya basamak, biz yönergeleri tamamen Gelişmiş kullanıcılarımızın gereksinimlerini karşılamak için Visual Studio uyarlamak için yerine geçen genel kurallar genişletmek ihtiyacımız olan alanları içerir.  
  
-   [Visual Studio için yaygın denetim desenleri](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md)  
  
    -   [Ortak Denetimler](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_CommonControls)  
  
    -   [Metin denetimi](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TextControls)  
  
    -   [Düğmeler ve köprüleri](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ButtonsAndHyperlinks)  
  
## <a name="composite-patterns"></a>Bileşik desenler  
 Çeşitli görevleri gerçekleştirmek üzere kullanıcıların beklediğiniz yollar vardır. Mümkün olduğunda, bu desenleri hem etkileşim ve görsel tasarım için kullanılacak özellikleri tasarlanmalıdır.  
  
 En önemli bazı Visual Studio içinde birçok bileşik desenler varken bakımından tutarlılık şunlardır:  
  
-   [Visual Studio için bileşik desenler](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md)  
  
    -   [Nesne üzerinde kullanıcı Arabirimi ve gözatma](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_OnObjectUI)  
  
    -   [Seçimi modelleri](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_SelectionModels)  
  
    -   [Kalıcılığı ve ayarları kaydediliyor](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_PersistenceAndSavingSettings)  
  
    -   [Dokunma girişi](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_TouchInput)

