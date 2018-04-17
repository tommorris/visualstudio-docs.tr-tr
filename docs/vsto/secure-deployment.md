---
title: Güvenli dağıtımı | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- deploying applications [Office development in Visual Studio], security
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- ClickOnce deployment [Office development in Visual Studio], security
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1efc8087476cbe879a647288c35a7e7f329100a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="secure-deployment"></a>Güvenli Dağıtım
  Office çözümü oluşturduğunuzda, geliştirme bilgisayarınızda kod projenize çalışmasına izin vermek için otomatik olarak güncelleştirilir. Çözümünüzü dağıtırken, ancak, bir sertifika ile çözüm imzalama veya kullanarak güven kararı temel alacağı kanıt gerekir [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] güven istemi anahtarını. Daha fazla bilgi için bkz: [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Bir ağ konumuna belgeyi dağıtırsanız belge düzeyi özelleştirmeleri için Ayrıca belgenin konumunu Office uygulamasının Güven Merkezi'ndeki güvenilir konumlar listesine eklemeniz gerekir. Belge izinlerini son kullanıcı bilgisayarlarında nasıl ayarlandığı hakkında daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
## <a name="preventing-office-solutions-from-running-code"></a>Office çözümlerinde kod çalışmasını engelliyor  
 Yöneticiler, bir bilgisayarda çalışan tüm Office çözümleri önlemek için kayıt defterini kullanabilir. Yönetilen kod uzantısı olan bir Office çözümü açıldığında, Office çalışma zamanı denetimleri için Visual Studio Araçları bir giriş olup olmadığını adıyla `Disabled` altında bir bilgisayarda aşağıdaki kayıt defteri anahtarlarının bulunmaktadır:  
  
-   `HKEY_CURRENT_USER\Software\Microsoft\VSTO`  
  
-   `HKEY_LOCAL_MACHINE\Software\Microsoft\VSTO`  
  
 Office çözümlerinde kod çalıştırılmasını engellemek için oluşturma bir `Disabled` birine veya ikisine de bu kayıt defteri anahtarları altında girdisi ve aşağıdaki veri türlerini ve değerlerini belirtin `Disabled`:  
  
-   REG_SZ veya REG_EXPAND_SZ "0" (sıfır) dışında herhangi bir dizeye ayarlayın.  
  
-   0 (sıfır) dışında başka bir değere ayarlanmış REG_DWORD.  
  
 Kodu çalıştırmak Office çözümleri etkinleştirmek için her iki ayarlar `Disabled` girişleri 0 (sıfır) veya kayıt defteri girdilerini silin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Çalıştırmak veya Office çözümleri barındırmak için bilgisayarları hazırlama](http://msdn.microsoft.com/en-us/be1b173f-7261-4d74-aa4e-94ccd43db8d8)   
 [Office Çözümleri Güvenliğini Sağlama](../vsto/securing-office-solutions.md)  
  
  