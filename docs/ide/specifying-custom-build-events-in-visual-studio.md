---
title: Visual Studio'da özel derleme olayları belirtme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c45f439a8bb1ae559e915769f8ea89ef7f4bf863
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="specify-custom-build-events-in-visual-studio"></a>Visual Studio'da özel derleme olayları belirtme

Özel derleme olay belirterek, otomatik olarak komutları bir yapı başlamadan önce ya da sona erdikten sonra çalıştırabilirsiniz. Örneğin, çalıştırabilirsiniz bir *.bat* bir yapı başlamadan önce dosya veya yapılandırma tamamlandıktan sonra yeni dosyaları bir klasöre kopyalayın. Yalnızca derleme derleme işlemindeki bu noktalarına başarıyla ulaşırsa derleme olaylarını çalıştırın.

 Kullanmakta olduğunuz programlama dili hakkında ayrıntılı bilgi için aşağıdaki konulara bakın:

-   Visual Basic--[nasıl yapılır: belirtin derleme olayları (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md).

-   C# ve F #'ta--[nasıl yapılır: belirtin derleme olayları (C#)](../ide/how-to-specify-build-events-csharp.md).

-   Visual C++--[belirt derleme olaylarını](/cpp/ide/specifying-build-events).

## <a name="syntax"></a>Sözdizimi

DOS komutları ile aynı söz dizimini yapı olayları izler ancak makroları derleme olaylarını daha kolay oluşturmak için kullanabilirsiniz. Kullanılabilir makroları listesi için bkz: [oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

 En iyi sonuçlar için bu biçim ipuçları izleyin:

-   Ekleme bir `call` tümünü Çalıştır olayları oluşturmadan önce deyimi *.bat* dosyaları.

     Örnek: `call C:\MyFile.bat`

     Örnek: `call C:\MyFile.bat call C:\MyFile2.bat`

-   Dosya yolları tırnak işaretleri içine alın.

     Örnek (için [!INCLUDE[win8](../debugger/includes/win8_md.md)]): "% ProgramFiles (x86) %\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe"-, "$(TargetPath)"

-   Birden çok komut, satır sonları kullanarak ayırın.

-   Gerektiği gibi joker karakterler.

     Örnek: `for %I in (*.txt *.doc *.html) do copy %I c:\` *mydirectory*`\`

    > [!NOTE]
    >  `%I` Yukarıdaki kod olmalıdır `%%I` toplu komut.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)
- [Derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)
- [MSBuild özel karakterleri](../msbuild/msbuild-special-characters.md)
- [İzlenecek yol: bir uygulama oluşturma](../ide/walkthrough-building-an-application.md)
