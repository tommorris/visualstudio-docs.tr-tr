---
title: Dağıtmak için ClickOnce uygulamaları başkalarının oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- preserved branding information
- useManifestForTrust element
- customer deployments [ClickOnce]
- multiple ClickOnce deployment and branding
- ClickOnce applications, previous .NET Framework versions
- application manifests [ClickOnce]
- <useManifestForTrust> element
- manifests [ClickOnce]
- trust applications, ClickOnce
- ClickOnce applications, deployed by others
- ClickOnce applications, previous .NET Framework
ms.assetid: d20766c7-4ef3-45ab-8aa0-3f15b61eccaa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cd6808ac38a67146e53438e5b8f6dc0e07fd0bc5
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34065084"
---
# <a name="creating-clickonce-applications-for-others-to-deploy"></a>Başkalarının Dağıtması için ClickOnce Uygulamaları Oluşturma
Uygulamaları dağıtmak ClickOnce Dağıtımları oluşturmakta olduğunuz tüm geliştiriciler planlayın. Bunların çoğu, yalnızca ClickOnce kullanarak kendi uygulama paketini ve ardından dosyaları kapalı büyük bir kuruluşa gibi bir müşteriye el. Müşteri, bir alt ağı üzerinde uygulamayı barındırmak için sorumlu olur. Bu konuda bazı sürümlerinde .NET Framework sürüm 3.5 önce bu tür dağıtımlarda devralınmış sorunları ele alınmıştır. Ardından, .NET Framework 3. 5'yeni "bildirimi güven için kullan" özelliğini kullanarak tarafından sağlanan yeni bir çözüm açıklanır. Son olarak, .NET Framework'ün daha eski sürümleri hala kullanan müşteriler için ClickOnce dağıtımları oluşturmak için önerilen stratejileri ile sonlanır.  
  
## <a name="issues-involved-in-creating-deployments-for-customers"></a>Müşteriler için dağıtımları oluşturmada ortaya çıkabilecek sorunları  
 Bir müşteri için bir dağıtım sağlamak planlama yaparken birkaç sorunla karşılaşabilirsiniz. İlk sorunu kod imzalama ile ilgilidir. Bir ağ üzerinden dağıtılması için ClickOnce dağıtımı uygulama bildirimini ve dağıtım bildirimi hem de bir dijital sertifika ile imzalanmalıdır. Bu Geliştirici sertifikası veya Müşteri'nin bildirimleri imzalarken kullanılıp kullanılmayacağını soru başlatır.  
  
 ClickOnce uygulamasının kimliği dağıtım bildiriminin dijital imza tabanlı olarak hangi sertifikanın kullanılacağını soru kritik. Geliştirici dağıtım bildirimi oturum açtığında, büyük bir şirket müşteri ise ve şirketin birden fazla bölme uygulama özelleştirilmiş bir sürümünü dağıtır çakışmalarına neden.  
  
 Örneğin, Adventure Works Finans departmanı ve İnsan Kaynakları departmanı olduğunu varsayalım. Her iki departman ClickOnce uygulaması bir SQL veritabanında depolanan verilerden raporlar oluşturan Microsoft Corporation lisans. Microsoft, her bölüm için verileri özelleştirilmiş uygulama sürümü sağlar. Uygulamalar aynı Authenticode sertifikası ile imzalanmış ClickOnce ilk aynı olacak şekilde ikinci uygulama Algıla gibi her iki uygulamayı kullanmayı dener ve bir kullanıcı bu bir hata karşılaşacağınız. Bu durumda, müşteri öngörülemeyen ve istenmeyen tarafı uygulaması tarafından yerel olarak depolanan herhangi bir veri kaybı içeren etkilerle karşılaşabilir.  
  
 Kod imzalama için ek sorunlarla ilgili `deploymentProvider` ClickOnce uygulama güncelleştirmelerini bulacağınız dağıtım bildiriminde öğesi. Bu öğe imzalamadan önce dağıtım bildirimine eklenmesi gerekiyor. Bu öğe daha sonra eklediyseniz, dağıtım bildirimi yeniden imzalanması gerekir.  
  
### <a name="requiring-the-customer-to-sign-the-deployment-manifest"></a>Uygulama bildirimini imzalamak müşteri gerektirme  
 Benzersiz olmayan dağıtımların bu sorun için bir çözüm uygulama bildirimi Geliştirici oturum olmalıdır ve müşteri dağıtım bildirimini imzalayın. Bu yaklaşım çalışırken, diğer sorunlar ortaya çıkar. Authenticode sertifikası korumalı bir varlık kalması gereken olduğundan, müşteri dağıtımı imzalamak için geliştirici yalnızca sertifika veremez. Müşteri dağıtım bildirimi kendilerini .NET Framework SDK ile birlikte ücretsiz olarak sağlanan araçları kullanarak oturum açabilirsiniz, ancak bu müşteri istekli veya sağlamak mümkün olandan daha fazla teknik bilgi gerektirebilir. Böyle durumlarda, geliştirici genellikle bir uygulama, Web sitesi ya da müşteri imzalama için uygulamanın kendi sürümünü gönderebilmek için başka bir mekanizma oluşturur.  
  
### <a name="the-impact-of-customer-signing-on-clickonce-application-security"></a>ClickOnce uygulama güvenliği üzerinde imzalama müşteri etkisi  
 Geliştirici ve müşteri müşteri uygulama bildirimi imzalamalısınız kabul olsa bile, özellikle güvenilir uygulama dağıtımına uygularken bu uygulamanın kimliğini çevreleyen diğer sorunlar başlatır. (Bu özellik hakkında daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).) Adventure Works kendilerine Microsoft Corporation tarafından sağlanan herhangi bir uygulama tam güven ile çalışır, istemci bilgisayarları yapılandırmak üzere istediğini varsayın. Adventure Works dağıtım bildirimi oturum açtığında, ClickOnce Uygulama güven düzeyini belirlemek için Adventure çalışması güvenlik imzasını kullanır.  
  
## <a name="creating-customer-deployments-by-using-application-manifest-for-trust"></a>Müşteri dağıtımları için güven uygulama bildirimi kullanarak oluşturma  
 .NET Framework 3. 5'te ClickOnce geliştiricilere ve müşterilere bildirimleri nasıl imzalanması gerektiğini senaryoyu için yeni bir çözüm sunan yeni bir özellik içerir. ClickOnce Uygulama bildirimi adlı yeni bir öğe destekleyen `<useManifestForTrust>` dijital imza uygulama bildiriminin ne güven kararları almak için kullanılması gereken olduğunu belirtmek bir geliştirici sağlar. Geliştirici ClickOnce paketleme araçları kullanır — Mage.exe, MageUI.exe ve Visual Studio gibi — bu öğe uygulama bildiriminde dahil olarak, yayımcı adını ve uygulamanın adını bildiriminde katıştırmak için.  
  
 Kullanırken `<useManifestForTrust>`, dağıtım bildirimi bir sertifika yetkilisi tarafından verilen bir Authenticode sertifikası ile imzalanmış gerekmez. Bunun yerine, kendinden imzalı bir sertifika bilinen ile imzalanabilir. Kendinden imzalı bir sertifika, standart .NET Framework SDK araçlarını kullanarak, müşteri veya geliştirici tarafından oluşturulan ve standart ClickOnce dağıtım araçlarını kullanarak dağıtım bildirimine sonra uygulanır. Daha fazla bilgi için bkz: [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx).  
  
 Kendinden imzalı bir sertifika için dağıtım bildirimini kullanarak birkaç avantaj sunar. Müşterinin elde etmek veya kendi Authenticode sertifikası oluşturma gereksinimini tarafından `<useManifestForTrust>` geliştiricinin uygulama üzerinde kendi marka kimliğini korumasına izin verirken, müşteri dağıtımı basitleştirir. Sonuç daha güvenli ve benzersiz uygulama kimliklerine sahip imzalanmış dağıtımlar kümesidir. Bu, aynı uygulamanın birden fazla müşteriye dağıtma oluşabilecek olası çakışmaları ortadan kaldırır.  
  
 ClickOnce dağıtımı ile oluşturma hakkında adım adım bilgiler için `<useManifestForTrust>` etkin, [izlenecek yol: ClickOnce uygulaması bu mu değil gerektiren Re-Signing'el ile dağıtma ve bu korur markalama bilgileri](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md).  
  
### <a name="how-application-manifest-for-trust-works-at-runtime"></a>Çalışma zamanında güven Works için nasıl uygulama bildirimi  
 Çalışma zamanında uygulama bildirimi için güven kullanarak nasıl çalıştığını daha iyi anlamak için aşağıdaki örneği göz önünde bulundurun. .NET Framework 3.5 hedefleyen bir ClickOnce uygulaması, Microsoft tarafından oluşturulur. Uygulama bildirimini kullanır `<useManifestForTrust>` öğesi ve Microsoft tarafından imzalanır. Adventure Works, kendinden imzalı bir sertifika kullanarak dağıtım bildirimi imzalar. Adventure Works istemciler Microsoft tarafından imzalanmış herhangi bir uygulamaya güvenmesi için yapılandırılır.  
  
 Kullanıcı dağıtım bildirimi bağlantısını tıklattığında ClickOnce Uygulama kullanıcının bilgisayara yükler. Sertifika ve dağıtım bilgileri istemci bilgisayarda ClickOnce uygulamaya benzersiz şekilde tanımlar. Kullanıcı aynı uygulamayı başka bir konumdan yeniden yüklemeye çalışırsa, ClickOnce Uygulama istemcide zaten belirlemek için bu kimlik kullanabilirsiniz.  
  
 Ardından, ClickOnce ClickOnce vereceği güven düzeyini belirler uygulama bildiriminizi imzalamak için kullanılan Authenticode sertifikası inceler. Adventure Works istemcilerine Microsoft tarafından imzalanmış herhangi bir uygulamaya güvenmesi için yapılandırılmış olduğundan, bu ClickOnce uygulamasına tam güven verilir. Daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
## <a name="creating-customer-deployments-for-earlier-versions"></a>Müşteri dağıtımları önceki sürümler için oluşturma  
 Bir geliştirici ClickOnce uygulamaları için .NET Framework'ün daha eski sürümlerini kullanan müşteriler ne dağıtıyor? Aşağıdaki bölümlerde avantajları ve dezavantajları birlikte çeşitli önerilen çözümler özetler.  
  
### <a name="sign-deployments-on-behalf-of-customer"></a>Müşteri adına dağıtımları imzalayın  
 Olası bir Dağıtım stratejisi müşterinin kendi özel anahtarını kullanarak, müşterilerin adına dağıtımları imzalamak için bir mekanizma oluşturmak geliştiricinin içindir. Bu, geliştirici özel anahtarları veya birden çok dağıtım paketlerini yönetin zorunluluğunu ortadan kaldırır. Geliştirici, her müşteri için yalnızca aynı dağıtılmasını sağlar. İmzalama hizmetini kullanarak kendi ortam için özelleştirmek üzere müşteri kadar olur.  
  
 Bu yöntemin bir dezavantajı, uygulamanız için gerekli gider ve saat ' dir. Bu tür bir hizmet, .NET Framework SDK'SINDA sağlanan araçları kullanarak oluşturulabilir olsa da, ürün yaşam döngüsü için daha fazla geliştirme zamanı ekleyeceksiniz.  
  
 Bu konuda daha önce belirtildiği gibi başka bir dezavantajı uygulamanın her müşterinin sürümü çakışmalarına neden aynı uygulama kimliği, olmasıdır. İlgili bir sorun varsa, geliştirici her uygulama benzersiz bir ad vermek için dağıtım bildirimi oluştururken kullanılan ad alanı değiştirebilirsiniz. Bu uygulamanın her sürümü için ayrı bir kimlik oluşturmak ve olası kimlik çakışmalarını ortadan kaldırmak. Bu alana karşılık gelen `-Name` Mage.exe ve için bağımsız değişken **adı** alanını **adı** MageUI.exe sekmesindedir.  
  
 Örneğin, geliştirici Application1 adlı bir uygulama oluşturdu söyleyin. Ad alanı Application1 olarak ayarlanmış tek bir dağıtım oluşturmak yerine, geliştirici Application1-CustomerA, Application1-CustomerB gibi bu ad, bir müşteriye özgü varyasyonunu ile birkaç dağıtımlar oluşturmayı ve benzeri.  
  
### <a name="deploy-using-a-setup-package"></a>Kurulum Paketi kullanarak dağıtın  
 İkinci olası Dağıtım stratejisi ClickOnce uygulaması ilk dağıtımını gerçekleştirmek için bir Microsoft Setup projesi oluşturmaktır. Bu birkaç farklı biçimlerinden birinde sağlanabilir: yürütülebilir bir kurulum olarak bir MSI dağıtım olarak (. EXE) veya toplu komut dosyası ile birlikte bir dolap (.cab) dosyası olarak.  
  
 Bu teknik kullanılarak, geliştirici müşteri uygulama dosyaları, uygulama bildirimi ve şablon olarak hizmet veren bir dağıtım bildirimi içeren dağıtımı sağlar. Müşteri bunları dağıtım için bir URL (sunucusu veya dosya paylaşımı konumu kullanıcıların ClickOnce uygulamasını yükleyecek), bir dijital sertifika yanı sıra belirtmeyi tercih Kurulum programını çalıştırmaları. Kurulum uygulaması güncelleştirme denetimi aralığını gibi ek ClickOnce yapılandırma seçenekleri için istemek de seçebilirsiniz. Bu bilgilerin toplandıktan sonra Kurulum programı, gerçek dağıtım bildirimi oluşturmak, imzalar ve belirlenen sunucu konumuna ClickOnce uygulaması yayımlama.  
  
 Müşteri bu durumda dağıtım bildirimi imzalayabilirsiniz üç yolu vardır:  
  
1.  Müşteri, bir sertifika yetkilisi (CA) tarafından verilen geçerli bir sertifika kullanabilirsiniz.  
  
2.  Bu yaklaşım, alternatif olarak, kendinden imzalı bir sertifika ile dağıtım bildirimini imzalamak müşteri seçebilirsiniz. Bu dezavantajı kullanıcı yüklenip yüklenmeyeceğini sorulduğunda "Bilinmeyen Yayımcı" sözcükler görüntülenecek uygulama neden olur. Ancak, zaman ve bir sertifika yetkilisi tarafından verilen bir sertifika için gereken para harcamanız zorunda kalmaktan daha küçük müşteriler engellediğini avantajı vardır.  
  
3.  Son olarak, geliştirici, kendi otomatik olarak imzalanan sertifika Kurulum paketine dahil edebilirsiniz. Bu konuda daha önce ele alınan uygulama kimliği ile ilgili olası sorunları tanıtır.  
  
 Kurulum dağıtım projesi yönteminin dezavantajı, özel bir dağıtım uygulaması oluşturmak için gerekli gider ve saat ' dir.  
  
### <a name="have-customer-generate-deployment-manifest"></a>Sahip müşteri oluşturmak dağıtım bildirimi  
 Üçüncü olası Dağıtım stratejisi el yalnızca uygulama dosyalarını ve uygulama bildirimini müşteriye kapalıdır. Bu senaryoda, .NET Framework SDK'sını kullanarak oluşturmak ve dağıtım bildirimi imzalamak için müşteri sorumludur.  
  
 Bu yöntemin dezavantajı .NET Framework SDK Araçları yüklemek ve bir geliştirici veya bunları kullanmayı becerikli olan sistem yöneticisi müşteri gerektirmesidir. Bazı müşteriler kendi bölümü çok az kayıpla veya hiç teknik çaba gerektiren bir çözüm talep edebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Test etmek için ClickOnce uygulamaları dağıtma ve üretim sunucuları teslim etmeden](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md)   
 [İzlenecek yol: Bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [İzlenecek yol: Yeniden İmzalama Gerektirmeyen ve Marka Bilgisini Koruyan bir ClickOnce Uygulamasını El ile Dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-app-no-re-signing-required.md)