---
title: 'Nasıl yapılır: uygulama ve dağıtım bildirimlerini imzalama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- manifests [Visual Studio]
- code signing [Visual Studio], Authenticode
- deployment manifests [Visual Studio]
- signing manifests [Visual Studio]
- application manifests [Visual Studio]
- ClickOnce deployment [Visual Studio], signing assemblies
- key files [Visual Studio]
- assemblies [Visual Studio], signing
ms.assetid: 64173505-8bfb-41cf-a0de-b9075173f3a2
caps.latest.revision: 61
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ed26d1dec6251ef856ab9cad6b74bba2a4190b81
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691877"
---
# <a name="how-to-sign-application-and-deployment-manifests"></a>Nasıl Yapılır: Uygulama ve Dağıtım Bildirimlerini İmzalama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: oturum uygulama ve dağıtım bildirimlerini](https://docs.microsoft.com/visualstudio/ide/how-to-sign-application-and-deployment-manifests).  
  
Bir uygulamayı ClickOnce dağıtımını kullanarak yayınlamak istiyorsanız uygulama ve dağıtım bildirimlerinin ortak/özel anahtar çifti ile imzalanmış olması gerekir ve Authenticode teknolojisi kullanılarak. Windows sertifika deposu veya bir anahtar dosyasından bir sertifika kullanarak bildirimleri imzalayabilirsiniz.  
  
 ClickOnce dağıtımı hakkında daha fazla bilgi için bkz. [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md).  
  
 ClickOnce bildirimlerini imzalanması, .exe tabanlı uygulamalar için isteğe bağlıdır. Daha fazla bilgi için bu belgedeki "İmzalanmamış bildirimler üretme" bölümüne bakın.  
  
 Anahtar dosyaları oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir genel-özel anahtar çifti oluşturma](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114).  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] .pfx uzantılı yalnızca kişisel bilgi değişimi (PFX) anahtar dosyalarını destekler. Ancak, farklı türde Sertifikalar Geçerli kullanıcının Windows sertifika deposundan tıklayarak seçebileceğiniz **Store ' seçin** üzerinde **imzalama** proje özellikleri.  
  
### <a name="to-sign-application-and-deployment-manifests-using-a-certificate"></a>Uygulama ve dağıtım bildirimlerini imzalamak için bir sertifika kullanıyor  
  
1.  Proje Özellikleri penceresine gidin ('nde proje düğümüne sağ **Çözüm Gezgini** seçip **özellikleri**, veya tür **proje özellikleri** içinde**Hızlı başlatma** penceresinde ya da alt + ENTER tuşlarına basın **Çözüm Gezgini** pencere). Üzerinde **imzalama** sekmesinde **ClickOnce bildirimlerini imzala** onay kutusu.  
  
2.  Tıklayın **Store ' seçin** düğmesi.  
  
     **Bir sertifika seçin** iletişim kutusu görünür ve Windows sertifika deposunun içeriğini görüntüler.  
  
    > [!TIP]
    >  Tıklarsanız **sertifika özelliklerini görüntülemek için burayı tıklatın**, **sertifika ayrıntıları** iletişim kutusu görüntülenir. Bu iletişim kutusu sertifika ile ilgili ayrıntılı bilgiler içerir ve ek seçenekler içerir. Tıklayabilirsiniz **sertifikaları** Ek Yardım bilgilerini görüntülemek için.  
  
3.  Bildirimleri imzalamak için kullanmak istediğiniz sertifikayı seçin.  
  
4.  Ayrıca, bir zaman damgası sunucusunun adresini belirleyebilirsiniz **zaman damgası sunucu URL'si** metin kutusu. Bu, bildirimin imzalandığı zamanı belirten bir zaman damgası sağlayan bir sunucudur.  
  
### <a name="to-sign-application-and-deployment-manifests-using-an-existing-key-file"></a>Uygulama ve dağıtım bildirimlerini imzalamak için mevcut bir anahtar dosyasını kullanarak  
  
1.  Üzerinde **imzalama** sayfasında **ClickOnce bildirimlerini imzala** onay kutusu.  
  
2.  Tıklayın **dosyadan Seç** düğmesi.  
  
     **Dosya Seç** iletişim kutusu görüntülenir.  
  
3.  İçinde **Dosya Seç iletişim** kutusunda, kullanmak ve ardından istediğiniz anahtar dosyanın (.pfx) konumuna göz atın **açık**.  
  
    > [!NOTE]
    >  Bu seçenek yalnızca .pfx uzantılı dosyaları destekler. Bir anahtar dosyası veya başka bir biçim, Windows sertifika deposuna kaydedin ve sertifikayı seçin sertifika varsa önceki yordamda açıklanmıştır. Seçilen sertifikanın amacı kod imzalamayı içermelidir.  
  
     **Dosyasını açmak için parola gir** iletişim kutusu görüntülenir. (.Pfx dosyası zaten Windows sertifika deponuza depolanır ve parola korumalı ise, bir parola girmeniz istenmez.)  
  
4.  Anahtar dosyaya erişmek için parolayı girin ve ENTER tuşuna basın.  
  
### <a name="to-sign-application-and-deployment-manifests-using-a-test-certificate"></a>Uygulama ve dağıtım bildirimlerini imzalamak için bir test sertifikası kullanarak  
  
1.  Üzerinde **imzalama** sayfasında **ClickOnce bildirimlerini imzala** onay kutusu.  
  
2.  Test için yeni bir sertifika oluşturmak için tıklayın **Test sertifikası Oluştur** düğmesi.  
  
3.  İçinde **Test sertifikası Oluştur** iletişim kutusunda, test sertifikanızın güvenliğinin sağlanmasına yardımcı olmak için bir parola girin.  
  
## <a name="generating-unsigned-manifests"></a>İmzalanmamış bildirimler oluşturma  
 ClickOnce bildirimlerini imzalanması, .exe tabanlı uygulamalar için isteğe bağlıdır. Aşağıdaki yordamlar imzasız ClickOnce bildirimlerinin nasıl oluşturulacağını gösterir.  
  
> [!IMPORTANT]
>  İmzalanmamış bildirimler, geliştirme ve test uygulamanızın basitleştirebilir. Ancak, imzalanmamış bildirimler üretim ortamında önemli güvenlik riskleri tanıtır. Yalnızca ClickOnce uygulamanız Internet veya diğer kötü amaçlı kod kaynaklarından tamamen yalıtılmış bir intranet bilgisayarda çalışıyorsa imzalanmamış bildirimleri kullanmayı düşünün.  
  
 Varsayılan olarak, üretilen karmada bir veya daha fazla dosya özellikle hariç tutulmadığı sürece ClickOnce otomatik olarak imzalı bildirimler üretir. Diğer bir deyişle, tüm dosyalar karmaya uygulama sonuçları imzalı Bildirimlerde yayımlarken, bile **ClickOnce bildirimlerini imzala** onay kutusu işaretli değilse.  
  
#### <a name="to-generate-unsigned-manifests-and-include-all-files-in-the-generated-hash"></a>İmzalanmamış bildirimler oluşturmak ve tüm dosyaları oluşturulan karmaya dahil etmek için  
  
1.  Tüm dosyalar karmaya dahil etmek imzalanmamış bildirimler oluşturmak için öncelikle uygulamayı imzalanmış bildirimlerle birlikte yayınlamanız gerekir. Bu nedenle, ilk önceki yordamlardan birini izleyerek ClickOnce bildirimlerini imzala ve ardından uygulamayı yayınlayın.  
  
2.  Üzerinde **imzalama** sayfasında, NET **ClickOnce bildirimlerini imzala** onay kutusu.  
  
3.  Yayınlama sürümünü, uygulamanızın yalnızca bir sürümü kalacak şekilde sıfırlayın. Varsayılan olarak, Visual Studio otomatik olarak uygulama yayımlama Yayımla sürümü her zaman değişiklik sayısını artırır. Daha fazla bilgi için [nasıl yapılır: ClickOnce yayımla sürümünü ayarlama](../deployment/how-to-set-the-clickonce-publish-version.md).  
  
4.  Uygulamayı yayınlayın.  
  
#### <a name="to-generate-unsigned-manifests-and-exclude-one-or-more-files-from-the-generated-hash"></a>İmzalanmamış bildirimler oluşturmak ve bir veya daha fazla dosya ve oluşturulan karmadan hariç tutmak için  
  
1.  Üzerinde **imzalama** sayfasında, NET **ClickOnce bildirimlerini imzala** onay kutusu.  
  
2.  Açık **uygulama dosyaları** iletişim kutusu ve kümesi **karma** için **hariç** ve oluşturulan karmadan hariç tutmak istediğiniz dosyaları için.  
  
    > [!NOTE]
    >  Bir dosyayı karma oluşturmadan hariç, böylece önceki yordamda gösterildiği imzalı bildirimleri önce yayınlamanız gerekmez bildirimler, otomatik imzalama devre dışı bırakmak üzere ClickOnce yapılandırır.  
  
3.  Uygulamayı yayınlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanımlayıcı adlı derlemeler](http://msdn.microsoft.com/library/d4a80263-f3e0-4d81-9b61-f0cbeae3797b)   
 [Nasıl yapılır: genel-özel anahtar çifti oluşturma](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)   
 [İmzalama sayfası, Proje Tasarımcısı](../ide/reference/signing-page-project-designer.md)   
 [ClickOnce Güvenliği ve Dağıtımı](../deployment/clickonce-security-and-deployment.md)



