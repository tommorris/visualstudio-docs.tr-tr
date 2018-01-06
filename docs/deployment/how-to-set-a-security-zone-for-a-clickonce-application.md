---
title: "Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, security settings
- code access security, ClickOnce applications
- security zones, ClickOnce applications
ms.assetid: d3dac454-518a-44d7-a76e-ccb7b9c3a150
caps.latest.revision: "18"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 86dbdf312c1356c6fb63fcfa32f1dd362b4c7599
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Bir Güvenlik Bölgesi Ayarlama
Kod erişimi güvenliği izinleri ClickOnce uygulaması için ayarladığınızda, temel bir izin kümesi ile başlatmak gereken **güvenlik** sayfasında **Proje Tasarımcısı**.  
  
 Çoğu durumda, aynı zamanda seçebilirsiniz **Internet** izinleri, sınırlı sayıda içeren bölge veya **yerel Intranet** daha geniş bir izin kümesi içeren bölge. Uygulamanız özel izinleri gerektiriyorsa, seçerek bunu yapabilirsiniz **özel** güvenlik bölgesi. Özel izinleri ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
### <a name="to-set-a-security-zone"></a>Bir güvenlik bölgesini ayarlamak için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Tıklatın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarlarını etkinleştir** onay kutusu.  
  
4.  Seçin **kısmi güven uygulamasıdır** seçenek düğmesi.  
  
     Denetimleri **ClickOnce güvenlik izinleri** bölüm etkinleştirilir.  
  
5.  İçinde **uygulamanız, gelen yüklenecek bölge** aşağı açılan listesinde, bir güvenlik bölgesi seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)