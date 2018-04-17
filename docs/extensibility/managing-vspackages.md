---
title: VSPackages yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9e3241bae84b89b53e30c3d0949e4f8551110e7d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="managing-vspackages"></a>VSPackages yönetme
Çoğu durumda VSPackages, proje ve öğe şablonları kaydetmek ve paket otomatik olarak yüklenmesini yönetme hakkında endişelenmeniz gerekmez. Ancak, bazı durumlarda, paket yönetmek için biraz daha fazla bilgi edinmek gerekebilir.  
  
## <a name="using-the-experimental-instance"></a>Deneysel örneğini kullanarak  
 Deneysel örneği hakkında daha fazla bilgi için bkz: [deneysel örneği](../extensibility/the-experimental-instance.md).  
  
## <a name="registering-and-unregistering-vspackages"></a>Kaydetme ve kaydını kaldırma VSPackages  
 Kaydolun ve VSPackages ve diğer tür uzantılarla kaydı konusunda bilgi edinmek için bkz: [kaydetme ve kaydını kaldırma VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="loading-a-vspackage"></a>Bir VSPackage yükleniyor  
 VSPackages autoload CMDUICONTEXT GUID açık belirli bir zaman için ayarlayabilirsiniz. Daha fazla bilgi için bkz: [yüklenirken VSPackages](../extensibility/loading-vspackages.md).  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>AsyncPackage kullanarak VSPackages arka planda yükleme  
 Visual Studio'da daha iyi UI yanıtlama hızı için arka plan iş parçacığında yükleme paketini AsyncPackage sınıfı sağlar. Daha fazla bilgi için bkz: [nasıl yapılır: arka planda yükleme VSPackages için kullanım AsyncPackage](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md).  
  
## <a name="rule-based-ui-context-for-extensions"></a>Uzantıları için kural tabanlı UI bağlamı  
 Kural tabanlı UI bağlamları altında çalışacağı bir kullanıcı Arabirimi bağlamı etkinleştirilir ve ilişkili VSPackages yüklenen kesin koşullarını tanımlamak uzantı yazarların sağlar. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio uzantıları için kullanım kural tabanlı UI bağlamı](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md).  
  
## <a name="diagnosing-extension-performance"></a>Tanılama uzantısını performansı  
Uzantılar, başlatma ve çözüm yük performansı etkileyebilir. Visual Studio uzantısı etkisi nasıl hesaplanır ve nasıl yerel olarak uzantı uzantısı etkileyen bir performans gösterilebilir olmadığını sınamak için analiz edilmeden öğrenin. Daha fazla bilgi için bkz: [nasıl yapılır: Tanılama uzantısını performans](how-to-diagnose-extension-performance.md). 
  
## <a name="troubleshooting-vspackages"></a>Sorun giderme VSPackages  
 Yükleme veya hataları yaşıyor VSPackages sorun giderme teknikleri öğrenin: [VSPackages sorun giderme](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage’lar](../extensibility/internals/vspackages.md)