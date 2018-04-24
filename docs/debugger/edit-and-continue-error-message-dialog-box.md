---
title: Düzenle ve devam et hata iletisi iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.ENC.SupportedButNotAvaiable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b521eafcc62a49f2dd2a4c327158070bdbe62ce
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="edit-and-continue-error-message-dialog-box"></a>Düzenle ve Devam Et Hata İletisi İletişim Kutusu
Düzenle ve devam et, destekleyen bir dilde ayıklarken bu iletişim kutusu görünür ancak **Düzenle ve devam et** yapmış olduğunuz kod değişiklikleri türü için kullanılamaz. Hata iletisi kutu içinde daha ayrıntılı bir açıklama sağlar. Bu iletişim kutusunu dahil görmek için olası nedenler:  

-   SQL Server kod düzenleme çalışıldı.

-   İyileştirilmiş kod düzenleme çalışıldı. (Sürüm derleme için hata ayıklama derlemesi geçmeniz gerekebilir.)

-   Kod çalıştırılırken düzenlemeye çalıştığınız (yerine hata ayıklayıcısı'ndaki duraklatıldı sırada). Deneyin [kesme noktası ayarlama](../debugger/using-breakpoints.md) ve duraklatıldı sırada kod düzenleme.

-   Yönetilmeyen hata ayıklama etkin olduğunda, yönetilen kod düzenleme çalışıldı. Düzenle ve devam et ile çalışmıyor [karışık mod hata ayıklaması](../debugger/how-to-debug-in-mixed-mode.md).

-   Düzenle ve devam et tarafından programlama dilinde desteklenmeyen bir kod değişikliği yapılan. Daha fazla bilgi için bkz: desteklenmeyen kod değişiklikleri konular [C#](../debugger/supported-code-changes-csharp.md), [Visual Basic](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md), ve [C++](../debugger/supported-code-changes-cpp.md).
  
-   Başlayarak yerine bağlı bir program kodunda düzenlemeye çalıştığınız **hata ayıklama** menüsü.  
  
-   Kod bir Dr hata ayıklama sırasında Düzenle çalışıldı. Watson dökümü.  
  
-   İşlenmeyen özel durum oluştu sonra kod ve seçeneği düzenlemeye çalıştığınız "**işlenmeyen özel durum çağrı yığınındaki bırakma**" seçilmedi.  
  
-   Kod katıştırılmış çalışma zamanı uygulama hata ayıklama sırasında Düzenle çalışıldı.
  
-   Yönetilen kod 4.5.1 önce .NET Framework sürümünü kullanarak düzenlemeye çalıştığınız ve hedef bir 64-bit uygulamadır. İsterseniz kullanım Düzenle ve devam et, hedef x86 için ayarlamanız gerekir. (*projectname* **özellikleri**, **derleme** sekmesinde **Gelişmiş derleyici** ayarı.).  
  
-   Hata ayıklama sırasında değiştirildi ve yüklenene bütünleştirilmiş kodda Düzenle çalışıldı.  
  
-   Yüklenmemiş bir bütünleştirilmiş kod düzenleme çalışıldı.  
  
-   (Yeni sürümü derleme hataları olduğundan), uygulamanın eski bir sürümü hata ayıklama başlatıldı.
  
## <a name="uielement-list"></a>UIElement Listesi  
 **TAMAM**  
 İletişim kutusundan çıkmak ve hemen önceki düzenleme denemesini iptal edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Düzenle ve devam et blog gönderisine](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/)  
 [Desteklenen Kod Değişiklikleri (C++)](../debugger/supported-code-changes-cpp.md)