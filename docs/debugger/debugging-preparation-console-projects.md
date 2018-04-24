---
title: 'Hata ayıklama hazırlığı: Konsol projeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], console applications
- debugging console applications
- console applications, debugging
ms.assetid: 9641f1d9-2d5a-48b1-8731-6525e8f67892
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b864ed1a1c0a105a0ab5f441f6d7a9a935dc6dc
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-preparation-console-projects"></a>Hata Ayıklama Hazırlığı: Konsol Projeleri
Bir konsol projesi hata ayıklamaya hazırlanıyor bazı hususlar sahip bir Windows proje hata ayıklamaya hazırlanıyor için benzer. Daha fazla bilgi için bkz: [Windows Forms uygulamaları](../debugger/debugging-preparation-windows-forms-applications.md), ve [hata ayıklama hazırlığı: Windows Forms uygulamaları (.NET)](http://msdn.microsoft.com/en-us/a8bc54de-41a3-464d-9a12-db9bdcbc1ad5). Tüm konsol uygulamaları benzerlik nedeniyle, bu konu aşağıdaki proje türleri şunları içerir:  
  
-   C# konsol uygulaması  
  
-   Visual Basic konsol uygulaması  
  
-   C++ konsol uygulaması (.NET)  
  
-   C++ konsol uygulaması (Win32)  
  
 Konsol uygulamanız için komut satırı bağımsız değişkenleri belirtmeniz gerekebilir. Daha fazla bilgi için bkz: [bir C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md), [bir Visual Basic hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), veya [C# hata ayıklama yapılandırması proje ayarları ](../debugger/project-settings-for-csharp-debug-configurations.md).  
  
 Bu bağımsız değişkenler tüm özellikleri proje gibi hata ayıklama oturumları ve Visual Studio oturumları arasında kalıcı olmasını sağlar. Konsol uygulaması, daha önce ayıkladıktan ise, bu nedenle, girdiğiniz önceki oturumlarından bağımsız değişkenleri olabilir unutmayın  **\<Proje > özellik sayfaları** iletişim kutusu.  
  
 Bir konsol uygulaması kullanan **konsol** penceresi girişi kabul etmek ve çıktı iletileri görüntülemek için. Yazılacak **konsol** penceresinde uygulamanızı kullanmalıdır **konsol** hata ayıklama nesnesi yerine nesne. Yazılacak **Visual Studio çıkış** penceresi, hata ayıklama nesnesi her zamanki gibi kullanın. Burada, uygulamanızın yazma veya yanlış yerde iletileri için bakarak bildiğinizden emin olun. Daha fazla bilgi için bkz: [konsol sınıfı](/dotnet/api/system.console), [hata ayıklama sınıfı](/dotnet/api/system.diagnostics.debug), ve [çıktı penceresi](../ide/reference/output-window.md).  
  
## <a name="starting-the-application"></a>Uygulama başlatma  
 Bazı konsol uygulamaları başlattığınızda tamamlamayı çalıştıran ve çıkın. Bu davranış yürütme sonu ve hata ayıklama için yeterli süre vermeyebilir. Bir uygulamada hata ayıklamak için uygulamayı başlatmak için aşağıdaki yordamlardan birini kullanın:  
  
-   Uygulamanızı çalıştırma başlar ve kesme ulaşana kadar çalışır.  
  
-   Uygulamanızı başlatır ve kaynak kodu ilk satırında hemen keser.  
  
-   Bir kaynak kod penceresinde, bir satırı sağ tıklatıp **çalıştırmak için imleç**.  
  
     Uygulamanızı başlar ve seçili satır ya da bir kesme noktası önce satır kesme noktası isabet durumunda çalışır.  
  
 Bir konsol uygulaması hata ayıklarken komut isteminden yerine, Visual Studio uygulamayı başlatmak isteyebilirsiniz. Bu durumda, uygulamayı komut isteminden başlatmak ve Visual Studio hata ayıklayıcısı eklemektir. Daha fazla bilgi için bkz: [eklemek için çalışan işlemler](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
 Visual Studio'dan bir konsol uygulaması başlattığınızda **konsol** penceresi bazen Visual Studio penceresi görüntülenir. Visual Studio ve hiçbir şey konsol uygulamanızın başlatmaya çalışırsanız görünüyor gerçekleşir, Visual Studio pencereyi taşımak deneyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Visual C++ proje türleri](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)