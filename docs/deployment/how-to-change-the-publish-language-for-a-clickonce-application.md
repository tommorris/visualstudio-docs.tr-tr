---
title: "Nasıl yapılır: değişiklik ClickOnce uygulaması için yayımlama dili | Microsoft Docs"
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
- Publish language property
- ClickOnce deployment, changing publish language
- publishing, ClickOnce
ms.assetid: ef5024c4-cda1-4970-bc75-32a2a10c92c3
caps.latest.revision: "19"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 1643a3bec79b6f0e1b89548ab1a62c3dfd6c6e9a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-change-the-publish-language-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Yayımlama Dilini Değiştirme
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, dil ve kültür geliştirme bilgisayarınızın Yükleme varsayılanlarını sırasında görüntülenen kullanıcı arabirimi. Yerelleştirilmiş bir uygulama yayımlıyorsanız bir dil ve kültür yerelleştirilmiş sürümle eşleştirmek üzere belirtmeniz gerekir. Bu belirlenir `Publish language` projeniz için özellik.  
  
 `Publish language` Özelliği, ayarlanabilir **Yayımla Seçenekleri** iletişim kutusu, erişilebilir **Yayımla** sayfasında **Proje Tasarımcısı**.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-change-the-publish-language"></a>Yayımlama dilini değiştirmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  Tıklatın **seçenekleri** açmak için düğmeye **Yayımla Seçenekleri** iletişim kutusu.  
  
4.  Tıklatın **açıklama**.  
  
5.  İçinde **Yayımla Seçenekleri** iletişim kutusunda, bir dil seçin ve gelen kültür **yayımlama dili** aşağı açılan listeyi ve ardından **Tamam**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)