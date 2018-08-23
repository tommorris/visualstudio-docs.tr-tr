---
title: 'Nasıl yapılır: uygulama simgesi (Visual Basic, C#) belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
ms.assetid: ad8e14ed-adc2-45b6-a0be-818b16d5616f
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d696766d2dd32ada86d74754dce87320e8f1627
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697490"
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Nasıl Yapılır: Uygulama Simgesi Belirtme (Visual Basic C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: uygulama simgesi (Visual Basic, C#) belirtme](https://docs.microsoft.com/visualstudio/ide/how-to-specify-an-application-icon-visual-basic-csharp).  
  
`Icon` Proje özelliği, dosya Gezgini ve Windows görev çubuğunda görüntülenecek simge dosyası (.ico) için derlenmiş uygulama belirtir.  
  
 `Icon` Özelliği erişilebilir **uygulama** bölmesinde **Proje Tasarımcısı**; bir projeye kaynaklar veya içerik dosyaları olarak eklenen simge listesi içerir.  
  
> [!NOTE]
>  Bir uygulama için bir Icon özelliği ayarlandıktan sonra ayrıca ayarlayabilirsiniz `Icon` her özellik **penceresi** veya **Form** uygulama. Windows Presentation Foundation (WPF) tek başına uygulamalar için pencere simgeleri hakkında daha fazla bilgi için bkz. <xref:System.Windows.Window.Icon%2A> özelliği.  
  
### <a name="to-specify-an-application-icon"></a>Uygulama simgesi belirtmek için  
  
1.  İçinde **Çözüm Gezgini**, bir proje düğümü seçin (değil **çözüm** düğümü).  
  
2.  Menü çubuğunda, **proje**, **özellikleri**.  
  
3.  Zaman **Proje Tasarımcısı** görüntülenirse, seçin **uygulama** sekmesi.  
  
4.  **(Visual Basic)**  İçinde **simgesi** listesinde, bir simge (.ico) dosyasını seçin.  
  
     **C#** neredeyse **simgesi** listesinde  **\<Gözat … >** düğmesini ve ardından istediğiniz simge dosyasının konumuna göz atın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Uygulama özelliklerini yönetme](../ide/application-properties.md)  
 [Nasıl yapılır: ekleme veya kaldırma kaynakları](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)



