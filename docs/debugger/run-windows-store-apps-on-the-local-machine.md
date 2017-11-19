---
title: "Yerel makinede UWP uygulamaları çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: e42a21a8-6423-4caf-b4dc-72b263e76019
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08e0108a3fb7a93dc19fe1aa96988912068ace70
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="run-uwp-apps-on-the-local-machine"></a>Yerel makinede UWP uygulamaları çalıştırma
![Windows için yalnızca geçerlidir](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Hata ayıklama, test veya Performans Analizi bir UWP uygulaması üzerinde çalıştırmak için Visual Studio barındıran aynı makine üzerinde uygulamayı çalıştırabilirsiniz. Görüntü cihazda Dokunmatik özellikli ise, uygulama tam işlevselliğini alıştırma yapabilirsiniz; Aksi takdirde, fare ve klavye hareketleri sınırlı olacaktır.  
  
##  <a name="BKMK_How_to_run_on_a_local_machine"></a>Yerel makinede çalıştırma  
 Yerel makinede uygulamayı çalıştırmak için seçin **yerel makine** hata ayıklayıcısı hata ayıklamayı Başlat düğmesi yanında aşağı açılan listeden **standart** araç.  
  
 ![Yerel makine üzerinde çalışan](../debugger/media/vsrun_f5_local.png "VSRUN_F5_Local")  
  
 Göremiyorsanız **standart** araç tıklatın **Görünüm** menüsündeki **araç çubukları**ve ardından **standart**.  
  
 Aşağı açılan listeden yaptığınız seçim proje özellikleri dosyasında kalıcı ve varsayılan hedef çalıştırma olur.  
  
 Ayrıca, çalışma hedef doğrudan proje özelliklerini dosyasında ayarlayabilirsiniz. Proje adına sağ tıklayın **Çözüm Gezgini** ve ardından **özellikleri**. Ardından aşağıdakilerden birini yapın:  
  
-   C# ve Visual Basic projeleri tıklatın **hata ayıklama** ve ardından **yerel makine** gelen **hedef aygıt** aşağı açılan liste.  
  
     ![C &#35; ve Visual Basic proje özellik sayfası](../debugger/media/vsrun_cs_vb_projprop_local.png "VSRUN_CS_VB_ProjProp_Local")  
  
-   C++ ve JavaScript projelerinde genişletin **yapılandırma özellikleri** düğümünü tıklatın **hata ayıklama**ve ardından **yerel hata ayıklayıcı** gelen **hata ayıklayıcı başlatmak için** listesi.  
  
     ![C# 43; &#43; ve JavaScript proje özellikleri sayfasında](../debugger/media/vsrun_cpp_js_projprop_local.png "VSRUN_CPP_JS_ProjProp_Local")  