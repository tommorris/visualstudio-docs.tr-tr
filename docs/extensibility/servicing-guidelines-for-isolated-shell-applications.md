---
redirect_url: shell/servicing-guidelines-for-isolated-shell-applications
title: "Yalıtılmış kabuk uygulamaları için yönergeler bakım | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio Shell integrated mode, serviceability
- Shell integrated mode [Visual Studio], serviceability
ms.assetid: 747d1a47-b8b3-4e8b-93c0-768724be48f2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7e15d228794fb03441d42c081f11bf75b11fdd45
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="servicing-guidelines-for-isolated-shell-applications"></a>Yalıtılmış kabuk uygulamaları için hizmet verme yönergeleri
Visual Studio yalıtılmış Kabuk uygulama dağıttığınızda, yüklendikten sonra uygulamanız için yazılım güncelleştirmeleri sağlamak mümkün olması gerekir. Bunu yapmak için uygulamanızın Microsoft Installer (MSI) dosyası kullanarak yüklemeniz gerekir. Bu tür bir yükleme Web tarafından dağıtılabilir Microsoft tarafından sağlanan yazılım güncelleştirmeleri karşıdan yükle ve özel müdahalesi olmadan, müşteriler tarafından tüketilen sağlar.  
  
## <a name="servicing-requirements"></a>Bakım gereksinimlerini  
 Yalıtılmış Kabuk yüklemenizi güncelleştirmeleri yükleme programını aşağıdaki üç ölçütlerine sağlayarak izin verebileceğiniz emin olabilirsiniz.  
  
### <a name="redistribute-by-using-an-msi"></a>Bir MSI kullanarak yeniden Dağıt  
 Uygulamanızı yeniden dağıtmak için bir MSI kullanmanız gerekir, çünkü bir MSI ürün kimliğini korur ve emin olun uygulamanın istemci bilgisayardaki fiziksel bir yeri olduğu. Birleştirme modülleri (.msm dosyaları) gibi çıkışların sağlamaz ve kullanılmamalıdır.  
  
### <a name="accounting-for-custom-actions"></a>Özel Eylemler için hesap  
 Standart olmayan yükleme yönergeleri bir yükleyici programı özel eylemlerdir. Özel Eylemler dosya konumları, kayıt defteri ayarları, kullanıcı ayarlarını veya diğer yükleme öğeleri gibi parametreleri değiştirin. Özel Eylemler, yükleme sırasında verileri işlemek.  
  
 Özel Eylemler bir yükleme programı kullandığınızda, her yükleme zamanı özel eylemi kullanıcı uygulamayı kaldırırken eylemi geri almak için karşılık gelen bir özel eylem olmalıdır emin olmalısınız. Karşılık gelen sağlamak için Kurulum programı başarısız özel eylem kaldırırsanız, uygulamanız kaldırarak kısmen yüklü bırakır.  
  
-   Yazılım güncelleştirmeleri bu sürümleri değiştirin ya da karma değeri, bir dosya ya da karma değerleri belirli bir sürümünü kullanan özel bir eylem başarısız olur. Bu durumda, özel eylem bu değerleri el ile güncelleştirmeniz gerekir. Bir dosya ya da karma değerleri sürümleri ürün sürümleri arasında paylaşılan ek bir sorun oluşur. Bu bağımlılık mümkün olduğunca kaçının.  
  
### <a name="accounting-for-shared-files"></a>Paylaşılan dosyalar için hesap  
 Paylaşılan dosyaları aynı ada sahip ve aynı konuma birden fazla ürün tarafından yüklenir. Bu ürün sürümü, stok saklama birimi (SKU) veya her ikisi de farklı olabilir ve ürünleri belirli bir bilgisayarda birlikte bulunabilir. Bununla birlikte, paylaşılan dosyalar bakım sorunları çeşitli nedenlerle oluşturun:  
  
-   Bir uygulama için bir güncelleştirme henüz güncelleştirilmemiş ikinci bir uygulama tarafından kullanılan bir dosya sürümü değişebilir olduğundan paylaşılan dosyaları güncelleştiriliyor uygulama uyumluluğu sorunlarına neden olabilir. Dosyaları paylaşma ürün yükleyicilerini paylaşılan dosyalara başvurular sayısı. Bu nedenle, bir ürünü kaldırmadan azaltma yüklü örnek sayısını aşan paylaşılan dosyaları etkilemez.  
  
-   Hızlı düzeltme Mühendisliği (QFE) Yükleyici QFE yükleyici hizmet ürünlerin sürümlerine dosyaların sürümlerini geri döner. Bu işlem, potansiyel olarak güncelleştirilen bir paylaşılan dosya teslim bir uygulama keser.