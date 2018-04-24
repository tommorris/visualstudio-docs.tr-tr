---
title: 'Nasıl yapılır: Düzenle kullanın ve devam et (C#) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a1f073d401ddc1a99e365245f2a8c1b66b13fb8a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-use-edit-and-continue-c"></a>Nasıl Yapılır: Düzenle ve Devam Et'i Kullanma (C#)
Düzenle ve devam et için C# ile kodunuza kesme modunda hata ayıklama sırasında değişiklik yapabilirsiniz. Değişiklikleri durdurmak ve hata ayıklama oturumu yeniden başlatmak zorunda kalmadan uygulanabilir.  
  
 Kesme modunda değişiklik sonra da bir hata ayıklayıcı yürütme seçin, Düzenle ve devam et otomatik olarak çağrılır komutu gibi **devam**, **adım**, veya **sonraki deyimi Ayarla**, veya bir hata ayıklayıcı penceresinde işlevi değerlendirilemiyor.  
  
> [!NOTE]
>  Düzenle ve devam et hata ayıklama kodu, karışık yerel ve yönetilen kod veya SQL Server ortak dil çalışma zamanı (CLR) tümleştirmesini kodu en iyi duruma getirilmiş yaparken desteklenmez. Diğer desteklenmeyen senaryolar hakkında daha fazla bilgi için bkz: [desteklenen kod değişiklikleri (C# ve Visual Basic)](../debugger/supported-code-changes-csharp.md). Bu senaryolar, bir iletişim kutusu, Düzenle ve devam et açıklayan desteklenmiyor hata ayıklayıcı görüntüler kod değişiklikleri uygulamak çalışırsanız.  
  
### <a name="to-invoke-edit-and-continue-automatically"></a>Düzen çağrılacak ve otomatik olarak devam et  
  
1.  Kaynak kodunuz değişiklik kesme modunda.  
  
2.  Gelen **hata ayıklama** menüsünde tıklatın **devam**, **adım**, veya **sonraki deyimi Ayarla** veya işlevi bir hata ayıklayıcı penceresinde değerlendirin.  
  
     Yeni kod derlenir ve hata ayıklama yeni kodu ile devam eder. Bazı değişiklikler Düzenle ve devam et tarafından desteklenmez. Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri (C# ve Visual Basic)](../debugger/supported-code-changes-csharp.md).  
  
### <a name="to-enabledisable-edit-and-continue"></a>Düzenle ve devam et bırakmak için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  
  
2.  İçinde **seçenekleri** iletişim kutusunda, genişletin **hata ayıklama** düğümü ve select **Düzenle ve devam et**.  
  
3.  İçinde **seçenekleri** iletişim kutusu **Düzenle ve devam et** sayfasında, seçin veya temizleyin **etkinleştirmek Düzenle ve devam et** onay kutusu.  
  
     Hata ayıklama oturumu yeniden başlattığınızda ayarı etkinleşir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düzenle ve devam et (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)   
 [Desteklenen kod değişiklikleri (C# ve Visual Basic)](../debugger/supported-code-changes-csharp.md)   