---
title: "Güvenli dağıtımı | Microsoft Docs"
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
- deploying applications [Office development in Visual Studio], security
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- ClickOnce deployment [Office development in Visual Studio], security
ms.assetid: c5ba86b1-e87f-4508-8c5a-1295681a9590
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c77d5fb404be8dda323720c1e0c1ab2c1887c88f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)  
  
  