---
title: Visual Basic IntelliSense
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1334cb7f890f3924ca0720b4704e573a67058356
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="intellisense-for-visual-basic-code-files"></a>Visual Basic kodu dosyaları için IntelliSense

Visual Basic kaynak kod düzenleyicisinde aşağıdaki IntelliSense özellikleri sunar:

## <a name="syntax-tips"></a>Sözdizimi ipuçları

Sözdizimi ipuçları yazmakta olduğunuz ifadesinin sözdizimi görüntüler. Bu gibi deyimleri için yararlıdır [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).

## <a name="automatic-completion"></a>Otomatik Tamamlama

- Tamamlanma çeşitli anahtar sözcükleri

     Örneğin, `goto` ve bir boşluk, IntelliSense açılır menüde tanımlanan etiketler listesini görüntüler. Desteklenen diğer anahtar sözcükler dahil `Exit`, `Implements`, `Option`, ve `Declare`.

- Tamamlanma `Enum` ve `Boolean`

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

- [IntelliSense Kullanma](../ide/using-intellisense.md)