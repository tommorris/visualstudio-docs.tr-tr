---
title: "Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama | Microsoft Docs"
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
- ClickOnce applications, permissions
- permissions, ClickOnce applications
ms.assetid: 660459ca-ef73-44a8-b323-610001f63b93
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 671f48cfac80595832f7aeee71e0e87388f947e6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-custom-permissions-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Özel İzinleri Ayarlama
Dağıtabilmeniz için bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Internet veya yerel Intranet bölgeleri için varsayılan izinler kullanan uygulama. Alternatif olarak, uygulamanın ihtiyacı özel izinler için özel bir bölge oluşturabilirsiniz. Bunu üzerinde güvenlik izinlerini özelleştirerek yapmak **güvenlik** sayfasında **Proje Tasarımcısı**.  
  
### <a name="to-customize-a-permission"></a>Bir izni özelleştirmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **güvenlik** sekmesi.  
  
3.  Seçin **ClickOnce güvenlik ayarlarını etkinleştir** onay kutusu.  
  
4.  Seçin **kısmi güven uygulamasıdır** seçenek düğmesi.  
  
     Denetimleri **ClickOnce güvenlik izinleri** bölüm etkinleştirilir.  
  
5.  Gelen **uygulamanız, gelen yüklenecek bölge** aşağı açılan listesinde, tıklatın **(özel)**.  
  
6.  Tıklatın **Edit Permissions XML**.  
  
     App.manifest dosyası XML Düzenleyicisi'nde açar.  
  
7.  Önce `</applicationRequestMinimum>` öğesi, uygulamanızın gerektirdiği izinler için XML kodunu ekleyin.  
  
    > [!NOTE]
    >  Kullanabileceğiniz `ToXml` yöntemi bir izin kümesi uygulama bildirimi için XML kodunu oluşturmak için. Örneğin, için XML oluşturmak için <xref:System.Security.Permissions.EnvironmentPermission> izin kümesi, çağrı <xref:System.Security.Permissions.EnvironmentPermission.ToXml%2A> yöntemi. XML izni yapısı hakkında daha fazla bilgi için bkz [NIB: nasıl yapılır: bir izin kümesi bir XML dosyası kullanarak içeri](http://msdn.microsoft.com/en-us/dea16b54-c108-408a-ac36-cdc05f746236).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)