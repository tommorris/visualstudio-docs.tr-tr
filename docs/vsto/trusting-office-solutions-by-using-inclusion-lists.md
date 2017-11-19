---
title: "Ekleme listelerini kullanarak Office çözümlerine güvenme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- inclusion lists [Office development in Visual Studio], about inclusion lists
- security [Office development in Visual Studio], inclusion lists
- inclusion lists [Office development in Visual Studio]
ms.assetid: 6dae0128-435b-4fa1-aed9-73e728fdcacf
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7e50809b5e57a832c9f085172832dd2e1a4db45a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="trusting-office-solutions-by-using-inclusion-lists"></a>Ekleme Listelerini Kullanarak Office Çözümlerine Güvenme
  Ekleme listeleri yayımcıyı tanımlayan bir sertifikayla imzalanmış Office çözümlerine güven verme olanağı verir. Ekleme listeleri kullanıcıya özeldir ve belge düzeyi özelleştirmeleri ve VSTO eklentileri için kullanılabilir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Bir kullanıcı bu kullanıcı için güven verilmemiş Office çözümünü başladığında, Microsoft Office çözümü ondan ile güvenlik kararı ister bir [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] güven istemi. Kullanıcı çözümü güven karar verirse, özelleştirme çalışır ve kullanıcı olmayan sorulup sonraki.  
  
## <a name="inclusion-list-and-windows-installer"></a>Ekleme listesi ve Windows Installer  
 Windows Installer kullanarak Office çözümleri Program dosyaları dizinine yüklemek için yönetici hakları gerekir. Office çözümleri zaten FullTrust izni verilmiş çünkü Program Files dizininde Office çözümleri için Office çalışma zamanı için Visual Studio Araçları ekleme listesi artık denetler.  
  
## <a name="clickonce-trust-prompt"></a>ClickOnce güven istemi  
 Kullanarak [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] Office çözümleri, Yöneticiler için uygulama isteyen izin isteyen devre dışı bırakmak için güven istemi düzeyini yapılandırın veya güvenilen bir sertifika gerektirir. Bu yapılandırma erişimi denetleyen kayıt defteri anahtarını kullanarak yapılır ekleme listesi.  
  
 İstem devre dışıysa, güvenilir ve bilinen sertifikaya sahip çözümler yüklenebilir. İstem düzeyi gerekli Authenticode ayarlarsanız, çözüm bilinen yetkilisinden bir sertifika ile imzalanmalıdır, ancak bir sertifika bir güvenilen kök yetkilisi (güvenilen bir sertifika) bağlı gerektirmez. İsteme izin veriliyorsa, çözüm bilinmeyen kimliğe sahip bir sertifika ile imzalanabilir. Bu senaryoda, güven kararı son kullanıcıya ertelenmiş ve geçici bir sertifika çözümü yüklemek yeterli olacaktır.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: ekleme listesi güvenliğini yapılandırma](../vsto/how-to-configure-inclusion-list-security.md) ve Tablo 2 ' nin isteyen düzeyi kayıt defteri anahtarı değeri başlatmak etkiler, başlıklı [yapılandırma ClickOnce Güvenilen Yayımcılar](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="structure-of-the-inclusion-list"></a>Ekleme listesi yapısı  
 Geçerli ekleme listesi girdisi iki bölümden oluşur: dağıtım bildirimi ve çözümü imzalamak için kullanılan ortak anahtar için bir yol. Bir çözüm ekleme listesine eklendikten sonra kabul güvenilir. Office çözümü çalıştığında, Office uygulamasının şu anda çalışan çözüm özgün güvenilir sürümü ile aynı olduğunu doğrulamak için dağıtım bildiriminde imzalama anahtarı ekleme listesindeki ortak anahtarıyla karşılaştırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md)   
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)  
  
  