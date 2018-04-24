---
title: Hata ayıklama güvenliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], security
- debugger, security
- security [Visual Studio], debugging best practices
ms.assetid: d4fc3c43-e844-419c-8dbb-551cc2a9b09e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e3824bc4bc4f51baf822caee11a5fb4c106fa9e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="debugger-security"></a>Hata Ayıklama Güvenliği
Başka bir işlemde hata ayıklamak için Aksi takdirde, özellikle uzaktan hata ayıklama sırasında olurdu olmayan çok geniş powers sağlar. Kötü amaçlı bir hata ayıklayıcısı ayıklanacak makinede yaygın zarar verebilecek.  
  
 Bununla birlikte, çoğu geliştiricinin bir güvenlik tehdidi ters yönde akmasını sağlamak farkında olun değil. Kötü amaçlı kod ayıklayıcı işleminde hata ayıklama makine güvenliğini tehlikeye mümkündür: bir dizi karşı korumalı olacak güvenlik açıkları vardır.  
  
## <a name="security-best-practices"></a>En İyi Güvenlik Uygulamaları  
 Hata ayıklama yaptığınız kod hata ayıklayıcı arasında örtük güven ilişkisi yoktur. Bir şey hata ayıklamak istekli olup olmadığını da çalıştırmak istekli olmalıdır. Alt çizgi, ne ayıkladığınız güvenemez olmalıdır ' dir. Güven olamaz, ardından ayıklama değil ya da bir makineden tehlikeye destekleyebilir ve yalıtılmış bir ortamda ayıklama.  
  
 Olası saldırı yüzeyini azaltmak için hata ayıklama üretim makinelerde devre dışı bırakılmalıdır. Aynı nedenden dolayı hata ayıklama hiçbir zaman süresiz olarak etkinleştirilmesi gerekir.  
  
### <a name="managed-debugging-security"></a>Yönetilen hata ayıklama güvenliği  
 Burada, tüm yönetilen hata ayıklama uygulanır bazı genel öneriler bulunmaktadır.  
  
-   Güvenilmeyen bir kullanıcının işlemine iliştirme dikkatli olun: Bunu yaptığınızda, güvenilir olduğunu varsayın. Güvenilmeyen bir kullanıcının işleme iliştirilemiyor denediğinizde, bir güvenlik uyarısı iletişim kutusu onay işlemine eklemek istediğinizi soran görünür. "Kullanıcıların güvenilen", içerir, ve bir dizi standart kullanıcıların yaygın olarak .NET Framework yüklediyseniz, aşağıdaki gibi makinelerde tanımlanan **aspnet**, **localsystem**, **networkservice**, ve **yerelhizmet**. Daha fazla bilgi için bkz: [güvenlik uyarısı: güvenilmeyen bir kullanıcıya ait bir işlem ekleme tehlikeli olabilir. Aşağıdaki bilgiler şüpheli görünüyorsa veya emin değilseniz, bu işlem için eklemeyin](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md).  
  
-   Internet ve içine yüklenirken kapalı bir proje yüklerken dikkatli olun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bu, çok bile hata ayıklama olmadan yapmak için risklidir. Bunu yaptığınızda, projeyi ve içerdiği kodu güvenilir olduğunu varsayarak.  
  
 Daha fazla bilgi için bkz: [yönetilen kod hata ayıklama](../debugger/debugging-managed-code.md).  
  
### <a name="remote-debugging-security"></a>Uzaktan hata ayıklama güvenliği  
 Yerel hata ayıklama, uzaktan hata ayıklama daha genellikle güvenlidir. Uzaktan hata ayıklama araştırılan toplam yüzey alanını artırır.  
  
 Visual Studio uzaktan hata ayıklama İzleyicisi (msvsmon.exe) uzaktan hata ayıklama kullanılır ve bu yapılandırma için çeşitli güvenlik önerileri vardır. Hayır kimlik doğrulama modu güvensiz olduğundan Windows kimlik doğrulaması, kimlik doğrulama modunu yapılandırmak için tercih edilen yöntem değildir.  
  
 ![Hata iletişim kutusu](../debugger/media/dbg_err_remotepermissionschanged.png "DBG_ERR_RemotePermissionsChanged")  
  
 Windows kimlik doğrulaması modunu kullanırken, kullanıcıya bilgisayardaki tüm izinleri verilir çünkü bir güvenilmeyen kullanıcı için msvsmon bağlanma izni verme tehlikeli olduğundan emin olun...  
  
 Uzak makinedeki bilinmeyen bir işlem hata ayıklama değil: hata ayıklayıcı çalıştıran makine etkileyebilir veya msvsmon.exe, Visual Studio uzaktan hata ayıklama İzleyicisi tehlikeye olası açıkları vardır. Bilinmeyen bir işlem kesinlikle hata ayıklama gerekir, yerel olarak hata ayıklama deneyin ve yerelleştirilmiş tüm olası tehditler tutmak için bir Güvenlik Duvarı'nı kullanın.  
  
 Daha fazla bilgi için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
### <a name="web-services-debugging-security"></a>Web Hizmetleri güvenlik hata ayıklama  
 Yerel olarak hata ayıklama daha güvenlidir, ancak sonra büyük olasılıkla sahip olmadığınız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] web sunucusunda yüklüyse, yerel hata ayıklama pratik olmayabilir. Genellikle, Web hizmetlerinde hata ayıklama işlemi, uzaktan, geliştirme sırasında bu nedenle uzaktan hata ayıklama güvenlik önerilerini de hata ayıklama Web hizmet için geçerli dışında gerçekleştirilir. Burada, bazı ek en iyi yöntemler verilmiştir. Daha fazla bilgi için bkz: [hata ayıklama XML Web Hizmetleri](http://msdn.microsoft.com/en-us/c900b137-9fbd-4f59-91b5-9c2c6ce06f00).  
  
-   Güvenliği aşılmış bir Web sunucusunda hata ayıklama etkinleştirmeyin.  
  
-   Hata ayıklama önce Web sunucusu güvenli olduğunu bildiğinizden emin olun. Güvenli olduğundan emin değilseniz, hata ayıklama değil.  
  
-   Internet'te kullanıma sunulan bir Web hizmeti hata ayıklama, özellikle dikkatli olun.  
  
### <a name="external-components"></a>Dış bileşenler  
 Özellikle kodu yazmadı varsa programınızı etkileşimde dış bileşenlere güven durumunu unutmayın. Ayrıca bileşenlerinin unutmayın, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya hata ayıklayıcı kullanabilirsiniz.  
  
### <a name="symbols-and-source-code"></a>Simgeler ve kaynak kodu  
 İki [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] göz önünde bulundurulması güvenlik gerektiren araçlar şunlardır:  
  
-   Kaynak sunucu, kaynak kodu kaynak kodu depodan sürümleriyle sağlar. Bir programın kaynak kodunun geçerli sürümünün olmadığında yararlıdır. [Güvenlik Uyarısı: Hata ayıklayıcı güvenilmeyen komut yürütmeli](../debugger/security-warning-debugger-must-execute-untrusted-command.md).  
  
-   Simgeler sağlamak için kullanılan simge sunucusunu bir kilitlenme sırasında sistem çağrısı hata ayıklamak gerekli.  
  
 Bkz: [simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Güvenlik Uyarısı: Güvenilmeyen bir kullanıcının sahip olduğu işleme ekleme tehlikeli olabilir. Aşağıdaki bilgiler şüpheli görünüyorsa veya emin değilseniz, bu işlem için eklemeyin](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md)   
 [Güvenlik Uyarısı: Hata ayıklayıcı güvenilmeyen komut yürütmeli](../debugger/security-warning-debugger-must-execute-untrusted-command.md)