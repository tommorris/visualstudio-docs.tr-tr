---
title: "Menüleri ve komutları genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menus, common tasks
- VSPackages, menu tasks
- .vsct files, common menu tasks
ms.assetid: 7b2be4b9-e3fe-4412-874f-ae72ebc84c4b
caps.latest.revision: "49"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c53f836b6384968bf812ae9ae559a281fda6f13
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-menus-and-commands"></a>Genişletme menüleri ve komutları
Komutlar için Visual Studio Eylemler ve işlemleri eklemeniz yoludur. Çoğu durumda, menüleri veya araç çubuklarını komutlar görüntülenir. VSPackage proje şablonu nasıl çok basit bir komut uygulandığını gösterir. Bir biraz daha uzun ancak hala temel için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
 Visual Studio komutları, menüleri ve araç çubukları hakkında daha fazla bilgi için bkz: [komutları, menüleri ve araç çubuklarını](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Komutları, menüleri ve araç çubuklarını VSPackage projeleri parçası olan .vsct dosyasında tanımlanır. Visual Studio IDE ve .vsct dosyasında hakkında bilgi bulabilirsiniz [nasıl VSPackages ekleme kullanıcı arabirimi öğeleri](../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Aşağıdaki konular, komutları, menüleri ve araç çubuklarını farklı türde eklemek açıklanmaktadır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Visual Studio menü çubuğunda bir menü ekleme](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)  
 Visual Studio menü çubuğu üstünde bir menü eklemek açıklanmaktadır.  
  
 [Menü öğeleri bağlama klavye kısayolları](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
 Menü öğesi için bir klavye kısayolu (örneğin, CTRL + 3) ına nasıl ekleneceğini açıklar.  
  
 [Bir menüye alt menü ekleme](../extensibility/adding-a-submenu-to-a-menu.md)  
 Alt menü üst menü ekleme açıklanmaktadır.  
  
 [Alt menü listesine kullanılan bir en kısa süre önce ekleme](../extensibility/adding-a-most-recently-used-list-to-a-submenu.md)  
 En son kullanılan listesini ına nasıl ekleneceğini açıklar.  
  
 [Düğmelerinin yeniden kullanılabilir grupları oluşturma](../extensibility/creating-reusable-groups-of-buttons.md)  
 Böylece birden fazla menülerde dahil komutu öğeleri gruplandırmak açıklar.  
  
 [Menü komutlarına simgeler ekleme](../extensibility/adding-icons-to-menu-commands.md)  
 Araç çubuğu ve menü komutu için bir simge eklemeyi açıklar.  
  
 [Menü komutu metin değiştirme](../extensibility/changing-the-text-of-a-menu-command.md)  
 Kullanımını açıklar `TextChanges` dinamik olarak değiştirilecek menü öğesi etkinleştirmek üzere bayrağı.  
  
 [Bir komut görünümünü değiştirme](../extensibility/changing-the-appearance-of-a-command.md)  
 Dinamik olarak etkinleştirme veya bir komut devre dışı açıklar.  
  
 [Kullanıcı arabirimi güncelleştiriliyor](../extensibility/updating-the-user-interface.md)  
 En son değişiklikleri yansıtacak şekilde kullanıcı arabiriminin bir güncelleştirmeyi uygulamak açıklar.  
  
 [Yerelleştirme menü komutları](../extensibility/localizing-menu-commands.md)  
 Menü komutları yerelleştirme açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler