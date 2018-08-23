---
title: VSPackage'ları yönetme | Microsoft Docs
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
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
caps.latest.revision: 36
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 349dc380e23e5f76ad32631384bc4db8fceeff00
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694882"
---
# <a name="managing-vspackages"></a>VSPackage’ları Yönetme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yönetme VSPackages](https://docs.microsoft.com/visualstudio/extensibility/managing-vspackages).  
  
Çoğu durumda VSPackages, proje ve öğe şablonlarını kaydetme ve paket otomatik olarak yük yönetilmesi konusunda endişelenmesine gerek yoktur. Ancak, bazı durumlarda, paket yönetmek için biraz daha fazla bilgi edinmek gerekebilir.  
  
## <a name="using-the-experimental-instance"></a>Deneysel örneği kullanma  
 Deneysel örnek hakkında daha fazla bilgi için bkz. [deneysel örneğinde](../extensibility/the-experimental-instance.md).  
  
## <a name="registering-and-unregistering-vspackages"></a>VSPackage Kaydetme ve Kaydını Kaldırma  
 Kaydolun ve VSPackages ve diğer tür uzantılarla kaydı konusunda bilgi edinmek için bkz: [kaydetme ve kaydını kaldırma VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="loading-a-vspackage"></a>VSPackage yükleme  
 VSPackage sorsorgu CMDUICONTEXT GUID açık belirli bir zaman için ayarlanabilir. Daha fazla bilgi için [VSPackage yükleme](../extensibility/loading-vspackages.md).  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>AsyncPackage kullanarak arka planda VSPackage'ı yükleme  
 Visual Studio kullanıcı Arabirimi yanıt sürelerinde için arka plan iş parçacığında yükleme paketi AsyncPackage sınıfı sağlar. Daha fazla bilgi için [nasıl yapılır: arka planda VSPackage yükleme için kullanım AsyncPackage](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md).  
  
## <a name="rule-based-ui-context-for-extensions"></a>Uzantıları için kural tabanlı UI bağlamı  
 Uzantı yazarları, altında çalışacağı bir UI bağlamı etkinleştirildi ve ilişkili VSPackages yüklenen kesin koşulları tanımlamak kural tabanlı UI bağlamı sağlar. Daha fazla bilgi için [nasıl yapılır: Visual Studio uzantıları kullanım kural tabanlı UI bağlamı](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md).  
  
## <a name="troubleshooting-vspackages"></a>VSPackage Sorunlarını Giderme  
 Yükleme veya sorun yaşadığınızda VSPackage sorunlarını giderme teknikleri öğrenin: [VSPackage sorunlarını giderme](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage’lar](../extensibility/internals/vspackages.md)

