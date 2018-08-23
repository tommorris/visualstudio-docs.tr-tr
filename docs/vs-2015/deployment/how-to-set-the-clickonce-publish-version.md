---
title: 'Nasıl yapılır: ayarlama ClickOnce yayım sürümü | Microsoft Docs'
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
- ClickOnce deployment, setting publish version
- publishing, ClickOnce
- Publish Version property
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: d832f28ddbd12bd72d018c841cf114ddae709e38
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694630"
---
# <a name="how-to-set-the-clickonce-publish-version"></a>Nasıl yapılır: ClickOnce Yayım Sürümü'nü Ayarlama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: ClickOnce yayımla sürümünü ayarlama](https://docs.microsoft.com/visualstudio/deployment/how-to-set-the-clickonce-publish-version).  
  
[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] `Publish Version` Özelliği yayımlamakta olduğunuz uygulamayı güncelleştirme olarak kabul edilip edilmeyeceğini belirler. Her zaman sürümü artırılır, uygulama bir güncelleştirme olarak yayımlanır.  
  
 `Publish Version` Özelliği, üzerinde ayarlanabilir **Yayımla** sayfasının **Proje Tasarımcısı**.  
  
> [!NOTE]
>  Otomatik artış bir proje seçeneği `Publish Version` özelliği her zaman uygulama yayımlanır; bu seçenek varsayılan olarak etkindir. Daha fazla bilgi için [nasıl yapılır: ClickOnce yayımlama sürüm otomatik artış](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md).  
  
### <a name="to-change-the-publish-version"></a>Yayımla sürümünü değiştirmek için  
  
1.  Seçili bir projeyle **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Tıklayın **Yayımla** sekmesi.  
  
3.  İçinde **yayımlama sürümü** artış, alan **ana**, **küçük**, **derleme**, veya **düzeltme** sürümü sayı.  
  
    > [!NOTE]
    >  Hiçbir zaman bir sürüm numarası azaltmayın. Bunun yapılması, bu nedenle öngörülemeyen güncelleştirme davranışlara neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Nasıl yapılır: otomatik olarak artırma ClickOnce yayım sürümü](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



