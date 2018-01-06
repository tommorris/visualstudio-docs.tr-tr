---
title: "Nasıl yapılır: Visual Studio dosyaları nereye kopyalayacağını belirtme | Microsoft Docs"
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
- publishing, specifying location
- Publish Location property
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
caps.latest.revision: "12"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 9392686e08048ea88615b927cf942d66a4b9a06c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>Nasıl yapılır: Visual Studio'nun Dosyaları Nereye Kopyalayacağını Belirtme
ClickOnce kullanarak bir uygulamayı yayımladığınızda `Publish Location` özelliği, burada bildirimi ve uygulama dosyalarını konur konumu belirtir. Bu, bir dosya yolu veya FTP sunucusu yolu olabilir.  
  
 Belirleyebileceğiniz `Publish Location` özelliği **Yayımla** sayfasında **Proje Tasarımcısı**, veya Yayımlama Sihirbazı'nı kullanarak. Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
> [!NOTE]
>  ClickOnce kullanarak bir uygulama birden fazla sürümünü yüklediğinizde, yükleme uygulamanın önceki sürümleri arşivindeki belirttiğiniz yayımlama konumu adlı bir klasöre taşır. Bu şekilde tutar önceki sürümlerde yükleme dizinini temizleyin önceki sürümünden klasörlerinin arşivleme.  
  
### <a name="to-specify-a-publishing-location"></a>Bir yayımlama konumu belirtmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünde tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  İçinde **yayımlama konumu** alanında, aşağıdaki biçimlerden birini kullanarak yayımlama konumu girin:  
  
    -   Bir dosya paylaşımını veya disk yoluna yayımlamak için bir UNC yolu kullanılarak yolunu girin (\\\Server\ApplicationName) veya bir dosya yolu (C:\Deploy\ApplicationName).  
  
    -   Bir FTP sunucusuna yayımlamak için ftp://ftp.microsoft.com/ApplicationName biçimini kullanarak yolunu girin.  
  
     Metin mevcut olması gerektiğini unutmayın **yayımlama konumu** Gözat sırayla kutusunda (**...** ) düğmesinin çalışması için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)