---
title: Hata ayıklayıcıda verilerin özel görünümlerini oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 06/27/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02bb65aa2b0601315a3f5dec2cc9459af210db3e
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39177678"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcıda verilerin özel görünümlerini oluşturma
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı incelemek ve programınızın durumunu değiştirmek için çeşitli araçlar sağlar. Bu araçlar işlevi yalnızca kesme modunda çoğunu.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>Değişken pencereler ve DataTips verilerin özel görünümlerini oluşturma
 Çoğu [hata ayıklayıcı, windows](../debugger/debugger-windows.md), gibi **Otolar** ve **izleme** windows ayıklarken değişkenleri İnceleme izin verir. Yerel türler ve hata ayıklayıcı değişken pencerelerinde ve yönetilen nesnelerin görünümünü özelleştirebilirsiniz [DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). Bu, kendi uygulamalarında oluşturma türlerini görüntülemek yararlı olabilir. Daha fazla bilgi için [yerel nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-native-objects.md) ve [yönetilen nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md).
  
## <a name="create-custom-visualizers"></a>Özel görselleştiriciler oluşturma  
 Görselleştiriciler, bir nesnenin veya değişkenin içeriklerini anlamlı bir şekilde görüntülemek etkinleştirin. Visual Studio hata ayıklayıcısının Görselleştirici Büyüteç simgesini kullanarak açabileceğiniz farklı windows başvuruyor ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi"). Örneğin, bir HTML dizesi yorumlanır ve bir tarayıcıda görüntülenen olarak görüntülemek için HTML görselleştiriciyi kullanabilirsiniz. Görselleştiriciler ipuçlarından erişebileceğiniz **izleme** penceresinde **Otolar** penceresinde **Yereller** penceresinde veya **QuickWatch** iletişim bir kutu. Daha fazla bilgi için [özel görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı temel bilgileri](../debugger/getting-started-with-the-debugger.md)   
 [Komut penceresi](../ide/reference/command-window.md)   
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)