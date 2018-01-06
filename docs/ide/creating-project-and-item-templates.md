---
title: "Projeler ve dosyalar için Visual Studio şablonları | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [Visual Studio], project
- templates [Visual Studio], item
- item templates [Visual Studio]
- project templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3959b01fdfc0ff77bdd5a3ffa0c96366b9da87d7
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="project-and-item-templates"></a>Proje ve öğe şablonları

Proje ve öğe şablonları, bazı temel kod ve kendi amaçları için özelleştirebilirsiniz yapısı, kullanıcılara vermek yeniden kullanılabilir saplamalar sağlar.

## <a name="visual-studio-templates"></a>Visual Studio şablonları

Bir dizi önceden tanımlanmış proje ve öğe şablonları, Visual Studio ile yüklenir. Örneğin, Visual Basic ve C# **Windows Forms uygulaması** ve **sınıf kitaplığı** 'nda gösterilen şablonları **yeni proje** iletişim kutusu, proje şablonlardır. Öğe şablonları gösterilmiştir **Yeni Öğe Ekle** iletişim kutusuna ve kod dosyaları, XML dosyalarını, HTML sayfaları ve stil sayfalarını gibi öğeleri içerir.

Bu şablonlar projeleri oluşturmaya başlamak için ya da mevcut projeleri genişletmek için kullanıcılar için bir başlangıç noktası sağlar. Proje şablonları belirli proje türü için gerekli olan dosyalar sağlamak, standart derleme başvurularını içerir ve varsayılan proje özelliklerini ve derleyici seçeneklerini ayarlama. Öğe şablonları, içerir, örneğin bir çok dosyalı öğe için belirli dosya uzantısına sahip tek bir boş dosya, saplama koda sahip kaynak kodu dosyaları, Tasarımcı bilgi dosyaları ve katıştırılmış kaynakları karmaşıklığı aralığında değişebilir.

Yüklü Şablonlar, ek olarak **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları, kendi şablonları veya indirme ve topluluk tarafından oluşturulan kullanım şablonları yazabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md) ve [nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md).

## <a name="contents-of-a-template"></a>Bir şablon içeriği

Tüm proje ve öğe şablonları, Visual Studio ile yüklü ya da sizin tarafınızdan oluşturulan aynı ilkeleri kullanarak işlev ve benzer içeriğe sahip. Tüm şablonları aşağıdaki öğeleri içerir:

- Şablon kullanıldığında, oluşturulan dosyalar. Bu, kaynak kodu dosyaları, katıştırılmış kaynakları, proje dosyalarını vb. içerir.

- Bir .vstemplate dosyası. Bu dosya şablonda görüntülemek için gereken bilgileri sağlar meta veriler içeriyor **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları ve bir proje veya öğeyi şablonu oluşturun. .Vstemplate dosyaları hakkında daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).

Bu dosyaları bir .zip dosyasına sıkıştırılır ve doğru klasöre yerleştirin, Visual Studio bunları otomatik olarak aşağıdaki konumlarda görüntüler:

- Proje şablonları görünür **yeni proje** iletişim kutusu.

- Öğe şablonları görünür **Yeni Öğe Ekle** iletişim kutusu.

Şablon klasörleri hakkında daha fazla bilgi için bkz: [nasıl yapılır: şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="starter-kits"></a>Başlangıç Paketleri

Başlangıç paketleri diğer topluluk üyeleriyle paylaşılabilir Gelişmiş şablonlarıdır. Starter Kit, belgeleri ve yararlı, gerçek uygulamaları derleme oluştururken yeni araçları ve programlama tekniklerinin öğrenin kullanıcılara yardımcı olmak için diğer kaynakları derle kod örnekleri içerir. Temel içeriğini ve yordamlar başlangıç paketleri için şablonlar olanlarla aynıdır. Daha fazla bilgi için bkz: [nasıl yapılır: başlangıç paketleri oluşturma](../ide/how-to-create-starter-kits.md).

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)  
[Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)  
[Şablon parametreleri](../ide/template-parameters.md)  
[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)  
[Visual Studio şablonları NuGet paketleri](/nuget/visual-studio-extensibility/visual-studio-templates)