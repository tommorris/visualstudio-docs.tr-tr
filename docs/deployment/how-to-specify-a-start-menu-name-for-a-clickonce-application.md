---
title: 'Nasıl yapılır: ClickOnce uygulaması için Başlat menüsü adı belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a089fa67c975496c56d29d2d55c2f055888c96d9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31558873"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Başlat Menüsü Adı Belirtme
Zaman bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamanın yüklü çevrimiçi ve çevrimdışı kullanım için bir giriş eklenen **Başlat** menü ve **Program Ekle veya Kaldır** listesi. Varsayılan olarak, görünen adı uygulama derlemesinin adını aynıdır, ancak ayarlayarak görünen adı değiştirebilirsiniz **ürün adı** içinde **Yayımla Seçenekleri** iletişim kutusu.  
  
 **Ürün adı** görüntülenir publish.htm sayfasında; yüklü çevrimdışı bir uygulama için giriş adı olacaktır **Başlat** menü ve bu da olacak gösterir adı **ekleme veya kaldırma Programları**.  
  
 **Yayımcı adı** yukarıdaki publish.htm sayfasında görünecek **ürün adı**, ve yüklü çevrimdışı bir uygulama için uygulamanın simgesini içeren klasörün adını olacaktır **Başlat**  menüsü.  
  
 Ayarlayabileceğiniz **ürün adı** ve **Yayımcı adı** özelliklerinde **Yayımla Seçenekleri** iletişim kutusu, kullanılabilir **Yayımla** sayfası **Proje Tasarımcısı**.  
  
### <a name="to-specify-a-start-menu-name"></a>Başlat menüsü adı belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **seçenekleri** açmak için düğmeye **Yayımla Seçenekleri** iletişim kutusu.  
  
4.  Tıklatın **açıklama**.  
  
5.  İçinde **Yayımla Seçenekleri** iletişim kutusunda, görüntülemek için bir ad girin **ürün adı**.  
  
6.  İsteğe bağlı olarak, bir yayımcı adını girebilirsiniz **Yayımcı adı**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)