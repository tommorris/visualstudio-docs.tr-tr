---
title: ClickOnce ve Authenticode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- .pfx files
- ClickOnce deployment, Authenticode
- Authenticode, ClickOnce
- ClickOnce deployment, certificates
- ClickOnce deployment, security
ms.assetid: ab5b6712-f32a-4e33-842f-e88ab4818ccf
caps.latest.revision: "18"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: aa1ab7ac947a5fbdf9d0423c57a987a4ffe8be97
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="clickonce-and-authenticode"></a>ClickOnce ve Authenticode
*Authenticode* uygulamanın yayımcı özgünlüğünü doğrulayan dijital sertifikalar ile uygulama kodu imzalamak için endüstri standardı şifreleme kullanan bir Microsoft teknolojisidir. Uygulama dağıtımı için Authenticode kullanarak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Truva atı riskini azaltır. Truva atı bir virüs veya kötü amaçlı bir üçüncü taraf kurulu olan güvenilir bir kaynaktan geliyor yasal bir program olarak görünen diğer zararlı program ' dir. İmzalama [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımları bir dijital sertifika ile olan dosya ve derlemeler değil doğrulamak için isteğe bağlı bir adım.  
  
 Aşağıdaki bölümlerde Authenticode içinde kullanılan dijital sertifikalar farklı türlerini açıklayan, sertifikalar kullanılarak doğrulanacağını nasıl sertifika yetkililerini (CA), zaman damgası sertifikaları rolü ve depolama için kullanılabilir yöntemleri sertifikalar.  
  
## <a name="authenticode-and-code-signing"></a>Authenticode ve kod imzalama  
 A *dijital sertifika* yayımcıya açıklayan meta verileri birlikte şifreleme ortak/özel bir anahtar çiftini içeren bir dosyadır sertifikanın verildiği ve sertifikayı veren Teşkilatı.  
  
 Authenticode sertifikaları çeşitli türleri vardır. Her biri farklı imzalama yapılandırılır. İçin [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar, kod imzalama için geçerli olan Authenticode sertifikası olması gerekir. Oturum açmaya çalışırsanız bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama başka bir dijital e-posta sertifikası gibi sertifika türü ile çalışmaz. Daha fazla bilgi için bkz: [kod imzalama giriş](http://go.microsoft.com/fwlink/?LinkId=179452).  
  
 Kod üç yöntemden birini imzalama için bir sertifika elde edebilirsiniz:  
  
-   Bir sertifika satıcıdan satın alın.  
  
-   Kuruluşunuzdaki dijital sertifikalar oluşturmaktan sorumlu bir gruptan alırsınız.  
  
-   Yeni SelfSignedCertificate PowerShell cmdlet'ini kullanarak kendi sertifikanızı oluşturmak ya da MakeCert.exe kullanarak olduğu birlikte [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
### <a name="how-using-certificate-authorities-helps-users"></a>Sertifika yetkililerini kullanarak kullanıcıların nasıl yardımcı  
 Yeni SelfSignedCertificate ya da MakeCert.exe yardımcı programını kullanılarak oluşturulan sertifika yaygın olarak adlandırılan bir *self-cert* veya *test cert*. Bu tür bir sertifika .snk dosyası .NET Framework çalışan benzer şekilde çalışır. Yalnızca bir genel/özel şifreleme anahtar çiftinden oluşur ve yayımcı hakkında doğrulanabilen bilgi içerir. Kendi kendine sertifikaları dağıtmak için kullanabileceğiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] intranet yüksek güven uygulamalarla. Ancak, ne zaman bu uygulamaları çalıştıran bir istemci bilgisayarda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bunları Bilinmeyen bir yayımcıdan geliyormuş gibi tanımlar. Varsayılan olarak, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] self-sertifikaları ile imzalanmış ve Internet üzerinde dağıtılan uygulamaları güvenilir uygulama dağıtımı kullanmak olamaz.  
  
 Bunun aksine, bir sertifika bir CA'dan bir sertifika satıcı ya da bir bölüm gibi kuruluşunuzda alırsanız, sertifika, kullanıcılarınızın daha fazla güvenlik sunar. Yalnızca imzalı yazılım yayımcısını tanımlar, ancak sahip imzaladıktan CA denetleyerek kimliğini doğrular. CA kök yetkilisi değilse, Authenticode ayrıca "CA sertifikaları için yetkili olup olmadığını doğrulamak için geri kök yetkilisi olarak zincirler". Daha fazla güvenlik için mümkün olduğunda bir CA tarafından verilen bir sertifika kullanmanız gerekir.  
  
 Self-cert oluşturma hakkında daha fazla bilgi için bkz: [yeni SelfSignedCertificate](https://technet.microsoft.com/itpro/powershell/windows/pkiclient/new-selfsignedcertificate) veya [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx).  
  
### <a name="timestamps"></a>Zaman damgaları  
 İmzalamak için kullanılan sertifikaları [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları sona zaman, bir belirli bir süre sonra genellikle on iki ay boyunca. Sürekli olarak uygulamaları yeni sertifikalar ile yeniden imzalamak için gereken kaldırmak için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zaman damgası destekler. Bir uygulama bir zaman damgası ile imzalandığında sertifikasını sürdürecektir bile süresi dolduktan sonra kabul, zaman damgası geçerli sağlanır. Böylece [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] süresi dolan sertifikaları, ancak karşıdan yüklemek ve çalıştırmak için geçerli zaman damgaları uygulamalarla. Süresi dolmuş sertifikaları olan yüklenmiş uygulamaların güncelleştirmeleri indirmek ve yüklemek de sağlar.  
  
 Uygulama sunucusuna zaman damgası eklemek için zaman damgası sunucusu kullanılabilir olmalıdır. Zaman damgası sunucusu seçme hakkında daha fazla bilgi için bkz: [nasıl yapılır: oturum uygulama ve dağıtım bildirimlerini](../ide/how-to-sign-application-and-deployment-manifests.md).  
  
### <a name="updating-expired-certificates"></a>Süresi dolan sertifikaları güncelleştirme  
 .NET Framework önceki sürümlerde, sertifikanın süresi dolmuş uygulamayı güncelleştirme Uygulama çalışmayı durdurmasına neden olabilir. Bu sorunu gidermek için aşağıdaki yöntemlerden birini kullanın:  
  
-   .NET Framework sürüm 2.0 SP1 veya daha sonra Windows XP veya sürüm 3.5 veya Windows Vista sonraki güncelleştirin.  
  
-   Uygulamayı kaldırın ve yeni bir sürümü geçerli bir sertifika ile yeniden yükleyin.  
  
-   Sertifika güncelleştirmeleri bir komut satırı derleme oluşturun. Bu işlem hakkında adım adım bilgiler bulunabilir [Microsoft destek makalesi 925521](http://go.microsoft.com/fwlink/?LinkId=179454).  
  
### <a name="storing-certificates"></a>Sertifikaları depolama  
  
-   Dosya sisteminizde .pfx dosyası olarak sertifikaları depolamak veya bir anahtar kapsayıcısı içinde depolayabilirsiniz. Bir Windows etki alanındaki bir kullanıcı bir dizi anahtar kapsayıcıları olabilir. Bu bir .pfx dosyasına bunun yerine kaydetmeniz gerekir, belirtmediğiniz sürece varsayılan olarak, sertifikaları MakeCert.exe, kişisel anahtar kapsayıcısında depolar. Mage.exe ve MageUI.exe [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] oluşturmak için Araçlar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımları, her iki biçimde depolanan sertifikalar kullanmak olanak tanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [Güvenilir Uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md)   
 [Mage.exe (Bildirim Oluşturma ve Düzenleme Aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)