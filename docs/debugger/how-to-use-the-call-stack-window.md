---
title: Visual Studio Hata Ayıklayıcısı'ndaki çağrı yığınını görüntülemek | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/06/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.callstack
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
- aspx
helpviewer_keywords:
- threading [Visual Studio], displaying calls to or from
- functions [debugger], viewing code on call stack
- disassembly code
- breakpoints, Call Stack window
- debugging [Visual Studio], switching to another stack frame
- debugging [Visual Studio], Call Stack window
- Call Stack window, viewing source code for functions on the call stack
- stack, switching stack frames
- Call Stack window, viewing disassembly code for functions on the call stack
ms.assetid: 5154a2a1-4729-4dbb-b675-db611a72a731
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d20a1ac9f1a09b93f577c6aa90f550ccd6ff0def
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="view-the-call-stack-and-use-the-call-stack-window-in-the-visual-studio-debugger"></a>Çağrı yığınını görüntülemek ve Visual Studio hata ayıklayıcısında çağrı yığını penceresini kullanma

Kullanarak **çağrı yığını** penceresinde, şu anda yığında olan işlev veya yordam çağrıları görüntüleyebilirsiniz. **Çağrı yığını** penceresi içinde yöntemleri ve işlevleri denir sipariş gösterir. Çağrı yığınını incelemek ve bir uygulamanın yürütme akışını anlamak için iyi bir yoludur.
  
Zaman [hata ayıklama simgeleri](#bkmk_symbols) çağrı yığını bölümü için kullanılabilir değil **çağrı yığını** penceresi çağrı yığını kısmı doğru bilgilerini görüntülemek kuramıyor olabilir. Bu gerçekleşirse, aşağıdaki gösterim görünür:  
  
`[Frames below may be incorrect and/or missing, no symbols loaded for name.dll]`

>  [!NOTE]
> **Çağrı yığını** penceresi benzer hata ayıklama perspektife Eclipse gibi bazı IDE içinde. 

> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana burada etkin ayarlarınıza veya sürümünüze bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.  Bkz: [IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
  
## <a name="view-the-call-stack-while-in-the-debugger"></a>Çağrı yığını ayıklayıcısında görüntüleyin 
  
-   Hata ayıklama, buna **hata ayıklama** menüsünde, select **Windows > çağrı yığını**.

 ![Çağrı yığını penceresi](../debugger/media/dbg_basics_callstack_window.png "CallStackWindow")

Sarı bir ok yürütme işaretçinin şu anda bulunduğu yığın çerçevesi tanımlar. Varsayılan olarak, bu, bilgileri kaynağında görünür yığın çerçevesi olan **Yereller**, **otomobiller**, **izleme**, ve **ayrıştırılmış** windows . Hata ayıklayıcı bağlamını yığında başka bir çerçeve değiştirmek istiyorsanız, bunu yapabilirsiniz [başka bir yığın çerçevesine geçme](#bkmk_switch).   
  
## <a name="display-non-user-code-in-the-call-stack-window"></a>Çağrı yığını penceresinde kullanıcı olmayan kodu görüntüleme  
  
-   Sağ **çağrı yığını** penceresini açın ve select **Göster harici kod**.

Kullanıcı olmayan kodudur ne zaman gösterilmez herhangi bir kod [sadece kendi kodumu](../debugger/just-my-code.md) etkinleştirilir. Yönetilen kodda kullanıcı olmayan kod çerçeveleri varsayılan olarak gizlidir. Aşağıdaki gösterim yerine kullanıcı olmayan kod çerçeveleri görünür:  
  
**[\<Harici kod >]**  
  
## <a name="bkmk_switch"></a> Başka bir yığın çerçevesi (hata ayıklayıcı bağlamını değiştirme) geçiş
  
1.  İçinde **çağrı yığını** penceresinde, yığın çerçeve olan kodu ve görüntülemek istediğiniz verileri sağ tıklatın.

    Veya, bir çerçevede çift tıklayarak **çağrı yığını** penceresinde seçili çerçeveye geçiş. 
  
2.  Seçin **geçiş çerçeveye**.  
  
     Süslü kuyruklu yeşil bir ok seçtiğiniz yığın çerçevesi yanında görüntülenir. Hala sarı ok ile işaretlenmiş özgün çerçevesinde yürütme işaretçi kalır. Seçerseniz **adım** veya **devam** gelen **hata ayıklama** menüsünde yürütme devam özgün çerçevede, seçtiğiniz çerçevenin.  
  
## <a name="view-the-source-code-for-a-function-on-the-call-stack"></a>Çağrı yığınındaki işlevi için kaynak kodu görüntüleme  
  
-   İçinde **çağrı yığını** penceresinde, sağ tıklatın, kaynak kodu işlevi istediğiniz görebilir ve **gitmek için kaynak kodunu**.

## <a name="run-to-a-specific-function-from-the-call-stack-window"></a>Belirli bir işlev çağrı yığını penceresinde çalıştırma  
  
-  İçinde **çağrı yığını** penceresinde işlevi seçin, sağ tıklatın ve seçin **çalıştırmak için imleç**.  
  
## <a name="set-a-breakpoint-on-the-exit-point-of-a-function-call"></a>Bir işlev çağrısı çıkış noktasında bir kesme noktası ayarlama  
  
-   Bkz: [bir çağrı yığını işlevini bir kesme noktası belirleyerek](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_the_call_stack_window).

## <a name="display-calls-to-or-from-another-thread"></a>İçin veya başka bir iş parçacığından çağrıları görüntüleme  
  
-   Sağ **çağrı yığını** penceresini açın ve select **dahil çağrıları To/From diğer iş parçacıkları**.   
  
## <a name="visually-trace-the-call-stack"></a>Görsel olarak çağrı yığınını izleme  

Visual Studio Enterprise (yalnızca) kullanıyorsanız, hata ayıklarken çağrı yığınında için kod haritalarını görüntüleyebilirsiniz.

- İçinde **çağrı yığını** penceresinde kısayol menüsünü açın. Seçin **çağrı yığını kod haritasında Göster**. (Klavye: **CTRL** + **SHIFT** + **`**)  
  
    Ayrıntılı bilgi için bkz: [hata ayıklarken çağrı yığınında yöntemler eşleme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).

![Çağrı yığını kod haritasında Göster](../debugger/media/dbg_basics_show_call_stack_on_code_map.gif "ShowCallStackOnCodeMap")
  
## <a name="view-the-disassembly-code-for-a-function-on-the-call-stack"></a>Çağrı yığınındaki bir işlev için ayrıştırılmış kodu görüntüleme  
  
-   İçinde **çağrı yığını** penceresinde, sağ tıklatın, Ayrıştırılmış kod işlevi istediğiniz görebilir ve **ayrıştırılmış Git**.    

## <a name="change-the-optional-information-displayed"></a>Değişiklik görüntülenen isteğe bağlı bilgiler  
  
-   Sağ **çağrı yığını** penceresi ve kümesi ya da temizleyin **Göster \< ***istediğiniz bilgileri***>**.  
  
## <a name="bkmk_symbols"></a> Bir modül için yük simgeleri
İçinde **çağrı yığını** penceresinde, şu anda yüklenen simgeleri yok kod simgelerini hata ayıklama yükleyebilirsiniz. Bu simgeleri .NET Framework veya Microsoft ortak simgesi sunucularından indirilen sistem simgeleri ya da bir simge yolu ayıkladığınız bilgisayarda sembolleri olabilir.  
  
Bkz: [simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
### <a name="to-load-symbols"></a>Simgeler yüklemek için  
  
1.  İçinde **çağrı yığını** penceresinde, hangi simgeleri yığın çerçevesi yüklenmedi sağ tıklatın. Çerçeve soluk.  
  
2.  İşaret **yük simgeleri** ve ardından **Microsoft simge sunucuları** (varsa) veya sembol yoluna göz atın.  
  
### <a name="to-set-the-symbol-path"></a>Simge yolu ayarlamak için  
  
1.  İçinde **çağrı yığını** penceresinde, seçin **simge ayarlarını** kısayol menüsünden.  
  
     **Seçenekleri** iletişim kutusu açılır ve **simgeleri** sayfası görüntülenir.  
  
2.  Tıklatın **simge ayarları**.  
  
3.  İçinde **seçenekleri** iletişim kutusunda, klasör simgesine tıklayın.  
  
     İçinde **simge (.pdb) dosya konumları** kutusunda, bir imleç görüntülenir.  
  
4.  Simgenin konumu bir directory yol adı ayıkladığınız bilgisayarda yazın. Yerel ve uzaktan hata ayıklama için yerel bilgisayarınızda bir yolu budur.
  
5.  Tıklatın **Tamam** kapatmak için **seçenekleri** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık kod ve eksik bilgileri çağrı yığını penceresi](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)  
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)   
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Kesme noktalarını kullanma](../debugger/using-breakpoints.md)