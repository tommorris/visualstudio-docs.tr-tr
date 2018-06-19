---
title: Eski etkinlik Tasarımcısı kullanarak iş akışı Tasarımcısı-
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- activities, configuring
- custom activities
- Activity Designer
- child activities, adding
- activities, adding child
- activities, creating custom
ms.assetid: 2fea8a05-6e58-423d-94bf-a822b15ffb80
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fdf7ae585697db19293362a31c5751d44c7421c5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974851"
---
# <a name="using-the-legacy-activity-designer"></a>Eski etkinlik Tasarımcısı'nı kullanarak

Bu konu, eski Windows iş akışı Tasarımcısı'nda etkinlik Tasarımcısı kullanmayı açıklar. .NET Framework sürüm 3.5 veya WinFX hedefleme eski Tasarımcısı'nı kullanın.

Etkinlik Tasarımcısı özel etkinliklerinizi oluşturmanıza olanak sağlar.

## <a name="creating-a-custom-activity"></a>Özel etkinlik oluşturma

Etkinlik Tasarımcısı'nı kullanarak bir özel etkinlik oluşturmak için aşağıdaki adımları izleyin:

1.  Üzerinde **proje** menüsünde tıklatın **etkinlik Ekle**.

2.  Seçin **etkinlik** veya **etkinlikle (kod ayrımı)** şablonu.

    1.  Kullanım **etkinlik** etkinlik tanımı ve kullanıcı kodla aynı kod dosyasında bir etkinlik oluşturmak için şablon.

    2.  Kullanım **etkinlikle (kod ayrımı)** iş akışı biçimlendirmesi ve ayrı kod dosyasındaki kullanıcı kodu olarak ifade edilen etkinlik tanımı'yla bir etkinlik oluşturmak için şablon.

3.  Bir etkinlik adı yazın veya varsayılan adı bırakın ve ardından **Ekle**.

Yeni bir proje türü oluşturarak özel etkinlikler kümesi oluşturabilirsiniz **iş akışı etkinlik kütüphanesini**. Bu proje türü hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir iş akışı etkinlik Kitaplığı'nı (eski) oluşturmanız](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md).

## <a name="configuring-an-activity"></a>Bir etkinliği yapılandırma

Etkinlik Tasarımcısı etkin olsa da, aşağıdaki tabloda listelenen özellikleri yapılandırmak için özellik tarayıcısı kullanabilirsiniz.

|Özellik|Açıklamalar|
|--------------|--------------|
|**Ad**|Etkinlik adı.|
|**Taban sınıfı**|Etkinlik türetildiği temel sınıf. Varsayılan taban sınıf [öğeler SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020). İçinde **özellikleri** penceresinde tıklatın **temel sınıf** üç nokta **[...]**  başka bir taban sınıf içinde seçmek için [göz atın ve bir .NET türünü seç iletişim kutusu (eski)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md).|
|**Açıklama**|Kullanıcı tanımlı etkinlik açıklaması.|
|**Etkin**|Kümesine **True** Etkinlik yürütme ve doğrulama etkinleştirmek için varsayılan olarak. Kümesine **False** Etkinlik yürütme ve doğrulama devre dışı bırakmak için. Etkinlik yürütme ve doğrulama hakkında daha fazla bilgi için bkz: [geliştirme iş akışı etkinlikleri](http://go.microsoft.com/fwlink?LinkID=65024).|

## <a name="adding-child-activities"></a>Alt etkinlikler ekleme

Alt etkinlikler araç kutusu'ndan tasarlarken etkinlik sürükleyebilirsiniz. Özellik tarayıcısı kullanarak her alt etkinliği sonra yapılandırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [İş akışı etkinliklerini geliştirme](http://go.microsoft.com/fwlink?LinkID=65024)
- [Özel etkinlikler oluşturma](http://go.microsoft.com/fwlink?LinkID=65021)
- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)
- [Özel etkinlikler örnekleri](http://go.microsoft.com/fwlink?LinkID=65022)
- [Nasıl Yapılır: İş Akışı Etkinlik Kitaplığı Oluşturma (Eski)](../workflow-designer/how-to-create-a-workflow-activity-library-legacy.md)
- [Eski İş Akışı Tasarımcısını Kullanma](../workflow-designer/using-the-legacy-workflow-designer.md)