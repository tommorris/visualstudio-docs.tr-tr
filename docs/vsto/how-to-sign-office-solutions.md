---
title: 'Nasıl yapılır: Office çözümlerini imzalama'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- certificates [Office development in Visual Studio], Office solutions
- security [Office development in Visual Studio], signing Office solutions
- signing manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d5fa4a837de66a39502e2c9e2d8466f3998acc4d
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34262197"
---
# <a name="how-to-sign-office-solutions"></a>Nasıl yapılır: Office çözümlerini imzalama
  Bir çözümü imzalarsanız, kanıt olarak sertifika kullanarak çözümlerine güven verebilirsiniz. Birden çok çözümleri için aynı sertifikayı kullanabilirsiniz ve tüm çözümler hiçbir ek güvenlik ilkesi güncelleştirmeleriyle güvenilen olacaktır.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Uygulamayı manuel olarak düzenlemeniz ve dağıtım bildirimlerini bildirim oluşturma ve düzenleme Aracı'nı kullanarak (*mage.exe* ve *mageui.exe*), kullanılmadan önce bildirimlerini yeniden imzalamanız gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: yeniden, uygulama ve dağıtım bildirimlerini imzalama](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="sign-by-using-a-certificate"></a>Bir sertifika kullanarak oturum açın  
 Bir sertifika benzersiz bir anahtar ve çözüm yayımcı kimliğini içeren bir dosyadır. Bir sertifika yetkilisinden sertifika satın alın veya kendi sertifikanızı oluşturabilir ve bunu oturum bir sertifika yetkilisi sağlayabilirsiniz.  
  
 Visual Studio hata ayıklamayı etkinleştirmek için geçici bir sertifika ile Office çözümlerini imzalar. Dağıtılan çözümlerinde durum kanıt olarak geçici sertifika kullanmamalısınız.  
  
### <a name="to-sign-an-office-solution-by-using-a-certificate"></a>Bir sertifika kullanarak Office çözümü imzalamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın * SolutionName ***özellikleri**.  
  
2.  Tıklatın **imzalama** sekmesi.  
  
3.  Seçin **ClickOnce bildirimlerini imzalayacak**.  
  
4.  Tıklayarak sertifikayı bulun **deposundan seçmek** veya **dosyasından seçin** ve sertifikada gezinin.  
  
5.  Doğru sertifikayı kullanılmakta olduğunu doğrulamak için tıklatın **daha fazla ayrıntı** sertifika bilgilerini görüntülemek için.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri güvenli](../vsto/securing-office-solutions.md)   
 [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md)   
 [İmzalama Sayfası, Proje Tasarımcısı](/visualstudio/ide/reference/signing-page-project-designer)  
  
  