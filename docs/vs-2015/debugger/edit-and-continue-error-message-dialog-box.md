---
title: Düzenle ve devam et hata iletisi iletişim kutusu | Microsoft Docs
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
- vs.debug.ENC.SupportedButNotAvaiable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d649df9584fc06ee08b7a7d1e846597c12519019
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675006"
---
# <a name="edit-and-continue-error-message-dialog-box"></a>Düzenle ve Devam Et Hata İletisi İletişim Kutusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Düzenle ve devam et hata iletisi iletişim kutusu](https://docs.microsoft.com/visualstudio/debugger/edit-and-continue-error-message-dialog-box).  
  
Düzenle ve devam et, destekleyen bir dilde hata ayıklaması yapıyorsanız, bu iletişim kutusu görüntülenir ancak **Düzenle ve devam et** yapmış olduğunuz değişiklikleri kod türü için kullanılabilir değil. Hata iletisi kutu içinde daha ayrıntılı bir açıklama sağlar. Bu iletişim kutusunu dahil görmek için olası nedenler:  
  
-   Yönetilemeyen hata ayıklama etkinleştirildiğinde, yönetilen kod düzenleme denedi. Düzenle ve devam et seçenekleri çalışmaz karışık mod hata ayıklama ile.  
  
-   SQL Server kod düzenleme denedi.  
  
-   Kod bir Dr hata ayıklarken Düzenle denedi. Watson dökümü.  
  
-   İşlenmeyen bir özel durum oluştuktan sonra kod ve seçeneği düzenlemeye çalıştığınız "**işlenmemiş özel durumlarda çağrı yığınını geriye doğru izleme**" seçilmedi.  
  
-   Kod katıştırılmış çalışma zamanı uygulamanın hata ayıklarken Düzenle denedi.  
  
-   Başlangıç yerine ekli bir program kodunda düzenlemeye çalıştığınız **hata ayıklama** menüsü.  
  
-   En iyi duruma getirilmiş kod düzenleme denedi.  
  
-   Yönetilen kodu 64 bitlik bir uygulama hedeflendiğinde Düzenle denedi. İsterseniz kullanım Düzenle ve devam et, hedef x86 için ayarlamanız gerekir. (*Proje* **özellikleri**, **derleme** sekmesinde **Gelişmiş derleyici** ayarı.).  
  
-   Hata ayıklama sırasında değiştirildi ve yeniden yüklendi bütünleştirilmiş kodu düzenleme denedi.  
  
-   Yüklenmemiş olan bütünleştirilmiş kodu düzenleme denedi.  
  
-   (Yeni sürümü derleme hataları olduğundan) eski bir sürümünü, uygulamanızın hata ayıklama başlangıç.  
  
-   Bunu çalışırken kod düzenleme denedi.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **TAMAM**  
 İletişim kutusundan çıkmak ve hemen önceki düzenleme denemesi iptal edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Desteklenen Kod Değişiklikleri (C++)](../debugger/supported-code-changes-cpp.md)



