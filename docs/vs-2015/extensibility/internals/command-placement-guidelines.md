---
title: Komut yerleştirme yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
caps.latest.revision: 29
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 81c40e2ee18f828ad379cdaabc40854fb87ccfb8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694800"
---
# <a name="command-placement-guidelines"></a>Komut Yerleştirme Yönergeleri
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [komut yerleştirme yönergeleri](https://docs.microsoft.com/visualstudio/extensibility/internals/command-placement-guidelines).  
  
Visual Studio tümleşik geliştirme ortamında (IDE) komutları konumlandırma için en iyi komut kümesi boyutuna bağlı olarak değişir. Komutları tanımlanır ve .vsct dosyaları bilgileri göre yerleştirilmiş.  
  
## <a name="best-practices-for-all-command-sets"></a>Tüm komut kümesi için en iyi uygulamalar  
 Her komut kümesi için aşağıdaki yönergeleri izleyin:  
  
-   Bir grafik komutu yapısı önceden hazırlayın. Komutlar, birleşik giriş kutuları, komut grupları ve birden fazla konumda kullanılacak kısayol menüleri belirleyin.  
  
-   Aynı grubu içinde görünen komutlar ilişkili olmalıdır.  
  
-   Tek bir komut içeren gruplar kabul edilir.  
  
-   Paketler için mevcut Visual Studio menü komutları çok sayıda eklememelisiniz. Bunun yerine, bunlar menülere veya yeni komutlar barındırmak için alt menülere oluşturmalısınız.  
  
-   Bir komut, komut adı gibi varolan bir menüye üzerinde amacı açıktır ve bunu mevcut komutları ile karıştırılmamalıdır böylece yerleştirdiğinizde.  
  
## <a name="best-practices-for-small-command-sets"></a>Küçük komut kümesi için en iyi uygulamalar  
 Ayrıca birkaç komutları içeren bir VSPackage geliştiriyorsanız aşağıdaki yönergeleri izleyin:  
  
-   Mümkün olduğunda, kullanın [üst öğe](../../extensibility/parent-element.md) komutu, birleşik giriş kutusu, Grup veya alt menüsünü uygun gruba yerleştirmek için.  
  
-   VSPackage'ı tarafından görüntülenen menüler bu gruplara atayın.  
  
-   Üst öğesi bir alt menü veya bir komut olmalıdır bir [Group öğesi](../../extensibility/group-element.md). Komutlar ve menüler alt gruplara ve gruplar için üst menü atayın.  
  
-   Bir komutu ekleyerek ek gruplarında koyabilirsiniz bir [CommandPlacements öğesi](../../extensibility/commandplacements-element.md) bölümü bir komut tanımı sonra ve ardından ekleyerek `CommandPlacements Element` bir [CommandPlacement öğesi](../../extensibility/commandplacement-element.md) her ek grup.  
  
## <a name="best-practices-for-large-command-sets"></a>Büyük komut kümesi için en iyi uygulamalar  
 Ayrıca, VSPackage'ı birden çok bağlamlarda görünecek komutların çoğu varsa, aşağıdaki yönergeleri izleyin:  
  
-   Menüleri, gruplar ve komutlar Self bırakarak olun. Atama diğer bir deyişle, bir `Parent Element` öğesinin tanımındaki.  
  
-   Kullanım `CommandPlacement Element` girişleri `CommandPlacements Element` menüler, gruplar ve komutlar, ana menüler ve gruplar koymak bölümü.  
  
-   İçinde `CommandPlacements` bölümünde, verilen bir menü doldurmak girdileri veya grup birbirine bitişik olması. Bu okunabilirliği kolaylık sağlar ve yapar `Priority` sıralamasına belirlemek daha kolay.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage kullanıcı arabirimi öğelerini nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

