---
title: 'Nasıl yapılır: otomatik olarak artırma ClickOnce yayım sürümünü | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 178599f8f32ff2cbe1c12996eafb15feee62d463
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>Nasıl yapılır: ClickOnce Yayım Sürümünü Otomatik Olarak Artırma
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] değiştirmek uygulamanın `Publish Version` özellik, bir güncelleştirme olarak yayımlanan uygulamaya eklenmesine neden olur. Varsayılan olarak, Visual Studio otomatik olarak arttırır `Revision` sayısı `Publish Version` her uygulama yayımlayın.  
  
 Bu davranışı devre dışı bırakabilirsiniz **Yayımla** sayfasında **Proje Tasarımcısı**.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>Yayımla sürümünü otomatik olarak artırma devre dışı bırakmak için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  İçinde **yayımlama sürümü** bölümünde, Temizle **otomatik olarak her sürüm düzeltmelerle Artır** onay kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: kümesi ClickOnce yayım sürümünü](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)