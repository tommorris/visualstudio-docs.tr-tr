---
title: 'Nasıl yapılır: uygulama simgesi (Visual Basic, C#) belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b5e2984e9da7d3df4187c1a32b481ed0a70c876d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Nasıl Yapılır: Uygulama Simgesi Belirtme (Visual Basic C#)

`Icon` Özelliği bir proje için dosya Gezgini ve Windows görev çubuğunda gösterilecek simge dosyası (.ico) derlenmiş uygulama için belirtir.

`Icon` Özelliği, içinde erişilebilir **uygulama** bölmesinde **Proje Tasarımcısı**; projeye kaynaklar veya içerik dosyaları olarak eklenen simgeler listesini içerir.

> [!NOTE]
> Bir uygulama için simge özelliğini ayarladıktan sonra aynı zamanda ayarlayabilirsiniz `Icon` her özellik **penceresi** veya **Form** uygulamadaki. Windows Presentation Foundation (WPF) bağımsız uygulamalar için pencere simgeleri hakkında daha fazla bilgi için bkz: <xref:System.Windows.Window.Icon%2A> özelliği.

## <a name="to-specify-an-application-icon"></a>Uygulama simgesi belirtmek için

1. İçinde **Çözüm Gezgini**, proje düğümüne seçin (değil **çözüm** düğüm).

1. Menü çubuğunda seçin **proje** > **özellikleri**.

1. Zaman **Proje Tasarımcısı** görünen seçin **uygulama** sekmesi.

1. **(Visual Basic)**  &mdash;İçinde **simgesi** listesinde, bir simge (.ico) dosyasını seçin.

    **C#**&mdash;yakınında **simgesi** listesinde, seçin  **\<Gözat... >** düğmesine tıklayın ve ardından istediğiniz simge dosyasının konumuna göz atın.

## <a name="see-also"></a>Ayrıca bkz.

[Uygulama Sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[Uygulama Sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md)
