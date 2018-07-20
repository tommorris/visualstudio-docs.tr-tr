---
title: 'Nasıl yapılır: artırma ClickOnce yayım sürümünü otomatik olarak | Microsoft Docs'
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
ms.openlocfilehash: beada30e45ce2d46500654bca5051bd51db02d66
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151970"
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>Nasıl yapılır: otomatik olarak artırma ClickOnce yayım sürümü
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, değiştirme `Publish Version` özelliği, bir güncelleştirme olarak yayımlanacak uygulama neden olur. Varsayılan olarak, Visual Studio otomatik olarak artırır `Revision` sayısı `Publish Version` her zaman uygulama yayımlayın.  
  
 Bu davranışı devre dışı bırakabilirsiniz **Yayımla** sayfasının **Proje Tasarımcısı**.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>Yayınlama sürümünü otomatik olarak artırma devre dışı bırakmak için  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklayın **Yayımla** sekmesi.  
  
3.  İçinde **yayımlama sürümü** bölümünde, NET **her yayında düzeltmeyi otomatik artış** onay kutusu.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: ayarlama ClickOnce yayım sürümü](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)