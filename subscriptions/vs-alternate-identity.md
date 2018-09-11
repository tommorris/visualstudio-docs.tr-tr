---
title: Visual Studio aboneleri için kimlikleri
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: Azure DevOps Services ve Azure için kullanılacak Visual Studio aboneliğiniz için alternatif bir kimlik ekleme
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: vs subscription
ms.openlocfilehash: 15b364cc8375d4e0e64b20ad7e8a6b19ba4140f5
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283567"
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio aboneleri için kimlikleri

Visual Studio aboneliğinizi etkinleştirme, kimlik (veya oturum açma) ki bağlantı, Visual Studio aboneliği ile etkinleştirme sırasında kullanılır. Bu şekilde, biz, üzerinde tanıyabilmesi [Visual Studio abonelik portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs), Azure DevOps hizmetlerinde ve azure'da.

Azure DevOps Hizmetleri'nde, biz oturum her zaman Visual Studio abonelik durumunuzu denetleyin ve otomatik olarak bir üye olduğu her hesap içinde özelliklerini verin.
Bu özellikler bir aboneliği avantajı olarak dahil olduğu için Visual Studio aboneliğinize bağlı bir kimlik kullanarak herhangi bir Azure DevOps hizmetleri hesabı üye olarak eklemek ücretsizdir.

Etkinleştirme sırasında Azure'da, size Visual Studio abonelik durumunuzu denetleyin, [aylık Azure kredisi](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) diğer bir deyişle bir abone Avantajlarınızı.

İçinde [Visual Studio abonelik portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs), eklemeniz mümkün olabilir bir **alternatif kimlik** --etkinleştirme sırasında kullanılan kimlik yanı sıra. Bugün, biz aboneliğinizi etkinleştirmek için bir Microsoft hesabı kullanıyorsanız alternatif bir kimlik eklemenizi sağlar. Bu şekilde bir iş de ekleyebilirsiniz ya da (Visual Studio, Office 365 veya şirket veya Okul ağınızın açarken kullandığınız) Okul hesabı, Azure DevOps kişisel hesabınız hem iş veya Okul hesabınızı kullanarak hizmetlere erişmek etmenize imkan sağlar.

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>Visual Studio aboneliğinize alternatif hesap ekleme

Visual Studio aboneliğinize alternatif hesap ekleme, abonelik avantajları, Azure DevOps Services ve Azure gibi abonelik için atanan daha farklı bir kimlik ile erişmenize olanak sağlar. Geçmişte, bu işlevi yalnızca bir Microsoft hesabı (MSA) için Visual Studio (VS) aboneliğiniz atanmışsa kullanılabilir. Biz bu işlev, Azure Active Directory'de (Azure AD), iş veya Okul hesapları için genişletilmiş sahiptir.

Bu işlem diğer hesap aboneliğine bir kopyasını sağlamaz; yalnızca iki avantajı ile alternatif hesap erişim olanağı da sağlar.

Tüm abonelikler için bir oturum açma (VS IDE, Azure DevOps Hizmetleri ve Azure) gerektiren avantajlarınızla bu hesabı kullanabilmeniz için bir "iş veya Okul hesabı" ekleyebilirsiniz.


### <a name="add-the-alternate-account"></a>Alternatif hesap ekleme


1. Microsoft hesabınızla Visual Studio abonelik portalında oturum açın (https://my.visualstudio.com).

2. Git **abonelikleri**.

    > [!div class="mx-imgBorder"]
    > ![Alternatif hesap ekleme - vs'de aboneliklere Git](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. Seçin **alternatif hesap ekleme**.
    > [!div class="mx-imgBorder"]
    > ![Seçin alternatif hesap ekleme ](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. İş veya Okul hesabınızı ekleyin.
    > [!div class="mx-imgBorder"]
    > ![İş veya Okul hesabı Ekle](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. Azure DevOps Hizmetleri'ne (https://{youraccount}.visualstudio.com) oturum açmak için iş veya Okul hesabınızı kullanın.
    > [!div class="mx-imgBorder"]
    > ![İş veya Okul hesabınızı kullanın](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

Alternatif hesabınızın alternatif (IDE, Azure DevOps Hizmetleri ve Azure) hesabıyla oturum açmak ihtiyacınız olan abonelik avantajlarını kullanmak her iki kimlikleri izin vererek, Visual Studio aboneliği eklenir.

## <a name="faq"></a>SSS

### <a name="q--why-doesnt-azure-devops-services-recognize-me-as-a-visual-studio-subscriber"></a>S: neden Azure DevOps Hizmetleri bana bir Visual Studio abonesi olarak tanımaz?

Y: birincil veya alternatif kimlik bilgilerinizi kullanarak oturum açtığınızda azure DevOps hizmetleriyle aboneliğinizi otomatik olarak tanıması gerekir. Aksi durumda, birkaç şey deneyebilirsiniz:

* Etkin bir Visual Studio aboneliğine sahip olduğunuzdan emin olun, [Azure DevOps Hizmetleri avantaj](vs-azure-devops.md).

* Geçerli bir oturum açma/kimlik, Visual Studio aboneliğiniz için birincil veya alternatif kimlik kullandığınızı onaylayın.

* Ziyaret [Visual Studio abonelik portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs) , Azure DevOps Hizmetleri için oturum açma önce en az bir kez.

Azure DevOps Hizmetleri, aboneliğinizin hala tanımazsa [Destek ekibiyle iletişime geçin](https://visualstudio.microsoft.com/team-services/support/)
