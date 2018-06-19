---
title: ClickOnce ve uygulama ayarlarını | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, application settings
ms.assetid: 891caba6-faef-4a3c-8f71-60e6fadb60eb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e325ed1d66729eaed18c577c27f09a3db45d98f6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31561707"
---
# <a name="clickonce-and-application-settings"></a>ClickOnce ve Uygulama Ayarları
Windows Forms için uygulama ayarları oluşturun, depolamak ve özel uygulama ve istemci üzerindeki kullanıcı tercihlerini korumak yapmayı kolaylaştırır. Aşağıdaki belge bir ClickOnce uygulamasında uygulama ayarları dosyalarının nasıl çalışır ve kullanıcı sonraki sürüme yükseltildiğinde nasıl ClickOnce ayarlarını da geçirir açıklar.  
  
 Yalnızca varsayılan uygulama ayarları sağlayıcısı için aşağıdaki bilgiler geçerlidir <xref:System.Configuration.LocalFileSettingsProvider> sınıfı. Özel bir sağlayıcı sağlarsanız, sağlayıcıyı nasıl verilerini depolar ve ayarlarına sürümleri arasında yükseltme nasıl belirler. Uygulama ayarları sağlayıcıları hakkında daha fazla bilgi için bkz: [uygulama ayarları mimarisi](/dotnet/framework/winforms/advanced/application-settings-architecture).  
  
## <a name="application-settings-files"></a>Uygulama ayarları dosyası  
 Uygulama ayarları iki dosya kullanır: *uygulama*. exe.config ve user.config nerede *uygulama* Windows Forms uygulamanızın adıdır. User.config uygulamanız kullanıcı kapsamlı ayarları depolayan istemci ilk kez üzerinde oluşturulur. *Uygulama*. exe.config, buna karşın var dağıtımdan önce ayarlar için varsayılan değerleri tanımlarsanız. Visual Studio içereceği bu dosyayı otomatik olarak kullandığınızda, **Yayımla** komutu. Mage.exe veya MageUI.exe emin olmanız gerekir kullanarak ClickOnce uygulamanızı oluşturursanız, bu dosya ile birlikte uygulama bildiriminizi olduğunda, uygulamanızın diğer dosyaları kullanıcının.  
  
 ClickOnce uygulama 's kullanmadan dağıtılan bir Windows Forms uygulamalarında *uygulama*. exe.config dosyası, uygulama dizininde depolanır, kullanıcının user.config file barındırırken **belgeler ve ayarlar**  klasörü. Bir ClickOnce uygulamasında *uygulama*. exe.config yaşar ClickOnce uygulaması önbelleğinin içinde uygulama dizinindeki ve user.config bu uygulama için ClickOnce veri dizini içinde bulunur.  
  
 Uygulama ayarları sağlar, uygulamanızın nasıl dağıtıldığına bakmaksızın, güvenli okuma erişimi *uygulama*. exe.config ve user.config güvenli okuma/yazma erişimi.  
  
 Bir ClickOnce uygulamasında uygulama ayarları tarafından kullanılan yapılandırma dosyalarını boyutunu ClickOnce önbellek boyutuyla sınırlıdır. Daha fazla bilgi için bkz: [ClickOnce önbelleğine genel bir bakış](../deployment/clickonce-cache-overview.md).  
  
## <a name="version-upgrades"></a>Sürüm yükseltme  
 Yalnızca her sürümü ClickOnce uygulaması, diğer tüm sürümlerden ayrılmış olduğundan, diğer sürümleri de için ayarlardan ClickOnce uygulaması için uygulama ayarları yalıtılır. Kullanıcı, uygulamanızın sonraki bir sürüme yükseltildiğinde, uygulama ayarları en son (en yüksek numaralı) sürümün ayarları güncelleştirilmiş sürümü ve birleştirmeler ayarları dosyaları yeni kümesine ayarları ile birlikte sağlanan ayarları karşı karşılaştırır.  
  
 Aşağıdaki tabloda, uygulama ayarları kopyalamak için hangi ayarların nasıl karar verir açıklanmaktadır.  
  
|Değişiklik türü|Yükseltme eylemi|  
|--------------------|--------------------|  
|İçin eklenen ayar *uygulama*. exe.config|Yeni bir ayar geçerli sürüme ait birleştirilmiş *uygulama*. exe.config|  
|Kaldırılmasını ayarı *uygulama*. exe.config|Geçerli sürümden 's kaldırılan eski ayar *uygulama*. exe.config|  
|Ayarın varsayılanı; değişti yerel ayar user.config içinde orijinal varsayılan hala ayarlandı.|Ayar içine güncel sürüme ait user.config yeni varsayılan değer olarak birleştirilir.|  
|Ayarın varsayılanı; değişti ayar, varsayılan olmayan user.config içinde ayarlandı.|Ayar güncel sürüme ait user.config tutulacağı varsayılan olmayan değer ile birleştirilir.|  
  
 Kendi uygulama ayarları sarmalayıcı sınıfı oluşturduysanız ve güncelleştirme mantığını özelleştirmek istiyorsanız, geçersiz kılabilirsiniz <xref:System.Configuration.ApplicationSettingsBase.Upgrade%2A> yöntemi.  
  
## <a name="clickonce-and-roaming-settings"></a>ClickOnce ve Dolaşım ayarları  
 ClickOnce Dolaşım ayarları, ağdaki makineler arasında izlemek ayarları dosyanız sağlayan çalışmaz. Dolaşım ayarlarına ihtiyacınız varsa, ağ üzerinden ayarları depolayan bir uygulama ayarları sağlayıcısı ya da ayarları uzak bir bilgisayarda depolamak için kendi özel ayar sınıflarınızı geliştirmeniz gerekir. Ayar sağlayıcıları daha fazla bilgi için bkz: [uygulama ayarları mimarisi](/dotnet/framework/winforms/advanced/application-settings-architecture).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [Uygulama ayarlarına genel bakış](/dotnet/framework/winforms/advanced/application-settings-overview)   
 [ClickOnce önbelleğine genel bakış](../deployment/clickonce-cache-overview.md)   
 [ClickOnce Uygulamalarında Yerel ve Uzak Veri Erişimi](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)