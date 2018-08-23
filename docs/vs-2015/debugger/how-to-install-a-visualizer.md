---
title: 'Nasıl yapılır: Görselleştiriciyi yükleme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5152c47635f8ca2f2bb0a6a32c7767682006860a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691514"
---
# <a name="how-to-install-a-visualizer"></a>Nasıl Yapılır: Görselleştiriciyi Yükleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: Görselleştiriciyi yükleme](https://docs.microsoft.com/visualstudio/debugger/how-to-install-a-visualizer).  
  
Görselleştirici oluşturduktan sonra kullanıma sunulacak böylece görselleştiricisi yüklemelisiniz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Görselleştirici yükleme basit bir işlemdir.  
  
> [!NOTE]
>  İçinde **Store** uygulamalar, yalnızca standart metin, HTML, XML ve JSON görselleştiriciler desteklenir. Özel (kullanıcı tarafından oluşturulmuş) görselleştiriciler desteklenmez.  
  
### <a name="to-install-a-visualizer"></a>Görselleştirici yüklemek için  
  
1.  Derlediğiniz görselleştiricisi içeren DLL bulun.  
  
2.  DLL aşağıdaki konumlardan birini kopyalayın:  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  Uzaktan hata ayıklama için yönetilen Görselleştirici kullanmak istiyorsanız, DLL uzak bilgisayarda aynı yoluna kopyalayın.  
  
4.  Hata ayıklama oturumunu yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)   
 [Nasıl yapılır: Görselleştirici yazma](../debugger/how-to-write-a-visualizer.md)



