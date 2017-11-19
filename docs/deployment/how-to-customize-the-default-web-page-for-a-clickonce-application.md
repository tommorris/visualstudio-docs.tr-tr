---
title: "Nasıl yapılır: ClickOnce uygulaması için varsayılan Web sayfasını özelleştirme | Microsoft Docs"
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
- Publish.htm Web page
- ClickOnce deployment default Web page
- deploying applications [ClickOnce], publishing
- publishing, ClickOnce
ms.assetid: 418de18c-bee9-4f24-9cd9-0252d175070d
caps.latest.revision: "14"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: fefafa0f9ea04a62d6ae79bd18834e36a1480f29
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-customize-the-default-web-page-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Varsayılan Web Sayfasını Özelleştirme
ClickOnce uygulaması için Web yayımlama sırasında bir Web sayfası otomatik olarak oluşturulur ve uygulama ile birlikte yayımlanır. Varsayılan sayfa adını uygulama ve uygulamayı yüklemek için önkoşulları yükleyin veya MSDN'de yardıma erişmek için bağlantılar içerir.  
  
> [!NOTE]
>  Sayfada gördüğünüz gerçek bağlantılar bilgisayar burada sayfa görüntülenir ve ne bağlı dahil olmak üzere önkoşulları.  
  
 Publish.htm Web sayfası için varsayılan addır; adını değiştirebilirsiniz **Proje Tasarımcısı**. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için bir yayımlama sayfası belirtme](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md).  
  
 Yalnızca yeni bir sürümü algılanırsa Publish.htm Web sayfası yayımlanır.  
  
> [!NOTE]
>  Yaptığınız değişiklikler, **Yayımla** ayarları Publish.htm sayfasında tek bir istisna etkilemez: başlangıçta yayımladıktan sonra önkoşulları ekleyip, önkoşul listesi artık doğru olacaktır. Değişiklikleri yansıtacak şekilde önkoşul bağlantı metnini düzenlemek gerekir.  
  
### <a name="to-customize-the-publish-web-page"></a>Yayımla Web sayfasını özelleştirme  
  
1.  ClickOnce uygulamanızı bir Web konumuna yayımlayın. Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
2.  Web sunucusunda Publish.htm dosyasını Visual Web Designer veya başka bir HTML Düzenleyicisi'ni açın.  
  
3.  İstediğiniz gibi sayfayı özelleştirmek ve kaydedin.  
  
4.  İsteğe bağlı. Visual Studio özelleştirilmiş yayımlama Web sayfanızın üzerine yazmasını engellemek için işaretini **otomatik olarak sonra dağıtım web sayfası oluşturmak her yayımlama** seçenekleri Yayımla iletişim kutusunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için bir yayımlama sayfası belirtme](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)