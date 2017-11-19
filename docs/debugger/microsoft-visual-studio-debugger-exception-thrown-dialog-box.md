---
title: "Microsoft Visual Studio hata ayıklayıcısı (özel durum oluştu) iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.exceptions.thrown
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
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: adda9e64a911a8a5119d28f97d3e2424710367d7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Özel durum işleme](/cpp/windows/exception-handling-cpp-component-extensions)