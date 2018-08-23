---
title: Araç penceresi içeren bir uzantı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: afa24a7faceade36cf6b3d19c7e86fb8d6676ba8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631083"
---
# <a name="creating-an-extension-with-a-tool-window"></a>Araç Penceresi İçeren Bir Uzantı Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [araç penceresi içeren bir uzantı oluşturma](https://docs.microsoft.com/visualstudio/extensibility/creating-an-extension-with-a-tool-window).  
  
Bu yordamda, VSIX proje şablonu kullanmayı öğrenin ve **özel araç penceresi** öğe şablonu, araç penceresi içeren bir uzantı oluşturma.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, size Visual Studio SDK İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yi daha sonra yükleyebilirsiniz. Daha fazla bilgi için [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="creating-a-tool-window"></a>Araç penceresi oluşturma  
  
1.  Adlı bir VSIX projesi oluşturun **FirstWindow**. VSIX proje şablonunda bulabilirsiniz **yeni proje** iletişim altında **Visual C# / genişletilebilirlik**.  
  
2.  Projeyi açtığında, adlı bir araç penceresi öğesi şablonu ekleme **FirstWindow**. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayıp **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **özel araç penceresi**. İçinde **adı** alan penceresinin en altında bir araç penceresi dosya adını değiştirerek **FirstWindow.cs**.  
  
3.  Projeyi oluşturmak ve hata ayıklamaya başlayın.  
  
     Visual Studio'nun deneysel örneğinde görünür. Deneysel örnek hakkında daha fazla bilgi için bkz. [deneysel örneğinde](../extensibility/the-experimental-instance.md).  
  
4.  Deneysel örneğinde Git **görünüm / diğer Windows**.  
  
     Bir menü öğesi için görmelisiniz **FirstWindow**. Tıklayın.  
  
     Başlığa sahip araç penceresi görmeniz gerekir **FirstWindow** ve bir düğmeyi bildiren **Me tıklayın!**

