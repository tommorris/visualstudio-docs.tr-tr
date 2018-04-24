---
title: 'Nasıl yapılır: ClickOnce uygulaması için varsayılan Web sayfasını özelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 743d7f259da4129eda578808d1ce04619104a3f1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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
 [Nasıl yapılır: ClickOnce Uygulaması için bir Yayımlama Sayfası Belirtme](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)