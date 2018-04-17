---
title: Komut yerleştirme yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c406a5a34ea2556d367c8f7af8a9fda70fcc2676
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="command-placement-guidelines"></a>Komut yerleştirme yönergeleri
Visual Studio tümleşik geliştirme ortamı (IDE) komutları konumlandırma için en iyi yöntemler komut kümesi boyutuna bağlı olarak değişir. Komutları tanımlanır ve .vsct dosyalarındaki bilgileri göre konumlandırıldı.  
  
## <a name="best-practices-for-all-command-sets"></a>Tüm komut kümeleri için en iyi yöntemler  
 Her komut kümesi için aşağıdaki yönergeleri izleyin:  
  
-   Bir grafik komut yapısının önceden hazırlayın. Komutları, birleşik giriş kutuları, komut grupları ve birden fazla konumda kullanılacak kısayol menüleri tanımlayın.  
  
-   Aynı grupta görünen komutlarını ilişkili olmalıdır.  
  
-   Tek bir komut içeren grupları kabul edilir.  
  
-   Paketler için mevcut Visual Studio menü komutları çok sayıda eklemeyin. Bunun yerine, bunlar menüleri veya yeni komutları barındırmak için alt menüler oluşturmanız gerekir.  
  
-   Bir komut adı komutu bir varolan menü amacı açıktır ve onu varolan komutları ile karıştırılmamalıdır yerleştirdiğinizde.  
  
## <a name="best-practices-for-small-command-sets"></a>Küçük komut kümeleri için en iyi yöntemler  
 Ayrıca birkaç komutları sahip bir VSPackage geliştiriyorsanız, aşağıdaki yönergeleri izleyin:  
  
-   Mümkün olduğunda kullanın [üst öğesi](../../extensibility/parent-element.md) komutu, birleşik giriş kutusu, Grup veya alt menü uygun gruba yerleştirmek için.  
  
-   Bu gruplar VSPackage tarafından görüntülenen menüleri atayın.  
  
-   Alt menü veya bir komut üst olmalıdır bir [Grup öğesi](../../extensibility/group-element.md). Komutlar ve alt menüler gruplarına atamak ve grupları üst menülere atayın.  
  
-   Ekleyerek bir komutu ek gruplarında koyabilirsiniz bir [CommandPlacements öğesi](../../extensibility/commandplacements-element.md) bölümünde komut tanımı sonra ve ardından ekleme `CommandPlacements Element` bir [CommandPlacement öğesi](../../extensibility/commandplacement-element.md) her Ek grubu.  
  
## <a name="best-practices-for-large-command-sets"></a>Büyük komutu kümeleri için en iyi yöntemler  
 Ayrıca, VSPackage birden çok bağlamlarda görünür komutların çoğu olacaksa, aşağıdaki yönergeleri izleyin:  
  
-   Menüleri, gruplar ve komutlar kendi kendine bölünerek yapın. Diğer bir deyişle, değil atamak bir `Parent Element` öğe tanımında.  
  
-   Kullanım `CommandPlacement Element` girişleri `CommandPlacements Element` bölüm menüleri, gruplar ve komutlar kendi üst menüleri ve grupları yerleştirin.  
  
-   İçinde `CommandPlacements` bölümünde, verilen bir menü doldurmak girdileri veya grup birbirine bitişik. Bu okunabilirlik yardımları ve yapar `Priority` derecelendirmeleri belirlemek daha kolay.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)