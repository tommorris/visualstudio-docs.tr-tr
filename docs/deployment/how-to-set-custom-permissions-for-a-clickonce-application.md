---
title: 'Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, permissions
- permissions, ClickOnce applications
ms.assetid: 660459ca-ef73-44a8-b323-610001f63b93
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 62c9d97b73c1c640f6fbc1ced15936be86f38e29
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
    >  Kullanabileceğiniz `ToXml` yöntemi bir izin kümesi uygulama bildirimi için XML kodunu oluşturmak için. Örneğin, için XML oluşturmak için <xref:System.Security.Permissions.EnvironmentPermission> izin kümesi, çağrı <xref:System.Security.Permissions.EnvironmentPermission.ToXml%2A> yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce Uygulamalarının Güvenliğini Sağlama](../deployment/securing-clickonce-applications.md)