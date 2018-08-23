---
title: Karışık modda hata ayıklama yalnızca Microsoft .NET Framework 2.0 veya 3.0 sürümü kullanılırken desteklenir | Microsoft Docs
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
- vs.debug.error.interop_unsupported_to_old
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc2a5193b23002d1b5403564b71bb707310618fb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686378"
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>Karışık Modda Hata Ayıklama Yalnızca Microsoft .NET Framework 2.0 veya 3.0 Sürümü Kullanılırken Desteklenir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [karışık mod hata ayıklama yalnızca kullanılırken desteklenir Microsoft .NET Framework 2.0 veya 3.0](https://docs.microsoft.com/visualstudio/debugger/mixed-mode-debugging-is-only-supported-when-using-microsoft-dotnet-framework-2-0-or-3-0).  
  
Daha önce Microsoft .NET Framework sürümleri 2.0 64-bit işlemlerinin karışık mod hata ayıklama için destek sağlıyor musunuz. Bu, hata ayıklama sırasında yerel kod için yönetilen kod veya yönetilen koda yerel koddan girilemiyor anlamına gelir.  
  
 Bu sorunu gidermek için şunları yapabilirsiniz:  
  
-   Microsoft .NET Framework 2.0 veya 3.0 kullanmak için projenizin güncelleştirin.  
  
-   Yönetilen ve yerel kodunuzu ayrı hata ayıklama oturumlarında hata ayıklayın.  
  
-   Karma kodunuzu bir 32 bitlik işlem olarak, aşağıdaki yordamlarda açıklandığı gibi hata ayıklayın.  
  
### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>İşletim sistemi 32 bit (Visual Basic veya C#) değiştirileceğini  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri** kısayol menüsünde.  
  
2.  Özellik Sayfaları'nda tıklatın **derleme** veya **hata ayıklama** sekmesi.  
  
3.  Tıklayın **Platform**ve ardından **x86** platformlar listesinden.  
  
     Varsayılan olarak, Visual Basic ve C# Derleyicileri herhangi bir CPU üzerinde çalıştırmak için kod üretir. Bu ikili dosyalar, bir 64 bit bilgisayarda 64 bit işlem çalıştırın. Bir 32 bit işlemde çalıştırmak için seçmelisiniz **Win32**değil **AnyCPU**.  
  
### <a name="to-change-the-operating-system-to-32-bit-cc"></a>İşletim sistemi 32-bit (C/C++) değiştirileceğini  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri** kısayol menüsünde.  
  
     Özellik Sayfaları'nda tıklatın **Platform**ve ardından **Win32** platformlar listesinden.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Bkz: [SQL hata ayıklamayı kurma](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [64 Bit uygulamalarda hata ayıklama](../debugger/debug-64-bit-applications.md)



