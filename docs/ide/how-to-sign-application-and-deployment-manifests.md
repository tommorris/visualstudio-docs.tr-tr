---
title: 'Nasıl yapılır: uygulama ve dağıtım bildirimlerini imzalama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
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
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a883995f95c5eaab86a14f07f9372614078d3c79
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-sign-application-and-deployment-manifests"></a>Nasıl Yapılır: Uygulama ve Dağıtım Bildirimlerini İmzalama
ClickOnce dağıtımı kullanarak bir uygulama yayımlamak isterseniz, uygulama ve dağıtım bildirimlerini ortak/özel anahtar çifti ile oturum açmanız gerekir ve Authenticode teknolojisi kullanılarak imzalanmış. Windows sertifika deposunda veya bir anahtar dosyası bir sertifika kullanarak bildirimleri imzalayabilirsiniz.  
  
 ClickOnce dağıtımı hakkında daha fazla bilgi için bkz: [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md).  
  
 ClickOnce bildirimleri imzalama .exe tabanlı uygulamalar için isteğe bağlıdır. Daha fazla bilgi için bu belgenin "Oluşturma imzasız bildirimler" bölümüne bakın.  
  
 Anahtar dosyaları oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir genel-özel anahtar çifti oluşturma](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair).  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .pfx uzantılıdır yalnızca kişisel bilgi değişimi (PFX) anahtar dosyaları destekler. Geçerli kullanıcının Windows sertifika deposundan tıklayarak diğer tür sertifikaların ancak seçebilirsiniz **deposundan seçmek** üzerinde **imzalama** Proje Özellikleri'nin sayfa.  
  
### <a name="to-sign-application-and-deployment-manifests-using-a-certificate"></a>Uygulama ve dağıtım imzalamak için bir sertifika kullanılarak bildirimleri  
  
1.  Proje Özellikleri penceresine gidin (proje düğümüne sağ tıklayın **Çözüm Gezgini** seçip **özellikleri**, veya türü **proje özellikleri** içinde**Hızlı başlatma** penceresinde, veya alt + ENTER içinde basın **Çözüm Gezgini** penceresi). Üzerinde **imzalama** sekmesine **ClickOnce bildirimlerini imzalayacak** onay kutusu.  
  
2.  Tıklatın **deposundan seçmek** düğmesi.  
  
     **Bir sertifika seçin** iletişim kutusu belirir ve Windows sertifika deposunda içeriğini görüntüler.  
  
    > [!TIP]
    >  Tıklatırsanız **sertifika özelliklerini görüntülemek için burayı tıklatın**, **sertifika ayrıntıları** iletişim kutusu görüntülenir. Bu iletişim kutusunu sertifika ile ilgili ayrıntılı bilgiler içerir ve ek seçenekleri içerir. Tıklayabilirsiniz **sertifikaları** Ek Yardım bilgilerini görüntülemek için.  
  
3.  Bildirimlerini imzalamak için kullanmak istediğiniz sertifikayı seçin.  
  
4.  Ayrıca, bir zaman damgası sunucusunun adresi belirtebilirsiniz **zaman damgası sunucu URL'si** metin kutusu. Bu bildirim imzalandığında belirten bir zaman damgası sağlayan bir sunucudur.  
  
### <a name="to-sign-application-and-deployment-manifests-using-an-existing-key-file"></a>Varolan anahtar dosyasını kullanarak uygulama ve dağıtım imzalamak için bildirimler  
  
1.  Üzerinde **imzalama** sayfasında, **ClickOnce bildirimlerini imzalayacak** onay kutusu.  
  
2.  Tıklatın **dosyasından seçin** düğmesi.  
  
     **Dosya Seç** iletişim kutusu görüntülenir.  
  
3.  İçinde **Dosya Seç iletişim** kutusunda, kullanın ve ardından istediğiniz anahtar dosyası (.pfx) konumuna göz atın **açık**.  
  
    > [!NOTE]
    >  Bu seçenek yalnızca .pfx uzantısı olan dosyaları destekler. Bir anahtar dosyası veya başka bir biçim, Windows sertifika deposunda depola ve sertifikayı seçin sertifika varsa önceki yordamda açıklanmıştır. Seçilen sertifikanın amacı, kod imzalama içermesi gerekir.  
  
     **Dosyayı açmak için parola gir** iletişim kutusu görüntülenir. (.Pfx dosyası, Windows sertifika deposunda zaten depolanmış veya değil parola korumalı, bir parola girmeniz istenmez.)  
  
4.  Anahtar dosyası erişim için parola girin ve ENTER tuşuna basın.  
  
### <a name="to-sign-application-and-deployment-manifests-using-a-test-certificate"></a>Uygulama ve dağıtım imzalamak için bir test sertifikası kullanarak bildirimleri  
  
1.  Üzerinde **imzalama** sayfasında, **ClickOnce bildirimlerini imzalayacak** onay kutusu.  
  
2.  Test için yeni bir sertifika oluşturmak için tıklatın **Test sertifikası oluşturma** düğmesi.  
  
3.  İçinde **Test sertifikası oluşturma** iletişim kutusunda, test sertifikanızı güvenli hale getirmek için bir parola girin.  
  
## <a name="generating-unsigned-manifests"></a>İmzalanmamış bildirimler oluşturma  
 ClickOnce bildirimleri imzalama .exe tabanlı uygulamalar için isteğe bağlıdır. Aşağıdaki yordamlar imzasız ClickOnce bildirimleri oluşturmak nasıl gösterir.  
  
> [!IMPORTANT]
>  İmzasız bildirimleri geliştirme ve uygulamanızın veya sınama basitleştirebilirsiniz. Ancak, bir üretim ortamında önemli güvenlik riskleri imzalanmamış bildirimler tanıtmaktadır. Yalnızca Internet veya diğer kaynakları, kötü amaçlı kod tamamen yalıtılmış bir intranet içerisinde bilgisayarlarda ClickOnce uygulamanızı çalıştırıyorsa, imzalanmamış bildirimler kullanmayı düşünün.  
  
 Bir veya daha fazla üretilen karma değerden özellikle çıkarılmamışsa sürece varsayılan olarak, ClickOnce imzalanmış bildirimler otomatik olarak oluşturur. Diğer bir deyişle, tüm dosyaları karmasında bulunan uygulama sonuçları imzalı bildirimleri yayımlarken, bile **ClickOnce bildirimlerini imzalayacak** onay kutusu işaretli.  
  
#### <a name="to-generate-unsigned-manifests-and-include-all-files-in-the-generated-hash"></a>İmzasız bildirimleri oluşturmak ve oluşturulan karma tüm dosyaları eklemek için  
  
1.  Karma tüm dosyaları dahil etme imzalanmamış bildirimler oluşturmak için önce imzalanmış bildirimler birlikte uygulama yayımlamanız gerekir. Bu nedenle, ClickOnce bildirimlerini önceki yordamlardan birini tarafından ilk kez oturum ve ardından uygulamayı yayımlayın.  
  
2.  Üzerinde **imzalama** sayfasında, Temizle **ClickOnce bildirimlerini imzalayacak** onay kutusu.  
  
3.  Bu yalnızca bir sürümü, uygulamanızın kullanılabilir olacak şekilde Yayımla sürümü sıfırlayın. Varsayılan olarak, Visual Studio otomatik olarak uygulama yayımlama Yayımla sürümü her zaman değişiklik sayısını artırır. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce yayımla sürümünü ayarlama](../deployment/how-to-set-the-clickonce-publish-version.md).  
  
4.  Uygulamayı yayımlayın.  
  
#### <a name="to-generate-unsigned-manifests-and-exclude-one-or-more-files-from-the-generated-hash"></a>İmzasız bildirimleri oluşturmak ve bir veya daha fazla üretilen karma değerden dışlamak için  
  
1.  Üzerinde **imzalama** sayfasında, Temizle **ClickOnce bildirimlerini imzalayacak** onay kutusu.  
  
2.  Açık **uygulama dosyalarını** iletişim kutusu ve kümesi **karma** için **hariç** oluşturulan karma değerden hariç tutmak istediğiniz dosyaları için.  
  
    > [!NOTE]
    >  Bir dosya karma değerden hariç önce önceki yordamda gösterildiği gibi ile imzalanmış bildirimler yayımlamanız gerekmez şekilde otomatik bildirimleri imzalama devre dışı bırakmak için ClickOnce yapılandırır.  
  
3.  Uygulamayı yayımlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanımlayıcı adlı derlemeler](/dotnet/framework/app-domains/strong-named-assemblies)   
 [Nasıl yapılır: bir genel-özel anahtar çifti oluşturma](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair)   
 [İmzalama sayfası, Proje Tasarımcısı](../ide/reference/signing-page-project-designer.md)   
 [ClickOnce Güvenliği ve Dağıtımı](../deployment/clickonce-security-and-deployment.md)