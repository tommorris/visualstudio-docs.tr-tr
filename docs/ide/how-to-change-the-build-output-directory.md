---
title: "Nasıl yapılır: yapı çıktı dizinini değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ccbb32b9fd035a9058812eb5a3df306ff629086f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-change-the-build-output-directory"></a>Nasıl Yapılır: Derleme Çıktı Dizinini Değiştirme
Çıktı konumunu projeniz tarafından oluşturulan bir başına yapılandırma temelini (hata ayıklama, yayın veya her ikisi de) belirtebilirsiniz.  
  
> [!NOTE]
>  Varsa bir **Kurulum** projesi bu makalenin sonundaki nota bakın.  
  
## <a name="changing-the-build-output-directory"></a>Derleme çıktı dizinini değiştirme  
  
#### <a name="to-change-the-build-output-directory"></a>Derleme çıktı dizinini değiştirme  
  
1.  Menü çubuğunda seçin **proje**, *Appname* **özellikleri**. Ayrıca, proje düğümüne sağ **Çözüm Gezgini** seçip **özellikleri**.  
  
2.  Visual Basic projesinde varsa, seçin **derleme** sekmesi. Visual C# projesinde varsa, seçin **yapı** sekmesi. C++ projesi ya da bir JavaScript projesini varsa, seçin **genel** sekmesi.  
  
3.  Yapılandırmada açılan en üstte, yapılandırmayı çıktısı seçin. dosya konumu (hata ayıklama, yayın veya tümü) değiştirmek istiyor.  
  
     Çıkış yolu girişini bulun (**yapı çıkış yolu** Visual Basic'te **çıktı dizini** Visual C++ ' ta **çıkış yolu** JavaScript ve C#). Proje dizininin göre yeni bir derleme çıktı dizinini belirtin.  
  
> [!NOTE]
>  Kurulum projesinde **çıktı dosyası adını** kutusu yalnızca proje dosyalarının konumu değil Setup.exe dosyasının konumunu değiştirir. Daha fazla bilgi için bkz: **derleme, yapılandırma özellikleri dağıtım projesi Özellikleri iletişim kutusu**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-page-project-designer-csharp.md)   
 [Genel özellik sayfası (Proje)](/cpp/ide/general-property-page-project)   
 [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)