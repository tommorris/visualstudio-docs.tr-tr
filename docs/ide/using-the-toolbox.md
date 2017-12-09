---
title: "Araç kutusunu kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.chooseitems
- vs.toolboxpages.activexcontrols
- VS.CHOOSEITEMS.windowsuixamlcomponents
- VS.chooseitems.silverlightcomponents
- VC.EDITORS.RIBBON
- vs.customizetoolbox
- VS.chooseitems.System.Workflow_Components
- vs.chooseitems.frameworkcomponents
- VS.ToolboxPages..NET_Framework_Components
- VS.chooseitems.Microsoft.VisualStudio.Toolbox.VsToolboxPage
- vs.chooseitems.comcomponents
- vs.toolboxpages.NGWS_components
helpviewer_keywords:
- toolbox, adding items
- Visual Studio, toolbox
- toolbox, tabs
- toolbox
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9290f2dbaae27bef7934d8fd619b4ee5355f4ec3
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="using-the-toolbox"></a>Araç Kutusunu Kullanma

Araç kutusu denetimleri ve diğer öğeleri projenize eklemek için kullanabilirsiniz. Farklı denetim kullanıyorsanız ve yeniden boyutlandırma ve denetimleri konumlandırmak Tasarımcı yüzeyine sürükleyip bırakabilirsiniz.

Araç kutusu gibi XAML dosyasının designer Görünüm Tasarımcısı görünümleri ile birlikte görüntülenir. Araç kutusu geçerli Tasarımcısı'nda kullanılabilen denetimleri görüntüler.

.NET Framework sürümünü projenizi araç kutusunda görünür denetimleri kümesini de etkiler hedefler. Proje düğümünde seçerek farklı bir .NET Framework sürümünü hedeflemek için projenizi ayarlayabilirsiniz **Çözüm Gezgini**ve ardından göz **uygulama/özellikler/hedef Framework**.

## <a name="managing-the-toolbox-and-its-controls"></a>Araç kutusu ve kendi denetimlerini yönetme

Varsayılan araç kutusunu Visual Studio IDE sol tarafında daraltılmış ve imleci üzerine taşındığında görüntülenir. Araç kutusu sabitleyebilirsiniz (tıklayarak **PIN** araç çubuğunda simge) açık kalmayacak şekilde taşıdığınızda imleci. Ayrıca, araç penceresi çıkar ve ekranınızda herhangi bir yere sürükleyin. Yerleştirme, çıkar ve araç sağ tıklayıp seçeneklerden birini seçerek araç gizle.

Araç kutusu sekmesinde öğeleri yeniden düzenleyin veya bağlam menüsünde aşağıdaki komutları kullanarak özel sekmeler ve öğeleri ekleyin:

-   **Öğeyi yeniden adlandırmak** -seçili öğeyi yeniden adlandırır.  
  
-   **Tümünü Göster** -tüm olası denetimleri (yalnızca geçerli Designer'a geçerli olanları) gösterir.  
  
-   **Liste görünümü** -denetimleri dikey listesini gösterir. Seçilmezse, denetimleri yatay olarak görünür.  
  
-   **Öğeleri seçin** -açar **araç kutusu öğelerini Seç** iletişim kutusu görünür öğeleri belirtebilirsiniz **araç**. Gösterebilir veya öğeyi seçerek veya onay kutusunu temizleyerek gizleyebilirsiniz.  
  
-   **Sıralama öğelerini alfabetik olarak** -öğeleri adına göre sıralar.  
  
-   **Araç çubuğunu sıfırlama** - varsayılan araç kutusunu ayarlarını geri yükler ve öğeleri.  
  
-   **Sekme ekleme** -yeni bir araç kutusu sekmesi ekler.  
  
-   **Yukarı Taşı** -seçili öğeyi yukarı taşır.  
  
-   **Aşağı Taşı** -seçilen öğeyi aşağı taşır.  

## <a name="creating-and-distributing-custom-toolbox-controls"></a>Oluşturma ve dağıtma özel araç çubuğu denetimleri

Visual Basic veya Visual C# içinde bir özel araç kutusu denetim oluşturabilirsiniz ve temel alan bir proje şablonu ile başlayabilirsiniz [Windows Presentation Foundation](../extensibility/creating-a-wpf-toolbox-control.md) veya [Windows Forms](../extensibility/creating-a-windows-forms-toolbox-control.md). Kodunuza için denetiminizi dağıtmak veya kullanarak Web'de Yayımlama [araç kutusu denetimleri yükleyici](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx).

## <a name="see-also"></a>Ayrıca bkz.

[Kod Düzenleyicisi'nde yazma](../ide/writing-code-in-the-code-and-text-editor.md)