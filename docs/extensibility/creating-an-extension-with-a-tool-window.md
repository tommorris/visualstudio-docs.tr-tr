---
title: Bir uzantısı bir araç penceresi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f918a5b8b48a7b9553cf3ca2e6c8fe9d38fbc9b8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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