---
title: "Hata ayıklama sayfası, Proje Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.ProjectPropertiesDebug
helpviewer_keywords:
- Project Designer, Debug page
- Debug page in Project Designer
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39b19b6e418203a33c410173d46e190bbd6c01e1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debug-page-project-designer"></a>Hata Ayıklama Sayfası, Proje Tasarımcısı
> [!WARNING]
>  Bu konu, UWP uygulamaları için geçerli değil. Bkz: [(VB, C#, C++ ve XAML) bir hata ayıklama oturumu Başlat](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) Windows geliştirme Merkezi'ndeki.  
  
 Kullanım **hata ayıklama** sayfasında **Proje Tasarımcısı** davranışı bir Visual Basic veya C# projesinde hata ayıklama özelliklerini ayarlamak için.  
  
 Erişim için **hata ayıklama** sayfası, proje düğümü seçin **Çözüm Gezgini**. Üzerinde **proje** menüsünde seçin *ProjectName***özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **hata ayıklama** sekmesi.  
  
## <a name="configuration-and-platform"></a>Yapılandırması ve platformu  
 Aşağıdaki seçenekler yapılandırma ve görüntülemek veya değiştirmek için platform seçmenize olanak tanır.  
  
 **Yapılandırma**  
 Görüntülemek veya değiştirmek için hangi yapılandırma ayarlarını belirtir. Ayarları **hata ayıklama** (varsayılan), **sürüm**, veya **tüm yapılandırmaları**. Daha fazla bilgi için bkz: [hata ayıklama ve yayın proje yapılandırmaları](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
 **Platform**  
 Görüntülemek veya değiştirmek için hangi platform ayarlarını belirtir. Seçimleri içerebilir **herhangi bir CPU** (varsayılan), **x64**, ve **x86**. Daha fazla bilgi için bkz: [hata ayıklama ve yayın proje yapılandırmaları](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
## <a name="start-action"></a>Eylemi Başlat  
 **Eylemi Başlat** uygulama hata ayıklaması başlattığınızda öğeyi belirtir: Proje, özel bir program, bir URL veya hiçbir şey. Varsayılan olarak, bu seçeneği ayarlanmış **başlangıç projesi**. **Eylemi Başlat** ayarı **hata ayıklama** sayfa belirler değerini `StartAction` özelliği.  
  
 **Başlangıç projesi**  
 Uygulama hata ayıklaması olduğunda çalıştırılabilir dosyanın (Windows uygulaması ve konsol uygulaması projeleri) başlaması gerektiğini belirtmek için bu seçeneği belirleyin. Bu seçenek varsayılan olarak seçilidir.  
  
 **Dış program Başlat**  
 Uygulama hata ayıklaması sırasında belirli bir programı başlaması gerektiğini belirtmek için bu seçeneği belirleyin.  
  
 **URL ile tarayıcıyı başlatın**  
 Uygulama hata ayıklaması sırasında belirli bir URL erişilmesi gerektiğini belirtmek için bu seçeneği belirleyin.  
  
## <a name="start-options"></a>Başlatma seçenekleri  
 **Komut satırı bağımsız değişkenleri**  
 Bu metin kutusunda, hata ayıklama için kullanılacak komut satırı bağımsız değişkenleri girin.  
  
 **Çalışma dizini**  
 Bu metin kutusunda projenin başlatılacak dizini girin. Veya Gözat düğmesine (**...** ) bir dizin seçin.  
  
 **Uzak makine kullanın**  
 Uzak bir bilgisayardan uygulama hatalarını ayıklamak için bu onay kutusunu seçin ve metin kutusuna bir uzak bilgisayara yolunu girin.  
  
## <a name="enable-debuggers"></a>Hata ayıklayıcıları etkinleştir  
 **Yönetilmeyen kod hata ayıklamayı etkinleştir**  
 Bu seçenek yerel kodda hata ayıklama desteklenip desteklenmediğini belirtir. COM nesnelerine çağrıları yapıyorsanız veya projenizin çağıran yerel kodda yazılan özel bir programı başlatın ve yerel kod hata ayıklama, bu onay kutusunu seçin. Yönetilmeyen kod hata ayıklama devre dışı bırakmak için bu onay kutusunu temizleyin. Bu onay kutusu varsayılan olarak işaretli değildir.  
  
 **SQL Server hata ayıklamayı etkinleştir**  
 Seçin veya etkinleştirmek veya SQL yordamları, Visual Basic uygulamasında hata ayıklama devre dışı bırakmak için bu onay kutusunu temizleyin. Bu onay kutusu varsayılan olarak işaretli değildir.  
  
 **Barındırma işlemi Visual Studio etkinleştir**  
 Barındırma işlemi Visual Studio etkinleştirmek için bu onay kutusunu seçin. Bu onay kutusu varsayılan olarak seçilidir. Daha fazla bilgi için bkz: [barındırma süreci (vshost.exe)](../../ide/hosting-process-vshost-exe.md).  
  
 Bir güvenlik bölgesinde hata ayıklamak için bu seçeneği etkinleştirin ve **seçili izin kümesi ile bu uygulamanın hatalarını ayıklama** içinde [Gelişmiş Güvenlik Ayarları iletişim kutusu](../../ide/reference/advanced-security-settings-dialog-box.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da hata ayıklama](../../debugger/debugging-in-visual-studio.md)   
 [Proje ayarları için C# hata ayıklama yapılandırmaları](../../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Hata ayıklama özellikleri yönetme](http://msdn.microsoft.com/en-us/92474d16-e7fe-4fac-9287-6bd6b3a7eb68)   
 [Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../../ide/how-to-create-and-edit-configurations.md)