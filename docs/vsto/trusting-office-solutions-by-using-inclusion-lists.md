---
title: Ekleme listelerini kullanarak Office çözümlerine güven
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- inclusion lists [Office development in Visual Studio], about inclusion lists
- security [Office development in Visual Studio], inclusion lists
- inclusion lists [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9e2fea115b941af4b119b59dade16114cab3383d
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844231"
---
# <a name="trust-office-solutions-by-using-inclusion-lists"></a>Ekleme listelerini kullanarak Office çözümlerine güven
  Ekleme listeleri yayımcıyı tanımlayan bir sertifikayla imzalanmış Office çözümlerine güven verme olanağı verir. Ekleme listeleri kullanıcıya özeldir ve belge düzeyi özelleştirmeleri ve VSTO eklentileri için kullanılabilir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Bir kullanıcı bu kullanıcı için güven verilmemiş Office çözümünü başladığında, Microsoft Office çözümü ondan ile güvenlik kararı ister bir [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] güven istemi. Kullanıcı çözümü güven karar verirse, özelleştirme çalışır ve kullanıcı olmayan sorulup sonraki.  
  
## <a name="inclusion-list-and-windows-installer"></a>Ekleme listesi ve Windows Installer  
 Office çözümleriyle yükleme *Program Files* Windows Installer kullanarak dizin yönetici haklarını gerektirir. Office çözümleri için *Program Files* dizin, Office çalışma zamanı için Visual Studio Araçları Office çözümleri zaten FullTrust izni verilmiş olduğundan ekleme listesi artık denetler.  
  
## <a name="clickonce-trust-prompt"></a>ClickOnce güven istemi  
 Kullanarak [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] Office çözümleri, Yöneticiler için uygulama isteyen izin isteyen devre dışı bırakmak için güven istemi düzeyini yapılandırın veya güvenilen bir sertifika gerektirir. Bu yapılandırma erişimi denetleyen kayıt defteri anahtarını kullanarak yapılır ekleme listesi.  
  
 İstem devre dışıysa, güvenilir ve bilinen sertifikaya sahip çözümler yüklenebilir. İstem düzeyi gerekli Authenticode ayarlarsanız, çözüm bilinen yetkilisinden bir sertifika ile imzalanmalıdır, ancak bir sertifika bir güvenilen kök yetkilisi (güvenilen bir sertifika) bağlı gerektirmez. İsteme izin veriliyorsa, çözüm bilinmeyen kimliğe sahip bir sertifika ile imzalanabilir. Bu senaryoda, güven kararı son kullanıcıya ertelenmiş ve geçici bir sertifika çözümü yüklemek yeterli olacaktır.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: ekleme listesi güvenliğini yapılandırma](../vsto/how-to-configure-inclusion-list-security.md) ve Tablo 2 ' nin isteyen düzeyi kayıt defteri anahtarı değeri başlatmak etkiler, başlıklı [yapılandırma ClickOnce Güvenilen Yayımcılar](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="structure-of-the-inclusion-list"></a>Ekleme listesi yapısı  
 Geçerli ekleme listesi girdisi iki bölümden oluşur: dağıtım bildirimi ve çözümü imzalamak için kullanılan ortak anahtar için bir yol. Bir çözüm ekleme listesine eklendikten sonra kabul güvenilir. Office çözümü çalıştığında, Office uygulamasının şu anda çalışan çözüm özgün güvenilir sürümü ile aynı olduğunu doğrulamak için dağıtım bildiriminde imzalama anahtarı ekleme listesindeki ortak anahtarıyla karşılaştırır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md)   
 [Office çözümleri güvenli](../vsto/securing-office-solutions.md)  
  
  