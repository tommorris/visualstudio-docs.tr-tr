---
title: "Hata: Hedef bilgisayardaki Visual Studio uzaktan hata ayıklayıcı hizmeti geriye bu bilgisayara bağlanamıyor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.service_access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f4553bceb8757b49c6d21f4bbe85e47f90e5b4dc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>Hata: Hedef bilgisayardaki Visual Studio Uzaktan Hata Ayıklayıcı hizmeti geriye bu bilgisayara bağlanamıyor
Bu hata, Visual Studio uzaktan hata ayıklayıcı hizmeti hata ayıklama yaptığınız bilgisayara bağlanmaya çalıştığında, kimlik doğrulaması yapamayan bir kullanıcı hesabı altında çalıştığı anlamına gelir.  
  
 Hesapları erişebilmeniz için aşağıdaki tabloda gösterilmektedir bilgisayarı:  
  
|||||  
|-|-|-|-|  
||LocalSystem hesabı|Etki alanı hesabı|Aynı kullanıcı adı ve parola iki bilgisayarda olan yerel hesaplar|  
|Her iki bilgisayar aynı etki alanında|Evet|Evet|Evet|  
|Her iki bilgisayar arasında iki yönlü güvene sahip etki alanları|Hayır|Hayır|Evet|  
|Bir çalışma grubunda bir veya iki bilgisayar|Hayır|Hayır|Evet|  
|Bilgisayarlar farklı etki alanları|Hayır|Hayır|Evet|  
  
 Bunlara ek olarak:  
  
-   Böylece herhangi bir işlem hata ayıklama Visual Studio uzaktan hata ayıklayıcı hizmetin altında çalışacağı hesabın uzak bilgisayarda yönetici olması gerekir.  
  
-   Hesabın verilebilmesi de sahip `Log on as a service` ayrıcalık kullanan uzak bilgisayarda **yerel güvenlik ilkesi** yönetim aracı.  
  
-   Bir yerel hesap erişim bilgisayarı kullanıyorsanız, Visual Studio uzaktan hata ayıklayıcı hizmeti yerel bir hesap altında çalıştırılmalıdır.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Visual Studio uzaktan hata ayıklayıcı hizmeti uzak bilgisayarda doğru ayarlandığından emin olun. Daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
2.  Uzaktan hata ayıklayıcı hizmeti hata ayıklayıcı ana bilgisayarın erişebileceği bir hesap altında önceki tabloda gösterildiği gibi çalıştırın.  
  
### <a name="to-add-log-on-as-a-service-privilege"></a>"Hizmet olarak oturum aç" Ayrıcalık eklemek için  
  
1.  Üzerinde **Başlat** menüsünde seçin **Denetim Masası**.  
  
2.  Denetim Masası'nda seçin **Klasik Görünüm**gerekirse,.  
  
3.  **Yönetim Araçları**'na çift tıklayın.  
  
4.  Yönetimsel Araçlar penceresinde çift **yerel güvenlik ilkesi**.  
  
5.  İçinde **yerel güvenlik ayarları** penceresinde genişletin **yerel ilkeler** klasör.  
  
6.  Tıklatın **kullanıcı hakları ataması**.  
  
7.  İçinde **İlkesi** sütun, çift tıklatın **hizmet oturum açma** geçerli yerel Grup ilke atamalarını görüntülemek için **bir hizmet olarak oturum açın** iletişim kutusu.  
  
8.  Yeni kullanıcılar eklemek için tıklatın **kullanıcı veya Grup Ekle** düğmesi.  
  
9. Kullanıcı ekleme işlemini tamamladığınızda, tıklatın **Tamam**.  
  
### <a name="to-work-around-this-error"></a>Bu hata olarak çözmek için  
  
-   Bir hizmeti yerine bir uygulama olarak uzaktan hata ayıklama İzleyicisi'ni çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)