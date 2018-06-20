---
title: Windows Vista'da ClickOnce dağıtımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- UAC manifest generation
- ClickOnce deployment, Windows
- manifest generation
- Windows, ClickOnce deployment
ms.assetid: b21a0ebc-0ff6-4f49-8993-7d1ad3f8cac2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81bd18d10b91f06636ad6bba8230ec29b0d81312
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36235160"
---
# <a name="clickonce-deployment-on-windows-vista"></a>Windows Vista'da ClickOnce dağıtımı

Visual Studio'da uygulamaları oluşturma kodlanmış ikili olarak XML verileri uygulamanın yürütülebilir dosyası içinde Windows Vista kullanıcı hesabı denetimi (UAC) normalde gömülü bir bildirim üretir.  ClickOnce ve Kayıtsız COM uygulamaları harici bir bildirim gerektirdiğinden, Visual Studio gömülü bir bildirim yerine UAC verisi içeren bu proje için bir dosya oluşturur. ClickOnce ve Kayıtsız COM dağıtımları için Visual Studio harici UAC bildirim bilgileri oluşturmak için app.manifest adlı dosyadan bilgileri kullanır. Tüm diğer durumlarda, Visual Studio uygulama yürütülebilir dosyada UAC veri katıştırır. 

Visual Studio bildirim oluşturmak üzere aşağıdaki seçenekleri sağlar:  
  
-   Gömülü bir bildirim kullanın. UAC veri uygulamanın yürütülebilir dosyasına katıştırma ve normal bir kullanıcı olarak çalıştırın.  
  
     Bu, (ClickOnce kullanmadığınız sürece) varsayılan ayardır. Bu ayar, Visual Studio faaliyet normal şekilde Windows Vista'da destekler, hem iç hem de dış nesil kullanarak bildirim `AsInvoker`.  
  
-   Harici bildirim kullanın. Harici bildirim app.manifest kullanarak oluşturun.  
  
     Bu, yalnızca harici bildirim app.manifest bilgileri kullanarak oluşturur. ClickOnce veya Kayıtsız COM kullanarak bir uygulama yayımladığınızda, Visual Studio app.manifest'i projeye ekler ve bu seçeneği ekler.  
  
-   Hiçbir bildirim kullanın. Bildirim olmadan uygulama oluşturun.  
  
     Bu yaklaşım da denir *sanallaştırma*. Visual Studio'nun önceki sürümlerindeki mevcut uygulamalarla uyumluluk için bu seçeneği kullanın.  
  
 Yeni özellikler mevcuttur **uygulama** sayfası Proje Tasarımcısı (Visual C# projeleri yalnızca için) ve MSBuild proje dosyası biçiminde.  
  
 Visual Studio IDE'de UAC bildirim üretme yapılandırma yöntemi proje türü (Visual C# veya Visual Basic) bağlı olarak farklılık gösterir.  
  
   * Visual C# projeleri için bildirim üretme yapılandırma hakkında daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md).  
  
   * Visual Basic projeleri için bildirim üretme yapılandırma hakkında daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [Kullanıcı izinleri ve Visual Studio](http://msdn.microsoft.com/en-us/d5c55084-1e7b-4b61-b478-137db01c0fc0)   
 [Uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Uygulama Sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)