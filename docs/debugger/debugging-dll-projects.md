---
title: DLL projelerinde hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 05/23/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- templates, debugging DLLs
- DLLs, debugging
- debugging [Visual Studio], DLLs
ms.assetid: 433cab30-d191-460b-96f7-90d2530ca243
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c5da503dd3eb1aec83c5f1fdef58261960d66d7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31477423"
---
# <a name="debugging-dll-projects-from-visual-studio"></a>Visual Studio'dan DLL projelerinde hata ayıklama
Aşağıdaki Visual Studio şablonları DLL'leri oluşturun:  
  
-   (C++, C# ve Visual Basic) Sınıf kitaplığı   

-   (C++): Win32 konsol DLL projesi
  
     Daha fazla bilgi için bkz: [MFC hata ayıklama teknikleri](../debugger/mfc-debugging-techniques.md).

-   (C++, C# ve Visual Basic): Windows Forms denetimi kitaplığı
  
     Bir Windows Forms Denetim Kitaplığı hata ayıklama, bir sınıf kitaplığı proje hata ayıklama için benzer. Çoğu durumda, başka bir projeden Windows denetimi çağırır. Arama projenin hata ayıklamasını yaparken, Windows Denetim koda adım kesme noktalarını ayarlayın ve diğer hata ayıklama işlemleri. Daha fazla bilgi için bkz: [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index).  

  
##  <a name="vxtskdebuggingdllprojectsbuildingadebugversion"></a> Hata ayıklama sürümü oluşturma  
 Nasıl hata ayıklama başlattığınız olsun, DLL Dosyasının hata ayıklama sürümü ilk derleme ve hata ayıklama sürümü nerede bulacağınızı uygulama bekler konumda olduğundan emin olun emin olun. Bu belirgin görünebilir, ancak bu adımı unutursanız, uygulamanın DLL farklı bir sürümünü bulmak ve yüklemek. Program neden isabetini hiçbir zaman ulaşıldı merak ediyor sırasında çalışmaya devam eder. Hata ayıklama yaptığınız zaman programınızı yüklenen Hata Ayıklayıcı'nın açarak hangi DLL'lerin doğrulayabilirsiniz **modülleri** penceresi. **Modülleri** penceresi, her bir DLL veya EXE ayıkladığınız işlemde yüklü listeler. Daha fazla bilgi için bkz: [nasıl yapılır: modüller penceresini kullanma](../debugger/how-to-use-the-modules-window.md).  
 C++'da yazılmış kod eklemek hata ayıklayıcı için kod yayma gerekir `DebuggableAttribute`. Bu, kod için otomatik olarak ile bağlayarak ekleyebilirsiniz [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) bağlayıcı seçeneği.  
  
##  <a name="vxtskdebuggingdllprojectsmixedmodedebugging"></a> Karışık mod hata ayıklaması  
 Yönetilen kod veya yerel koda DLL çağrıları çağrı yapan uygulamanın yazılabilir. Yönetilen DLL yerel kod tarafından çağrılır ve her ikisi de hata ayıklamak istediğiniz, yönetilen ve yerel hata ayıklayıcıları her ikisi de etkinleştirilmesi gerekir. Bu konuda seçebileceğiniz  **\<Proje > özellik sayfaları** iletişim kutusu veya penceresi. Bunu nasıl yapacağınız olup, DLL projesi veya arama uygulama projesi hata ayıklama başlamanıza bağlıdır. Daha fazla bilgi için bkz: [nasıl yapılır: karışık modda hata ayıklama](../debugger/how-to-debug-in-mixed-mode.md).  
  
##  <a name="vxtskdebuggingdllprojectschangingdefaultconfigurations"></a> Varsayılan yapılandırmaları değiştirme  
 Proje şablonu ile bir konsol uygulama projesi oluşturduğunuzda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklama ve yayın yapılandırmaları için gereken ayarları otomatik olarak oluşturur. Gerekirse, bu ayarları değiştirebilirsiniz. Daha fazla bilgi için bkz: [bir C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md), [C# hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-csharp-debug-configurations.md), [bir Visual Basic hata ayıklama yapılandırması proje ayarları ](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), ve [nasıl yapılır: kümesi hata ayıklama ve dağıtım yapılandırmalarını](../debugger/how-to-set-debug-and-release-configurations.md).  
  
##  <a name="vxtskdebuggingdllprojectswaystodebugthedll"></a> DLL hata ayıklamak için yollar  
 Bu bölümdeki projelerin her biri bir DLL oluşturur. DLL doğrudan çalıştıramazsınız; bir uygulama tarafından genellikle bir EXE çağrılması gerekir. Daha fazla bilgi için bkz: [oluşturma ve yönetme Visual C++ projeleri](/cpp/ide/creating-and-managing-visual-cpp-projects). Çağrı yapan uygulamanın herhangi biri aşağıdaki ölçütlere uygun:  
  
-   Başka bir projeye aynı yerleşik bir uygulama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sınıf kitaplığı içeren çözüm.  
  
-   Bir test veya üretim bilgisayarda zaten dağıtılmış varolan bir uygulama.  
  
-   Web sitesinde bulunan ve bir URL aracılığıyla erişilebilir.  
  
-   DLL katıştırır bir Web sayfasını içeren bir Web uygulamasıdır.  
  
###  <a name="vxtskdebuggingdllprojectsthecallingapplication"></a> Çağıran uygulamada hata ayıklama  
DLL hata ayıklamak için çağıran uygulama, genellikle ya da bir EXE ya da bir Web uygulaması hata ayıklama tarafından başlatın. Hata ayıklamak için birkaç yolu vardır.  
  
-   Arama uygulaması için bir proje varsa, bu projeyi açın ve yürütülmesini Başlat **hata ayıklama** menüsü. Daha fazla bilgi için bkz: [hata ayıklayıcısını kullanmaya başlama](../debugger/getting-started-with-the-debugger.md).  
  
-   Çağrı yapan uygulamanın bir test veya üretim bilgisayarda zaten dağıtılmış varolan bir programı ise ve zaten çalışıyor kendisine ekleyebilirsiniz. Internet Explorer tarafından barındırılan bir denetim veya bir Web sayfasındaki denetimi DLL ise, bu yöntemi kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: bir çalışan işlem ekleme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
-   DLL projesinde ayıklayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: DLL projesinde hata ayıklama](../debugger/how-to-debug-from-a-dll-project.md).  
  
-   Buradan ayıklayabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [komut penceresi](#vxtskdebuggingdllprojectstheimmediatewindow). Bu durumda, **hemen** penceresi uygulamanın rol oynar.  
  
Çağıran uygulamada hata ayıklama başlamadan önce genellikle Sınıf Kitaplığı'nda bir kesme noktası belirleyerek isteyeceksiniz. Daha fazla bilgi için bkz: [kullanarak kesme noktaları](../debugger/using-breakpoints.md). Kesme noktası isabet olduğunda sorunu ayırt etmek kadar her satır, eylem Gözlemleme koduyla geçebilirsiniz. Daha fazla bilgi için bkz: [hata ayıklayıcı kodda gezinme](../debugger/navigating-through-code-with-the-debugger.md).
  
###  <a name="vxtskdebuggingdllprojectstheimmediatewindow"></a> Komut penceresi  
 Bir arama uygulaması gerek kalmadan işlevler veya yöntemler dll değerlendirebilirsiniz. Tasarım zamanı hata ayıklama yapın ve kullandığınız **hemen** penceresi. Bu şekilde hata ayıklamak için DLL projesi açıkken izleme bu adımları uygulayın:  
  
1.  Hata ayıklayıcıyı açmak **hemen** penceresi.  
  
2.  Adlı bir yöntem test etmek için `Test` sınıfında `Class1`, türünde bir nesne örneği `Class1` hemen penceresinde aşağıdaki C# kodu yazarak. Bu yönetilen kod Visual Basic ve C++ için uygun sözdizimini değişikliklerle çalışır:  
  
    ```  
    Class1 obj = new Class1();  
    ```  
  
     C# ' ta tüm adları tam olarak nitelenmiş olmalıdır. Ayrıca, herhangi bir yöntemi veya değişkenleri geçerli kapsamdaki ve hata ayıklama oturumu bağlamında olması gerekir.  
  
3.  Varsayılarak `Test` alır `int` parametresi değerlendirmek `Test` kullanarak **hemen** penceresi:  
  
    ```  
    ?obj.Test(10)  
    ```  
  
     Sonuç yazdırılır **hemen** penceresi.  
  
4.  Hata ayıklama devam edebilirsiniz `Test` içindeki bir kesme noktası yerleştirme ve işlevi yeniden hesaplama:  
  
    ```  
    ?obj.Test(10);  
    ```  
  
     Kesme noktası isabet ve adım adım kuramaz `Test`. Yürütme ayrıldıktan sonra `Test`, hata ayıklayıcı geri Tasarım modunda olacaktır.

## <a name="vxtskdebuggingdllprojectsexternal"></a> C++ projesi dış bir DLL'den hata ayıklama

Hata ayıklama özelliği (kod üzerinden atlama gibi) kullanılabilir bağlı olacaktır, projenize dış DLL ayıkladığınız, [DLL hata ayıklama yapılandırmasını](#vxtskdebuggingdllprojectsbuildingadebugversion) , oluşturulan ve olup olmadığını [.pdb dosyasını](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) ve diğer gerekli dosyalar DLL için kullanılabilir.

Projenizi DLL ve hata ayıklama için kullanılan .pdb dosyasını bulmak gerekir. Bu dosyaları kopyalamak için bir özel derleme görevi oluşturabilirsiniz  **\<proje klasörü > \Debug** çıkış klasörü veya kopyalayabilir dosyaları çıkış klasörüne el ile.

Üstbilgi dosyaları ve *.lib dosya konumlarını özellik sayfalarında kolayca ayarlayabilirsiniz (C++ projesine sağ tıklayın ve seçin **Görünüm Özellikleri**ve ardından **tüm yapılandırmaları**) kopyalamak için gerek kalmadan bunları çıktı klasörünüze kopyalayın:

- C/C++ klasörü (genel kategori) - başlık dosyaları içeren klasör belirtin **ek içeren dizinler** alan.
- Bağlayıcı klasörü (genel kategori) - .lib dosyasını içeren klasörü belirtin **ek kitaplıkları dizinler** alan. 
- Bağlayıcı klasörü (giriş kategori) - belirtin tam yolunu ve dosya .lib dosyasında için **ek bağımlılıklar** alan.

Yapılandırma doğru olduğunda yürütülmesini başlatarak ayıklayabilirsiniz **hata ayıklama** menüsü.

Proje ayarları hakkında daha fazla bilgi için bkz: [özellik sayfaları (Visual C++)](/cpp/ide/property-pages-visual-cpp).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Visual C++ proje türleri](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Proje ayarları için C# hata ayıklama yapılandırmaları](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)