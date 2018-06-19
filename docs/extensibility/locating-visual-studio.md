---
title: Visual Studio bulma | Microsoft Docs
ms.custom: ''
ms.date: 08/21/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- deployment, VSIX
ms.assetid: 680c3b25-7901-4768-8363-6d1fcd1ea636
ms.author: heaths
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ed6125c69b9068ebfb3d776ccbefaf88043f83a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138619"
---
# <a name="locating-visual-studio"></a>Visual Studio bulma

Visual Studio 2017 ile başlayarak, aynı sürümü veya hatta sürümü birden çok örneğini yükleyebilirsiniz. Bu, önceki yüklemenizin korurken birincil geliştirme makinenizde yeni işlevselliği Önizleme istediğinizde yararlıdır. Bu değişiklikler nedeniyle örneğini bulmak için kullanabileceğiniz tek ortam değişkeni veya kayıt defteri değeri yoktur. Bunun yerine kullanabileceğiniz bir [COM sorgu API](https://msdn.microsoft.com/library/microsoft.visualstudio.setup.configuration.aspx) dahili ilgili ölçütlere göre örneklerini bulmak için.

Yerel ve yönetilen kod için kullanılabilen NuGet paketleri ile hızlı, salt okunur bir API budur.

| Kod | Paket |
| ---- | --- |
| Yerel | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Native |
| Yönetilen | https://nuget.org/packages/Microsoft.VisualStudio.Setup.Configuration.Interop |

Verilen bir yolu veya geçerli işlem tek bir örnek bulun veya tüm örneklerini numaralandıramıyor. Bkz: [örneklerimizi](https://github.com/Microsoft/vs-setup-samples) Visual Studio bulmak tüm örnekleri için.

## <a name="tools"></a>Araçlar

Visual Studio ve başka araçlar derleme ortamları, PowerShell komut dosyaları, yükleyicileri ve daha fazla senaryo bulmak için doğrudan kullanın veya kendi komut dosyalarınızı birlikte yeniden açık kaynaklı araçları sayısı sahibiz.

| Proje | Açıklama |
| ------- | ----------- |
| [vswhere](https://github.com/Microsoft/vswhere) | Yayın veya yayın öncesi, hangi ürününün yüklü olduğunu ve hangi iş yüklerini yüklü gibi bir ölçüte uyan örneklerini bulmak için yerel yürütülebilir tek dosya. Ayrıca, Visual Studio 2017 için ve döndürülen daha az bilgi ancak Visual Studio 2010 ve yeni, bulma destekler. Bkz: [wiki](https://github.com/Microsoft/vswhere/wiki) örnekleri için. |
| [VSSetup cmdlet'leri](https://github.com/Microsoft/vssetup.powershell) | Desteklenen PowerShell cmdlet'leri 2.0 ve daha yeni, aynı ölçütüne göre örneklerini bulmak için kullanabileceğiniz Zengin gibi nesneler döndürmesini _vswhere_ ve örnekleri hakkında daha fazla özellikleri bulur. Bkz: [wiki](https://github.com/Microsoft/vssetup.powershell/wiki) örnekleri için. |
| [VSIXBootstrapper](https://github.com/Microsoft/vsixbootstrapper) | Otomatik olarak bulur _VSIXInstaller_ ve yüklemek için komut satırı aracılığıyla geçirir bir _*.vsix_ dosya. Bu sorgu API'lerini doğrudan desteği olmayan yükleyicileri yararlı olabilir. Bkz: [wiki](https://github.com/Microsoft/vsixbootstrapper/wiki) örnekleri için. |

## <a name="see-also"></a>Ayrıca Bkz.

* [Visual Studio 2017 kurulumu yapılan değişiklikler](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup)
