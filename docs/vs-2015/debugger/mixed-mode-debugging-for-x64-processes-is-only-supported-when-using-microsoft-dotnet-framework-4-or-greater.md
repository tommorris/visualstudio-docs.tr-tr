---
title: Karışık modda hata ayıklama işlemleri Microsoft.NET Framework 4 kullanırken yalnızca desteklenen x64 için veya büyük | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0297d9bcfb380261d2ad2e73853ded70285f1b35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697102"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>x64 işlemleri için karışık modda hata ayıklama yalnızca Microsoft.NET Framework 4 veya daha yenisi kullanılırken desteklenir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [karışık modda hata ayıklama işlemleri Microsoft.NET Framework 4 kullanırken yalnızca desteklenen x64 için veya büyük](https://docs.microsoft.com/visualstudio/debugger/mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoft-dotnet-framework-4-or-greater).  
  
NET Framework sürümleri daha önce 4'ten x64 karma mod hata ayıklama için desteği olmayan işler. Bu, yerel kod için yönetilen kod veya yerel koda yönetilen kod için hata ayıklama sırasında girilemiyor olduğunu gösterir.  
  
### <a name="workarounds"></a>Geçici Çözümler  
  
-   Microsoft .NET Framework 4 veya daha sonra kullanmak için projenizin güncelleştirin.  
  
     – veya –  
  
     Yönetilen ve yerel kodunuzu ayrı hata ayıklama oturumlarında hata ayıklayın.  
  
     – veya –  
  
     Karma kodunuzu bir 32 bitlik işlem olarak, aşağıdaki yordamlarda açıklandığı gibi hata ayıklayın.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Platform 32-bit (Visual Basic veya C#) değiştirileceğini  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri**.  
  
2.  Özellik Sayfaları'nda tıklatın **derleme** veya **hata ayıklama** sekmesi.  
  
3.  Tıklayın **Platform** x86 platformlar listesinden seçin.  
  
     Varsayılan olarak, Visual Basic ve C# Derleyicileri varsayılan herhangi bir CPU üzerinde çalıştırmak için kod üretir. Bu ikili dosyalar, bir 64 bit bilgisayarda 64 bit işlem çalıştırın. Bir 32 bit işlemde çalıştırmak için seçmelisiniz **Win32**değil **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>32-bit (C/C++) için platform değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından tıklayın **özellikleri**.  
  
2.  Özellik Sayfaları'nda tıklatın **Platform** ve Win32 platformları listesinden seçin.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Bkz: [SQL hata ayıklamayı kurma](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [64 Bit uygulamalarda hata ayıklama](../debugger/debug-64-bit-applications.md)



