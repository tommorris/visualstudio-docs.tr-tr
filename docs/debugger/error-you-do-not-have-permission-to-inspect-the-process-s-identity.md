---
title: "Hata: İşlem &#39; incelemek için izniniz yok s kimlik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f51087d4f7882c34826942a898328640107a5ac6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Hata: İşlem &#39; incelemek için izniniz yok s kimliği
İşlem kimliğini İnceleme iznine sahip değil. Bu, sisteminizin yapılandırması nedeniyle olabilir.  
  
 Hata ayıklayıcısı hata ayıklama için gerekli bilgileri işlem kimliğini İnceleme mümkün değildi. Terminal Hizmetleri devre dışı bırakılıyor en olası nedeni. Terminal Hizmetleri hizmeti varsayılan olarak etkindir. Yeniden etkinleştirmek için aşağıdaki adımları izleyin.  
  
### <a name="to-enable-terminal-services"></a>Terminal Hizmetleri'ni etkinleştirmek için  
  
1.  Tıklatın **Başlat** ve ardından **Denetim Masası**.  
  
2.  Denetim Masası'nda seçin **Klasik Görünüm'e geçiş**gerekirse, çift tıklayın ve ardından **Yönetimsel Araçlar**.  
  
3.  İçinde **Yönetimsel Araçlar** penceresinde çift **Bilgisayar Yönetimi**.  
  
4.  Bilgisayar Yönetimi penceresinde **hizmetler ve uygulamalar** düğümü.  
  
5.  Altında **hizmetler ve uygulamalar**, tıklatın **Hizmetleri**.  
  
     Hizmetler listesi sağ bölmede görüntülenir.  
  
6.  İçinde **Hizmetleri** listesinde, sağ **Terminal Hizmetleri** ve ardından **özellikleri**.  
  
7.  İçinde **Terminal Hizmetleri özellikleri** penceresinde, Git **genel** sekmesinde ve ayarlama **başlangıç türü** için **el ile**.  
  
8.  **Tamam**'ı tıklatın.  
  
9. Bilgisayarı yeniden başlatın.  
  
     Bu yordam, Uzak Masaüstü otomatik olarak etkinleştirmez. Uzak Masaüstü bilgisayarınızda etkinleştirmek istiyorsanız, aşağıdaki ek yordamı gerçekleştirin.  
  
### <a name="to-enable-remote-desktop"></a>Uzak Masaüstü'nü etkinleştirmek için  
  
1.  Tıklatın **Başlat** ve ardından sağ **Bilgisayarım**.  
  
2.  Seçin **özellikleri**.  
  
     **Sistem Özellikleri** penceresi görüntülenir.  
  
3.  Tıklatın **uzak**.  
  
4.  Altında **Uzak Masaüstü**seçin **kullanıcıların bu bilgisayara uzaktan bağlanmasına izin vermek**.  
  
5.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)