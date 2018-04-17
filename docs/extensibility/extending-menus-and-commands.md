---
title: Menüleri ve komutları genişletme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, common tasks
- VSPackages, menu tasks
- .vsct files, common menu tasks
ms.assetid: 7b2be4b9-e3fe-4412-874f-ae72ebc84c4b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 830748be6f2cedf57b94a9824bc0912820067718
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="extending-menus-and-commands"></a>Genişletme menüleri ve komutları
Komutlar için Visual Studio Eylemler ve işlemleri eklemeniz yoludur. Çoğu durumda, menüleri veya araç çubuklarını komutlar görüntülenir. VSPackage proje şablonu nasıl çok basit bir komut uygulandığını gösterir. Bir biraz daha uzun ancak hala temel için bkz: [uzantı menü komutu ile oluşturma](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
 Visual Studio komutları, menüleri ve araç çubukları hakkında daha fazla bilgi için bkz: [komutları, menüleri ve araç çubuklarını](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Komutları, menüleri ve araç çubuklarını VSPackage projeleri parçası olan .vsct dosyasında tanımlanır. Visual Studio IDE ve .vsct dosyasında hakkında bilgi bulabilirsiniz [nasıl VSPackages ekleme kullanıcı arabirimi öğeleri](../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Aşağıdaki konular, komutları, menüleri ve araç çubuklarını farklı türde eklemek açıklanmaktadır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Visual Studio Menü Çubuğuna Menü Ekleme](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)  
 Visual Studio menü çubuğu üstünde bir menü eklemek açıklanmaktadır.  
  
 [Menü Öğelerine Klavye Kısayolları Bağlama](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
 Menü öğesi için bir klavye kısayolu (örneğin, CTRL + 3) ına nasıl ekleneceğini açıklar.  
  
 [Bir Menüye Alt Menü Ekleme](../extensibility/adding-a-submenu-to-a-menu.md)  
 Alt menü üst menü ekleme açıklanmaktadır.  
  
 [Bir Alt Menüye Son Kullanılanlar Listesi Ekleme](../extensibility/adding-a-most-recently-used-list-to-a-submenu.md)  
 En son kullanılan listesini ına nasıl ekleneceğini açıklar.  
  
 [Yeniden Kullanılabilir Düğme Grupları Oluşturma](../extensibility/creating-reusable-groups-of-buttons.md)  
 Böylece birden fazla menülerde dahil komutu öğeleri gruplandırmak açıklar.  
  
 [Menü Komutlarına Simge Ekleme](../extensibility/adding-icons-to-menu-commands.md)  
 Araç çubuğu ve menü komutu için bir simge eklemeyi açıklar.  
  
 [Bir Menü Komutunun Metnini Değiştirme](../extensibility/changing-the-text-of-a-menu-command.md)  
 Kullanımını açıklar `TextChanges` dinamik olarak değiştirilecek menü öğesi etkinleştirmek üzere bayrağı.  
  
 [Bir Komutun Görünümünü Değiştirme](../extensibility/changing-the-appearance-of-a-command.md)  
 Dinamik olarak etkinleştirme veya bir komut devre dışı açıklar.  
  
 [Kullanıcı Arabirimini Güncelleştirme](../extensibility/updating-the-user-interface.md)  
 En son değişiklikleri yansıtacak şekilde kullanıcı arabiriminin bir güncelleştirmeyi uygulamak açıklar.  
  
 [Menü Komutlarını Yerelleştirme](../extensibility/localizing-menu-commands.md)  
 Menü komutları yerelleştirme açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler