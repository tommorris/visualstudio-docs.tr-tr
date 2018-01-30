---
title: "Derleme olaylarını Visual Studio'da özel belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ede663f1053f6a3261de542b31b73fc9c8a10bb8
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="specifying-custom-build-events-in-visual-studio"></a>Visual Studio'da Özel Derleme Olayları Belirtme
Özel derleme olay belirterek, otomatik olarak komutları bir yapı başlamadan önce ya da sona erdikten sonra çalıştırabilirsiniz. Örneğin, .bat dosyası derleme önce başlar çalıştırmak veya yapı tamamlandıktan sonra yeni dosyaları bir klasöre kopyalayın. Yalnızca derleme derleme işlemindeki bu noktalarına başarıyla ulaşırsa derleme olaylarını çalıştırın.  
  
 Kullanmakta olduğunuz programlama dili hakkında ayrıntılı bilgi için aşağıdaki konulara bakın:  
  
-   Visual Basic--[nasıl yapılır: derleme olayları belirtme (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md).  
  
-   C# ve F #'ta--[nasıl yapılır: derleme olayları belirtme (C#)](../ide/how-to-specify-build-events-csharp.md).  
  
-   Visual C++--[derleme olaylarını belirtme](/cpp/ide/specifying-build-events).  
  
## <a name="syntax"></a>Sözdizimi  
 DOS komutları ile aynı söz dizimini yapı olayları izler ancak makroları derleme olaylarını daha kolay oluşturmak için kullanabilirsiniz. Kullanılabilir makroları listesi için bkz: [oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
 En iyi sonuçlar için bu biçim ipuçları izleyin:  
  
-   Ekleme bir `call` tüm olayları, oluşturmadan önce deyimi .bat dosyaları çalıştırın.  
  
     Örnek:`call C:\MyFile.bat`  
  
     Örnek:`call C:\MyFile.bat call C:\MyFile2.bat`  
  
-   Dosya yolları tırnak işaretleri içine alın.  
  
     Örnek (için [!INCLUDE[win8](../debugger/includes/win8_md.md)]): "% ProgramFiles (x86) %\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe"-, "$(TargetPath)"  
  
-   Birden çok komut, satır sonları kullanarak ayırın.  
  
-   Gerektiği gibi joker karakterler.  
  
     Örnek: `for %I in (*.txt *.doc *.html) do copy %I c:\` *mydirectory*`\`  
  
    > [!NOTE]
    >  `%I`Yukarıdaki kod olmalıdır `%%I` toplu komut.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)   
 [Derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [MSBuild özel karakterleri](../msbuild/msbuild-special-characters.md)   
 [İzlenecek yol: Uygulama Oluşturma](../ide/walkthrough-building-an-application.md)