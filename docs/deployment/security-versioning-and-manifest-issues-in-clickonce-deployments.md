---
title: "Güvenlik, sürüm ve bildirim sorunları ClickOnce dağıtımlarında | Microsoft Docs"
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
- versioning, ClickOnce applications
- ClickOnce applications, Windows Vista User Account Control
- ClickOnce applications, versioning issues
- security, ClickOnce applications
- Windows 7, ClickOnce deployments
- ClickOnce applications, manifest issues
- User Account Control, ClickOnce applications
- Windows Vista, ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, security issues
ms.assetid: d5d0c90b-ac1a-44e2-88dc-0d0ffd881624
caps.latest.revision: "21"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 603ff665e2c01abe62954e4e65e49a095d358b29
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="security-versioning-and-manifest-issues-in-clickonce-deployments"></a>ClickOnce Dağıtımlarında Güvenlik, Sürüm ve Bildirim Sorunları
Çok çeşitli sorunlar ile vardır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] güvenlik, uygulama sürümü ve bildirim sözdizimi ve neden olabilir semantiği bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımının.  
  
## <a name="clickonce-and-windows-vista-user-account-control"></a>ClickOnce ve Windows Vista kullanıcı hesabı denetimi  
 İçinde [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)], uygulamalar varsayılan olarak, geçerli kullanıcının yönetici izinlerine sahip bir hesapla oturum oturum açmamış olsa bile standart bir kullanıcı olarak çalıştırın. Bir uygulama yönetici izinleri gerektiren bir eylem gerçekleştirmeniz gerekirse, yönetici kimlik bilgilerini girmesini ister işletim sistemi söyler. Kullanıcı Hesabı Denetimi (UAC) olarak adlandırılır, bu özellik bir kullanıcının açık onayını olmadan işletim sisteminin tamamını etkileyebilecek değişiklikler uygulamaların engeller. Windows uygulamaları bildirme belirterek bu izni ayrıcalık gerektiren `requestedExecutionLevel` özniteliğini `trustInfo` uygulama bildiriminde bölümü.  
  
 Uygulamaları ve güvenlik ayrıcalık saldırılara açığa çıkma riskini nedeniyle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] UAC istemci için etkinse, uygulamaları izin yükseltme isteği olamaz. Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ayarlamaya çalışır uygulama kendi `requestedExecutionLevel` özniteliğini `requireAdministrator` veya `highestAvailable` üzerinde yüklenmez [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)].  
  
 Bazı durumlarda, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama yönetici izinlerine sahip yükleyici algılama mantığı nedeniyle çalıştırmayı deneyebilirsiniz [!INCLUDE[windowsver](../deployment/includes/windowsver_md.md)]. Bu durumda, ayarlayabileceğiniz `requestedExecutionLevel` uygulama bildirimine özniteliğinde `asInvoker`. Bu yükseltme olmadan çalıştırmak uygulamanın kendisinin neden olur. [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)]otomatik olarak bu öznitelik tüm uygulama bildirimlerine ekler.  
  
 Uygulamasının tüm kullanım süresi için yönetici izinleri gerektiren bir uygulama geliştiriyorsanız, uygulamanın Windows Installer (MSI) teknolojisi kullanarak dağıtmayı düşünmelisiniz. Daha fazla bilgi için bkz: [Windows Installer Temelleri](../extensibility/internals/windows-installer-basics.md).  
  
## <a name="online-application-quotas-and-partial-trust-applications"></a>Çevrimiçi uygulama kotaları ve kısmi güven uygulamaları  
 Varsa, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bir yükleme çevrimiçi yerine çalışır, çevrimiçi uygulamalar için ayrılan kota içine sığması gerekir. Ayrıca, kısmi güvende gibi kısıtlı bir güvenlik izinleri kümesi ile çalışan bir ağ uygulaması kota boyutu yarısı büyük olamaz.  
  
 Daha fazla bilgi için ve nasıl çevrimiçi uygulama kotasını değiştirmek için bkz: [ClickOnce önbelleğine genel bir bakış](../deployment/clickonce-cache-overview.md).  
  
## <a name="versioning-issues"></a>Sürüm oluşturma sorunları  
 Tanımlayıcı adlar, derlemenizi atamak ve bir uygulama güncelleştirmesini yansıtacak şekilde derleme sürüm numarasını Artır sorunlarla karşılaşabilirsiniz. Tanımlayıcı adlı bir derleme başvurusu ile derlenmiş bir derlemeyi kendisini derlenmelidir veya derleme eski sürümü başvuru dener. Derleme kendisine ait bağlanma isteği eski sürüm değeri kullandığından bu derleme çalışacaktır.  
  
 Örneğin, 1.0.0.0 sürümü ile kendi projesinde tanımlayıcı adlı bir derleme olduğunu varsayalım. Derlemeyi derledikten sonra ana uygulamanızı içeren projesine bir başvuru olarak ekleyin. Derleme güncelleştirmek, 1.0.0.1 sürüme artırmak ve ayrıca uygulama derlemeden dağıtmak çalışırsanız, uygulamanın çalışma zamanında derlemesini yüklemek mümkün olmaz.  
  
 Yalnızca düzenliyorsanız, bu hata oluşabilir, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] el ile; bildirimlerini kullanarak dağıtım oluşturursanız, bu hata ile karşılaşmazsınız [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)].  
  
## <a name="specifying-individual-net-framework-assemblies-in-the-manifest"></a>Bildirimde bağımsız .NET Framework derlemelerini belirtme  
 Uygulamanızı el ile düzenlediyseniz yüklenemeyecek bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] daha eski bir sürümü başvurmak için dağıtım bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] derleme. Örneğin, bir sürümü için System.Net derlemesine başvuru eklediyseniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] bildiriminde belirtilen sürümden önce ardından bir hata ortaya çıkabilecek. Genel olarak, size tek başvurular belirtmek çalışmamalısınız [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürümü olarak derlemeleri [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] uygulama bildiriminde bir bağımlılık olarak uygulamanızın çalıştığı karşı belirtilir.  
  
## <a name="manifest-parsing-issues"></a>Bildirim Ayrıştırma sorunları  
 Tarafından kullanılan bildirim dosyaları [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] XML dosyalarıdır ve doğru biçimlendirilmiş ve geçerli olması gerekir: XML sözdizimi kurallarına uymalı ve yalnızca öğeleri ve özniteliklerinin ilgili XML Şeması'nda tanımlanan kullanın.  
  
 Bildirim dosyasında sorunlara neden olabilecek bir şey tek veya çift tırnak işareti gibi özel bir karakter içeriyorsa, uygulamanız için bir ad seçmektir. Uygulamanın adını parçası olan kendi [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kimliği. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]şu anda özel karakterler içeren kimlikleri ayrıştırma değil. Etkinleştirmek, uygulamanızın başarısız olursa, adı yalnızca alfabetik ve sayısal karakter kullanıyorsanız ve tekrar dağıtmayı denemeden emin olun.  
  
 Dağıtımı veya uygulama bildirimlerinizi el ile düzenlediyseniz, kasıtsız olarak bunları bozulmuş olabilir. Bozulmuş bir bildirim doğru engeller [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yükleme. Tıklayarak çalışma zamanında tür hatalarını ayıklayabilirsiniz **ayrıntıları** üzerinde **ClickOnce hata** iletişim kutusu ve günlük hata iletisinde okuma. Günlük şu iletilerden birini listeler:  
  
-   Sözdizimi hatası ve satır numarası ve karakter açıklaması hatanın oluştuğu konum.  
  
-   Öğe veya öznitelik bildirim şemasını ihlal kullanılan adı. XML el ile bildirimlerinize eklediyseniz, bildirim şemalarıyla eklemeyi karşılaştırmak gerekecektir. Daha fazla bilgi için bkz: [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md) ve [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md).  
  
-   Bir kimlik çakışması. Dağıtım ve uygulama bildirimlerinde bağımlılık başvuruları her ikisinde de benzersiz olmalıdır, `name` ve `publicKeyToken` öznitelikleri. Herhangi bir bildirim içinde iki öğe arasında her iki öznitelik eşleşirse, Bildirim ayrıştırma başarısız olur.  
  
## <a name="precautions-when-manually-changing-manifests-or-applications"></a>Bildirimler veya uygulamalar el ile değiştirirken önlemler  
 Bir uygulama bildirimi güncelleştirdiğinizde, uygulama bildirimi ve dağıtım bildirimini yeniden imzalamalısınız. Dağıtım bildirimi o dosyanın karması ve dijital imzasını içeren uygulama bildirimi başvuru içeriyor.  
  
### <a name="precautions-with-deployment-provider-usage"></a>Dağıtım sağlayıcısı kullanımı ile önlemler  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Dağıtım bildirimi sahip bir `deploymentProvider` uygulamanın yüklü ve hizmet gelen konumunun tam yolunu gösteren özelliği:  
  
```  
<deploymentProvider codebase="http://myserver/myapp.application" />  
```  
  
 Bu yol ayarlanır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulaması oluşturur ve yüklü uygulamalar için zorunlu. Yolun standart konumuna işaret eden nerede [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yükleyici uygulamasından ve güncelleştirmeleri yükler. Kullanırsanız **xcopy** kopyalamak için komut bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama farklı bir konuma ancak değiştirmeyin `deploymentProvider` özelliği [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yüklemeye çalıştığında hala geri özgün konuma başvuru yapar uygulama.  
  
 Taşımak veya uygulamanın kopyalamak istiyorsanız, aynı zamanda güncelleştirmelisiniz `deploymentProvider` yolu, böylece istemci gerçekten yeni konumdan yükler. Uygulamaları yüklediyseniz, bu yolu güncelleştirme çoğunlukla bir konudur. Her zaman ayarı özgün URL aracılığıyla başlatılan çevrimiçi uygulamalar için `deploymentProvider` isteğe bağlıdır. Varsa `deploymentProvider` bu kullanılacaktır; Aksi takdirde, uygulamayı başlatmak için kullanılan URL temel URL olarak uygulama dosyalarını indirmek için kullanılacak, ayarlanmadı.  
  
> [!NOTE]
>  Bildirim her güncelleştirdiğinizde de onu tekrar oturum açmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım sorunlarını giderme](../deployment/troubleshooting-clickonce-deployments.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md)