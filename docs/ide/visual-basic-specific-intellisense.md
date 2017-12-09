---
title: Visual Basic IntelliSense | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 520b5b2d9d0a66df3bbe17a0e8deea69147cbf17
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="intellisense-for-visual-basic-code-files"></a>Visual Basic kodu dosyaları için IntelliSense

Visual Basic kaynak kod düzenleyicisinde aşağıdaki IntelliSense özellikleri sunar:

## <a name="syntax-tips"></a>Sözdizimi ipuçları

Sözdizimi ipuçları yazmakta olduğunuz ifadesinin sözdizimi görüntüler. Bu gibi deyimleri için yararlıdır [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).

## <a name="automatic-completion"></a>Otomatik Tamamlama

- Tamamlanma çeşitli anahtar sözcükleri

     Örneğin, `goto` ve bir boşluk, IntelliSense açılır menüde tanımlanan etiketler listesini görüntüler. Desteklenen diğer anahtar sözcükler dahil `Exit`, `Implements`, `Option`, ve `Declare`.

- Tamamlanma `Enum` ve`Boolean`

    Bir deyim bir numaralandırma üyesine başvurur, IntelliSense üyelerinin listesini görüntüler `Enum`. Ne zaman bir deyim başvurduğu bir `Boolean`, IntelliSense doğru yanlış açılır menü görüntüler.

Tamamlama açılabilir varsayılan seçimini kaldırarak **otomatik listesi üyeleri** gelen **genel** özellik sayfasında **Visual Basic** klasör.

Tamamlanma listesi üyeleri, tam sözcüğü veya ALT + sağ ok çağırarak el ile çalıştırabilirsiniz. Daha fazla bilgi için bkz: [kullanarak IntelliSense](../ide/using-intellisense.md).

## <a name="intellisense-in-zone"></a>Bölgedeki IntelliSense

IntelliSense bölgesinde yardımcı olur aracılığıyla uygulamaları dağıtmak için ihtiyaç duyan Visual Basic geliştiricileri [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ve kısmi güven ayarlar kısıtlanmıştır. Bu özellik:

- İle uygulamanın çalıştırılacağı İzinleri seçmenize olanak tanır.

- Seçilen görüntü API'leri listesi üyeleri kullanılabilir olarak bölge ve ek izinler kullanılamaz olarak gerektiren API'ları görüntüleyin.

Daha fazla bilgi için bkz: [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md).

## <a name="filtered-completion-lists"></a>Filtrelenmiş tamamlanma listeleri

Visual Basic'de IntelliSense tamamlanma listeleri listeler altına bulunan iki sekme denetimleri sahip. **Ortak** varsayılan olarak seçilir, sekme, yazmakta olduğunuz deyimini tamamlamak için en sık kullanılan öğe görüntüler. **Tüm** sekmesini görüntüler için de üzerinde olanlar da dahil olmak üzere otomatik tamamlama, kullanılabilir tüm öğeleri **ortak** sekmesi.

## <a name="see-also"></a>Ayrıca bkz.

[IntelliSense Kullanma](../ide/using-intellisense.md)