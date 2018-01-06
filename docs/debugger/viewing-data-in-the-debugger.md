---
title: "Hata ayıklayıcıda veri özel görünümlerini oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 06/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e8f008ba3cde911ed5c21f281d30fda2a77bf824
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger"></a>Visual Studio Hata Ayıklayıcısı'ndaki veri özel görünümlerini oluşturma
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı inceleme ve programınızı durumunu değiştirmek için çeşitli araçlar sağlar. Bu araçlar işlevi yalnızca kesme modunda çoğunu.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>Değişken pencereler ve DataTips veri özel görünümlerini oluşturma
 Çoğu [hata ayıklayıcı, windows](../debugger/debugger-windows.md), gibi **otomobiller** ve **izleme** windows hata ayıklarken değişkenleri incelemek izin verir. Yerel türler ve hata ayıklayıcı değişken pencerelerini hem de yönetilen nesneleri görünümünü özelleştirebilirsiniz [DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). Bu, kendi uygulamalarında oluşturma türlerini görüntülemek yararlı olabilir. Daha fazla bilgi için bkz: [yerel nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-native-objects.md) ve [yönetilen nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md).
  
## <a name="create-custom-visualizers"></a>Özel görselleştiriciler oluşturma  
 Görselleştiriciler anlamlı bir şekilde bir nesneye veya değişken içeriğini görüntülemenizi sağlar. Visual Studio Hata Ayıklayıcısı'ndaki Görselleştirici Büyüteç simgesini kullanarak açabilirsiniz farklı windows başvuruyor ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi"). Örneğin, HTML Görselleştirici yorumlanır ve bir tarayıcıda görüntülenen gibi bir HTML dizesi görüntülemek için kullanabilirsiniz. Görselleştiriciler DataTips erişebilirsiniz **izleme** penceresinde **otomobiller** penceresinde **Yereller** penceresinde veya **QuickWatch** iletişim bir kutu. Daha fazla bilgi için bkz: [özel görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Komut penceresi](../ide/reference/command-window.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)