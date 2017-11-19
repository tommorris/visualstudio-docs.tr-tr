---
title: "Bir uzantısı bir araç penceresi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cda2d9bc4bde1c0bf9d9dd82c48864725f0e25f0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-an-extension-with-a-tool-window"></a>Bir uzantısı bir araç penceresi oluşturma
Bu yordamda, VSIX proje şablonu kullanmayı öğrenin ve **özel araç penceresi** öğe şablonu uzantı bir araç penceresi oluşturulamadı.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="creating-a-tool-window"></a>Araç penceresi oluşturma  
  
1.  Adlı VSIX proje oluşturma **FirstWindow**. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Proje açıldığında adlı bir aracı pencere öğesi şablonu Ekle **MyWindow**. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **özel araç penceresi**. İçinde **adı** alan penceresinin alt kısmında, araç penceresi dosya adını değiştirmek **MyWindow.cs**.  
  
3.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
     Visual Studio'nun deneysel örneği görüntülenir. Deneysel örneği hakkında daha fazla bilgi için bkz: [deneysel örneği](../extensibility/the-experimental-instance.md).  
  
4.  Deneysel örneğinde Git **görünüm / diğer pencereler**.  
  
     Menü öğesi için görmelisiniz **MyWindow**. Tıklayın.  
  
     Başlığa sahip araç penceresi görmeniz gerekir **MyWindow** ve düğmesi bildiren **bana tıklayın!**