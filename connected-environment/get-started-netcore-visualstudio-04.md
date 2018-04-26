---
title: .NET Core geliştirme ortamı Visual Studio - 4. adım - Debug ile bulutta Kubernetes kullanarak kapsayıcılarla bir kapsayıcı içinde Kubernetes oluşturun | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 75588fcabbba739c4670da42e24665428ff89130
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Bağlı ortam .NET Core ve Visual Studio ile çalışmaya başlama

Önceki adımda: [bir geliştirme ortamı oluşturma](get-started-netcore-visualstudio-03.md)

## <a name="debug-a-container-in-kubernetes"></a>Kubernetes kapsayıcısında hata ayıklama
Geliştirme ortamı başarıyla oluşturulduktan sonra uygulama ayıklayabilirsiniz. Örneğin satırında 20 dosyasındaki kodu bir kesme noktası belirleyerek `HomeController.cs` burada `Message` değişkeni ayarlanır. Tıklatın **F5** hata ayıklama başlatılamıyor. 

Visual Studio geliştirme ortamı oluşturun ve uygulamayı dağıtın ve sonra çalışan web uygulaması ile bir tarayıcı açın ile iletişim kurar. Kapsayıcı yerel olarak çalışıyor, ancak gerçekte Azure bizim geliştirme ortamında çalışıyor gibi görünebilir. Bağlı ortam Azure'da çalışan kapsayıcısı geçici bir SSH tüneli oluşturduğundan localhost adresi için nedenidir.

Tıklayın "**hakkında**" bağlantı kesme tetiklemek için sayfanın üstündeki. Hata ayıklama kodu yerel olarak çalıştırma çağrı yığını, yerel değişkenleri, özel durum bilgileri, vb. gibi yaptığınız gibi bilgileri için tam erişime sahip.

> [!div class="nextstepaction"]
> [Başka bir kapsayıcı çağırın](get-started-netcore-visualstudio-05.md)