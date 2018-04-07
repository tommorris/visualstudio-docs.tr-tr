---
title: Kişisel e-postalar VLSC görüntülenen
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/23/2018
ms.topic: Get-Started-Article
description: Visual Studio abonelikleri – neden Hotmail veya Gmail adresleri My aboneleri için görüyorum?
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: cfe035d82976e3df683f4e3a35bd9d7f3c8cf9e2
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Visual Studio abonelikleri – neden Hotmail veya Gmail adresleri my aboneleri için görüyorum? 

Şirketler Toplu Lisanslama hizmeti Merkezi (VLSC) gelen yeni Visual Studio geçirirken [abonelikleri Yönetim Portalı](https://manage.visualstudio.com), Yöneticiler, "oturum açma e-posta adresi" bazı aboneleri için bulmak Şaşkın gösterir, Hotmail, Gmail veya Yahoo gibi e-posta adresi bir 3. taraf.

## <a name="cause"></a>Sebep

Bu senaryo, eski msDN abonesi deneyimi ile ilişkili oturum açma işlemleri nedeniyle oluşur. Kullanıcıların, değişiklik olmadan yeni portalı VLSC'de geçirildi. Bazı yöneticiler, kullanıcılar kişisel hesaplar abonelik faydaları erişmek için kullanmış farkında olabilir. 2016'tamamlandı, Visual Studio abone geçişler önce Visual Studio Abonelik başarıyla kullanmak için gereken iki eylem vardı:
1. Yönetici "abonelik atanan işlerini kullanarak bir tek tek abone" ya da Okul e-posta adresi.
2. Abone "aboneliği etkinleştirildi".

Abone etkinleştirme işlemi sırasında: oturum açmak için bir Microsoft hesabı (msA) gerektiriyordu. Abone iş veya Okul hesabı yapmaya çalışırsanız eşleşmedi (örneğin John@contoso.com) MSA, bir yeni MSA oluşturma veya mevcut bir yararlanın. Bu ","atanan için e-posta adresinden"farklı olan kullanıcıların oturum açma e-posta adresi" ile sonuçlandı.

> [!NOTE] 
> Yeni abone deneyimi [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs) iş/Okul ve Microsoft Account (msA) kimlik türlerini destekler.

Son olarak, yönetici geçiş VLSC adresi ile ilgili abonenin"oturum açma e-posta yeni abone yönetim deneyimi doldurmak için" dan veri sürüyor olduğundan, bu daha önce gözden kaçan kişisel hesapları nedeniyle yakın zamanda geçirilmiş admins görebilirsiniz Bu bilgiler daha görünür hale getirmek değişiklikler kullanıcı arabirimine.

## <a name="solution"></a>Çözüm

Sorunu düzeltmek için oturum açma e-posta adreslerini güncelleştirmek için abone bilgilerini düzenlemek gerekir.  Düzenlemeler, tek tek aboneleri için ya da toplu yapılabilir. Tam bilgi için lütfen ziyaret [bir abonelik](/visualstudio/subscriptions/edit-license).  

Subscriber(s) e-posta adresleri güncelleştirdikten sonra kullanıcıların oturum açma bilgileri değişti bildirmek isteyebilirsiniz.  