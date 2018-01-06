---
title: "Hata: Çalışma grubu uzak oturum açma hatası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.workgroup_remote_logon_failure
dev_langs:
- CSharp
- VB
- FSharp
- JScript
- C++
helpviewer_keywords:
- logon failure, remote debugging
- remote debugging, logon failure
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 38ec2de37279e1f383751c9652aeeac74473c50f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-workgroup-remote-logon-failure"></a>Hata: Çalışma Grubu Uzak Oturum Açma Başarısız
Bu hata görünür:  
  
 Oturum açma hatası: Bilinmeyen kullanıcı adı veya hatalı parola  
  
 **Nedeni**  
  
 Bu hata, bir çalışma grubunda bir makineden hata ayıklama ve uzak bilgisayara bağlanmaya oluşabilir. Olası nedenler şunlardır:  
  
-   Eşleşen adı ve parolayla hesabı uzak makinede yoktur.  
  
-   Visual Studio bilgisayarı ve uzak makine üzerinde çalışma gruplarındaki varsa, bu hata nedeniyle varsayılan oluşabilir **yerel güvenlik ilkesi** uzak makinede ayarlama. İçin varsayılan ayar **yerel güvenlik ilkesi** ayar **yalnızca konuk - yerel kullanıcılar konuk olarak kimlik doğrulaması**. Bu kurulumu temel hata ayıklamak için uzak makineye ayarda değiştirme **Klasik - yerel kullanıcıların kimliğini kendileri olarak**.  
  
> [!NOTE]
>  Şu görevleri gerçekleştirmek için yönetici olmanız gerekir.  
  
### <a name="to-open-the-local-security-policy-window"></a>Yerel Güvenlik İlkesi penceresini açmak için  
  
1.  Başlat **secpol.msc** Microsoft Yönetim Konsolu ek bileşenini. Secpol.msc Windows arama, Windows çalıştıran kutusu veya bir komut isteminde yazın.  
  
### <a name="to-add-user-rights-assignments"></a>Kullanıcı hakları ataması eklemek için  
  
1.  Açık **yerel güvenlik ilkesi** penceresi.  
  
2.  Genişletme **yerel ilkeler** klasör.  
  
3.  Tıklatın **kullanıcı hakları ataması**.  
  
4.  İçinde **İlkesi** sütun, çift **programları hata ayıklama** geçerli yerel Grup ilke atamalarını görüntülemek için **yerel güvenlik ilkesi ayarını** iletişim kutusu.  
  
     ![Yerel Güvenlik İlkesi kullanıcı hakları](../debugger/media/dbg_err_localsecuritypolicy_userrightsdebugprograms.png "DBG_ERR_LocalSecurityPolicy_UserRightsDebugPrograms")  
  
5.  Yeni kullanıcılar eklemek için tıklatın **kullanıcı veya Grup Ekle** düğmesi.  
  
### <a name="to-change-the-sharing-and-security-model"></a>Paylaşım ve güvenlik modeli değiştirmek için  
  
1.  Açık **yerel güvenlik ilkesi** penceresi.  
  
2.  Genişletme **yerel ilkeler** klasör.  
  
3.  Tıklatın **güvenlik seçenekleri**.  
  
4.  İçinde **İlkesi** sütun, çift **ağ erişimi: Yerel hesaplar için paylaşım ve güvenlik modeli**.  
  
5.  İçinde **ağ erişimi: Yerel hesaplar için paylaşım ve güvenlik modeli** iletişim kutusunda, değerini değiştirin **Klasik - yerel kullanıcıların kimliğini kendileri olarak** tıklatıp **Uygula**düğmesi.  
  
     ![Yerel Güvenlik İlkesi güvenlik seçenekleri](../debugger/media/dbg_err_localsecuritypolicy_securityoptions_networkaccess.png "DBG_ERR_LocalSecurityPolicy_SecurityOptions_NetworkAccess")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)