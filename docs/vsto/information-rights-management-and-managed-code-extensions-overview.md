---
title: "Bilgi Hakları Yönetimine ve yönetilen kod uzantılarına genel bakış | Microsoft Docs"
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
- Information Rights Management [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- IRM [Office development in Visual Studio]
- documents [Office development in Visual Studio], restricted permissions
- rights management [Office development in Visual Studio]
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 561f17acd17cb34892d3f2d4f0eefa05dfced0e4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="information-rights-management-and-managed-code-extensions-overview"></a>Bilgi Hakları Yönetimine ve Yönetilen Kod Uzantılarına Genel Bakış
  Microsoft Office Word ve Microsoft Office Excel, yetkisiz kişilerin hassas bilgileri görmesini veya değiştirmesini önlemeye yardımcı olabilecek bir özellik olan Bilgi Hakları Yönetimi (IRM) sağlar. Bilgi Hakları Yönetimi nasıl çalıştığı hakkında daha fazla bilgi için belirli Office uygulamasında yardımına bakın.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="running-code-behind-documents-with-restricted-permissions"></a>Kısıtlı izinle belgelerin arkasında kodu çalıştırma  
 Çözümünüzü bir belge veya varsayılan olarak, IRM kullanan çalışma kitabındaki içeriyorsa, Word ve Excel herhangi kodun çalışmasına izin vermez. Belgenin yazarını olan veya tam denetim erişimi varsa, böylece çözümünüzün çalışması varsayılan değiştirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: çalıştırma arkasında kısıtlı izinle belgelerin koduna izin](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md).  
  
 IRM kullanımını engeller <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> belgede önbelleğe alınmış veriyi almak veya değiştirmek için.  
  
## <a name="end-users-restricting-permissions-to-documents-that-use-managed-code-extensions"></a>Son kullanıcılar yönetilen kod uzantıları kullanan belgeler için izinlerini kısıtlayarak  
 IRM çözümünüzde belge veya çalışma kitabına tam denetim erişimi olan herkes izinleri kısıtlamak için kullanabilirsiniz. Örneğin, muhasebe departmanındaki bir son kullanıcı veritabanından verilerle çalışma otomatik olarak dolduran bir çözüm kullanıyorsa, bu kullanıcı yalnızca kendi departmanında kişilere erişimi değiştir ve başkaları için okuma erişimi izin vermek isteyebilirsiniz. Kullanıcı kısıtlı izinleri eklediğinde, varsayılan olarak, çalışma sayfası arka plan kod çalıştırılamıyor ve çalışma ile verileri doldurulmaz.  
  
 Sorunu düzeltmek için belge veya çalışma kitabına tam denetim erişim biriyle nesne modeli programlı erişmesine izin vermek için varsayılan izin ayarlarını değiştirmeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: çalıştırma arkasında kısıtlı izinle belgelerin koduna izin](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge düzeyi çözümlerde belge koruması](../vsto/document-protection-in-document-level-solutions.md)   
 [Office belgelerinde parola koruması](../vsto/password-protection-on-office-documents.md)   
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office Çözümleri Tasarlama ve Oluşturma](../vsto/designing-and-creating-office-solutions.md)  
  
  