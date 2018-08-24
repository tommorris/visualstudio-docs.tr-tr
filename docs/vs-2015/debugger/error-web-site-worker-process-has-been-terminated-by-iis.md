---
title: 'Hata: Web sitesi çalışan işlemi IIS tarafından sonlandırıldı. | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.web_server_process_terminated
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 5707b972-71a6-4cc6-ab99-c7c00ca8628c
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 81396165841b0c23a317a857e73d7adbf88971dc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686433"
---
# <a name="error-web-site-worker-process-has-been-terminated-by-iis"></a>Hata: Web sitesi çalışan işlemi IIS tarafından sonlandırıldı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: Web sitesi çalışan işlemi IIS tarafından sonlandırıldı](https://docs.microsoft.com/visualstudio/debugger/error-web-site-worker-process-has-been-terminated-by-iis).  
  
Hata ayıklayıcı Web sitesinde kod yürütme durduruldu. Bu, çalışan işlemi yanıt durmuş varsaymak Internet Information Services (IIS) neden oldu. Bu nedenle, IIS çalışan işlemi sonlandırıldı.  
  
 Hatalarını ayıklamaya devam etmek için IIS çalışan işleminin devam izin verecek şekilde yapılandırmanız gerekir. Bu hata iletisi, IIS 7'den önceki IIS sürümleriyle görünmüyor.  
  
### <a name="to-configure-iis-7-to-allow-the-worker-process-to-continue"></a>IIS 7, devam etmek çalışan işlemi izin verecek şekilde yapılandırmak için  
  
1.  Açık **Yönetimsel Araçlar** penceresi.  
  
    1.  Tıklayın **Başlat**ve ardından **Denetim Masası**.  
  
    2.  İçinde **Denetim Masası**, seçin **Klasik görünümüne geç**, gerekirse ve çift tıklatarak **Yönetimsel Araçlar**.  
  
2.  İçinde **Yönetimsel Araçlar** penceresinde çift **Internet Information Services (IIS) Yöneticisi'ni**.  
  
     IIS Yöneticisi'ni açar.  
  
3.  İçinde **bağlantıları** bölmesini genişletin \<bilgisayar adı > gerekirse düğümü.  
  
4.  Altında \<bilgisayar adı > düğümünü tıklatın **uygulama havuzları**.  
  
5.  İçinde **uygulama havuzları** listesinde, uygulamanızın çalıştığı havuzun adına sağ tıklayın ve ardından **Gelişmiş ayarlar**.  
  
6.  İçinde **Gelişmiş ayarlar** iletişim kutusunda, bulun **işlem modeli** bölümünde ve aşağıdaki eylemlerden birini gerçekleştirin:  
  
    -   Ayarlama **Ping etkin** için **False**.  
  
    -   Ayarlama **Ping en yüksek yanıt süresi** 90 saniyeden büyük olan bir değer.  
  
     Ayarı **Ping etkin** için **False** IIS çalışan işlemi hala çalışıyor ve siz, hataları ayıklanan işlem kadar çalışan işlemi etkin tutar denetlemesini durdurur. Ayarı **Ping en yüksek yanıt süresi** IIS çalışan işlemi izlemeye devam etmek için büyük bir değer sağlar.  
  
7.  Tıklayın **Tamam** kapatmak için **Gelişmiş ayarlar** iletişim kutusu.  
  
8.  IIS Yöneticisi'ni kapatın ve **Yönetimsel Araçlar** penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)


