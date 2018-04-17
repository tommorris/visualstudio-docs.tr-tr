---
title: Komut, Grup ve araç çubuğu yerleştirme varsayılan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands [Visual Studio], default groups
- toolbars [Visual Studio], default
- commands [Visual Studio], default editor
- command groups
- commands [Visual Studio], default IDE
- commands [Visual Studio], default product
ms.assetid: 35342110-d639-4577-8367-00b21dcc6f07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0753a29e323f18ad40bcc62a70cf8e9b1123b728
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="default-command-group-and-toolbar-placement"></a>Varsayılan komutu, Grup ve araç çubuğu yerleştirme
UI ürün bütünlüğünü ve tutarlılık için belirli komut grupları varsayılan olarak, görüntüler. ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutları ve komut grupları için tanımları sağlar. VSPackages de standart komutları ve komut gruplarını kullanabilirsiniz.  
  
 Varsayılan komut gruplarını üç kategoriye ayrılır: IDE komutları, ürün komutları ve düzenleyici komutları.  
  
## <a name="default-ide-commands"></a>Varsayılan IDE komutları  
 Varsayılan IDE araç bulunan tüm ürünleri tarafından paylaşılan komutları içerir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bunlar gibi genel proje işlemleriyle ilgili komutları **kaydetmek** komut ve **Öğe Ekle** komutu. VSPackages eklemeyin veya bir özel durum dışında bu araç, çıkart: Ürün veya VSPackage yeni bir araç penceresi ekler sonra pencere üzerinde kullanılabilir aracı windows listesine eklenmelidir **Görünüm** menüsü. Yeni ürün veya VSPackages kendi araç ekleyebilirsiniz.  
  
## <a name="default-product-commands"></a>Varsayılan ürün komutları  
 Her ürünün IDE önemli içeren ve sık kullanılan komutlar kendi varsayılan araç çubuğu ile sağlayabilir. Ancak, varolan menüleri ve araç çubuklarını mümkün olduğunca kullanın ve bunları gerektiği gibi diğer görev özel araç çubukları ile desteklemek için en iyisidir.  
  
 Bir araç için Öncelik alanını satır yerleşimi belirler. Araç sıfır öncelik üçüncü satırı (Satır 3), menü çubuğundaki altına yerleştirir (satır 1) ve **standart** araç (satır 2). Bu nedenle, satırda başka araç çubukları görüntülenir (öncelik + 3). Yer ise sonraki araç çubukları aynı satırda yerleştirilir; Aksi takdirde, bunlar sonraki satıra otomatik olarak taşınır.  
  
## <a name="default-editor-commands"></a>Varsayılan düzenleyici komutları  
 Özel bir düzenleyici sunar VSPackage en önemli içeren ve sık kullanılan komutlar bu Düzenleyici'de varsayılan araç sağlamalıdır. Düzenleyici etkin olduğunda ve Düzenleyici etkin olmadığı zaman gizleneceğini Düzenleyici araç çubuğu görüntülenmelidir. Bu görünürlük denetlenir `VisibilityConstraints Element` .vsct dosyasının.  
  
 Düzenleyici araç çubukları IDE ve ürün araç çubukları yerleştirilmelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDE tanımlı komutlar, menüler ve grupları](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)   
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)