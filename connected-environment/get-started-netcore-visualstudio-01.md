---
title: Visual Studio - adım 1 - yükleme araçları ile bulutta Kubernetes kullanarak kapsayıcılarla .NET Core geliştirme ortamı oluşturma | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: 4f25d4ae550f47533628bf073f2f22d9ed158cab
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Bağlı ortam .NET Core ve Visual Studio ile çalışmaya başlama

Bu kılavuzda, öğreneceksiniz nasıl yapılır:

1. Geliştirme için en iyi duruma getirilmiş Azure Kubernetes tabanlı ortamı oluşturun.
1. Visual Studio kullanarak kapsayıcılardaki kodu tekrarlayarak geliştirin.
1. Bağımsız olarak iki ayrı hizmetleri ve başka bir hizmet için arama yapmak için kullanılan Kubernetes DNS hizmet bulma geliştirin.
1. Üretken geliştirin ve kodunuzu bir ekip ortamında test.

[!INCLUDE[](includes/see-troubleshooting.md)]

## <a name="install-the-connected-environment-cli"></a>CLI bağlı Ortamı'nı yükler
Bağlı bir ortam en düşük yerel makine Kurulum gerektirir. Geliştirme ortamı yapılandırmasının çoğu bulutta depolanan ve diğer kullanıcılarla paylaşılabilir.

1. Yükleme [Windows için Git](https://git-scm.com/downloads)seçin varsayılan seçenekleri yükleyin. 
1. Karşıdan **kubectl.exe** gelen [bu bağlantıyı](https://storage.googleapis.com/kubernetes-release/release/v1.9.0/bin/windows/amd64/kubectl.exe) ve **kaydetmek** YOLUNUZU konumunda için.
1. İndirme ve çalıştırma [bağlı ortam CLI yükleyici](https://aka.ms/get-vsce-windows). 

## <a name="get-kubernetes-debugging-tools"></a>Hata ayıklama araçları Kubernetes Al
Ayrı bir araç olarak bağlı ortam CLI kullanabilirsiniz, ancak gibi zengin özellikler **Kubernetes hata ayıklama** kullanarak .NET Core geliştiriciler için kullanılabilir **VS Code** veya **Visual Studio**.

### <a name="visual-studio-debugging"></a>Visual Studio hata ayıklama 
1. En son sürümünü yüklemek [Visual Studio 2017](https://www.visualstudio.com/vs/)
1. Visual Studio Yükleyicisi'nde, aşağıdaki iş yükü seçili olduğundan emin olun:
    * ASP.NET ve web geliştirme
1. Yükleme [bağlı ortam için Visual Studio uzantısı](https://aka.ms/get-vsce-visualstudio)

Şimdi Visual Studio ile ASP.NET web uygulamasını oluşturmak için hazır olarak çalışıyoruz.

> [!div class="nextstepaction"]
> [Bir ASP.NET web uygulaması oluşturma](get-started-netcore-visualstudio-02.md)