---
title: Visual Studio aboneleri için kimlikleri
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 3/15/2018
Ms.topic: Get-Started-Article
Description: How to add an alternate identity for your Visual Studio subscription, to use for VSTS and Azure.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 70bfd305ec35b562fb722fb853016c3df4240ff8
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio aboneleri için kimlikleri

Visual Studio aboneliğiniz etkinleştirdiğinizde, kimlik (veya oturum açma) biz bağlantı Visual Studio abonelik ile etkinleştirme sırasında kullanılan. Bu şekilde, biz üzerinde tanıyabilirsiniz [Visual Studio abone portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs), VSTS ve azure'da.

VSTS, biz her zaman oturum açtığınızda Visual Studio abonelik durumunuzu denetleyin ve otomatik olarak bir üye olduğu her hesap özeliklerin verin. Bu özellikler abone avantaj olarak dahil olduğu için Visual Studio aboneliğinize bağlı bir kimlik kullanırken herhangi bir VSTS hesabı üye olarak eklemek ücretsizdir.

Etkinleştirme sırasında Azure içinde Biz Visual Studio abonelik durumunuzu denetleyin, [aylık Azure kredisini](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) diğer bir deyişle abone avantajı.

İçinde [Visual Studio abone portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs), eklemek mümkün olabilir bir **alternatif kimlik**--etkinleştirme sırasında kullanılan kimliği yanı sıra. Bugün sorundan aboneliğinizi etkinleştirmek için bir Microsoft hesabı kullandıysanız alternatif kimlik eklemenize izin verir. Bu şekilde bir iş de ekleyebilirsiniz veya (Visual Studio, Office 365 veya şirket veya Okul ağınızın oturum açarken kullandığınız) okulunuzda hesabını VSTS hem kişisel hesabınızı hem de iş veya Okul hesabınızı kullanarak erişmenize olanak izin verme.

## <a name="how-to-add-an-alternate-identity-to-your-visual-studio-subscription"></a>Visual Studio aboneliğiniz için bir alternatif kimlik ekleme

1. Oturum [Visual Studio abone portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs).

  > "Kişisel hesabı" veya "iş veya Okul hesabı", "kişisel hesap" Seç seçmek için sorulursa (Microsoft hesabınızı).
  >
  > Bazen Microsoft hesabınız ve iş veya Okul hesabınızla aynı e-posta adresi paylaştığından seçmeniz gerekir. Her iki kimlikleri aynı e-posta adresi kullansa da, bunlar farklı profiller, güvenlik ayarları ve izinleri hala ayrı kimliklerle demektir.
  >
  > 30 Mart 2018 başlangıç, artık Azure Active Directory'de yönetilen bir etki alanı kullanan bir e-posta kullanarak bir Microsoft hesabı oluşturmak mümkün olmayacaktır. Yine de bu e-posta bir iş hesabını kullanarak oturum açabilirsiniz.

2. Git **abonelikleri** sekmesi.

  ![Abonelik seçin](_img/vs-alternate-identity/choose-subscriptions-my-visual-studio-com-portal.png)

3. Altında **ilgili bağlantılar**gidin **alternatif Hesap Ekle**.

  ![İlgili bağlantılar altında alternatif hesabı eklemek için Git](_img/vs-alternate-identity/add-alternate-account-my-visual-studio-com-portal.png)

4. İş veya Okul hesabınızı girin ve seçin **Ekle**.

  ![İş veya Okul hesabınızı girin](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. VSTS hesabınızda oturum açmak için iş veya Okul hesabınızı kullanın (```https://{youraccount}.visualstudio.com```). Yay, bu nedenle yeniden 15 dakikadan daha sonra denetleyin bilgi için kısa bir gecikme olabilir. 

## <a name="faq"></a>SSS

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>S: neden VSTS bana bir Visual Studio abone olarak tanımıyor?
A: birincil veya alternatif kimlik bilgilerinizi kullanarak oturum açtığınızda VSTS aboneliğinizi otomatik olarak tanıması gerekir. Değilse, birkaç deneyebilirsiniz:

* Etkin bir Visual Studio aboneliğiniz olup olmadığını denetleyin, [bir avantajı olarak VSTS içeren](vs-vsts.md).

* Herhangi bir oturum açma/kimliği, Visual Studio aboneliğiniz için birincil veya alternatif kimlik kullanıyorsanız onaylayın.

* Ziyaret [Visual Studio abone portalı](https://my.visualstudio.com?wt.mc_id=o~msft~docs) en az bir kez oturum açtığınızda VSTS önce.

VSTS aboneliğiniz hala tanımazsa [desteğe başvurun](https://www.visualstudio.com/team-services/support/)

