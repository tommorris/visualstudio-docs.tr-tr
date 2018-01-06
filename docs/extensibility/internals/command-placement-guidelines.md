---
title: "Komut yerleştirme yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5c79d58530a7f6afc5779fab1bc0b5a1626cb595
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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