---
title: Bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: fa3b993b-ab95-47fa-a38b-b788f3a5b2d8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 60f10479e0ce6fa08e888d92556ff47b5d82af66
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-an-extension-with-an-editor-item-template"></a>Bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma
Sınıflandırıcı, adornments ve kenar boşlukları düzenleyiciye eklemek temel Düzenleyici uzantıları oluşturmak için Visual Studio SDK içinde yer alan öğe şablonları kullanabilirsiniz. Düzenleyici öğe şablonları, Visual C# veya Visual Basic VSIX projeleri için kullanılabilir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-classifier-extension"></a>Bir sınıflandırıcı uzantısı oluşturma  
 Uygun metni renkleri bir düzenleyici sınıflandırıcı Düzenleyicisi sınıflandırıcı öğesi şablon oluşturur (Bu durumda, her şeyi) herhangi bir metin dosyası olarak.  
  
1.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** ve ardından **genişletilebilirlik**. İçinde **şablonları** bölmesinde, **VSIX proje**. İçinde **adı** kutusuna `TestClassifier`. **Tamam**'ı tıklatın.  
  
2.  İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. Git Visual C# **genişletilebilirlik** düğümü ve select **Düzenleyicisi sınıflandırıcı**. Varsayılan dosya adı (EditorClassifier1.cs) bırakın.  
  
3.  Aşağıdaki gibi üç kod dosyaları vardır:  
  
    -   EditorClassifier1.cs içeren `EditorClassifier1` sınıfı.  
  
    -   EditorClassifier1ClassificationDefinition.cs içeren `OEditorClassifier1ClassificationDefinition` sınıfı.  
  
    -   EditorClassifier1Format.cs içeren `EditorClassifier1Format` sınıfı.  
  
    -   EditorClassifier1Provider.cs içeren `EditorClassifier1Provider` sınıfı.  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio'nun deneysel örneği görüntülenir.  
  
     Bir metin dosyası açarsanız, tüm metni karşı mor arka plan altı çizilir.  
  
## <a name="creating-a-text-relative-adornment-extension"></a>Bir metin göreli Adornment uzantısı oluşturma  
 Metin karakteri tüm örneklerini süsler metin göreli adornment düzenleyici metin Adornment şablon oluşturur kırmızı anahattı ve mavi bir arka plana sahip bir kutusunu kullanarak ' bir'. Metin göreli çünkü kutusunu her zaman bile bunlar taşınmış yeniden biçimlendirilen ya da kapatıldığında 'bir' karakterleri, yer paylaşımları.  
  
1.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** ve ardından **genişletilebilirlik**. İçinde **şablonları** bölmesinde, **VSIX proje**. İçinde **adı** kutusuna `TestAdornment`. **Tamam**'ı tıklatın.  
  
2.  İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. Git Visual C# **genişletilebilirlik** düğümü ve select **düzenleyici metin Adornment**. Varsayılan dosya adı (TextAdornment1.cs/vb) bırakın.  
  
3.  Aşağıdaki gibi iki kod dosyaları vardır:  
  
    -   TextAdornment1.cs içeren `TextAdornment1` sınıfı.  
  
    -   extAdornment1TextViewCreationListener.cs içeren `TextAdornment1TextViewCreationListener` sınıfı.  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir. Bir metin dosyası açarsanız, tüm 'bir' karakterlerini kırmızı mavi arka plan özetlenmiştir.  
  
## <a name="creating-a-viewport-relative-adornment-extension"></a>Bir görünüm penceresinin göreli Adornment uzantısı oluşturma  
 Düzenleyici görünüm penceresinin Adornment şablon görünüm penceresinin sağ üst köşesinde kırmızı anahattına sahip bir mor kutusu ekler bir görünüm penceresinin göreli adornment oluşturur.  
  
> [!NOTE]
>  *Görünüm penceresinin* şu anda görüntülenen metin görünümü alanıdır.  
  
#### <a name="to-create-a-viewport-adornment-extension-by-using-the-editor-viewport-adornment-template"></a>Düzenleyici görünüm penceresinin Adornment şablonu kullanarak bir görünüm penceresinin adornment uzantısı oluşturmak için  
  
1.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** ve ardından **genişletilebilirlik**. İçinde **şablonları** bölmesinde, **VSIX proje**. İçinde **adı** kutusuna `ViewportAdornment`. **Tamam**'ı tıklatın.  
  
2.  İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. Git Visual C# **genişletilebilirlik** düğümü ve select **Düzenleyicisi görünüm penceresinin Adornment**. Varsayılan dosya adı (ViewportAdornment1.cs/vb) bırakın.  
  
3.  Aşağıdaki gibi iki kod dosyaları vardır:  
  
    -   ViewportAdornment1.cs içeren `ViewportAdornment1` sınıfı.  
  
    -   ViewportAdornment1TextViewCreationListener.cs içeren `ViewportAdornment1TextViewCreationListener` sınıfı  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir. Yeni bir metin dosyası oluşturursanız, kırmızı anahattı sahip bir mor kutusu görünüm penceresinin sağ üst köşesinde görüntülenir.  
  
## <a name="creating-a-margin-extension"></a>Kenar boşluğu uzantısı oluşturma  
 "Hello world!" sözcükler ile birlikte görüntülenir yeşil bir kenar boşluğu Düzenleyicisi kenar boşluğu şablon oluşturur Yatay kaydırma çubuğu aşağıda.  
  
#### <a name="to-create-a-margin-extension-by-using-the-editor-margin-template"></a>Düzenleyici kenar boşluğu şablonu kullanarak bir kenar boşluğu uzantısı oluşturmak için  
  
1.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#** veya **Visual Basic** ve ardından **genişletilebilirlik**. İçinde **şablonları** bölmesinde, **VSIX proje**. İçinde **adı** kutusuna `MarginExtension`. **Tamam**'ı tıklatın.  
  
2.  İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. Git Visual C# **genişletilebilirlik** düğümü ve select **Düzenleyicisi görünüm penceresinin Adornment**. Varsayılan dosya adı (EditorMargin1.cs/vb) bırakın.  
  
3.  Aşağıdaki gibi iki kod dosyaları vardır:  
  
    -   EditorMargin1.cs içeren `EditorMargin1` sınıfı.  
  
    -   EditorMargin1Factory.cs içeren `EditorMargin1Factory` sınıfı.  
  
4.  Bu projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir. Bir metin dosyası açarsanız, "Merhaba EditorMargin1" sözcükler sahip yeşil bir kenar boşluğu altında yatay kaydırma çubuğu görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Hizmeti ve Düzenleyici Uzantı Noktaları](../extensibility/language-service-and-editor-extension-points.md)