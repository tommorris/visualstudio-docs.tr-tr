---
title: Microsoft Visual Studio hata ayıklayıcısı (özel durum oluştu) iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.exceptions.thrown
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Microsoft Visual Studio Debugger (Exception Thrown) dialog box
- exception handling, during debugging
- debugger, exceptions
- throwing exceptions, during debugging
ms.assetid: 1fe98d10-c8f9-4b39-a920-99169bfd542e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24ccb3de6b22f54b239b5b772490a8d05a990dbd
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31475031"
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>Microsoft Visual Studio Hata Ayıklayıcısı (Özel Durum Oluştu) İletişim Kutusu
Programın bir özel durum oluştu. Bu iletişim kutusu, özel durum türünü bildirir. Bu özel durumu işlemek kodunuzu gerekir. Özel durum işleme için aşağıdaki seçenekler arasından seçim yapabilirsiniz:  
  
 **Sonu**  
 Hata ayıklayıcısında araya girmektir yürütülmesine izin verir. Özel durum işleyici sonu önce çağrılır. Aradan devam ederseniz, özel durum işleyici çağrılır.  
  
 **Devam etmek**  
 Devam etmek yürütme, özel durum işleyicisi özel durumu işlemek iletmenize olanak sağlar. Bu seçenek, belirli türde bir özel durumlar için kullanılamaz. **Devam** devam etmek uygulama izin verir. Yerel bir uygulamada, özel durum işlenemezse neden olur. Yönetilen bir uygulamada ya da sona erdirmek için program veya barındırma bir uygulama tarafından işlenmesi için özel durum neden olur.  
  
> [!NOTE]
>  Yönetilen kod içinde işlenmeyen bir özel sonra devam edemiyor. Seçme **devam** sonra durdurmak hata ayıklama işlenmeyen bir özel durum yönetilen kodda neden olur.  
  
 **Yoksay**  
 Özel durum işleyici çağırmadan devam etmek yürütme sağlar. Özel durum işleyici çağrılır olduğundan, bu ek özel durumlar ve hatalar da dahil daha fazla sonuçlara yol açabilir. Bu seçenek, belirli türde bir özel durumlar için kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durumları hata ayıklayıcısı ile yönetme](../debugger/managing-exceptions-with-the-debugger.md)   
 [Özel durumlar için en iyi yöntemler](/dotnet/standard/exceptions/best-practices-for-exceptions)   
 [Özel Durum İşleme](/cpp/windows/exception-handling-cpp-component-extensions)