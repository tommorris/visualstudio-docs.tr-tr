---
title: Verilerin özel Görselleştiricilerini oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.visualizer.troubleshoot
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers
ms.assetid: c24c006f-f2ac-429f-89db-677fc0c6e1ea
caps.latest.revision: 31
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a025068d1657d9feb569a77731aa8bab517bae2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685803"
---
# <a name="create-custom-visualizers-of-data"></a>Verilerin özel Görselleştiricilerini oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [özel Görselleştiriciler veri oluşturma](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).  
  
Görselleştiriciler bileşenlerinin [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] hata ayıklayıcı kullanıcı arabirimi. A *Görselleştirici* bir iletişim kutusu veya bir değişkeni veya nesneyi, veri türüne uygun bir şekilde görüntülemek için başka bir arabirim oluşturur. Örneğin, bir HTML Görselleştirici bir HTML dizesi olarak yorumlar ve sonucu bir tarayıcı penceresinde görüneceği şekilde görüntüler; bit eşlem Görselleştirici bir bit eşlem yapısı yorumlar ve onu gösteren grafiği görüntüler. Bazı görselleştiriciler yanı sıra değişiklik verilerini görüntülemek etkinleştirin.  
  
 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] Hata ayıklayıcı altı standart görselleştiriciler içerir. Bunlar, metin, HTML, XML ve JSON görselleştiriciler, her biri dize nesneler üzerinde çalışmak, bir WPF nesne görsel ağacı özelliklerini görüntülemek için WPF ağacı görselleştiricisini, ve veri kümesi, DataView ve DataTable nesneleri için çalışan bir veri kümesi görselleştiricisi. Ek görselleştiriciler, gelecekte Microsoft Corporation'ın indirilebilir olabilir ve üçüncü taraflar ve topluluktan kullanılabilir. Ayrıca, kendi görselleştiriciler yazabilir ve bunları yüklemek [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] hata ayıklayıcı.  
  
> [!NOTE]
>  İçinde **Store** uygulamalar, yalnızca standart metin, HTML, XML ve JSON görselleştiriciler desteklenir. Özel (kullanıcı tarafından oluşturulmuş) görselleştiriciler desteklenmez.  
  
 Görselleştiriciler hata ayıklayıcıda bir Büyüteç simgesi ile gösterilir. Büyüteç simgesini gördüğünüzde bir **DataTip**, hata ayıklayıcı değişken penceresinde veya buna **QuickWatch** iletişim kutusu, veri türüne uygun Görselleştirici seçmek için Büyüteç tıklayabilirsiniz karşılık gelen nesne.  
  
 Görselleştiriciler Compact Framework'te desteklenmez.  
  
> [!NOTE]
>  Hata ayıklama görselleştiricileri kısmi güven uygulama tarafından izin verilenden daha yüksek ayrıcalıklar gerektirir. Sonuç olarak, kısmi güven ile koddaki durdurulduğunda görselleştiriciler yüklenmiyor. Görselleştirici kullanarak hata ayıklama için tam güven ile kodu çalıştırmanız gerekir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: Görselleştirici yazma](../debugger/how-to-write-a-visualizer.md)  
  
 [İzlenecek yol: Görselleştiriciyi C# ' de yazma](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)  
  
 [Nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md)  
  
 [Nasıl yapılır: Görselleştiriciyi hata ayıklama ve Test](../debugger/how-to-test-and-debug-a-visualizer.md)  
  
 [Görselleştirici API Başvurusu](../debugger/visualizer-api-reference.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)



