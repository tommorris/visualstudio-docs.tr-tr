---
title: 'Nasıl yapılır: yazmaç değerini düzenleme | Microsoft Docs'
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
- vs.debug.register.edit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 465ecd4e8003b82a0a7dfbab33004ef2b80d7f32
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687920"
---
# <a name="how-to-edit-a-register-value"></a>Nasıl Yapılır: Yazmaç Değerini Düzenleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: bir kayıt değeri düzenlemek](https://docs.microsoft.com/visualstudio/debugger/how-to-edit-a-register-value).  
  
Yazmaçlar penceresi yalnızca adres seviyesinde hata ayıklamayı etkin değilse kullanılabilir **seçenekleri** iletişim kutusu, **hata ayıklama** düğümü.  
  
### <a name="to-change-the-value-of-a-register"></a>Bir kayıt değeri değiştirmek için  
  
1.  İçinde **kaydeder** penceresinde, SEKME tuşunu veya fare ekleme noktasını değiştirmek istediğiniz değeri için kullanın. Yazmaya başladığınızda, imleci üzerine yazmak istediğiniz değer önünde yer almalıdır.  
  
2.  Yeni bir değer girin.  
  
    > [!CAUTION]
    >  YAZMAÇ değerlerini (özellikle de EIP ve EBP kayıtları) değiştirilmesi, program yürütme etkileyebilir.  
  
    > [!CAUTION]
    >  Kayan nokta değerlerini düzenlemek, kesirli bileşenlerin ondalıktan ikiliye dönüştürülmesi nedeniyle küçük yanlışlıklara neden olabilir. Görünüşte zararsız bir düzenleme bile, kayan nokta kaydı en az önemli bitlerin bazılarının değişiklikleri neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yazmaçlar penceresini kullanma](../debugger/how-to-use-the-registers-window.md)





