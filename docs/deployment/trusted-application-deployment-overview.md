---
title: "Güvenilir Uygulama dağıtımına genel bakış | Microsoft Docs"
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
- ClickOnce deployment, install without prompting
- ClickOnce deployment, security
- trusted application deployment
ms.assetid: b24a1702-8fbe-45b1-87a0-9618a0708f1d
caps.latest.revision: "31"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 34e83d6b035ba6ea91190fa89b9e1a63366e7907
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="trusted-application-deployment-overview"></a>Güvenilir Uygulama Dağıtımına Genel Bakış
Bu konu nasıl dağıtılacağı bir bakış sunar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Güvenilir Uygulama Dağıtımı teknolojisi kullanarak yükseltilmiş izinleri olan uygulamalar.  
  
 Güvenilir uygulama dağıtımı, parçası [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım teknolojisi, kuruluşların ek bir yönetilen uygulamayı daha güvenli bir biçimde kullanıcıya sormadan izinleri atamak için herhangi bir boyuttaki kolaylaştırır. Güvenilir uygulama dağıtımı ile bir kuruluş Authenticode sertifikaları kullanarak tanımlanan güvenilir yayımcılar, listesini sağlamak için bir istemci bilgisayarı yalnızca yapılandırabilirsiniz. Bundan sonra tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bunlardan birini imzalı uygulama Güvenilen Yayımcılar daha yüksek bir güven düzeyi alır.  
  
> [!NOTE]
>  Güvenilir uygulama dağıtımı bir kullanıcının bilgisayarına tek seferlik yapılandırma gerektirir. Yönetilen Masaüstü ortamlarında, bu yapılandırma genel ilke kullanılarak gerçekleştirilebilir. Bu, uygulamanız için istediğiniz değil ise, bunun yerine izin yükseltme kullanın. Daha fazla bilgi için bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md).  
  
## <a name="trusted-application-deployment-basics"></a>Güvenilir Uygulama dağıtımının temelleri  
 Aşağıdaki tabloda nesneleri ve oynayan rolleri güvenilir uygulama dağıtımı'gösterir.  
  
|Nesne veya rol|Açıklama|  
|--------------------|-----------------|  
|Yönetici|Güncelleştirme ve istemci bilgisayardan sorumlu sorumlu kuruluş varlık|  
|Güven Yöneticisi|Ortak dil çalışma zamanı (CLR) istemci uygulama güvenliği zorlama için sorumlu alt sistem.|  
|Yayımcı|Yazar ve uygulamayı tutar varlık.|  
|Dağıtıcı|Paketler ve kullanıcıların uygulamaya dağıtan varlık.|  
|sertifika|Ortak ve özel anahtarı içeren şifrelenmiş bir imza; genellikle orijinalliği bir sertifika yetkilisi (CA) tarafından verilmiş.|  
|Authenticode sertifikası|Bir sertifika ile ekli meta veri açıklayan, bunun yanı sıra, sertifika çalıştırılacağı kullanır.|  
|Sertifika yetkilisi|Yayımcılar kimliğini doğrular ve sertifikaları veren bir kuruluş publisher'ın meta verileriyle katıştırılmış.|  
|kök yetkilisi|Diğer sertifikaları sertifika yetkililerine yetki veren sertifika yetkilisi.|  
|anahtar kapsayıcısı|Sertifikaları depolamak için bir mantıksal depolama alanında Microsoft Windows.|  
|güvenilir bir yayımcı|Authenticode sertifikası için bir istemci bilgisayarda bir sertifika güven listesi (CTL) eklenmiş olan bir yayımcı.|  
  
 Büyük kuruluşlarda yayımcı ve dağıtıcı sık iki ayrı varlık şunlardır:  
  
-   Yayımcı oluşturur grubudur [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
-   Dağıtıcı, dağıtan genellikle bilgi teknolojisi (BT) departmanı, grubudur [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kurumsal masaüstü bilgisayarlar için uygulama.  
  
 Güvenilir uygulama dağıtımı yararlanmak için şu adımları izlemelisiniz:  
  
1.  Yayımcı için bir sertifika edinin.  
  
2.  Tüm istemcilerin Güvenilen Yayımcılar deposuna yayımcı ekleyin.  
  
3.  Oluştur, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
4.  Dağıtım bildirimini yayımcının sertifika ile oturum açın.  
  
5.  Uygulama dağıtımı, istemci bilgisayarlarda yayımlayın.  
  
### <a name="obtain-a-certificate-for-the-publisher"></a>Yayımcı için bir sertifika edinin  
 Dijital sertifikalar Microsoft Authenticode kimlik doğrulaması ve güvenlik sistemi çekirdek bileşenidir. Authenticode, Windows işletim sistemi, standart bir parçasıdır. Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları güvenilir uygulama dağıtımı'na katılmak bunlar bağımsız olarak bir dijital sertifika ile imzalanmalıdır. Authenticode ile nasıl çalıştığı hakkında tam açıklama için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], bkz: [ClickOnce ve Authenticode](../deployment/clickonce-and-authenticode.md).  
  
### <a name="add-the-publisher-to-the-trusted-publishers-store"></a>Güvenilen Yayımcılar deposuna yayımcı ekleme  
 İçin [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] daha yüksek bir güven düzeyi almak için uygulamanın güvenilir bir yayımcı olarak sertifikanızı uygulamanın çalışacağı her istemci bilgisayara eklemeniz gerekir. Bu görevi gerçekleştirme tek seferlik bir yapılandırmadır. Bu tamamlandıktan sonra kadar dağıtabilirsiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları istediğiniz ve tüm yüksek güven ile çalışacak şekilde, publisher'ın sertifikayla imzalanmış.  
  
 Yönetilen bir masaüstü ortamında uygulamanızda dağıtıyorsanız; Windows işletim sistemi çalıştıran Örneğin, bir Kurumsal intranet; Grup İlkesi ile yeni bir sertifika güven listesi (CTL) oluşturarak, bir istemcinin deposuna Güvenilen Yayımcılar ekleyebilirsiniz. Daha fazla bilgi için bkz: [bir Grup İlkesi nesnesi için bir sertifika güven listesi oluşturma](http://go.microsoft.com/fwlink/?LinkId=102576).  
  
 Yönetilen bir masaüstü ortamında uygulamanızda değil dağıtıyorsanız, güvenilir bir yayımcı depoya bir sertifika eklemek için aşağıdaki seçenekler vardır:  
  
-   <xref:System.Security.Cryptography?displayProperty=fullName> Ad alanı.  
  
-   Internet Explorer'ın bir bileşeni olan ve bu nedenle bulunan Windows 98 ve tüm sonraki sürümler CertMgr.exe. Daha fazla bilgi için bkz: [Certmgr.exe (sertifika yönetim aracı)](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool).  
  
### <a name="create-a-clickonce-application"></a>ClickOnce uygulaması oluşturma  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] istemci uygulaması uygulamayı tanımlayan ve yükleme parametrelerini sağlayan bildirim dosyalarıyla birlikte. Programınıza kapatabilirsiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kullanarak uygulama **Yayımla** komutunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Alternatif olarak, gerekli tüm dosyaları oluşturabilirsiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bulunan araçları kullanarak dağıtım [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Ayrıntılı adımlar için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımı, bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
 Güvenilir uygulama dağıtımı için belirli [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ve yalnızca kullanılabilir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar.  
  
### <a name="sign-the-deployment"></a>Dağıtımı imzalayın  
 Sertifikanızı aldıktan sonra onu dağıtımınızı imzalamak için kullanmanız gerekir. Uygulamanızı kullanarak dağıtıyorsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Yayımlama Sihirbazı, size bir sertifika kendiniz belirtmediyseniz Sihirbazı otomatik olarak bir test sertifikası sizin için oluşturur. Aynı zamanda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Proje Tasarımcısı penceresinde, ancak bir CA tarafından sağlanan bir sertifika sağlamak için.  Ayrıca bkz. [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama] (http://msdn.microsoft.com/library/31kztyey\(v=vs.110\).  
  
> [!CAUTION]
>  Uygulama bir test sertifikası ile dağıtılması önermiyoruz.  
  
 Mage.exe veya MageUI.exe SDK araçları kullanarak da uygulamayı imzalayabilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Dağıtım imzalama ile ilgili komut satırı seçeneklerinin tam bir listesi için bkz: [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
### <a name="publish-the-application"></a>Uygulama yayımlama  
 Oturum hemen sonra [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirimleri, uygulama, yükleme konumuna yayımlamak hazır. Yükleme konumu, bir Web sunucusu, bir dosya paylaşımı veya yerel disk olabilir. İstemci dağıtım bildirimi ilk kez eriştiğinde, güven yöneticisi seçmelisiniz olup olmadığını [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama yetkilisi verildiğini veya güven daha yüksek bir düzeyde bir yüklü çalıştırmayı güvenilir yayımcı. Güven Yöneticisi depolamak istemcinin güvenilir yayımcı depolanan sertifikalarla dağıtım imzalamak için kullanılan sertifika karşılaştırarak bu seçenek sağlar. Güven Yöneticisi bir eşleşme bulursa, uygulama yüksek güven ile çalışır.  
  
## <a name="trusted-application-deployment-and-permission-elevation"></a>Güvenilir uygulama dağıtımı ve izin yükseltme  
 Geçerli yayımcı güvenilir bir yayımcı değilse, güven yöneticisi olup çözemiyorsa uygulamanızı yükseltilmiş izinlerin istediği hakkında kullanıcı sorgulamaya izin yükseltme kullanır. Ancak, izin yükseltme yönetici tarafından devre dışıysa, uygulamayı çalıştırma izni elde edilemiyor. Uygulama çalışmaz ve kullanıcıya bir bildirim görüntülenir. İzin yükseltme hakkında daha fazla bilgi için bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md).  
  
## <a name="limitations-of-trusted-application-deployment"></a>Güvenilir uygulama dağıtımı sınırlamaları  
 Güvenilir uygulama dağıtımı yükseltilmiş güven vermek için kullanabileceğiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Web üzerinden veya bir kuruluşun dosya paylaşımı aracılığıyla dağıtılan uygulamalar. Güvenilir uygulama dağıtımı için kullanmak zorunda değil [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] varsayılan olarak, bu uygulamaların tam güven verildiğinden, CD'ye, dağıtılmış uygulamalar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [İzlenecek yol: ClickOnce Uygulamasını El ile Dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)
