---
title: Özellik Sayfaları, JavaScript
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- javascript.project.property.debugging.debuggertype
- javascript.project.property.debugging.requireauthentication
- javascript.project.property.outputpath
- javascript.project.property.debugging.launchapplication
- javascript.project.property.defaultlanguage
- javascript.project.property.debugging.machinename
- javascript.project.property.debugging.allowlocalnetworkloopback
ms.assetid: a05ab01f-3d5d-4675-a845-eab51807d3a3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5690abe8e155c33d8e998ea0a18749e172da7e34
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="property-pages-javascript"></a>Özellik Sayfaları, JavaScript
**Özellik sayfaları**proje ayarlarına erişim sağlar. Görünür sayfalarını kullanabilirsiniz **özellik sayfaları** proje özelliklerini değiştirmek için.

Proje Özellikleri erişmek için bir proje düğümünde seçin **Çözüm Gezgini**. Üzerinde **proje** menüsünde tıklatın **özellikleri**.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

Aşağıdaki sayfaları ve seçenekleri görünür **özellik sayfaları**.

## <a name="configuration-and-platform-page"></a>Yapılandırma ve Platform sayfası
 Yapılandırma ve görüntülemek veya değiştirmek için platform seçmek için aşağıdaki seçenekleri kullanın.

 **Yapılandırma**

 Görüntülemek veya değiştirmek için yapılandırma ayarlarını belirtir. Ayarlar **hata ayıklama** (varsayılan), **sürüm**, **tüm yapılandırmaları**, veya kullanıcı tanımlı bir yapılandırma. Daha fazla bilgi için bkz: [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları Visual Studio'da](../../debugger/how-to-set-debug-and-release-configurations.md).

 **Platform**

 Görüntülemek veya değiştirmek için platform ayarlarını belirtir. Ayarlar **herhangi bir CPU** (için varsayılan [!INCLUDE[win8_appname_long](../../debugger/includes/win8_appname_long_md.md)] uygulamalar), **x64**, **ARM**, **x86**, veya kullanıcı tanımlı bir platform. Daha fazla bilgi için bkz: [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları Visual Studio'da](../../debugger/how-to-set-debug-and-release-configurations.md).

## <a name="general-page"></a>Genel sayfası
 Proje genel özelliklerini ayarlamak için aşağıdaki seçenekleri kullanın.

> [!NOTE]
> Bazı seçeneklere yalnızca UWP uygulamalarında kullanılabilir.


 **Çıkış yolu**

 Projenin yapılandırması için çıkış dosyalarının konumunu belirtir. Göreli yolu; mutlak bir yol girin, mutlak yolu projede kaydedilir. Bin\Debug varsayılan yoldur.

 Basitleştirilmiş derleme yapılandırmaları kullandığınızda, proje sistemi sürümünü veya bir hata ayıklama geliştirmek belirler. Tıkladığınızda **hata ayıklama**, **hata ayıklamayı Başlat** (veya F5 tuşuna basın) yapı, hata ayıklama konumunu bakılmaksızın koymak **çıkış yolu** , belirtin. Ancak, **yapı çözümü** komutunu **yapı** menüsü, belirttiğiniz konuma yerleştirir. Menü çubuğunda, Gelişmiş derleme yapılandırmaları etkinleştirmeyi seçerseniz **Araçları**, **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**seçin **genel**ve ardından temizlemek **Göster Gelişmiş derleme yapılandırmaları**onay kutusu. Bu, tüm yapılandırma değerleri üzerinde el ile denetim ve hata ayıklama ve yayın sürümü olup olmadığını yerleşik sunar.

 **Varsayılan dil**

 Proje için varsayılan dili belirtir. Seçtiğiniz dil seçeneği **saat, dil ve bölge** Denetim Masası'nda kullanıcının tercih edilen dili belirtir. Proje için bir varsayılan dil belirterek, kullanıcının tercih edilen dili uygulamada sağlanan Türkçe kaynaklar eşleşmiyorsa, belirtilen varsayılan dil kaynakları kullanılan emin olun.

## <a name="debug-page"></a>Hata ayıklama sayfası
 Davranış projesinde hata ayıklama özelliklerini ayarlamak için aşağıdaki seçenekleri kullanın.

> [!NOTE]
> Bazı seçeneklere yalnızca UWP uygulamalarında kullanılabilir.


 **Hata ayıklayıcı başlatmak için**

 Hata ayıklayıcı için varsayılan ana bilgisayar belirtir.

-   Seçin **yerel makine** Visual Studio ana bilgisayara uygulamayı başlatmak için. Daha fazla bilgi için bkz: [yerel makine üzerinde çalışan uygulamalar](../../debugger/run-windows-store-apps-on-the-local-machine.md).

-   Seçin **Simulator** Benzeticisinde uygulamayı başlatmak için. Daha fazla bilgi için bkz: [benzeticisinde çalışan uygulamalar](../../debugger/run-windows-store-apps-in-the-simulator.md).

-   Seçin **uzak makine** uzak bir bilgisayarda uygulamayı başlatmak için. Uzaktan hata ayıklama hakkında daha fazla bilgi için bkz: [uzak makinede çalışan uygulamalar](../../debugger/run-windows-store-apps-on-a-remote-machine.md).

**Uygulama başlatma**

F5 tuşuna basın veya'i tıklattığınızda uygulama başlatılıp başlatılmayacağını belirtir **hata ayıklama**, **hata ayıklamayı Başlat**. Seçin **Evet** için uygulamayı Başlat; Aksi halde seçin **Hayır**. Seçerseniz **Hayır**, başlatmak için farklı bir yöntem kullanıyorsanız uygulama hala ayıklayabilirsiniz.

**Hata ayıklayıcı türü**

Hata ayıklamak için kod türlerini belirtir. Seçin **yalnızca betik** JavaScript kodunda hata ayıklama için. Seçin **yalnızca yönetilen** ortak dil çalışma zamanı tarafından yönetilen kodda hata ayıklamak için. Seçin **yalnızca yerel** C++ kod hatalarını ayıklamak için. Seçin **betik ile yerel** C++ ve JavaScript hata ayıklamak için. Seçin **karma (yönetilen ve yerel)** yönetilen hata ayıklama hem ve C++ kodu.

**Yerel ağ geri döngü izin ver**

Uygulama test etmek için IP geri döngü adresine erişime izin verilip verilmediğini belirtir. Seçin **Evet** istemci uygulaması aynı makinede olması durumunda, aksi çalışan sunucu uygulaması olduğu geri döngü adresine kullanımına izin vermek için seçin **Hayır**. Bu özellik kullanılabilir yalnızca **başlatmak için hata ayıklayıcı** özelliği ayarlanmış **uzak makine**.

**Makine adı**

Hata ayıklayıcı barındırmak için uzak bilgisayarın adını belirtir. Bu özellik kullanılabilir yalnızca **başlatmak için hata ayıklayıcı** ayarlanır **uzak makine**.

**Kimlik doğrulaması gerektirir**

Uzak bilgisayar kimlik doğrulaması gerekip gerekmediğini belirtir. Bu özellik kullanılabilir yalnızca **başlatmak için hata ayıklayıcı** ayarlanır **uzak makine**.
