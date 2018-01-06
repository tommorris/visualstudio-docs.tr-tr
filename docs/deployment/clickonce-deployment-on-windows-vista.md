---
title: "Windows Vista'da ClickOnce dağıtımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 49ea73293e8cc491b515644a7e7d3f226a799339
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="clickonce-deployment-on-windows-vista"></a>Windows Vista'da ClickOnce Dağıtımı
Visual Studio'da uygulamaları oluşturma kodlanmış ikili olarak XML verileri uygulamanın yürütülebilir dosyası içinde Windows Vista kullanıcı hesabı denetimi (UAC) normalde gömülü bir bildirim üretir. ClickOnce ve Kayıtsız COM uygulamaları harici bildirim gerektirdiğinden, Visual Studio projeleri gömülü bir bildirim yerine UAC verileri içeren bu tür için bir dosya oluşturur. Varsayılan olarak, Visual Studio, bilgileri dış UAC bildirim bilgileri (ClickOnce ve Kayıtsız COM dağıtımı) oluşturmak veya uygulamanın yürütülebilir dosyasına (tüm diğer durumlarda) katıştırmak için app.manifest adlı dosyadan kullanır. Visual Studio bildirim oluşturmak üzere aşağıdaki seçenekleri sağlar:  
  
-   Gömülü bir bildirim kullanın. UAC veri uygulamanın yürütülebilir dosyasına katıştırma ve normal kullanıcı olarak çalıştırın.  
  
     Bu, (ClickOnce kullanmadığınız sürece) varsayılan ayardır. Bu ayar, Visual Studio faaliyet normal şekilde Windows Vista'da destekleyecek; diğer bir deyişle, her iki kullanarak bir iç ve dış bildirimi nesil `AsInvoker`.  
  
-   Harici bildirim kullanın. Harici bildirim app.manifest kullanarak oluşturun.  
  
     Bu, yalnızca harici bildirim app.manifest bilgileri kullanarak oluşturur. ClickOnce veya Kayıtsız COM kullanarak bir uygulama yayımladığınızda, Visual Studio app.manifest'i projeye ekler ve bu seçeneği ekler.  
  
-   Hiçbir bildirim kullanın. Bildirim olmadan uygulama oluşturun.  
  
     Bu yaklaşım da denir *sanallaştırma*. Visual Studio'nun önceki sürümlerindeki mevcut uygulamalarla uyumluluk için bu seçeneği kullanın.  
  
 Yeni özellikler mevcuttur **uygulama** sayfası Proje Tasarımcısı (Visual C# projeleri yalnızca için) ve MSBuild proje dosyası biçiminde.  
  
 Visual Studio IDE'de UAC bildirim üretme yapılandırma yöntemi (Visual C# ve Visual Basic) proje türüne göre değişebileceğini unutmayın.  
  
 Visual C# projeleri için bildirim üretme yapılandırma hakkında daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md).  
  
 Visual Basic projeleri için bildirim üretme yapılandırma hakkında daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [Kullanıcı izinleri ve Visual Studio](http://msdn.microsoft.com/en-us/d5c55084-1e7b-4b61-b478-137db01c0fc0)   
 [Uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Uygulama Sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)