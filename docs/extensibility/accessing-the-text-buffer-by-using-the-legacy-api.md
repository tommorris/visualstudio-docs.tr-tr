---
title: "Eski API kullanarak metin arabelleği erişim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text buffers
ms.assetid: cd6cf4ae-fff5-4e23-b293-7cbafdb8aed2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: facfc1670bf9d04035beffc47b7124bd5d309a7c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="accessing-the-text-buffer-by-using-the-legacy-api"></a>Eski API kullanarak metin arabelleği erişme
Metni metin akışları ve dosya Kalıcılık yönetilmesinden sorumludur. Arabellek okuma veya diğer biçimlere yazma rağmen arabellek ile tüm sıradan iletişim Unicode kullanılarak gerçekleştirilir. Eski API'leri metin arabelleği bir - ya da iki boyutlu bir koordinat sistemi arabelleği karakter konumları tanımlamak için kullanabilirsiniz.  
  
## <a name="one--and-two-dimension-coordinate-systems"></a>Bir ve iki boyutu sistemleri koordine  
 Tek boyutlu bir koordinat konumu ilk karakteri bir karakterin konumu arabellekteki 147 gibi temel alır. Kullandığınız <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> arabelleği tek boyutlu bir konuma erişmek için arabirim. İki boyutlu bir koordinat sistemi üzerinde satır ve dizin çiftleri temel alır. Örneğin, bir karakter 43 arabellekte 5 satırında 43, o satırdaki ilk karakter sağındaki beş karakter olabilir. Arabellek kullanarak iki boyutlu bir konuma erişim <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> arabirimi. Hem <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> arabirimleri metin arabelleği nesne tarafından uygulanan (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>) ve birbirlerinden kullanarak erişilebilir `QueryInterface`. Aşağıdaki diyagramda bu ve diğer anahtar arabirimler gösterilir <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 ![Metin arabellek nesnesi](../extensibility/media/vstextbuffer.gif "vsTextBuffer")  
Metin arabellek nesnesi  
  
 Her iki koordinat sistemi metin ara kullanılabilse de, iki boyutlu koordinatları kullanmak için optimize edilmiştir. Tek boyutlu bir koordinat sistemi performansa oluşturabilirsiniz. Bu nedenle, mümkün olduğunda iki boyutlu koordinat sistemi kullanır.  
  
 Arabellek ikinci sorumluluk dosya Kalıcılık metindir. Bunu yapmak için metin arabellek nesnesi uygulayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> ve proje öğeleri için belge veri nesnesi bileşeni ve kalıcı ilgili diğer ortam bileşenleri gibi davranır. Daha fazla bilgi için bkz: [açma ve kaydetme proje öğeleri](../extensibility/internals/opening-and-saving-project-items.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Eski API kullanarak görünüm ayarlarını değiştirme](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Eski API kullanarak Görünüm ayarlarının nasıl değiştirileceğini açıklar.  
  
 [Genel ayarları izlemek için metin Yöneticisi'ni kullanma](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Genel ayarları izlemek için metin Yöneticisi kullanımı açıklanmaktadır...  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçinde çekirdek Düzenleyicisi](../extensibility/inside-the-core-editor.md)