---
title: 'Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 697632e70c8b72fa0b540c3b1652d5a110a4b085
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696074"
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Bir Güvenlik Bölgesi Ayarlama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](https://docs.microsoft.com/visualstudio/deployment/how-to-set-a-security-zone-for-a-clickonce-application).  
  
Temel bir izin kümesi ile başlatmak gereken kod erişim güvenlik izinlerini ClickOnce uygulaması için ayarladığınızda, **güvenlik** sayfasının **Proje Tasarımcısı**.  
  
 Çoğu durumda, ayrıca seçebilirsiniz **Internet** sınırlı bir izin kümesi içeren bir bölge veya **yerel Intranet** büyük bir izin kümesi içeren bir bölge. Uygulamanız özel izinleri gerektiriyorsa, bunu seçerek yapabilirsiniz **özel** güvenlik bölgesi. Özel izinleri ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
### <a name="to-set-a-security-zone"></a>Bir güvenlik bölgesi ayarlama  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Tıklayın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarlarını etkinleştirme** onay kutusu.  
  
4.  Seçin **kısmi güven uygulamasıdır** seçenek düğmesini.  
  
     Denetimlerde **ClickOnce güvenlik izinleri** bölüm etkinleştirilir.  
  
5.  İçinde **uygulamanızı yükleneceği kaynak bölge** aşağı açılan listesinde, bir güvenlik bölgesi seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)



