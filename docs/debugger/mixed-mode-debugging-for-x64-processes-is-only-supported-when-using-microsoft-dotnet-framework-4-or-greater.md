---
title: Karışık modda hata ayıklama işlemleri Microsoft.NET Framework 4 kullanırken yalnızca desteklenen x64 için veya büyük | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 224e4de9e3a00882cb065037005b7644343262d5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>x64 işlemleri için karışık modda hata ayıklama yalnızca Microsoft.NET Framework 4 veya daha yenisi kullanılırken desteklenir
.NET framework sürümleri 4 sağlıyor mu'den önceki x64 karışık modda hata ayıklama için destek işler. Bu, yerel koda yönetilen koddan ya da yerel koddan yönetilen koda hata ayıklama sırasında adım edilemez olduğunu anlamına gelir.  
  
### <a name="workarounds"></a>Geçici Çözümler  
  
-   Microsoft .NET Framework 4 veya daha sonra kullanmak için projenizin güncelleştirin.  
  
     -veya-  
  
     Yönetilen ve yerel kod hata ayıklama ayrı hata ayıklama oturumu.  
  
     -veya-  
  
     Aşağıdaki yordamlarda açıklandığı gibi karma kodunuzu bir 32 bitlik işlem olarak hata ayıklama.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Platform 32-bit (Visual Basic veya C#) değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri**.  
  
2.  Özellik sayfaları tıklatın **derleme** veya **hata ayıklama** sekmesi.  
  
3.  Tıklatın **Platform** ve x86 platformları listeden seçin.  
  
     Varsayılan olarak, Visual Basic ve C# Derleyicileri varsayılan herhangi bir CPU'da çalıştırmak için kod oluşturur. Bir 64-bit bilgisayarda 64 bit işlemleri olarak bu ikili dosyaları çalıştırın. Bir 32 bitlik işlem olarak çalıştırmak için seçmelisiniz **Win32**değil **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>Platform 32-bit (C/C++) değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın ve ardından **özellikleri**.  
  
2.  Özellik sayfaları tıklatın **Platform** ve Win32 platformları listeden seçin.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Bkz: [SQL hata ayıklama Kurulumu ayarı](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [64 Bit uygulamalarda hata ayıklama](../debugger/debug-64-bit-applications.md)