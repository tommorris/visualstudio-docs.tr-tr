---
title: 'Nasıl yapılır: Görselleştiriciyi yükleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eea59575ce6f324540e59e6265ecdcbfd6b6cfd3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-install-a-visualizer"></a>Nasıl Yapılır: Görselleştiriciyi Yükleme
Görselleştirici oluşturduktan sonra böylece kullanılabilir olması Görselleştirici yüklemelisiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Görselleştirici yükleme basit bir işlemdir.  
  
> [!NOTE]
>  UWP uygulamalar, yalnızca standart metin, HTML, XML ve JSON görselleştiriciler desteklenir. Özel (kullanıcı tarafından oluşturulan) görselleştiriciler desteklenmez.  
  
### <a name="to-install-a-visualizer"></a>Görselleştirici yüklemek için  
  
1.  Hazırladığınız Görselleştirici içeren DLL bulun.  
  
2.  DLL aşağıdaki konumlardan birini kopyalayın:  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  Uzaktan hata ayıklama için yönetilen Görselleştirici kullanmak istiyorsanız, uzak bilgisayardaki aynı yola DLL kopyalayın.  
  
4.  Hata ayıklama oturumu yeniden başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)   
 [Nasıl yapılır: Görselleştirici yazma](../debugger/how-to-write-a-visualizer.md)