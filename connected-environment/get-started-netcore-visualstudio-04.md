---
title: .NET Core geliştirme ortamı Visual Studio - 4. adım - Debug ile bulutta Kubernetes kullanarak kapsayıcılarla bir kapsayıcı içinde Kubernetes oluşturun | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: 9b3aa6b0f710707800ea9a1f0533b0c37681ea05
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Bağlı ortam .NET Core ve Visual Studio ile çalışmaya başlama

Önceki adımda: [bir geliştirme ortamı oluşturma](get-started-netcore-visualstudio-03.md)

## <a name="debug-a-container-in-kubernetes"></a>Kubernetes kapsayıcısında hata ayıklama
Geliştirme ortamı başarıyla oluşturulduktan sonra uygulama ayıklayabilirsiniz. Örneğin satırında 20 dosyasındaki kodu bir kesme noktası belirleyerek `HomeController.cs` burada `Message` değişkeni ayarlanır. Tıklatın **F5** hata ayıklama başlatılamıyor. 

Visual Studio geliştirme ortamı oluşturun ve uygulamayı dağıtın ve sonra çalışan web uygulaması ile bir tarayıcı açın ile iletişim kurar. Kapsayıcı yerel olarak çalışıyor, ancak gerçekte Azure bizim geliştirme ortamında çalışıyor gibi görünebilir. Bağlı ortam Azure'da çalışan kapsayıcısı geçici bir SSH tüneli oluşturduğundan localhost adresi için nedenidir.

Tıklayın "**hakkında**" bağlantı kesme tetiklemek için sayfanın üstündeki. Hata ayıklama kodu yerel olarak çalıştırma çağrı yığını, yerel değişkenleri, özel durum bilgileri, vb. gibi yaptığınız gibi bilgileri için tam erişime sahip.

> [!div class="nextstepaction"]
> [Başka bir kapsayıcı çağırın](get-started-netcore-visualstudio-05.md)