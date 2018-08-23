---
title: 'Nasıl yapılır: Düzenle ve kullanma (C#) devam | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4305c39c62dfcc927ea7295ceec786d3da40f56
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683695"
---
# <a name="how-to-use-edit-and-continue-c"></a>Nasıl Yapılır: Düzenle ve Devam Et'i Kullanma (C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: kullanım Düzenle ve devam et (C#)](https://docs.microsoft.com/visualstudio/debugger/how-to-use-edit-and-continue-csharp).  
  
Düzenle ve devam et için C# ile hata ayıklama sırasında kodunuzda kesme modunda değişiklik yapabilirsiniz. Değişiklikleri durdurmak ve hata ayıklama oturumunu yeniden başlatmak zorunda kalmadan uygulanabilir.  
  
 Kesme modunda değişiklikleri yapın ve ardından bir hata ayıklayıcı yürütme seçin, Düzenle ve devam et otomatik olarak çağrılır komutu gibi **devam**, **adım**, veya **sonraki deyimi Ayarla**, veya hata ayıklayıcı penceresindeki bir işlevi değerlendirin.  
  
> [!NOTE]
>  Düzenle ve devam et desteklenmez karma yerel/yönetilen kodda ya da SQL Server ortak dil çalışma zamanı (CLR) tümleştirme kodunda Compact Framework'te, en iyi duruma getirilmiş kodu, hata ayıklama. Bu senaryolardan birinde kod değişiklikleri uygulamaya çalışırsanız, hata ayıklayıcı bir iletişim kutusunu Düzenle ve devam et desteklenmediğini Et'in koyar.  
  
### <a name="to-invoke-edit-and-continue-automatically"></a>Düzenleme çağrılacak ve otomatik olarak devam et  
  
1.  Kesme modunda kaynak kodunuzda bir değişiklik yapın.  
  
2.  Gelen **hata ayıklama** menüsünde tıklatın **devam**, **adım**, veya **sonraki deyimi Ayarla** veya hata ayıklayıcı penceresindeki bir işlevi değerlendirin.  
  
     Yeni kod derlenir ve hata ayıklama yeni kod iler devam eder. Bazı değişiklikler, Düzenle ve devam et tarafından desteklenmez. Daha fazla bilgi için [desteklenen kod değişiklikleri (C#)](../debugger/supported-code-changes-csharp.md).  
  
### <a name="to-enabledisable-edit-and-continue"></a>Etkinleştirmek/devre dışı Düzenle ve devam et  
  
1.  Üzerinde **Araçları** menüsünü tıklatın **seçenekleri**.  
  
2.  İçinde **seçenekleri** iletişim kutusunda **hata ayıklama** düğüm ve select **Düzenle ve devam et**.  
  
3.  İçinde **seçenekleri** iletişim kutusu **Düzenle ve devam et** sayfasında, seçin veya temizleyin **etkinleştirme Düzenle ve devam et** onay kutusu.  
  
     Hata ayıklama oturumunu yeniden başlattığınızda ayarı etkinleşir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düzenle ve devam et (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)   
 [Desteklenen kod değişiklikleri (C#)](../debugger/supported-code-changes-csharp.md)   
 [Düzenle ve devam et hataları ve Uyarıları (C#)](../misc/edit-and-continue-errors-and-warnings-csharp.md)



