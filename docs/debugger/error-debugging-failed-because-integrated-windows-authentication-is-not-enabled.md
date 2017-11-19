---
title: "Hata: Tümleşik Windows kimlik doğrulaması etkinleştirilmediğinden hata ayıklama başarısız oldu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.webdbg_ntlm_authn_not_enabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
- aspx
helpviewer_keywords: debugger, Web application errors
ms.assetid: 6027cd94-74cf-470f-b7ce-6f6b68bc56ba
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 88747922ae486adf65d2babe7a349e9538e8c9c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="error-debugging-failed-because-integrated-windows-authentication-is-not-enabled"></a>Hata: Tümleşik Windows Kimlik Doğrulaması Etkinleştirilmediğinden Hata Ayıklama Başarısız
Hata ayıklama isteyen kullanıcı kimlik doğrulaması, kimlik doğrulama hatası tarafından engellendi. Bir Web uygulaması veya XML Web Hizmetleri içinde adım çalıştığınızda oluşabilir. Bu hatanın bir nedeni, tümleşik Windows kimlik doğrulamasının etkinleştirilmemiş oluşturur. Etkinleştirmek için "Tümleşik Windows kimlik doğrulamasını etkinleştirmek için." adımları izleyin.  
  
 Tümleşik Windows kimlik doğrulaması etkinleştirildi ve bu hata görünmeye devam eder, bu hata nedeniyle kaynaklanır mümkündür **Windows etki alanı sunucuları için Özet kimlik doğrulaması** etkinleştirilir. Bu durumda, ağ yöneticinize başvurmanız gerekir.  
  
### <a name="to-enable-integrated-windows-authentication"></a>Tümleşik Windows kimlik doğrulamasını etkinleştirmek için  
  
1.  Web sunucusuna bir yönetici hesabı kullanarak oturum açın.  
  
2.  Tıklatın **Başlat** ve ardından **Denetim Masası**.  
  
3.  İçinde **Denetim Masası**, çift **Yönetimsel Araçlar**.  
  
4.  Çift **Internet Information Services**.  
  
5.  Web sunucusu düğümüne tıklayın.  
  
     A **Web siteleri** klasörü altında sunucu adı açılır.  
  
6.  Kimlik doğrulama veya tek tek Web sitelerinin tüm Web siteleri için yapılandırabilirsiniz. Tüm Web siteleri için kimlik doğrulamasını yapılandırmak için sağ **Web siteleri** klasörünü ve ardından **özellikleri**. Tek bir Web sitesi kimlik doğrulamasını yapılandırmak için açık **Web siteleri** klasörü, tek tek Web sitesini sağ tıklatın ve ardından **özellikleri**.  
  
     **Özellikleri** iletişim kutusu görüntülenir.  
  
7.  Tıklatın **dizin güvenliği** sekmesi.  
  
8.  İçinde **anonim erişim ve kimlik doğrulama denetimi** 'yi tıklatın **Düzenle**.  
  
     **Kimlik doğrulama yöntemleri** iletişim kutusu görüntülenir.  
  
9. Altında **kimlik doğrulamalı erişim**seçin **tümleşik Windows kimlik doğrulaması**.  
  
10. Tıklatın **Tamam** kapatmak için **kimlik doğrulama yöntemleri** iletişim kutusu.  
  
11. Tıklatın **Tamam** kapatmak için **özellikleri** iletişim kutusu.  
  
12. Kapat **Internet Information Services** penceresi.  
  
### <a name="to-enable-integrated-windows-authentication-in-windows-vistaiis-7"></a>Windows Vista/IIS 7'de tümleşik Windows kimlik doğrulamasını etkinleştirmek için  
  
1.  Web sunucusuna bir yönetici hesabı kullanarak oturum açın.  
  
2.  Windows kimlik doğrulaması ve II6 Yönetim uyumluluğu, daha önce bu, aşağıdaki adımları izleyerek yapmadıysanız Aç:  
  
    1.  Tıklatın **Başlat**, tıklatın **Denetim Masası** ve ardından **programlar**.  
  
    2.  Altında **programlar ve Özellikler**, tıklatın **kapatma Windows özelliklerini aç veya Kapat**.  
  
         Kullanıcı erişim denetimi iletişim kutusu belirir ve devam etmek izin ister.  
  
    3.  
              **Devam**'a tıklayın.  
  
         Windows özellikleri iletişim kutusu görüntülenir.  
  
    4.  Özellik listesinde genişletin **Internet Information Services** düğümü.  
  
    5.  Altında **Internet Information Services**, genişletin **World Wide Web Hizmetleri** düğümü.  
  
    6.  Altında **World Wide Web Hizmetleri**, tıklatın **güvenlik**.  
  
    7.  Tıklatın **Windows kimlik doğrulaması**.  
  
    8.  Altında **Internet Information Services**, genişletin **Web yönetimi araçları** düğümü.  
  
    9. Altında **Web yönetimi araçları**, genişletin **IIS 6 Yönetim uyumluluğu** düğümü ve select **IIS 6 metatabanı ve IIS 6 yapılandırma uyumluluğu** onay kutusu.  
  
    10. Altında **Web yönetimi araçları**seçin **IIS Yönetim Konsolu** tıklatıp **Tamam.**  
  
    11. Bu değişikliklerin devreye girmesi bilgisayarı yeniden başlatın.  
  
3.  Tıklatın **Başlat** ve ardından **Denetim Masası**.  
  
4.  Tıklatın **Klasik Görünüm**, çift tıklayın ve ardından **Yönetimsel Araçlar**.  
  
5.  İçinde **adı** sütun ve çift **Internet Information Services (IIS) Yöneticisi'ni**.  
  
6.  İçinde **bağlantıları** sütunu, sunucu düğümünü genişletin.  
  
     A **Web siteleri** klasörü altında sunucu adı açılır.  
  
7.  Genişletme **Web siteleri** düğümü ve tümleşik Windows kimlik doğrulamasını etkinleştirmek istediğiniz Web sitesini tıklatın.  
  
8.  Orta bölmede başlığı seçtiğiniz Web sitesi adını değiştirir. Bu bölmede altında **IIS** başlığı çift **kimlik doğrulama**.  
  
     Bölmenin başlık değişiklikler **kimlik doğrulama**.  
  
9. İçinde **kimlik doğrulaması** bölmesi, **adı** sütun, sağ **Windows kimlik doğrulaması** ve ardından **etkinleştirmek**.  
  
10. Kapat **Internet Information Services (IIS) Yöneticisi** penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web uygulamalarında hata ayıklama: Hatalar ve sorun giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)   
 [Microsoft Özet kimlik doğrulaması](http://go.microsoft.com/fwlink/?LinkId=77938)   
 [Windows Vista ile IIS 7.0 Web uygulamalarını ve Visual Studio çalıştırma](http://msdn.microsoft.com/Library/262a82ac-dd0e-4096-86c6-fb463e88be66)