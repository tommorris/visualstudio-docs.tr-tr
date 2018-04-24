---
title: Yalnızca hata ayıklama, zaman içinde iletişim kutusu seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Debugger.JIT
- vs.debug.options.JIT
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Just-In-Time debugging, setting options
- Options dialog box, debugging
ms.assetid: 7f11b2e3-3fb5-449d-b07c-6ecf1d6a487d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7be7dacbe7b3b89b8bdc09515c23d7597e7e55e5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="just-in-time-debugging-options-dialog-box"></a>Tam Zamanında, Hata Ayıklama, Seçenekler İletişim Kutusu
Erişim için **zaman içinde sadece** sayfasında, Git **Araçları** menüsüne ve ardından **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **hata ayıklama** düğümü ve select **zaman içinde sadece**. Bu sayfa, sadece zaman yönetilen kod, yerel kod ve komut dosyası hata ayıklamayı etkinleştirmek sağlar. Daha fazla bilgi için bkz: [Just-In-Time hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Sadece zaman bu programı türleri için hata ayıklamayı etkinleştirebilirsiniz:  
  
-   Yönetilen  
  
-   Yerel  
  
-   Komut Dosyası  
  
 Tam zamanında hata ayıklama olduğu dışından başlatılan bir program hata ayıklama için bir yöntem [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Oluşturulan bir program çalışabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dışında [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ortamı. Sadece zamanında hata ayıklama etkinleştirilirse, bir kilitlenme hata ayıklama isteyip istemediğinizi soran bir iletişim kutusu görüntüler.  
  
## <a name="associated-warnings"></a>İlişkili uyarıları  
 Bu sayfa, ziyaret ettiğinizde **seçenekleri** iletişim kutusu, böyle bir uyarı iletisi görebilirsiniz:  
  
 **Başka bir hata ayıklayıcı kendisini sadece zaman kayıtlı olan hata ayıklayıcı. Onarmak için hemen hata ayıklama veya Visual Studio onarım çalıştırma zamanında etkinleştirin.**  
  
 Başka bir hata ayıklayıcı, büyük olasılıkla daha eski bir sürümü varsa, bu ileti oluşur [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı sadece zaman ayarlamak, hata ayıklayıcı.  
  
 Görebileceğiniz başka bir ileti şu şekildedir:  
  
 **Tam zamanında hata ayıklama kaydı hata algılandı. Onarmak için hemen hata ayıklama veya Visual Studio onarım çalıştırma zamanında etkinleştirin.**  
  
 Bu uyarılar birini zaman sadece ile hata ayıklama görürseniz, [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] sorunun giderilmiş kadar yönetici ayrıcalıkları gerekiyor. Hemen etkinleştirmeye çalışırsanız-yönetici olmayan bu koşullar altında aşağıdaki hata iletisini görürsünüz:  
  
 **Erişim reddedildi. Bir yönetici etkinleştir sadece zamanında hata ayıklama sahip veya Visual Studio yüklemesini onarın.**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama, Seçenekler iletişim kutusu](../debugger/debugging-options-dialog-box.md)   
 [Nasıl yapılır: hata ayıklayıcı ayarları belirtin](../debugger/how-to-specify-debugger-settings.md)