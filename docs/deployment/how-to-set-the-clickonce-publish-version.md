---
title: 'Nasıl yapılır: kümesi ClickOnce yayım sürümünü | Microsoft Docs'
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
- ClickOnce deployment, setting publish version
- publishing, ClickOnce
- Publish Version property
ms.assetid: 06f15504-6385-40a6-b01d-cd90ca36dc73
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: a0f96a3837a2c3a05a8fac20a9b6e5d4448f9c7e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-set-the-clickonce-publish-version"></a>Nasıl yapılır: ClickOnce Yayım Sürümü'nü Ayarlama
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] `Publish Version` Özelliği, yayımladığınız uygulama bir güncelleştirme olarak kabul edilip edilmeyeceğini belirler. Her zaman sürümü artırılır, uygulama bir güncelleştirme olarak yayımlanır.  
  
 `Publish Version` Özelliği, üzerinde ayarlanabilir **Yayımla** sayfasında **Proje Tasarımcısı**.  
  
> [!NOTE]
>  Otomatik olarak artırır proje bir seçenek yoktur `Publish Version` özelliği her zaman uygulama yayımlanır; bu seçenek varsayılan olarak etkindir. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce yayımlama sürümü otomatik olarak Artır](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md).  
  
### <a name="to-change-the-publish-version"></a>Yayımla sürümünü değiştirmek için  
  
1.  Seçili bir proje ile **Çözüm Gezgini**, **proje** menüsünü tıklatın **özellikleri**.  
  
2.  Tıklatın **Yayımla** sekmesi.  
  
3.  İçinde **yayımlama sürümü** alan, Artır **ana**, **küçük**, **yapı**, veya **düzeltme** sürümü sayıları.  
  
    > [!NOTE]
    >  Hiçbir zaman bir sürüm numarası azaltmayın. Bunu yaparsanız, bu nedenle öngörülemeyen güncelleştirme davranışlara neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Nasıl yapılır: otomatik olarak artırma ClickOnce yayım sürümünü](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)