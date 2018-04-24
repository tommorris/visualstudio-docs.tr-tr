---
title: 'Nasıl yapılır: yazmaç değerini düzenleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.register.edit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de743aa67b3875654dee1b13b27a74e208bb6d53
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-edit-a-register-value"></a>Nasıl Yapılır: Yazmaç Değerini Düzenleme
Yazmaçlar penceresi yalnızca adres düzeyi hata ayıklama de etkinse, kullanılabilir **seçenekleri** iletişim kutusu, **hata ayıklama** düğümü.  
  
### <a name="to-change-the-value-of-a-register"></a>Bir kayıt değeri değiştirmek için  
  
1.  İçinde **kaydeder** penceresinde, sekme ya da ekleme taşımak için fareyi noktasını değiştirmek istediğiniz değeri kullanın. Yazmaya başladığınızda, imleci üzerine yazmak istediğiniz değer önünde yer almalıdır.  
  
2.  Yeni bir değer girin.  
  
    > [!CAUTION]
    >  YAZMAÇ değerlerini (özellikle de EIP ve EBP kayıtları) değiştirilmesi, program yürütme etkileyebilir.  
  
    > [!CAUTION]
    >  Kayan nokta değerlerini düzenlemek, kesirli bileşenlerin ondalıktan ikiliye dönüştürülmesi nedeniyle küçük yanlışlıklara neden olabilir. Bile görünen zararsız düzenleme kayan nokta kaydı en az önemli bitleri, bazı değişiklikler neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yazmaçlar penceresini kullanma](../debugger/how-to-use-the-registers-window.md)