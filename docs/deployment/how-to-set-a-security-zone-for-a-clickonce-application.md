---
title: 'Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, security settings
- code access security, ClickOnce applications
- security zones, ClickOnce applications
ms.assetid: d3dac454-518a-44d7-a76e-ccb7b9c3a150
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9be6bd056473a6cdf7d4bf3bef2aedafe5ae2143
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31564554"
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