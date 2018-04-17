---
title: 'Hata: İşlem incelemek için izniniz yok&#39;s kimlik | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f62f612d4b07e0799c318ae972220459e0700e3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Hata: İşlem incelemek için izniniz yok&#39;s kimliği
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