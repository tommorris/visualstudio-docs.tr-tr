---
title: 'Nasıl yapılır: ClickOnce uygulamaları için bir istemci bilgisayara güvenilir bir yayımcı eklemek | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, install without prompting
- trusted application deployment, Trusted Publishers
ms.assetid: 35fe324c-45a1-4509-b7be-5c18b4b1b4ab
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c9d718eba01a35c1f6991ab50d217c8b5f63065
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31562708"
---
# <a name="how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications"></a>Nasıl yapılır: ClickOnce Uygulamaları için Sunucu Bilgisayara Güvenilir Yayımcı Ekleme
Güvenilir uygulama dağıtımı ile istemci bilgisayarları yapılandırabilirsiniz. böylece, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları, kullanıcıya sormadan daha yüksek bir güven düzeyi ile çalışır. Aşağıdaki yordamlar CertMgr.exe komut satırı aracı bir yayımcının sertifika bir istemci bilgisayarındaki Güvenilen Yayımcılar deposuna eklemek için nasıl kullanılacağını gösterir.  
  
 Kullandığınız komutlar, sertifikayı veren sertifika yetkilisi (CA) bir istemcinin güvenilir kök parçası olmasına bağlı olarak biraz farklılık gösterir. Bir Windows istemci bilgisayarı bir etki alanının parçası ise, bu, bir listede, güvenilen kökler olarak kabul edilen CA'ları içerir. Bu liste, genellikle sistem yöneticisi tarafından yapılandırılır. Sertifikanız bu Güvenilen Kökleri biri tarafından veya bir CA tarafından bu zincirleri bu Güvenilen Kökleri birine verildiyse, sertifika istemcinin güvenilir kök deposuna ekleyebilirsiniz. Diğer taraftan, sertifikanız bu Güvenilen Kökleri biri tarafından değil verildiyse, sertifika istemcinin güvenilir kök deposuna hem güvenilir yayımcı deposuna eklemeniz gerekir.  
  
> [!NOTE]
>  Dağıtmayı planladığınız her istemci bilgisayar üzerinde bu şekilde sertifikalar eklemelisiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yükseltilmiş izinler gerektirir uygulama. El ile veya müşterilerinize dağıttığınız bir uygulama aracılığıyla sertifikalar ekleyebilirsiniz. Yalnızca herhangi bir sayıda geçmesi dağıtabileceğiniz bu bilgisayarlar bir kez yapılandırmanıza gerek [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar aynı sertifika ile imzalanmış.  
  
 Bir sertifika kullanarak programlı olarak bir depoya ekleyebilir <xref:System.Security.Cryptography.X509Certificates.X509Store> sınıfı.  
  
 Güvenilir uygulama dağıtımı genel bakış için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-the-trusted-root"></a>Güvenilen kök altında Güvenilen Yayımcılar deposuna sertifika eklemek için  
  
1.  CA'dan bir dijital sertifika edinin.  
  
2.  Sertifikayı Base64 X.509 (.cer) biçiminde dışarı aktarın. Sertifika biçimleri hakkında daha fazla bilgi için bkz: [sertifika verme](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  İstemci bilgisayarlarda komut isteminden aşağıdaki komutu çalıştırın:  
  
     **certmgr.exe-certificate.cer - c -s - r localMachine TrustedPublisher Ekle**  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-a-different-root"></a>Farklı bir kök altında Güvenilen Yayımcılar deposuna sertifika eklemek için  
  
1.  CA'dan bir dijital sertifika edinin.  
  
2.  Sertifikayı Base64 X.509 (.cer) biçiminde dışarı aktarın. Sertifika biçimleri hakkında daha fazla bilgi için bkz: [sertifika verme](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  İstemci bilgisayarlarda komut isteminden aşağıdaki komutu çalıştırın:  
  
     **certmgr.exe-good.cer - c -s - r localMachine kök ekleme**  
  
     **certmgr.exe-good.cer - c -s - r localMachine TrustedPublisher Ekle**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce ve Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Güvenilir Uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md)   
 [Nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştir](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Nasıl yapılır: ClickOnce uygulamaları için bir istemci bilgisayara güvenilir bir yayımcı Ekle](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Nasıl yapılır: yeniden uygulama ve dağıtım bildirimlerini imzalama](../deployment/how-to-re-sign-application-and-deployment-manifests.md)   
 [Nasıl yapılır: ClickOnce Güven İstemi Davranışını Yapılandırma](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)