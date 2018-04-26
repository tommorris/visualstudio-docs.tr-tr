---
title: Projeler ve dosyalar için Visual Studio şablonları
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- templates [Visual Studio], project
- templates [Visual Studio], item
- item templates [Visual Studio]
- project templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e595392f92c99f6f73d2a9d999356641c14b096d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="project-and-item-templates"></a>Proje ve öğe şablonları

Proje ve öğe şablonları, bazı temel kod ve kendi amaçları için özelleştirebilirsiniz yapısı, kullanıcılara vermek yeniden kullanılabilir saplamalar sağlar.

## <a name="visual-studio-templates"></a>Visual Studio şablonları

Bir dizi önceden tanımlanmış proje ve öğe şablonları, Visual Studio ile yüklenir. Örneğin, Visual Basic ve C# **Windows Forms uygulaması** ve **sınıf kitaplığı** 'nda gösterilen şablonları **yeni proje** iletişim kutusu, proje şablonlardır. Öğe şablonları göster **Yeni Öğe Ekle** iletişim kutusuna ve kod dosyaları, XML dosyalarını, HTML sayfaları ve stil sayfalarını gibi öğeleri içerir.

Bu şablonlar projeleri oluşturmaya başlamak için ya da mevcut projeleri genişletmek için kullanıcılar için bir başlangıç noktası sağlar. Proje şablonları belirli proje türü için gerekli olan dosyalar sağlamak, standart derleme başvurularını içerir ve varsayılan proje özelliklerini ve derleyici seçeneklerini ayarlama. Öğe şablonları, birden çok kaynak kodu dosyaları saplama koduyla, Tasarımcı bilgi dosyaları ve katıştırılmış kaynaklara belirli dosya uzantısına sahip tek bir boş dosya karmaşıklığı aralığında değişebilir.

Yüklü şablonlarında kullanabilirsiniz **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları, kendi şablonlarınızı yazmak veya karşıdan yüklemek ve topluluk tarafından oluşturulan şablonlar kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md) ve [nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md).

## <a name="contents-of-a-template"></a>Bir şablon içeriği

Tüm proje ve öğe şablonları, Visual Studio ile yüklü ya da sizin tarafınızdan oluşturulan aynı ilkeleri kullanarak işlev ve benzer içeriğe sahip. Tüm şablonları aşağıdaki öğeleri içerir:

- Şablon kullanıldığında, oluşturulan dosyalar. Bu dosyalar, kaynak kodu dosyaları, katıştırılmış kaynakları, proje dosyalarını vb. içerir.

- Bir *.vstemplate* şablonda görüntülemek için gereken meta verileri içeren dosya **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları ve bir proje oluşturun veya gelen öğesi Şablon. Hakkında daha fazla bilgi için *.vstemplate* dosyaları görmek [şablon parametreleri](../ide/template-parameters.md).

Ne zaman bu dosyaları sıkıştırılır içine bir *.zip* dosya ve doğru klasöre yerleştirin, Visual Studio otomatik olarak aşağıdaki konumlarda görüntüler:

- Proje şablonları görünür **yeni proje** iletişim kutusu.

- Öğe şablonları görünür **Yeni Öğe Ekle** iletişim kutusu.

Şablon klasörleri hakkında daha fazla bilgi için bkz: [nasıl yapılır: şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="starter-kits"></a>Başlangıç Paketleri

Başlangıç paketleri diğer topluluk üyeleriyle paylaşılabilir Gelişmiş şablonlarıdır. Başlangıç paketleri Derlenebilir kod örnekleri, belgelerine ve kullanıcıların yeni araçları ve programlama tekniklerinin yararlı, gerçek uygulamaları oluştururken öğrenin yardımcı olmak için diğer kaynakları içerir. Başlangıç paketleri için yordamları ve temel içeriğini şablonları aynıdır. Daha fazla bilgi için bkz: [nasıl yapılır: başlangıç paketleri oluşturma](../ide/how-to-create-starter-kits.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)
- [Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)
- [Şablon parametreleri](../ide/template-parameters.md)
- [Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)
- [Visual Studio şablonları NuGet paketleri](/nuget/visual-studio-extensibility/visual-studio-templates)