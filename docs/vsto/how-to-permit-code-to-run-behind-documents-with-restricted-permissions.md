---
title: 'Nasıl yapılır: kodun kısıtlı izinle belgelerin arkasında çalışmasına izin verme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Information Rights Management [Office development in Visual Studio]
- permissions [Office development in Visual Studio]
- IRM [Office development in Visual Studio]
- code [Office development in Visual Studio], running behind restricted documents
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: eb5b9421bd6d0228a93ba7ba7516c9ebc7b7c761
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Nasıl Yapılır: Kodun Kısıtlı İzinle Belgelerin Arkasında Çalışmasına İzin Verme
  Microsoft Office Bilgi Hakları Yönetimi (IRM) özelliğini, bir belge veya çalışma kitabı izinlerini kısıtlamak için kullanabilirsiniz. Varsayılan olarak, kısıtlı Microsoft Office Word belgesine veya Microsoft Office Excel çalışma kitabı arkasındaki kodda çalıştırma izni yok. Böylece, yönetilen kod uzantıları nesne modeline erişebilir ve çözümünüz çalışır varsayılan değiştirebilirsiniz.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Belge veya çalışma kitabının yazarı veya izin ayarlarını değiştirmek için tam denetim erişimi olması gerekir.  
  
### <a name="to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Kodun kısıtlı izinle belgelerin arkasında çalışmasına izin için  
  
1.  Belge veya çalışma kitabı Word veya Excel'de açın.  
  
2.  Tıklatın **dosya** sekmesinde, işaret **hazırlama**, işaret **izinleri kısıtla**ve ardından **kısıtlı erişim**.  
  
    > [!NOTE]  
    >  İlk kullanım Windows Rights Management istemcisini yüklemeniz istenir. İstemciyi yükledikten sonra adımları yineleyin gerekebilir.  
  
3.  İçinde **izin** iletişim kutusunda **bu belgeye erişimi kısıtlamak**ve ardından **diğer seçenekler**.  
  
4.  Altında **kullanıcılar için ek izinler**seçin **içeriğe programlamayla erişim**.  
  
 Word veya Excel nesne modeline programlı erişim izin verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bilgi Hakları Yönetimine ve yönetilen kod uzantılarına genel bakış](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Belge düzeyi çözümlerde belge koruması](../vsto/document-protection-in-document-level-solutions.md)   
 [Office belgelerinde parola koruması](../vsto/password-protection-on-office-documents.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  