---
title: "Nasıl yapılır: uygulama simgesi (Visual Basic, C#) belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
ms.assetid: ad8e14ed-adc2-45b6-a0be-818b16d5616f
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 17cce04dd94829225823de676e286b7d0158abec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Nasıl Yapılır: Uygulama Simgesi Belirtme (Visual Basic C#)
`Icon` Özelliği bir proje için dosya Gezgini ve Windows görev çubuğunda gösterilecek simge dosyası (.ico) derlenmiş uygulama için belirtir.  
  
 `Icon` Özelliği, içinde erişilebilir **uygulama** bölmesinde **Proje Tasarımcısı**; projeye kaynaklar veya içerik dosyaları olarak eklenen simgeler listesini içerir.  
  
> [!NOTE]
>  Bir uygulama için simge özelliğini ayarladıktan sonra aynı zamanda ayarlayabilirsiniz `Icon` her özellik **penceresi** veya **Form** uygulamadaki. Windows Presentation Foundation (WPF) bağımsız uygulamalar için pencere simgeleri hakkında daha fazla bilgi için bkz: <xref:System.Windows.Window.Icon%2A> özelliği.  
  
### <a name="to-specify-an-application-icon"></a>Uygulama simgesi belirtmek için  
  
1.  İçinde **Çözüm Gezgini**, proje düğümüne seçin (değil **çözüm** düğüm).  
  
2.  Menü çubuğunda seçin **proje**, **özellikleri**.  
  
3.  Zaman **Proje Tasarımcısı** görünen seçin **uygulama** sekmesi.  
  
4.  **(Visual Basic)**  İçinde **simgesi** listesinde, bir simge (.ico) dosyasını seçin.  
  
     **C#** yakınında **simgesi** listesinde, seçin  **\<Gözat... >** düğmesine tıklayın ve ardından istediğiniz simge dosyasının konumuna göz atın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Uygulama özelliklerini yönetme](../ide/application-properties.md)  
 [Nasıl yapılır: ekleme veya kaldırma kaynakları](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)