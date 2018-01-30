---
title: "Kişisel e-postalar VLSC görüntülenen"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/23/2018
Ms.topic: Get-Started-Article
Description: "Visual Studio Subscriptions – Why Am I Seeing Hotmail or Gmail Addresses for My Subscribers?"
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 2bfe2f39d432be5fc6ff7b24be2a218d02fce961
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Visual Studio abonelikleri – neden Hotmail veya Gmail adresleri My aboneleri için görüyorum? 

Şirketler Toplu Lisanslama hizmeti Merkezi (VLSC) gelen yeni Visual Studio geçirirken [abonelikleri Yönetim Portalı](https://manage.visualstudio.com), Yöneticiler, "oturum açma e-posta adresi" bazı aboneleri için bulmak Şaşkın gösterir, Hotmail, Gmail veya Yahoo gibi e-posta adresi bir 3. taraf.

## <a name="cause"></a>Sebep

Bu senaryo, eski MSDN abonesi deneyimiyle ilişkili oturum açma işlemleri nedeniyle oluşur. Kullanıcıların, değişiklik olmadan yeni portalı VLSC'de geçirildi. Bazı yöneticiler, kullanıcılar kişisel hesaplar abonelik faydaları erişmek için kullanmış farkında olabilir. 2016'tamamlandı, Visual Studio abone geçişler önce Visual Studio Abonelik başarıyla kullanmak için gereken iki eylem vardı:
1. Yönetici "abonelik atanan işlerini kullanarak bir tek tek abone" ya da Okul e-posta adresi.
2. Abone "aboneliği etkinleştirildi".

Abone etkinleştirme işlemi sırasında:
1. Oturum açmak için bir Microsoft hesabı (MSA) gereklidir.
2. Abone iş veya Okul hesabı yapmaya çalışırsanız eşleşmedi (örneğin John@contoso.com) MSA, bir yeni MSA oluşturma veya mevcut bir yararlanın.
3. Bu ","atanan için e-posta adresinden"farklı olan kullanıcıların oturum açma e-posta adresi" ile sonuçlandı.

> [!NOTE] 
> Yeni abone deneyimi [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) iş/Okul ve Microsoft hesabı (MSA) kimlik türlerini destekler.

Son olarak, yönetici geçiş VLSC adresi ile ilgili abonenin"oturum açma e-posta yeni abone yönetim deneyimi doldurmak için" dan veri sürüyor olduğundan, bu daha önce gözden kaçan kişisel hesapları nedeniyle yakın zamanda geçirilmiş admins görebilirsiniz Bu bilgiler daha görünür hale getirmek değişiklikler kullanıcı arabirimine.

## <a name="solution"></a>Çözüm

Sorunu düzeltmek için oturum açma e-posta adreslerini güncelleştirmek için abone bilgilerini düzenlemek gerekir.  Düzenlemeler, tek tek aboneleri için ya da toplu yapılabilir. Tam bilgi için lütfen ziyaret [bir abonelik](/visualstudio/subscriptions/edit-license).  

Subscriber(s) e-posta adresleri güncelleştirdikten sonra kullanıcıların oturum açma bilgileri değişti bildirmek isteyebilirsiniz.  