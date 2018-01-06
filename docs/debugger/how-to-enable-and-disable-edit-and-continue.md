---
title: "Nasıl yapılır: etkinleştirmek ve devre dışı Düzenle ve devam et (C#, VB, C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: 1c00546b983c9bbb0fd6c01717bd0a09c993e11b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>Nasıl yapılır: etkinleştirmek ve devre dışı Düzenle ve devam et (C#, VB, C++)
Düzenle ve devam et, etkinleştirmek veya devre dışı **seçenekleri** tasarım zamanında iletişim kutusu. Hata ayıklarken bu ayarı değiştiremezsiniz.  
  
Düzenle ve works yalnızca hata ayıklama derlemelerinde devam edin. Yerel C++ için Düzenle ve devam et gerektirir /INCREMENTAL kullanma seçeneği. C++'ta özellik gereksinimleri hakkında daha fazla bilgi için bkz [blog gönderisi](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/) ve [Düzenle ve devam et (Visual C++)](../debugger/edit-and-continue-visual-cpp.md).
  
#### <a name="to-enabledisable-edit-and-continue"></a>Düzenle ve devam et bırakmak için  
  
1.  Hata ayıklama oturumunda varsa, hata ayıklamayı durdurun (**Shift + F5**).

2.  Hata ayıklama seçenekleri sayfasını aç (**Araçlar > Seçenekler > hata ayıklama**).
  
3.  Seçin **genel**ve ekranı aşağı kaydırarak **Düzenle ve devam et** kategorisi (sağ bölme).  
  
4.  Etkinleştirmek için seçin **etkinleştirmek Düzenle ve devam et** onay kutusu. Devre dışı bırakmak için onay kutusunu temizleyin.  
  
    > [!NOTE]
    >  IntelliTrace etkinleştirilir ve IntelliTrace olayları ve arama bilgilerini toplamak, Düzenle ve devam et devre dışı bırakılmıştır. Daha fazla bilgi için bkz: [IntelliTrace](../debugger/intellitrace.md).

5. (C++) Etkinleştirmek için seçin **etkinleştirmek yerel Düzenle ve devam et**. Devre dışı bırakmak için onay kutusunu temizleyin.

6. (C++) Yerel kod için ek seçenekleri ayarlayın.

    - **Değişiklikleri uygulamak (yalnızca yerel) üzerinde devam**  
        Visual Studio otomatik olarak derler ve sonu durumundan işlemine devam zaman yapmış olduğunuz tüm bekleyen kod değişiklikleri uygular. Seçilmezse, hata ayıklama menüsünün altında "Kod değişiklikleri Uygula" öğesini kullanarak değişiklikleri uygulamak seçebilirsiniz.  
  
    - **Eski kod (yalnızca yerel) hakkında uyar**  
        Eski kod hakkında uyarı alın. 
  
7.  **Tamam**'ı tıklatın.    
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düzenle ve devam et](../debugger/edit-and-continue.md)