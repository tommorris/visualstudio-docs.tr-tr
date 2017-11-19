---
title: "Bir UWP veya Windows 8.1 uygulamasını yenileme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- JavaScript debugging, refreshing pages [UWP apps]
- debugging, refreshing pages [UWP apps]
- DOM Explorer, Refresh [UWP apps]
- Refresh [UWP apps]
ms.assetid: fd99ee60-fa94-46df-8b17-369f60bfd908
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c5f5592893452c3fdf7f535758f09d7877030c03
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="refresh-a-uwp-or-windows-81-app"></a>Bir UWP veya Windows 8.1 uygulama Yenile
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Hatalarını ayıkladığınız ve seçerek JavaScript kullanarak bir UWP uygulaması yenileme sırasında kodunuzu değişiklik yapabilirsiniz **yenileme Windows uygulaması** düğmesini **hata ayıklama** araç. Bu düğmesini seçerek uygulama hata ayıklayıcı durdurup olmadan yeniden yükler. Yenileme özelliği HTML, CSS ve JavaScript kodu değiştirin ve hızlı bir şekilde sonucunu görmenizi sağlar. Bu özellik, UWP ve Windows 8.1 uygulamaları için desteklenir.  
  
 Yenileme değil, uygulama durumunu korumak veya uygulamanız için aşağıdaki değişiklikleri yansıtacak:  
  
-   Paket bildiriminde belirtilen görüntülerine değişiklikler dahil, paket bildirim dosyasının değişiklikleri.  
  
-   Başvuru ekleme veya bir SDK başvurusu kaldırılması gibi değişiklikler veya Windows çalışma zamanı bileşenleri (.winmd dosyaları) değiştirir.  
  
-   Kaynak dizeleri .resjson dosyalarında değişiklikler gibi değiştirir.  
  
-   Proje dosyası yolu adı değişiklikleri, yeni proje dosyalarını veya silinen dosyaların sonucunda ortaya çıkan değiştirir.  
  
-   Proje ve öğe özelliği gibi değişiklikler seçilen hata ayıklama cihazdaki değişiklikler veya paket eylemi (Özellikler penceresinde) bir dosya için yapılan değişiklikler.  
  
> [!IMPORTANT]
>  Başvuruları değiştirme, paket bildirimi değiştirin ya da önceki listesinde belirtilen diğer değişiklik durdurun ve HTML, CSS ve JavaScript kaynak dosyalarını güncelleştirmek için hata ayıklayıcı yeniden sahip.  
  
### <a name="to-refresh-an-app"></a>Bir uygulama yenilemek için  
  
1.  Visual Studio'da gezinti uygulaması proje şablonunu kullanarak yeni bir proje oluşturun.  
  
     Bu, UWP uygulaması veya Windows 8.1 uygulama olabilir.  
  
2.  Şablon Visual Studio'da açıkken, hata ayıklama hedefi seçin.  
  
     Bir Windows Phone projesini geçerli başlangıç projenize ise, hata ayıklama hedefi için bir Windows Phone öykünücüsü seçin. Aksi takdirde seçin **Simulator** veya **yerel makine**.  
  
     ![Select hata ayıklama hedef listesi](../debugger/media/js_select_target.png "JS_Select_Target")  
  
3.  Uygulamayı hata ayıklama modunda çalıştırmak için F5 tuşuna basın.  
  
4.  Visual Studio'ya geçin. (F12 tuşuna basın.)  
  
5.  İçinde **Çözüm Gezgini**, **sayfaları** > **ev** klasörü, açık home.html.  
  
6.  Sayfa başlık metni değiştirme  
  
    ```html  
    Welcome to yourAppName!  
    ```  
  
     için aşağıdaki gibi başka bir:  
  
    ```html  
    Hello!  
    ```  
  
7.  Tıklatın **yenileme Windows uygulaması** düğmesi, bu gibi görünen: ![yenileme Windows Uygulama düğmesi](../debugger/media/js_refresh.png "JS_Refresh"). (Veya F4 tuşuna basın.)  
  
8.  Uygulamasına geçin. Uygulama yeniden başlatma hata ayıklayıcı olmadan yüklenir ve yeni sayfa başlığı görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlı Başlangıç: HTML ve CSS hata ayıklama](../debugger/quickstart-debug-html-and-css.md)