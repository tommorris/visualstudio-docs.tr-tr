---
title: "Nasıl yapılır: Office çözümlerini imzalama | Microsoft Docs"
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
- certificates [Office development in Visual Studio], Office solutions
- security [Office development in Visual Studio], signing Office solutions
- signing manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2883f75c6ca75e1875621f9c6779db09722d6945
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-sign-office-solutions"></a>Nasıl Yapılır: Office Çözümlerini İmzalama
  Bir çözümü imzalarsanız, kanıt olarak sertifika kullanarak çözümlerine güven verebilirsiniz. Birden çok çözümleri için aynı sertifikayı kullanabilirsiniz ve tüm çözümler hiçbir ek güvenlik ilkesi güncelleştirmeleriyle güvenilen olacaktır.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Kullanabilmek için önce uygulama manuel olarak düzenlemeniz ve bildirim oluşturma ve düzenleme aracı (mage.exe ve mageui.exe) kullanarak dağıtım bildirimleri, bildirimlerini yeniden imzalamanız gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: yeniden imzalama uygulama ve dağıtım bildirimlerini](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="signing-by-using-a-certificate"></a>Bir sertifika kullanarak imzalama  
 Bir sertifika benzersiz bir anahtar ve çözüm yayımcı kimliğini içeren bir dosyadır. Bir sertifika yetkilisinden sertifika satın alın veya kendi sertifikanızı oluşturabilir ve bunu oturum bir sertifika yetkilisi sağlayabilirsiniz.  
  
 Visual Studio hata ayıklamayı etkinleştirmek için geçici bir sertifika ile Office çözümlerini imzalar. Dağıtılan çözümlerinde durum kanıt olarak geçici sertifika kullanmamalısınız.  
  
#### <a name="to-sign-an-office-solution-by-using-a-certificate"></a>Bir sertifika kullanarak Office çözümü imzalamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın *SolutionName***özellikleri**.  
  
2.  Tıklatın **imzalama** sekmesi.  
  
3.  Seçin **ClickOnce bildirimlerini imzalayacak**.  
  
4.  Tıklayarak sertifikayı bulun **deposundan seçmek** veya **dosyasından seçin** ve sertifikada gezinin.  
  
5.  Doğru sertifikayı kullanılmakta olduğunu doğrulamak için tıklatın **daha fazla ayrıntı** sertifika bilgilerini görüntülemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md)   
 [İmzalama Sayfası, Proje Tasarımcısı](/visualstudio/ide/reference/signing-page-project-designer)  
  
  