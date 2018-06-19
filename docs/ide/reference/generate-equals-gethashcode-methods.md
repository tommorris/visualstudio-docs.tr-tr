---
title: C# eşittir oluşturmak ve Visual Studio'da GetHashCode yöntemi geçersiz kılar
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: cdbb5273d046be8f11cc2fbc4a03ed6767a31e00
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945317"
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-visual-studio"></a>Eşittir oluşturmak ve Visual Studio'da GetHashCode yöntemi geçersiz kılar

Bu kod oluşturma için geçerlidir:

- C#

**Ne:** oluşturmanıza olanak tanır **eşittir** ve **GetHashCode** yöntemleri.

**Ne zaman:** bir veya daha fazla alan tarafından yerine bellekteki nesne konuma göre karşılaştırılması gereken bir türe sahip olduğunda bu geçersiz kılmaları oluşturur.

**Neden:**

- Değer türü uyguluyorsanız, geçersiz kılma düşünmelisiniz **eşittir** ValueType eşittir yöntemi varsayılan uygulaması üzerinden daha yüksek performans elde etmek için yöntem.

- Bir başvuru türü uyguluyorsanız, geçersiz kılma düşünmelisiniz **eşittir** türünüz noktası, dize, BigNumber vb. gibi bir taban türü gibi görünüyorsa yöntemi.

- Geçersiz kılma **GetHashCode** yöntemi bir karma tablosunda düzgün çalışması için bir türü izin vermek için. Daha fazla kılavuzunu okuyun [eşitlik işleçleri](/dotnet/standard/design-guidelines/equality-operators).

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi tür bildiriminde yerleştirin.

   ![Vurgulanmış kodu](media/overrides-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - &nbsp; ![Ampul](media/bulb-cs.png) tür bildirimi ile satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Geçersiz kılmaları Önizleme oluşturma](media/overrides-preview-cs.png)

1. Seçin **oluşturmak Equals(object)** veya **oluşturmak eşittir ve GetHashCode** açılır menüsünden.

1. İçinde **çekme üyeleri** istediğiniz üyeleri için yöntemleri Oluştur iletişim kutusunda, seçin:

    ![Geçersiz kılmaları iletişim oluştur](media/overrides-dialog-cs.png)

    > [!TIP]
    > Üye listesi altındaki onay kutularını kullanarak bu iletişim kutusundan işleçleri oluşturmak seçebilirsiniz.

   Equals ve GetHashCode geçersiz kılmaları varsayılan uygulamaları ile oluşturulur.

   ![Yöntem sonuç oluştur](media/overrides-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)