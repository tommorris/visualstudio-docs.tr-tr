---
title: Visual Studio aboneleri için kimlikleri
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: VSTS ve Azure için kullanmak üzere Visual Studio aboneliğiniz için alternatif bir kimlik ekleme
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: vs subscription
ms.openlocfilehash: 70d11f83584d776fef9dae7e771bcdeb40a3c477
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326312"
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio aboneleri için kimlikleri

Visual Studio aboneliğiniz etkinleştirdiğinizde, kimlik (veya oturum açma) biz bağlantı Visual Studio abonelik ile etkinleştirme sırasında kullanılan. Bu şekilde, biz üzerinde tanıyabilirsiniz [Visual Studio abone portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs), Visual Studio Team Services (VSTS) içinde ve Azure.

VSTS, biz her zaman oturum açtığınızda Visual Studio abonelik durumunuzu denetleyin ve otomatik olarak bir üye olduğu her hesap özeliklerin verin.
Bu özellikler abone avantaj olarak dahil olduğu için Visual Studio aboneliğinize bağlı bir kimlik kullanırken herhangi bir VSTS hesabı üye olarak eklemek ücretsizdir.

Etkinleştirme sırasında Azure içinde Biz Visual Studio abonelik durumunuzu denetleyin, [aylık Azure kredisini](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) diğer bir deyişle abone avantajı.

İçinde [Visual Studio abone portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs), eklemek mümkün olabilir bir **alternatif kimlik** --etkinleştirme sırasında kullanılan kimliği yanı sıra. Bugün, biz aboneliğinizi etkinleştirmek için bir Microsoft hesabı kullandıysanız alternatif kimlik eklemenize izin verir. Bu şekilde bir iş de ekleyebilirsiniz veya (Visual Studio, Office 365 veya şirket veya Okul ağınızın oturum açarken kullandığınız) okulunuzda hesabını VSTS hem kişisel hesabınızı hem de iş veya Okul hesabınızı kullanarak erişmenize olanak izin verme.

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>Visual Studio aboneliğiniz başka bir hesaba ekleme

Visual Studio aboneliğiniz başka bir hesaba ekleme abonelik avantajları, Visual Studio Team Services (VSTS) ve Azure gibi abonelik için atanan daha farklı bir kimliğe sahip erişmenize olanak tanır. Geçmişte, bu işlev yalnızca bir Microsoft hesabı (MSA) için Visual Studio (VS) aboneliğinizi atanmışsa kullanılabilir. Biz bu işlev Azure Active Directory'de (Azure AD) iş veya Okul hesapları için genişletilmiş.

Bu abonelik diğer hesabına bir kopyasını sağlamaz; yalnızca iki avantajları alternatif hesabıyla erişim olanağı da sağlar.

Bu hesabı bir oturum açma (VS IDE VSTS ve Azure) gerektiren Avantajlarınızı ile kullanabilmeniz için tüm abonelikler için bir "iş veya Okul hesabı" ekleyebilirsiniz.


### <a name="add-the-alternate-account"></a>Alternatif hesabı Ekle


1. Visual Studio abone Portalı Microsoft hesabınızla oturum açın (https://my.visualstudio.com).

2. Git **abonelikleri**.


   ![Alternatif hesap add - VS Aboneliklerde gidin](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. Seçin **alternatif Hesap Ekle**.

   ![Seçin alternatif hesabı Ekle ](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. İş veya Okul hesabı ekleyin.

   ![İş veya Okul hesabı Ekle](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. Visual Studio Team Services (https://{youraccount}.visualstudio.com) oturum açmak için iş veya Okul hesabınızı kullanın.

   ![İş veya Okul hesabınızı kullanın](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

Alternatif hesabınız alternatif Hesapla (IDE, VSTS ve Azure) oturum açmak ihtiyaç duyduğunuz abonelik avantajlarından faydalanmak her iki kimlikleri izin vererek Visual Studio abonelik eklenir.

## <a name="faq"></a>SSS

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>S: neden VSTS bana bir Visual Studio abone olarak tanımıyor?

A: birincil veya alternatif kimlik bilgilerinizi kullanarak oturum açtığınızda VSTS aboneliğinizi otomatik olarak tanıması gerekir. Değilse, birkaç deneyebilirsiniz:

* Etkin bir Visual Studio aboneliğiniz olup olmadığını denetleyin, [bir avantajı olarak VSTS içeren](vs-vsts.md).

* Herhangi bir oturum açma/kimliği, Visual Studio aboneliğiniz için birincil veya alternatif kimlik kullanıyorsanız onaylayın.

* Ziyaret [Visual Studio abone portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs) en az bir kez oturum açtığınızda VSTS önce.

VSTS aboneliğiniz hala tanımazsa [desteğe başvurun](https://visualstudio.microsoft.com/team-services/support/)
