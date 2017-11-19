---
title: "SharePoint paketleme ve dağıtımını genişletme | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
ms.assetid: 4789ebb2-12bc-42b9-9427-e63d77137765
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b88c89d9464b5ac9bc588c4364de97c1f4e281d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-sharepoint-packaging-and-deployment"></a>SharePoint Paketleme ve Dağıtımını Genişletme
  Paketleme ve dağıtım işlemini SharePoint projeleri için genişletebilirsiniz.
  
##  <a name="creating-deployment-steps"></a>Dağıtım adımları oluşturma  
 Bir SharePoint projesi dağıttığınızda [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] dağıtım adımları, bir dizi yürütür. Visual Studio geri çekilen ve çözümleri ekleme gibi pek çok görev için yerleşik dağıtım adımlarını içerir. Ancak, kendi dağıtım adımları da oluşturabilirsiniz.  
  
 Bir dağıtım adımı oluşturma izlenecek yol için bkz: [izlenecek yol: SharePoint projeleri için bir özel dağıtım adımı oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).  
  
##  <a name="creating-deployment-configurations"></a>Dağıtım yapılandırmaları oluşturma  
 Dağıtım yapılandırması için belirli bir projenin yürütülür, ancak tüm SharePoint Proje öğeleri etkileyebilecek dağıtım adımları kümesidir. Her dağıtım yapılandırması Proje dağıtıldığında çalıştırılan adımları bir kümesini ve projeyi geri çekilebilir durumda çalıştırılan başka bir kümesini içerir. [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)]iki yerleşik dağıtım yapılandırmaları içerir, ancak Ayrıca kendi oluşturabilirsiniz. Dağıtım Yapılandırması oluşturduğunuzda, yerleşik dağıtım ve oluşturduğunuz dağıtım adımlar içerebilir.  
  
 Dağıtım yapılandırmasının nasıl oluşturulacağını izlenecek yol için bkz: [izlenecek yol: SharePoint projeleri için bir özel dağıtım adımı oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).  
  
##  <a name="run-code-when-a-sharepoint-solution-is-deployed-or-retracted"></a>Çalışma kodu, bir SharePoint dağıtıldığında veya geri çekildiğinde çözümdür  
 Bir SharePoint çözüm dağıtıldığında veya geri çekilebilir ek görevleri gerçekleştirmek için olayları işleyebilirsiniz. Visual Studio aşağıdaki senaryolarda işleyebilir olaylar oluşur:  
  
-   Önce ve sonra her bir dağıtım adımı için bir SharePoint proje öğesi yürütülür. Daha fazla bilgi için bkz: [nasıl yapılır: çalıştırma zaman dağıtım adımları yürütüldüğünde kodu](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md).  
  
-   İlk ve son bir SharePoint projesi dağıtıldığında veya geri çekilebilir sonra. Daha fazla bilgi için bkz: [nasıl yapılır: çalıştırma kodu bir SharePoint projesi dağıtıldığında veya geri çekildiğinde olduğu](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md).  
  
##  <a name="handling-deployment-conflicts"></a>Dağıtım çakışmalarını işleme  
 SharePoint Proje öğeleri, modüller, Web bölümleri, liste örnekleri ve içerik türleri gibi bazı türleri yerleşik dağıtım Çakışma çözümlemesi sağlar. Bu proje öğelerinden birini içeren bir çözümü dağıttığınızda, Visual Studio önce bir dosya adı, URL veya kimliği olan SharePoint sitesi üzerinde dağıttığınız öğesi bir dosya olarak zaten olup olmadığını denetler. Bir çakışma varsa, Visual Studio otomatik olarak bir çakışmayı çözebildiğinde veya çakışmayı veya dağıtımı iptal Visual Studio'nun isteyip istemediğinizi belirlemenizi isteyebilir. Daha fazla bilgi için bkz: [sorun giderme SharePoint paketleme ve dağıtım](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).  
  
 Bu özellik olup olmadığını denetler ve dağıtım çakışmaları çözümlenen kendi kodunuzu sağlayarak genişletebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: dağıtım çakışmalarını işleme](../sharepoint/how-to-handle-deployment-conflicts.md).  
  
##  <a name="run-command-line-operations-before-or-after-a-project-is-deployed"></a>Komut satırı işlemleri önce veya sonra bir proje dağıtılır  
 Bir SharePoint çözüm dağıtıldığında bir komut satırı işlemini çalıştırmak istiyorsanız, ayarlayabileceğiniz <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PreDeploymentCommand%2A> ve <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PostDeploymentCommand%2A> özelliklerini bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> nesnesi. Visual Studio önce ve projeyi dağıtıldıktan sonra bu komutları yürütür.  
  
 Bazı durumlarda, dağıtım çakışmaları görebilirsiniz. Çakışmaları çözümlemek için birkaç farklı yolu vardır. Daha fazla bilgi için bkz: [sorun giderme SharePoint paketleme ve dağıtım](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).  
  
##  <a name="customizing-validation-rules"></a>Doğrulama kuralları özelleştirme  
 Bir çözüm paketi (.wsp) dağıtmadan önce özel özellik ve paket özelliği veya paket geçerli olduğunu doğrulamak için doğrulama kuralları oluşturabilirsiniz. Örneğin, doğrulama sorunları gidermeye yardımcı olmak için geliştiricilere bilgileri, uyarılar veya hatalar bildirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: özel özellik oluşturmak ve paket doğrulama kuralları SharePoint çözümleri için](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: çalışma zaman dağıtım adımları yürütüldüğünde kodu](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)   
 [İzlenecek yol: SharePoint projeleri için özel bir dağıtım adımı oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [Nasıl yapılır: SharePoint çözümleri için özel özellik ve paket doğrulama kuralları oluşturma](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)   
 [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  
